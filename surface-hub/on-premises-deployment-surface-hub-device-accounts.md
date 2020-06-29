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
# Локальное развертывание для Surface Hub в среде с одним лесом


В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с одним лесом.

Если вы используете локальное развертывание в одном лесу с Microsoft Exchange 2013 или более поздней версии и Skype для бизнеса 2013 или более поздней версии, вы можете создавать учетные записи устройств с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts). Если вы используете развертывание с несколькими лесами, см. раздел [Локальное развертывание для Surface Hub в среде с несколькими лесами](on-premises-deployment-surface-hub-multi-forest.md).

1. Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.

   Убедитесь, что у вас есть права для запуска соответствующих командлетов.

   Обратите внимание, что `$strExchangeServer` здесь — это полное доменное имя (FQDN) сервера Exchange Server, а `$strLyncFQDN` — полное доменное имя сервера Skype для бизнеса.

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения. Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.

   При изменении существующего почтового ящика ресурса:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   При создании нового почтового ящика ресурса:

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> Необходимо включить базовую проверку подлинности виртуальных каталогов ActiveSync, так как Surface Hub не может выполнить проверку подлинности с помощью других способов проверки подлинности.

3. После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

   Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False. В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.

   Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs. После ее создания вы можете применить ту же политику к другим учетным записям устройств.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   Затем вам потребуется применить политику к вашей учетной записи устройства. Однако политики можно применять только к учетным записям пользователей, но не почтовым ящикам ресурса. Необходимо преобразовать почтовый ящик в пользовательский тип, применить политику, а затем преобразовать его обратно в почтовый ящик. Возможно, вам также придется повторно включить его и установить пароль.

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell. См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. Включите учетную запись в Active Directory, чтобы она смогла пройти проверку подлинности на Surface Hub.

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. Включите учетную запись устройства в Skype для бизнеса, активировав учетную запись AD устройства Surface Hub в пуле Skype для бизнеса Server.

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   Вам потребуется SIP-адрес и контроллер домена для Surface Hub, а также идентификатор пула и удостоверение пользователя Skype для бизнеса Server.

8. НЕОБЯЗАТЕЛЬНО. Вы также можете разрешить Surface Hub выполнять и принимать телефонные звонки по сети ТСОП, включив корпоративную голосовую связь для вашей учетной записи. Корпоративная голосовая связь не является обязательным требованием для Surface Hub, но если вы хотите использовать ТСОП для клиента Surface Hub, включите ее, как описано ниже.

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   Опять же, вам потребуется заменить предоставленные вами данные для контроллера домена и номера телефона собственными данными. Значение параметра `$true` не изменяется.
    

 ## Отключение анонимной почты и обмена мгновенными сообщениями




Surface Hub использует учетную запись устройства для предоставления услуг электронной почты и совместной работы (обмена мгновенными сообщениями, видео, голоса). Эта учетная запись устройства используется в качестве исходного удостоверения (стороны "от") при отправке электронной почты, мгновенных сообщений и размещении звонков. Так как эта учетная запись не поступает от отдельного идентифицируемого пользователя, она считается анонимной, так как она получена из учетной записи устройства Surface Hub.  

Предположим, что у вас есть политика клиента "на пользователя", назначаемая каждому устройству комнаты для собраний с удостоверением **SurfaceHubPolicy**. Чтобы отключить анонимную почту и обмен сообщениями, добавьте clientPolicyEntry к этой политике клиента с помощью следующих команд.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

Чтобы убедиться в том, что политика установлена, выполните указанные ниже действия.

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

Выводится следующее:

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
Чтобы изменить запись политики, выполните указанные ниже действия.

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
Чтобы удалить запись политики, выполните указанные ниже действия.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





