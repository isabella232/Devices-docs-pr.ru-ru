---
title: Локальное развертывание с одним лесом (Surface Hub)
description: В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с одним лесом.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: развертывание с одним лесом, локальное развертывание, учетная запись устройства, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836168"
---
# <span data-ttu-id="f83b5-104">Локальное развертывание для Surface Hub в среде с одним лесом</span><span class="sxs-lookup"><span data-stu-id="f83b5-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="f83b5-105">В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с одним лесом.</span><span class="sxs-lookup"><span data-stu-id="f83b5-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="f83b5-106">Если вы используете локальное развертывание в одном лесу с Microsoft Exchange 2013 или более поздней версии и Skype для бизнеса 2013 или более поздней версии, вы можете создавать учетные записи устройств с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts).</span><span class="sxs-lookup"><span data-stu-id="f83b5-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="f83b5-107">Если вы используете развертывание с несколькими лесами, см. раздел [Локальное развертывание для Surface Hub в среде с несколькими лесами](on-premises-deployment-surface-hub-multi-forest.md).</span><span class="sxs-lookup"><span data-stu-id="f83b5-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="f83b5-108">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="f83b5-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="f83b5-109">Убедитесь, что у вас есть права для запуска соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="f83b5-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="f83b5-110">Обратите внимание, что `$strExchangeServer` здесь — это полное доменное имя (FQDN) сервера Exchange Server, а `$strLyncFQDN` — полное доменное имя сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f83b5-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="f83b5-111">После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="f83b5-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f83b5-112">Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f83b5-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="f83b5-113">При изменении существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="f83b5-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="f83b5-114">При создании нового почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="f83b5-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="f83b5-115">Необходимо включить базовую проверку подлинности виртуальных каталогов ActiveSync, так как Surface Hub не может выполнить проверку подлинности с помощью других способов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f83b5-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="f83b5-116">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="f83b5-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="f83b5-117">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="f83b5-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="f83b5-118">В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.</span><span class="sxs-lookup"><span data-stu-id="f83b5-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="f83b5-119">Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="f83b5-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="f83b5-120">После ее создания вы можете применить ту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="f83b5-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="f83b5-121">Затем вам потребуется применить политику к вашей учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="f83b5-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="f83b5-122">Однако политики можно применять только к учетным записям пользователей, но не почтовым ящикам ресурса.</span><span class="sxs-lookup"><span data-stu-id="f83b5-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="f83b5-123">Необходимо преобразовать почтовый ящик в пользовательский тип, применить политику, а затем преобразовать его обратно в почтовый ящик. Возможно, вам также придется повторно включить его и установить пароль.</span><span class="sxs-lookup"><span data-stu-id="f83b5-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="f83b5-124">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="f83b5-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="f83b5-125">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="f83b5-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="f83b5-126">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f83b5-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="f83b5-127">См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="f83b5-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="f83b5-128">Включите учетную запись в Active Directory, чтобы она смогла пройти проверку подлинности на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f83b5-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="f83b5-129">Включите учетную запись устройства в Skype для бизнеса, активировав учетную запись AD устройства Surface Hub в пуле Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f83b5-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="f83b5-130">Вам потребуется SIP-адрес и контроллер домена для Surface Hub, а также идентификатор пула и удостоверение пользователя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f83b5-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="f83b5-131">НЕОБЯЗАТЕЛЬНО. Вы также можете разрешить Surface Hub выполнять и принимать телефонные звонки по сети ТСОП, включив корпоративную голосовую связь для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f83b5-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="f83b5-132">Корпоративная голосовая связь не является обязательным требованием для Surface Hub, но если вы хотите использовать ТСОП для клиента Surface Hub, включите ее, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f83b5-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="f83b5-133">Опять же, вам потребуется заменить предоставленные вами данные для контроллера домена и номера телефона собственными данными.</span><span class="sxs-lookup"><span data-stu-id="f83b5-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="f83b5-134">Значение параметра `$true` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="f83b5-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="f83b5-135">Отключение анонимной почты и обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="f83b5-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="f83b5-136">Surface Hub использует учетную запись устройства для предоставления услуг электронной почты и совместной работы (обмена мгновенными сообщениями, видео, голоса).</span><span class="sxs-lookup"><span data-stu-id="f83b5-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="f83b5-137">Эта учетная запись устройства используется в качестве исходного удостоверения (стороны "от") при отправке электронной почты, мгновенных сообщений и размещении звонков.</span><span class="sxs-lookup"><span data-stu-id="f83b5-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="f83b5-138">Так как эта учетная запись не поступает от отдельного идентифицируемого пользователя, она считается анонимной, так как она получена из учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f83b5-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="f83b5-139">Предположим, что у вас есть политика клиента "на пользователя", назначаемая каждому устройству комнаты для собраний с удостоверением **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="f83b5-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="f83b5-140">Чтобы отключить анонимную почту и обмен сообщениями, добавьте clientPolicyEntry к этой политике клиента с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="f83b5-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="f83b5-141">Чтобы убедиться в том, что политика установлена, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f83b5-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="f83b5-142">Выводится следующее:</span><span class="sxs-lookup"><span data-stu-id="f83b5-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="f83b5-143">Чтобы изменить запись политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f83b5-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="f83b5-144">Чтобы удалить запись политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f83b5-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





