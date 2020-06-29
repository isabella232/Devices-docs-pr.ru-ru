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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836379"
---
# <span data-ttu-id="8400c-104">Создание учетной записи устройства Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8400c-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="8400c-105">Создание учетной записи устройства Surface Hub (также называемой почтовым ящиком комнаты) позволяет Surface Hub 2 получать, утверждать и отклонять приглашения на собрания, а также присоединяться к собраниям с помощью Microsoft Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8400c-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="8400c-106">Настройте учетную запись устройства во время установки по раскрывающимся спискам взаимодействия (OOBE).</span><span class="sxs-lookup"><span data-stu-id="8400c-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="8400c-107">При необходимости вы можете изменить его позже (без использования параметров OOBE).</span><span class="sxs-lookup"><span data-stu-id="8400c-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="8400c-108">В отличие от стандартных почтовых ящиков, которые по умолчанию остаются отключенными, для входа в Microsoft Teams и Skype для бизнеса нужно включить учетную запись устройства Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="8400c-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="8400c-109">Surface Hub 2 использует Exchange ActiveSync, для которого требуется политика почтового ящика ActiveSync на учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="8400c-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="8400c-110">Примените политику почтовых ящиков ActiveSync по умолчанию, которая входит в состав Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8400c-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="8400c-111">Создайте учетную запись с помощью центра администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8400c-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="8400c-112">Вы можете использовать Exchange Online PowerShell для настройки отдельных функций, в том числе:</span><span class="sxs-lookup"><span data-stu-id="8400c-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="8400c-113">Обработка календаря для каждой учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8400c-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="8400c-114">Пользовательские автоматические ответы на планирование запросов.</span><span class="sxs-lookup"><span data-stu-id="8400c-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="8400c-115">Если политика почтового ящика ActiveSync по умолчанию уже была изменена другим процессом, вам, возможно, потребуется создать и назначить новую политику почтовых ящиков ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="8400c-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="8400c-116">Учетная запись устройства Surface Hub не поддерживает FIPs providers стороннего поставщика удостоверений и должна быть стандартной учетной записью Active Directory или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8400c-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="8400c-117">Создание учетной записи с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8400c-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8400c-118">В центре администрирования Microsoft 365 перейдите к разделу **ресурсы** и выберите **помещения & оборудование** , а затем выберите **+ комната**.</span><span class="sxs-lookup"><span data-stu-id="8400c-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="8400c-119">Укажите имя и адрес электронной почты для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="8400c-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="8400c-120">В состоянии по умолчанию оставить оставшиеся параметры неизменными.</span><span class="sxs-lookup"><span data-stu-id="8400c-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Укажите имя и адрес электронной почты](images/sh2-account2.png)

   ![Оставить оставшиеся параметры неизменными в состоянии по умолчанию](images/sh2-account3.png)

3. <span data-ttu-id="8400c-123">Установите пароль для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="8400c-123">Set the password for the device account.</span></span> <span data-ttu-id="8400c-124">Чтобы задать пароль, нажмите **Пользователи** и выберите **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="8400c-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="8400c-125">Теперь найдите нового пользователя, чтобы установить пароль.</span><span class="sxs-lookup"><span data-stu-id="8400c-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="8400c-126">Убедитесь, что вы **не** выбрали параметр сделать так, **чтобы пользователь изменил свой пароль при первом входе.**</span><span class="sxs-lookup"><span data-stu-id="8400c-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Установка пароля для учетной записи устройства](images/sh2-account4.png)

4. <span data-ttu-id="8400c-128">Назначение комнаты с лицензией на Office 365.</span><span class="sxs-lookup"><span data-stu-id="8400c-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="8400c-129">Рекомендуется назначать лицензии на **Конференц-зал** Office 365, а также новый параметр, который автоматически включает учетную запись Skype для бизнеса Online и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8400c-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Назначение лицензии на Office 365](images/sh2-account5.png)

### <span data-ttu-id="8400c-131">Завершение настройки с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8400c-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="8400c-132">**Skype для бизнеса:** Если вы используете Skype для бизнеса только (локально или в сети), вы можете включить объект Skype для бизнеса, выполнив команду **Enable-CsMeetingRoom** , чтобы включить такие функции, как комната для собраний, для звука и помещения на удержание.</span><span class="sxs-lookup"><span data-stu-id="8400c-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="8400c-133">**Календарь Microsoft Teams и Skype для бизнеса:** Настройка [**автоматической обработки календаря**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="8400c-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="8400c-134">Создание учетной записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8400c-134">Create account using PowerShell</span></span>

<span data-ttu-id="8400c-135">Вы можете создать учетную запись с помощью PowerShell, вместо того чтобы использовать портал центра администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8400c-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="8400c-136">Подключение к Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8400c-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="8400c-137">Создание почтового ящика помещения</span><span class="sxs-lookup"><span data-stu-id="8400c-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="8400c-138">Настройка автоматической обработки календаря</span><span class="sxs-lookup"><span data-stu-id="8400c-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="8400c-139">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="8400c-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="8400c-140">Подключение к Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8400c-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="8400c-141">Установка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="8400c-141">Install pre-requisites</span></span>

- [<span data-ttu-id="8400c-142">Распространяемый пакет Visual C++ 2017</span><span class="sxs-lookup"><span data-stu-id="8400c-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="8400c-143">Модуль PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8400c-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
