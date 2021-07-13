---
title: Пробуждение по локальной сети с использованием Surface Dock 2
description: Surface Dock 2 обеспечивает лучшую поддержку wake on LAN (WOL), позволяя администраторам удаленно разбудить устройства и автоматически выполнять задачи управления.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643855"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="63137-104">Пробуждение по локальной сети с использованием Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="63137-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="63137-105">Чтобы поддерживать устройства в полной мере в курсе, ИТ-администраторы должны иметь возможность управлять устройствами, когда они не используются, как правило, во время ночных окон обслуживания.</span><span class="sxs-lookup"><span data-stu-id="63137-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="63137-106">Surface Dock 2 обеспечивает лучшую поддержку wake on LAN (WOL), позволяя администраторам удаленно разбудить устройства и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или других сторонних решений.</span><span class="sxs-lookup"><span data-stu-id="63137-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="63137-107">Требования</span><span class="sxs-lookup"><span data-stu-id="63137-107">Requirements</span></span>

<span data-ttu-id="63137-108">Устройства должны иметь проводное подключение к Surface Dock 2 и оставаться подключенными к ac Power.</span><span class="sxs-lookup"><span data-stu-id="63137-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="63137-110">Поддерживаемые устройства Surface</span><span class="sxs-lookup"><span data-stu-id="63137-110">Supported Surface devices</span></span>

- <span data-ttu-id="63137-111">Surface Laptop 4 (процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="63137-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="63137-112">Surface Laptop 4 (процессоры AMD)</span><span class="sxs-lookup"><span data-stu-id="63137-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="63137-113">Surface Laptop 3 (процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="63137-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="63137-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="63137-114">Surface Pro 7+</span></span>
- <span data-ttu-id="63137-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="63137-115">Surface Pro 7</span></span>
- <span data-ttu-id="63137-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="63137-116">Surface Pro X</span></span>
- <span data-ttu-id="63137-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="63137-117">Surface Go 2</span></span>
- <span data-ttu-id="63137-118">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="63137-118">Surface Laptop Go</span></span>
- <span data-ttu-id="63137-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="63137-119">Surface Book 3</span></span>

<span data-ttu-id="63137-120">Surface Dock 2 обеспечивает поддержку WOL для устройств в следующих состояниях мощности:</span><span class="sxs-lookup"><span data-stu-id="63137-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="63137-121">Режим ожидания с подключением</span><span class="sxs-lookup"><span data-stu-id="63137-121">Connected standby</span></span>
- <span data-ttu-id="63137-122">Hibernation (состояние питания S4)</span><span class="sxs-lookup"><span data-stu-id="63137-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="63137-123">Отключение (состояние питания S5 "soft off")</span><span class="sxs-lookup"><span data-stu-id="63137-123">Shutdown (S5 “soft off” power state)</span></span>

<span data-ttu-id="63137-124">Дополнительные дополнительные информацию о состояниях власти [см.](/windows/win32/power/system-power-states)в этой информации.</span><span class="sxs-lookup"><span data-stu-id="63137-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="63137-125">Принцип работы</span><span class="sxs-lookup"><span data-stu-id="63137-125">How it works</span></span>

<span data-ttu-id="63137-126">Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby.</span><span class="sxs-lookup"><span data-stu-id="63137-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="63137-127">ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="63137-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="63137-128">Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние Microsoft Store, предоставляют встроенную поддержку WOL.</span><span class="sxs-lookup"><span data-stu-id="63137-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="63137-129">Чтобы включить WOL на устройствах без Surface Dock 2, см. в рубке [Wake on LAN для устройств Surface.](wake-on-lan-for-surface-devices.md)</span><span class="sxs-lookup"><span data-stu-id="63137-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="63137-130">Подробнее</span><span class="sxs-lookup"><span data-stu-id="63137-130">Learn more</span></span>

- [<span data-ttu-id="63137-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="63137-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="63137-132">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="63137-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="63137-133">Состояния power system</span><span class="sxs-lookup"><span data-stu-id="63137-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="63137-134">Настройка wake на локальной сети — диспетчер конфигурации</span><span class="sxs-lookup"><span data-stu-id="63137-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
