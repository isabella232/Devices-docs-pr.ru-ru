---
title: Сетевое развертывание с Office 365 (Surface Hub)
description: В этой статье приведены инструкции по добавлению учетной записи устройства Microsoft Surface Hub в чистом сетевом развертывании.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: учетная запись устройства Surface Hub, сетевое развертывание
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836131"
---
# <span data-ttu-id="7ba0d-104">Сетевое развертывание с Office 365 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="7ba0d-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="7ba0d-105">В этой статье приведены инструкции по добавлению учетной записи устройства Microsoft Surface Hub в чистом сетевом развертывании.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="7ba0d-106">При чистом сетевом развертывании (O365) учетные записи устройств можно создавать с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts).</span><span class="sxs-lookup"><span data-stu-id="7ba0d-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="7ba0d-107">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="7ba0d-108">Убедитесь, что у вас есть права для запуска соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="7ba0d-109">После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7ba0d-110">Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="7ba0d-111">При изменении существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="7ba0d-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="7ba0d-112">При создании нового почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="7ba0d-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="7ba0d-113">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="7ba0d-114">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="7ba0d-115">В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="7ba0d-116">Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="7ba0d-117">После ее создания вы можете применить ту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="7ba0d-118">Затем вам потребуется применить политику к вашей учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="7ba0d-119">В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7ba0d-120">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7ba0d-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="7ba0d-121">Подключитесь к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="7ba0d-122">Сначала необходимо установить модуль Azure AD для PowerShell версии 2.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="7ba0d-123">В командной строке PowerShell с повышенными привилегиями введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7ba0d-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="7ba0d-124">Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="7ba0d-125">Для этого можно запустить следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="7ba0d-126">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="7ba0d-127">Дополнительные сведения см. в разделе [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7ba0d-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="7ba0d-128">Surface Hub необходима лицензия для использования функций Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="7ba0d-129">Для включения Skype для бизнеса ваша среда должна соответствовать [необходимым требованиям для Skype для бизнеса Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="7ba0d-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="7ba0d-130">Затем вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="7ba0d-131">После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. <span data-ttu-id="7ba0d-132">Включите учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="7ba0d-133">Если модуль PowerShell Skype для бизнеса не установлен, [скачайте его](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="7ba0d-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="7ba0d-134">Начните с создания удаленного сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="7ba0d-135">Затем, если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета (например <em>alice@contoso.com</em>):</span><span class="sxs-lookup"><span data-stu-id="7ba0d-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="7ba0d-136">ИЛИ, задав переменную</span><span class="sxs-lookup"><span data-stu-id="7ba0d-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="7ba0d-137">Включите учетную запись Surface Hub с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="7ba0d-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="7ba0d-138">ИЛИ с помощью переменной $strRegistarPool выше</span><span class="sxs-lookup"><span data-stu-id="7ba0d-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="7ba0d-139">Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т.д.) и попробуйте войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="7ba0d-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





