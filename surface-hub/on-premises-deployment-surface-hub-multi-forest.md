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
# Локальное развертывание для Surface Hub в среде с несколькими лесами


В этой статье описывается, как добавить учетную запись устройства Microsoft Surface Hub в локальном развертывании с несколькими лесами.

Если вы используете локальное развертывание в нескольких лесах с Microsoft Exchange 2013 или более поздней версии и Skype для бизнеса 2013 или более поздней версии, вы можете создавать учетные записи устройств с помощью [указанных сценариев PowerShell](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts). Если вы используете развертывание с одним лесом, см. раздел [Локальное развертывание для Surface Hub в среде с одним лесом](on-premises-deployment-surface-hub-device-accounts.md).

1.  Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.

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

2.  После запуска сеанса создайте новый почтовый ящик в лесу ресурсов. Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.

    При изменении существующего почтового ящика ресурса:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

    Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение **False**. В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.

    Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs. После ее создания вы можете применить ту же политику к другим учетным записям устройств.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    Затем вам потребуется применить политику к вашей учетной записи устройства. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell. Дополнительные сведения см. в разделе [Управление паролями](password-management-for-surface-hub-device-accounts.md). Это должно быть установлено в лесу пользователя.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Включите учетную запись в Active Directory, чтобы она смогла пройти проверку подлинности на Surface Hub. Это должно быть установлено в лесу пользователя.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. Теперь нужно изменить почтовый ящик помещения на связанный почтовый ящик:

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  Включите учетную запись устройства в Skype для бизнеса, активировав учетную запись AD устройства Surface Hub в пуле Skype для бизнеса Server.

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    Вам потребуется SIP-адрес и контроллер домена для Surface Hub, а также идентификатор пула и удостоверение пользователя Skype для бизнеса Server.


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
 





