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
# <span data-ttu-id="ad2e9-104">Создание учетной записи устройства Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="ad2e9-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="ad2e9-105">Создание учетной записи устройства Surface Hub (также известной как почтовый ящик помещения) позволяет Surface Hub 2S принимать, утверждать или отклоницать запросы на собрания и присоединяться к собраниям.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="ad2e9-106">Настройте учетную запись устройства во время настройки при в режиме приостановки (OOBE).</span><span class="sxs-lookup"><span data-stu-id="ad2e9-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="ad2e9-107">При необходимости вы можете изменить его позже (без необходимости настройки при OOBE).</span><span class="sxs-lookup"><span data-stu-id="ad2e9-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="ad2e9-108">Вы можете создать учетную запись в Центре администрирования Microsoft 365 в сочетании с Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad2e9-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="ad2e9-109">**Создание учетной записи через Центр администрирования.**</span><span class="sxs-lookup"><span data-stu-id="ad2e9-109">**Create account via Admin center**.</span></span> <span data-ttu-id="ad2e9-110">Для удовлетворения минимальных требований можно настроить все необходимое для учетной записи непосредственно в Центре администрирования [Microsoft 365.](https://admin.microsoft.com/AdminPortal)</span><span class="sxs-lookup"><span data-stu-id="ad2e9-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="ad2e9-111">Некоторые функции, такие как общий доступ к доскам непосредственно из приложения доски, требуют использования PowerShell для настройки ActiveSync; См. ["Включить ActiveSync",](#enable-activesync-if-use-of-email-app-is-required) если на этой странице необходимо использовать почтовое приложение.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="ad2e9-112">**Создайте учетную запись с помощью PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="ad2e9-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="ad2e9-113">Сценарии PowerShell можно использовать для упрощения создания нескольких учетных записей устройств и быстрой настройки определенных функций, в том числе:</span><span class="sxs-lookup"><span data-stu-id="ad2e9-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="ad2e9-114">Обработка календаря для каждой учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="ad2e9-115">Настраиваемые автоматические ответы на запросы планирования.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="ad2e9-116">Если политика почтовых ящиков ActiveSync по умолчанию уже была изменена другими или другими процессами, скорее всего, вам придется создать и назначить новую политику почтовых ящиков ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="ad2e9-117">Вы можете проверить настройку учетной записи, заверив [сценарий проверки учетной записи ниже.](#account-verification-script)</span><span class="sxs-lookup"><span data-stu-id="ad2e9-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="ad2e9-118">Учетная запись устройства Surface Hub не поддерживает сторонних федеративных поставщиков удостоверений (FIP) и должна быть стандартной учетной записью Active Directory или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="ad2e9-119">Создание учетной записи через Центр администрирования</span><span class="sxs-lookup"><span data-stu-id="ad2e9-119">Create account via admin center</span></span>

1. <span data-ttu-id="ad2e9-120">В Центре администрирования Microsoft 365 перейдите в "Ресурсы" и выберите "Помещения **& Оборудование",** а затем выберите **"+ Добавить ресурс".** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ad2e9-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="ad2e9-121">В качестве имени и адреса электронной почты для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="ad2e9-122">Оставьте оставшиеся параметры без изменений в состоянии по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-122">Leave remaining settings unchanged in the default state.</span></span>

   ![Предоставление имени и адреса электронной почты](images/sh2-account2.png)

   ![Оставьте оставшиеся параметры без изменений в состоянии по умолчанию](images/sh2-account3.png)

3. <span data-ttu-id="ad2e9-125">Установите пароль для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-125">Set the password for the device account.</span></span> <span data-ttu-id="ad2e9-126">Чтобы установить пароль, выберите **"Пользователи",** а затем выберите **"Активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="ad2e9-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="ad2e9-127">Теперь найщите только что созданного пользователя, чтобы установить пароль.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="ad2e9-128">Убедитесь, **что не выбран** параметр "Сделать так, чтобы пользователь изменил свой пароль при первом **входе".**</span><span class="sxs-lookup"><span data-stu-id="ad2e9-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Настройка пароля для учетной записи устройства](images/sh2-account4.png)

4. <span data-ttu-id="ad2e9-130">Назначьте комнате лицензию на Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="ad2e9-131">Рекомендуется назначить лицензию на комнату для \*\*\*\* собраний Office 365, которая автоматически включает учетную запись для Microsoft Teams и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![Назначение лицензии на Office 365](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="ad2e9-133">Если вы используете Skype для бизнеса, вам необходимо будет завершать настройку [](#set-calendar-auto-processing-skype-for-business-only) с помощью PowerShell — календаря Skype для бизнеса: настройка автоматической установки календаря для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <span data-ttu-id="ad2e9-134">Создание учетной записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad2e9-134">Create account via PowerShell</span></span>

 <span data-ttu-id="ad2e9-135">Использование PowerShell для быстрой автоматизации задач на Surface Hub не обязательно требует навыков PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="ad2e9-136">Перед использованием соответствующих сценариев на этой странице убедитесь, что выполнены необходимые условия установки.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <span data-ttu-id="ad2e9-137">Необходимые условия для использования PowerShell для управления Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ad2e9-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="ad2e9-138">Запустите PowerShell с повышенными привилегиями**учетной**записи (запуск от прав администратора) и убедитесь, что система настроена на запуск сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="ad2e9-139">Чтобы узнать больше, обратитесь к [политике выполнения.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="ad2e9-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="ad2e9-140">[Установка модуля Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="ad2e9-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <span data-ttu-id="ad2e9-141">Подключение к Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad2e9-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="ad2e9-142">Создание почтового ящика</span><span class="sxs-lookup"><span data-stu-id="ad2e9-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="ad2e9-143">Настройка автоматической обработки календаря (только в Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="ad2e9-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="ad2e9-144">Включить ActiveSync, если требуется использование почтового приложения</span><span class="sxs-lookup"><span data-stu-id="ad2e9-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="ad2e9-145">Политика ActiveSync по умолчанию будет работать, если она не изменилась.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="ad2e9-146">В противном случае создайтеStupid новую политику и назначьте ее.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-146">Otherwise createStupid a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <span data-ttu-id="ad2e9-147">Подключение к Azure AD</span><span class="sxs-lookup"><span data-stu-id="ad2e9-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="ad2e9-148">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="ad2e9-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="ad2e9-149">Проверка на наличии доступных лицензий</span><span class="sxs-lookup"><span data-stu-id="ad2e9-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <span data-ttu-id="ad2e9-150">Сценарий проверки учетной записи</span><span class="sxs-lookup"><span data-stu-id="ad2e9-150">Account verification script</span></span>

<span data-ttu-id="ad2e9-151">После создания учетной записи устройства можно запустить следующий сценарий проверки.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="ad2e9-152">Этот сценарий проверяет ранее созданную учетную запись устройства и создает сводный отчет.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="ad2e9-153">Например:</span><span class="sxs-lookup"><span data-stu-id="ad2e9-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="ad2e9-154">Сведения о конкретных параметрах не отображаются.</span><span class="sxs-lookup"><span data-stu-id="ad2e9-154">Details of specific settings will not be shown.</span></span>

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

## <span data-ttu-id="ad2e9-155">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ad2e9-155">Learn more</span></span>

- [<span data-ttu-id="ad2e9-156">Создание локальных учетных записей Surface Hub 2S с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad2e9-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)