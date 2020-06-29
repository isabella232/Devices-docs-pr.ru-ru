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
# Сетевое развертывание с Office 365 (Surface Hub)


В этой статье приведены инструкции по добавлению учетной записи устройства Microsoft Surface Hub в чистом сетевом развертывании.

При чистом сетевом развертывании (O365) учетные записи устройств можно создавать с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts). 

1. Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.

   Убедитесь, что у вас есть права для запуска соответствующих командлетов.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения. Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.

   При изменении существующего почтового ящика ресурса:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   При создании нового почтового ящика ресурса:

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

   Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False. В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.

   Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs. После ее создания вы можете применить ту же политику к другим учетным записям устройств.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   Затем вам потребуется применить политику к вашей учетной записи устройства.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Подключитесь к Azure AD.
    
   Сначала необходимо установить модуль Azure AD для PowerShell версии 2. В командной строке PowerShell с повышенными привилегиями введите следующую команду:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи. Для этого можно запустить следующий командлет.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell. Дополнительные сведения см. в разделе [Управление паролями](password-management-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub необходима лицензия для использования функций Skype для бизнеса. Для включения Skype для бизнеса ваша среда должна соответствовать [необходимым требованиям для Skype для бизнеса Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).
   
   Затем вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.

   После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.

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

8. Включите учетную запись устройства в Skype для бизнеса.
   Если модуль PowerShell Skype для бизнеса не установлен, [скачайте его](https://www.microsoft.com/download/details.aspx?id=39366). 

   - Начните с создания удаленного сеанса PowerShell на компьютере.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - Затем, если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета (например <em>alice@contoso.com</em>):

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       ИЛИ, задав переменную
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - Включите учетную запись Surface Hub с помощью следующего командлета:
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       ИЛИ с помощью переменной $strRegistarPool выше
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т.д.) и попробуйте войти в эту учетную запись.





