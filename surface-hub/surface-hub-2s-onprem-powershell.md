---
title: Настройка Surface Hub 2 локальные учетные записи с помощью PowerShell
description: Сведения о том, как настроить Surface Hub 2S локальные учетные записи с помощью PowerShell
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836643"
---
# Настройка Surface Hub 2 локальные учетные записи с помощью PowerShell

## Подключение к Exchange Server PowerShell

> [!IMPORTANT]
> Для некоторых из этих командлетов требуется полное доменное имя (FQDN) для службы клиентского доступа на локальном сервере Exchange Server.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## Создание учетной записи устройства

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## Настройка автоматической обработки календаря

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## Включение объекта Skype для бизнеса

> [!NOTE]
> Важно знать полное доменное имя для пула регистраторов Skype для бизнеса.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## Политика почтового ящика для мобильных устройств

Возможно, потребуется создать политику почтовых ящиков для мобильных устройств (также называемую политикой ActiveSync), чтобы Surface Hub могли подключаться к сети или локальной среде.

## Создание политики почтовых ящиков мобильных устройств Surface HUB

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## Дополнительные параметры

Рекомендуется добавить подсказку в помещения Surface Hub, чтобы пользователи могли забывать о собрании в Skype для бизнеса или рабочих групп.

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
