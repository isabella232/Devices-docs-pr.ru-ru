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
# Создание учетной записи устройства Surface Hub 2S

Создание учетной записи устройства Surface Hub (также называемой почтовым ящиком комнаты) позволяет Surface Hub 2 получать, утверждать и отклонять приглашения на собрания, а также присоединяться к собраниям с помощью Microsoft Teams или Skype для бизнеса. Настройте учетную запись устройства во время установки по раскрывающимся спискам взаимодействия (OOBE). При необходимости вы можете изменить его позже (без использования параметров OOBE).

В отличие от стандартных почтовых ящиков, которые по умолчанию остаются отключенными, для входа в Microsoft Teams и Skype для бизнеса нужно включить учетную запись устройства Surface Hub 2S. Surface Hub 2 использует Exchange ActiveSync, для которого требуется политика почтового ящика ActiveSync на учетной записи устройства. Примените политику почтовых ящиков ActiveSync по умолчанию, которая входит в состав Exchange Online.

Создайте учетную запись с помощью центра администрирования Microsoft 365 или с помощью PowerShell. Вы можете использовать Exchange Online PowerShell для настройки отдельных функций, в том числе:

- Обработка календаря для каждой учетной записи устройства Surface Hub.
- Пользовательские автоматические ответы на планирование запросов.
- Если политика почтового ящика ActiveSync по умолчанию уже была изменена другим процессом, вам, возможно, потребуется создать и назначить новую политику почтовых ящиков ActiveSync.

> [!NOTE]  
> Учетная запись устройства Surface Hub не поддерживает FIPs providers стороннего поставщика удостоверений и должна быть стандартной учетной записью Active Directory или Azure Active Directory.

## Создание учетной записи с помощью центра администрирования Microsoft 365

1. В центре администрирования Microsoft 365 перейдите к разделу **ресурсы** и выберите **помещения & оборудование** , а затем выберите **+ комната**.

2. Укажите имя и адрес электронной почты для учетной записи устройства. В состоянии по умолчанию оставить оставшиеся параметры неизменными.

   ![Укажите имя и адрес электронной почты](images/sh2-account2.png)

   ![Оставить оставшиеся параметры неизменными в состоянии по умолчанию](images/sh2-account3.png)

3. Установите пароль для учетной записи устройства. Чтобы задать пароль, нажмите **Пользователи** и выберите **Активные пользователи**. Теперь найдите нового пользователя, чтобы установить пароль. Убедитесь, что вы **не** выбрали параметр сделать так, **чтобы пользователь изменил свой пароль при первом входе.**

   ![Установка пароля для учетной записи устройства](images/sh2-account4.png)

4. Назначение комнаты с лицензией на Office 365. Рекомендуется назначать лицензии на **Конференц-зал** Office 365, а также новый параметр, который автоматически включает учетную запись Skype для бизнеса Online и Microsoft Teams.

   ![Назначение лицензии на Office 365](images/sh2-account5.png)

### Завершение настройки с помощью PowerShell

- **Календарь Microsoft Teams и Skype для бизнеса:** Настройка [**автоматической обработки календаря**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) для этой учетной записи.

## Создание учетной записи с помощью PowerShell

Вы можете создать учетную запись с помощью PowerShell, вместо того чтобы использовать портал центра администрирования Майкрософт.

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

### Настройка автоматической обработки календаря

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Включить ActiveSync, если требуется использование почтового приложения

 Политика ActiveSync по умолчанию будет работать, если unchnaged. В противном случае создайте новую политику и назначьте ее.

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

### Проверка наличия доступных лицензий

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```