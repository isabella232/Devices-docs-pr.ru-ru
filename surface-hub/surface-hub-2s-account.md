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
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196732"
---
# <span data-ttu-id="2ec1d-104">Создание учетной записи устройства Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="2ec1d-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="2ec1d-105">Создание учетной записи устройства Surface Hub (также называемой почтовым ящиком комнаты) позволяет Surface Hub 2 получать, утверждать и отклонять приглашения на собрания, а также присоединяться к собраниям с помощью Microsoft Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="2ec1d-106">Настройте учетную запись устройства во время установки по раскрывающимся спискам взаимодействия (OOBE).</span><span class="sxs-lookup"><span data-stu-id="2ec1d-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="2ec1d-107">При необходимости вы можете изменить его позже (без использования параметров OOBE).</span><span class="sxs-lookup"><span data-stu-id="2ec1d-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="2ec1d-108">В отличие от стандартных почтовых ящиков, которые по умолчанию остаются отключенными, для входа в Microsoft Teams и Skype для бизнеса нужно включить учетную запись устройства Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="2ec1d-109">Surface Hub 2 использует Exchange ActiveSync, для которого требуется политика почтового ящика ActiveSync на учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="2ec1d-110">Примените политику почтовых ящиков ActiveSync по умолчанию, которая входит в состав Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="2ec1d-111">Создайте учетную запись с помощью центра администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="2ec1d-112">Вы можете использовать Exchange Online PowerShell для настройки отдельных функций, в том числе:</span><span class="sxs-lookup"><span data-stu-id="2ec1d-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="2ec1d-113">Обработка календаря для каждой учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="2ec1d-114">Пользовательские автоматические ответы на планирование запросов.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="2ec1d-115">Если политика почтового ящика ActiveSync по умолчанию уже была изменена другим процессом, вам, возможно, потребуется создать и назначить новую политику почтовых ящиков ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="2ec1d-116">Учетная запись устройства Surface Hub не поддерживает FIPs providers стороннего поставщика удостоверений и должна быть стандартной учетной записью Active Directory или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="2ec1d-117">Создание учетной записи с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ec1d-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="2ec1d-118">В центре администрирования Microsoft 365 перейдите к разделу **ресурсы** и выберите **помещения & оборудование** , а затем выберите **+ комната**.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="2ec1d-119">Укажите имя и адрес электронной почты для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="2ec1d-120">В состоянии по умолчанию оставить оставшиеся параметры неизменными.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Укажите имя и адрес электронной почты](images/sh2-account2.png)

   ![Оставить оставшиеся параметры неизменными в состоянии по умолчанию](images/sh2-account3.png)

3. <span data-ttu-id="2ec1d-123">Установите пароль для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-123">Set the password for the device account.</span></span> <span data-ttu-id="2ec1d-124">Чтобы задать пароль, нажмите **Пользователи** и выберите **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="2ec1d-125">Теперь найдите нового пользователя, чтобы установить пароль.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="2ec1d-126">Убедитесь, что вы **не** выбрали параметр сделать так, **чтобы пользователь изменил свой пароль при первом входе.**</span><span class="sxs-lookup"><span data-stu-id="2ec1d-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Установка пароля для учетной записи устройства](images/sh2-account4.png)

4. <span data-ttu-id="2ec1d-128">Назначение комнаты с лицензией на Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="2ec1d-129">Рекомендуется назначать лицензии на **Конференц-зал** Office 365, а также новый параметр, который автоматически включает учетную запись Skype для бизнеса Online и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Назначение лицензии на Office 365](images/sh2-account5.png)

### <span data-ttu-id="2ec1d-131">Завершение настройки с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ec1d-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="2ec1d-132">**Календарь Microsoft Teams и Skype для бизнеса:** Настройка [**автоматической обработки календаря**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="2ec1d-133">Создание учетной записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ec1d-133">Create account using PowerShell</span></span>

<span data-ttu-id="2ec1d-134">Вы можете создать учетную запись с помощью PowerShell, вместо того чтобы использовать портал центра администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="2ec1d-135">Подключение к Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ec1d-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="2ec1d-136">Создание почтового ящика</span><span class="sxs-lookup"><span data-stu-id="2ec1d-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="2ec1d-137">Настройка автоматической обработки календаря</span><span class="sxs-lookup"><span data-stu-id="2ec1d-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="2ec1d-138">Включить ActiveSync, если требуется использование почтового приложения</span><span class="sxs-lookup"><span data-stu-id="2ec1d-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="2ec1d-139">Политика ActiveSync по умолчанию будет работать, если unchnaged.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="2ec1d-140">В противном случае создайте новую политику и назначьте ее.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="2ec1d-141">Подключение к Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ec1d-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="2ec1d-142">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="2ec1d-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="2ec1d-143">Проверка наличия доступных лицензий</span><span class="sxs-lookup"><span data-stu-id="2ec1d-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```