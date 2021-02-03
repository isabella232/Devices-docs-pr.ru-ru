---
title: Создание учетной записи устройства Surface Hub 2S
description: На этой странице описана процедура создания учетной записи устройства Surface Hub 2S.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 76ac960be2ab30a30b4e29618f350a13a284f52a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312025"
---
# Создание учетной записи устройства Surface Hub 2S

Создание учетной записи устройства Surface Hub (также известной как почтовый ящик помещения) позволяет Surface Hub 2S принимать, утверждать или отклоницать запросы на собрания и присоединяться к собраниям. Настройте учетную запись устройства во время настройки при в режиме приостановки (OOBE). При необходимости вы можете изменить его позже (без необходимости настройки при OOBE).

Вы можете создать учетную запись в Центре администрирования Microsoft 365 в сочетании с Windows PowerShell: 

- **Создание учетной записи через Центр администрирования.** Для удовлетворения минимальных требований можно настроить все необходимое для учетной записи непосредственно в Центре администрирования [Microsoft 365.](https://admin.microsoft.com/AdminPortal) Некоторые функции, такие как общий доступ к доскам непосредственно из приложения доски, требуют использования PowerShell для настройки ActiveSync; См. ["Включить ActiveSync",](#enable-activesync-if-use-of-email-app-is-required) если на этой странице необходимо использовать почтовое приложение.

- **Создайте учетную запись с помощью PowerShell.** Сценарии PowerShell можно использовать для упрощения создания нескольких учетных записей устройств и быстрой настройки определенных функций, в том числе:
    - Обработка календаря для каждой учетной записи устройства Surface Hub.
    - Настраиваемые автоматические ответы на запросы планирования.
    - Если политика почтовых ящиков ActiveSync по умолчанию уже была изменена другими или другими процессами, скорее всего, вам придется создать и назначить новую политику почтовых ящиков ActiveSync.

> [!TIP]
> Вы можете проверить настройку учетной записи, заверив [сценарий проверки учетной записи ниже.](#account-verification-script)

> [!NOTE]  
> Учетная запись устройства Surface Hub не поддерживает сторонних федеративных поставщиков удостоверений (FIP) и должна быть стандартной учетной записью Active Directory или Azure Active Directory.

## Создание учетной записи через Центр администрирования

1. В Центре администрирования Microsoft 365 перейдите в "Ресурсы" и выберите "Помещения **& Оборудование",** а затем выберите **"+ Добавить ресурс".** ****

2. В качестве имени и адреса электронной почты для учетной записи устройства. Оставьте оставшиеся параметры без изменений в состоянии по умолчанию.

   ![Предоставление имени и адреса электронной почты](images/sh2-account2.png)

   ![Оставьте оставшиеся параметры без изменений в состоянии по умолчанию](images/sh2-account3.png)

3. Установите пароль для учетной записи устройства. Чтобы установить пароль, выберите **"Пользователи",** а затем выберите **"Активные пользователи".** Теперь найщите только что созданного пользователя, чтобы установить пароль. Убедитесь, **что не выбран** параметр "Сделать так, чтобы пользователь изменил свой пароль при первом **входе".**

   ![Настройка пароля для учетной записи устройства](images/sh2-account4.png)

4. Назначьте комнате лицензию на Office 365. Рекомендуется назначить лицензию на комнату для **** собраний Office 365, которая автоматически включает учетную запись для Microsoft Teams и Skype для бизнеса.

   ![Назначение лицензии на Office 365](images/sh2-account5.png)


> [!NOTE]  
> Если вы используете Skype для бизнеса, вам необходимо будет завершать настройку [](#set-calendar-auto-processing-skype-for-business-only) с помощью PowerShell — календаря Skype для бизнеса: настройка автоматической установки календаря для этой учетной записи. 

## Создание учетной записи с помощью PowerShell

 Использование PowerShell для быстрой автоматизации задач на Surface Hub не обязательно требует навыков PowerShell. Перед использованием соответствующих сценариев на этой странице убедитесь, что выполнены необходимые условия установки.

### Необходимые условия для использования PowerShell для управления Surface Hub 

1. Запустите PowerShell с повышенными привилегиями**учетной**записи (запуск от прав администратора) и убедитесь, что система настроена на запуск сценариев PowerShell. Чтобы узнать больше, обратитесь к [политике выполнения.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?) 
2. [Установка модуля Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)


### Подключение к Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### Создание почтового ящика

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### Настройка автоматической обработки календаря (только в Skype для бизнеса)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Включить ActiveSync, если требуется использование почтового приложения

 Политика ActiveSync по умолчанию будет работать, если она не изменилась. В противном случае создайтеStupid новую политику и назначьте ее.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### Подключение к Azure AD

```powershell
Connect-AzureAD
```

### Назначение лицензии

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### Проверка на наличии доступных лицензий

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## Сценарий проверки учетной записи

После создания учетной записи устройства можно запустить следующий сценарий проверки. Этот сценарий проверяет ранее созданную учетную запись устройства и создает сводный отчет. Например:

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

Сведения о конкретных параметрах не отображаются.

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## Подробнее

- [Создание локальных учетных записей Surface Hub 2S с помощью PowerShell](surface-hub-2s-onprem-powershell.md)