---
title: Создание учетной записи устройства Surface Hub 2S
description: На этой странице описывается процедура создания учетной записи устройства Surface Hub 2S.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385227"
---
# <a name="create-surface-hub-2s-device-account"></a>Создание учетной записи устройства Surface Hub 2S

Создание учетной записи устройства Surface Hub (также известной как почтовый ящик Room) позволяет Surface Hub 2S получать, утверждать или отклоницать запросы на собрания и присоединяться к собраниям. Настройка учетной записи устройства во время установки out-of-Box Experience (OOBE). При необходимости вы можете изменить его позже (не проходить через установку OOBE).

Учетную запись можно создать из центра администрирования Microsoft 365 в сочетании с Windows PowerShell: 

- **Создание учетной записи через центр администрирования.** Чтобы соответствовать минимальным требованиям, вы можете настроить все необходимое для учетной записи непосредственно из центра [администрирования Microsoft 365.](https://admin.microsoft.com/AdminPortal) Некоторые функции, такие как совместное использование доски непосредственно из приложения доски, требуют использования PowerShell для настройки ActiveSync; см. [на странице Включить ActiveSync,](#enable-activesync-if-use-of-email-app-is-required) если на этой странице требуется использование приложения электронной почты.

- **Создание учетной записи с помощью PowerShell**. Скрипты PowerShell можно использовать для облегчения создания нескольких учетных записей устройств и быстрой настройки определенных функций, включая:
    - Обработка календаря для каждой учетной записи устройства Surface Hub.
    - Настраиваемые автоматические ответы на запросы планирования.
    - Если политика почтовых ящиков ActiveSync по умолчанию уже изменена кем-то другим или другим процессом, вам, скорее всего, придется создать и назначить новую политику почтовых ящиков ActiveSync.

> [!TIP]
> Вы можете проверить настройку учетной записи, запуская ниже [сценарий проверки учетной записи.](#account-verification-script)

> [!NOTE]  
> Учетная запись устройства Surface Hub не поддерживает сторонних поставщиков удостоверений (FIPs) и должна быть стандартной учетной записью Active Directory или Azure Active Directory.

## <a name="create-account-via-admin-center"></a>Создание учетной записи с помощью центра администрирования

1. В центре администрирования Microsoft 365 перейдите в **Службы** ресурсов и выберите номера & **оборудования,** а затем **выберите + Добавить ресурс**.

2. Укай имя и адрес электронной почты для учетной записи устройства. Оставьте оставшиеся параметры без изменений в состоянии по умолчанию.

   ![Предоставление имени и адреса электронной почты](images/sh2-account2.png)

   ![Оставьте оставшиеся параметры без изменений в состоянии по умолчанию](images/sh2-account3.png)

3. Установите пароль для учетной записи устройства. Чтобы установить пароль, выберите **Пользователи,** а затем выберите **активных пользователей.** Теперь поиск для вновь созданного пользователя, чтобы установить пароль. Убедитесь, **что при первом** входе не выберите параметр Make this user change their **password.**

   ![Установите пароль для учетной записи устройства](images/sh2-account4.png)

4. Назначьте номер с лицензией Office 365. Рекомендуется назначить лицензию На собраний **** Office 365, которая автоматически включает учетную запись для Microsoft Teams и Skype для бизнеса.

   ![Назначение лицензии Office 365](images/sh2-account5.png)


> [!NOTE]  
> Если вы используете Skype для бизнеса, вам потребуется окончательное решение о настройке с помощью PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) для этой учетной записи. 

## <a name="create-account-via-powershell"></a>Создание учетной записи с помощью PowerShell

 Использование PowerShell для быстрой автоматизации задач в Surface Hub необязательно требует экспертизы PowerShell. Убедитесь, что вы выполнили необходимые условия установки перед использованием соответствующих скриптов на этой странице.

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>Необходимые условия для использования PowerShell для управления Surface Hub 

1. Запустите PowerShell с повышенными привилегиями учетной записи **(Запустите**в качестве администратора) и убедитесь, что ваша система настроена для запуска сценариев PowerShell. Чтобы узнать больше, обратитесь [к политике выполнения](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Установка модуля Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)


### <a name="connect-to-exchange-online-powershell"></a>Подключение к Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>Создание почтового ящика

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>Настройка автоматической обработки календаря (только skype для бизнеса)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>Включить ActiveSync, если требуется использование приложения электронной почты

 Политика ActiveSync по умолчанию будет работать, если она не изменится. В противном случае создайте новую политику и назначьте.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>Подключение к Azure AD

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>Назначение лицензии

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>Проверка доступных лицензий

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>Сценарий проверки учетной записи

После создания учетной записи устройства можно запустить следующий сценарий проверки. Этот скрипт проверяет ранее созданную учетную запись устройства и создает сводный отчет. Пример

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

## <a name="learn-more"></a>Подробнее

- [Создание локальных учетных записей Surface Hub 2S с помощью PowerShell](surface-hub-2s-onprem-powershell.md)