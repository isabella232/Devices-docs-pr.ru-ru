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
# <span data-ttu-id="dda48-104">Настройка Surface Hub 2 локальные учетные записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dda48-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="dda48-105">Подключение к Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="dda48-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dda48-106">Для некоторых из этих командлетов требуется полное доменное имя (FQDN) для службы клиентского доступа на локальном сервере Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="dda48-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="dda48-107">Создание учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="dda48-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="dda48-108">Настройка автоматической обработки календаря</span><span class="sxs-lookup"><span data-stu-id="dda48-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="dda48-109">Включение объекта Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dda48-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="dda48-110">Важно знать полное доменное имя для пула регистраторов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dda48-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="dda48-111">Политика почтового ящика для мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="dda48-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="dda48-112">Возможно, потребуется создать политику почтовых ящиков для мобильных устройств (также называемую политикой ActiveSync), чтобы Surface Hub могли подключаться к сети или локальной среде.</span><span class="sxs-lookup"><span data-stu-id="dda48-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="dda48-113">Создание политики почтовых ящиков мобильных устройств Surface HUB</span><span class="sxs-lookup"><span data-stu-id="dda48-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="dda48-114">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="dda48-114">Additional settings</span></span>

<span data-ttu-id="dda48-115">Рекомендуется добавить подсказку в помещения Surface Hub, чтобы пользователи могли забывать о собрании в Skype для бизнеса или рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="dda48-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
