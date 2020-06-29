---
title: Локальное развертывание с несколькими лесами (Surface Hub)
description: В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с несколькими лесами.
keywords: развертывание с несколькими лесами, локальное развертывание, учетная запись устройства, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836136"
---
# <span data-ttu-id="49856-104">Локальное развертывание для Surface Hub в среде с несколькими лесами</span><span class="sxs-lookup"><span data-stu-id="49856-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="49856-105">В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="49856-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="49856-106">Если вы используете локальное развертывание в нескольких лесах с Microsoft Exchange 2013 или более поздней версии и Skype для бизнеса 2013 или более поздней версии, вы можете создавать учетные записи устройств с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts).</span><span class="sxs-lookup"><span data-stu-id="49856-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="49856-107">Если вы используете развертывание с одним лесом, см. раздел [Локальное развертывание для Surface Hub в среде с одним лесом](on-premises-deployment-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="49856-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="49856-108">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="49856-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="49856-109">Убедитесь, что у вас есть права для запуска соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="49856-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="49856-110">Обратите внимание, что `$strExchangeServer` здесь — это полное доменное имя (FQDN) сервера Exchange Server, а `$strLyncFQDN` — полное доменное имя сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="49856-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="49856-111">После запуска сеанса создайте новый почтовый ящик в лесу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="49856-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="49856-112">Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="49856-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="49856-113">При изменении существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="49856-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="49856-114">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="49856-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="49856-115">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение **False**.</span><span class="sxs-lookup"><span data-stu-id="49856-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="49856-116">В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.</span><span class="sxs-lookup"><span data-stu-id="49856-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="49856-117">Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="49856-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="49856-118">После ее создания вы можете применить ту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="49856-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="49856-119">Затем вам потребуется применить политику к вашей учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="49856-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="49856-120">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="49856-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="49856-121">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="49856-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="49856-122">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49856-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="49856-123">Дополнительные сведения см. в разделе [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="49856-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="49856-124">Это должно быть установлено в лесу пользователя.</span><span class="sxs-lookup"><span data-stu-id="49856-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="49856-125">Включите учетную запись в Active Directory, чтобы она смогла пройти проверку подлинности на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="49856-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="49856-126">Это должно быть установлено в лесу пользователя.</span><span class="sxs-lookup"><span data-stu-id="49856-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="49856-127">Теперь нужно изменить почтовый ящик помещения на связанный почтовый ящик:</span><span class="sxs-lookup"><span data-stu-id="49856-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="49856-128">Включите учетную запись устройства в Skype для бизнеса, активировав учетную запись AD устройства Surface Hub в пуле Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49856-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="49856-129">Вам потребуется SIP-адрес и контроллер домена для Surface Hub, а также идентификатор пула и удостоверение пользователя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49856-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="49856-130">Отключение анонимной почты и обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="49856-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="49856-131">Surface Hub использует учетную запись устройства для предоставления услуг электронной почты и совместной работы (обмена мгновенными сообщениями, видео, голоса).</span><span class="sxs-lookup"><span data-stu-id="49856-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="49856-132">Эта учетная запись устройства используется в качестве исходного удостоверения (стороны "от") при отправке электронной почты, мгновенных сообщений и размещении звонков.</span><span class="sxs-lookup"><span data-stu-id="49856-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="49856-133">Так как эта учетная запись не поступает от отдельного идентифицируемого пользователя, она считается анонимной, так как она получена из учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="49856-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="49856-134">Предположим, что у вас есть политика клиента "на пользователя", назначаемая каждому устройству комнаты для собраний с удостоверением **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="49856-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="49856-135">Чтобы отключить анонимную почту и обмен сообщениями, добавьте clientPolicyEntry к этой политике клиента с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="49856-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="49856-136">Чтобы убедиться в том, что политика установлена, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="49856-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="49856-137">Выводится следующее:</span><span class="sxs-lookup"><span data-stu-id="49856-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="49856-138">Чтобы изменить запись политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="49856-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="49856-139">Чтобы удалить запись политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="49856-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





