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

- **Skype для бизнеса:** Если вы используете Skype для бизнеса только (локально или в сети), вы можете включить объект Skype для бизнеса, выполнив команду **Enable-CsMeetingRoom** , чтобы включить такие функции, как комната для собраний, для звука и помещения на удержание.

- **Календарь Microsoft Teams и Skype для бизнеса:** Настройка [**автоматической обработки календаря**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) для этой учетной записи.

## Создание учетной записи с помощью PowerShell

Вы можете создать учетную запись с помощью PowerShell, вместо того чтобы использовать портал центра администрирования Майкрософт.

### Подключение к Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### Создание почтового ящика помещения

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### Настройка автоматической обработки календаря

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### Назначение лицензии

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## Подключение к Skype для бизнеса Online с помощью PowerShell

### Установка предварительных требований

- [Распространяемый пакет Visual C++ 2017](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [Модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
