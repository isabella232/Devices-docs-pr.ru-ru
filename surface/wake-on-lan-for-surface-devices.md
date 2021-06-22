---
title: Пробуждение по локальной сети для устройств Surface
description: Узнайте, как можно использовать wake On LAN для удаленного пробуждения устройств для автоматического выполнения задач управления.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613807"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="5d0b5-104">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="5d0b5-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="5d0b5-105">Чтобы поддерживать устройства в полной мере в курсе, ИТ-администраторы должны иметь возможность управлять устройствами, когда они не используются, как правило, во время ночных окон обслуживания.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="5d0b5-106">Wake on LAN (WOL) позволяет администраторам удаленно разбудить устройства и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или сторонних решений.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d0b5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5d0b5-107">Requirements</span></span>

<span data-ttu-id="5d0b5-108">Устройства должны быть подключены к власти переменного тока и иметь проводное подключение к одному из следующих совместимых адаптеров Ethernet:</span><span class="sxs-lookup"><span data-stu-id="5d0b5-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="5d0b5-109">Адаптер Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="5d0b5-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="5d0b5-110">Адаптер Surface Ethernet</span><span class="sxs-lookup"><span data-stu-id="5d0b5-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="5d0b5-111">Surface USB-C для Ethernet и USB-адаптер</span><span class="sxs-lookup"><span data-stu-id="5d0b5-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="5d0b5-112">Концентратор адаптеров для путешествий Microsoft USB-C</span><span class="sxs-lookup"><span data-stu-id="5d0b5-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="5d0b5-113">Док-станция Surface.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-113">Surface Dock</span></span>
- <span data-ttu-id="5d0b5-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="5d0b5-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="5d0b5-115">Surface Dock 2 обеспечивает лучшую поддержку wake на локальной сети без необходимости дополнительной ИТ-конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="5d0b5-116">Дополнительные дополнительные информации см. в [сайте Wake on LAN for Surface Dock 2.](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5d0b5-117">Принцип работы</span><span class="sxs-lookup"><span data-stu-id="5d0b5-117">How it works</span></span>

<span data-ttu-id="5d0b5-118">Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="5d0b5-119">ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="5d0b5-120">Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние Microsoft Store, предоставляют встроенную поддержку WOL.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="5d0b5-121">Дополнительные информацию о бодрствования устройствах с помощью диспетчера конфигурации конечной точки см. в этой ссылке [Configure Wake on LAN - Configuration Manager.](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="5d0b5-122">Поддержка wake на локальной сети зависит от состояния сна: подключенного ожидания или hibernation (состояние питания S4).</span><span class="sxs-lookup"><span data-stu-id="5d0b5-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="5d0b5-123">Подключенный режим ожидания</span><span class="sxs-lookup"><span data-stu-id="5d0b5-123">Connected Standby</span></span>

<span data-ttu-id="5d0b5-124">По умолчанию Windows 10 поддерживает wake на lan-устройствах Surface в подключенной режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="5d0b5-125">Поддерживаемые устройства Surface — подключенное в режиме ожидания</span><span class="sxs-lookup"><span data-stu-id="5d0b5-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="5d0b5-126">Surface Laptop 4 (только процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="5d0b5-127">Surface Laptop 3 (только процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="5d0b5-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5d0b5-128">Surface Pro 7+</span></span>
- <span data-ttu-id="5d0b5-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="5d0b5-129">Surface Pro 7</span></span>
- <span data-ttu-id="5d0b5-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="5d0b5-130">Surface Pro X</span></span>
- <span data-ttu-id="5d0b5-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="5d0b5-131">Surface Go 2</span></span>
- <span data-ttu-id="5d0b5-132">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="5d0b5-132">Surface Laptop Go</span></span>
- <span data-ttu-id="5d0b5-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="5d0b5-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="5d0b5-134">Спячка</span><span class="sxs-lookup"><span data-stu-id="5d0b5-134">Hibernation</span></span>

<span data-ttu-id="5d0b5-135">Чтобы разбудить устройства из режима Hibernation, необходимо включить параметр политики UEFI с помощью режима управления [surface Enterprise](surface-enterprise-management-mode.md) (SEMM) (не требуется для устройств, подключенных к Surface Dock 2).</span><span class="sxs-lookup"><span data-stu-id="5d0b5-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="5d0b5-136">Поддерживаемые устройства Surface - Hibernation</span><span class="sxs-lookup"><span data-stu-id="5d0b5-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="5d0b5-137">Surface Laptop 4 (только процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="5d0b5-138">Surface Laptop 3 (только процессоры Intel)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="5d0b5-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5d0b5-139">Surface Pro 7+</span></span>
- <span data-ttu-id="5d0b5-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="5d0b5-140">Surface Pro 7</span></span>
- <span data-ttu-id="5d0b5-141">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="5d0b5-141">Surface Laptop Go</span></span>
- <span data-ttu-id="5d0b5-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="5d0b5-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="5d0b5-143">Включить параметр Wake на локальной сети UEFI</span><span class="sxs-lookup"><span data-stu-id="5d0b5-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="5d0b5-144">Чтобы включить параметр Wake on LAN UEFI, необходимо записать целевые устройства в SEMM, создать пакет конфигурации и применить пакет к устройствам.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="5d0b5-145">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="5d0b5-145">For more information, refer to:</span></span>

- [<span data-ttu-id="5d0b5-146">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="5d0b5-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="5d0b5-147">Регистрация устройств Surface в SEMM и их настройка</span><span class="sxs-lookup"><span data-stu-id="5d0b5-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="5d0b5-148">Загрузка и установка [**конфигуратора Surface UEFI.**](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="5d0b5-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="5d0b5-149">Выберите **пакет**  >  **начните**  >  **настройку Create**+ Certificate  > **Protection**.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="5d0b5-150">Перейдите **к расширенным настройкам** и включив **wake on lan-сайт** **в On**.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="5d0b5-151">Примени пакет к целевым устройствам.</span><span class="sxs-lookup"><span data-stu-id="5d0b5-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Включить wake на параметре политики LAN UEFI](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="5d0b5-153">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5d0b5-153">Learn more</span></span>

- [<span data-ttu-id="5d0b5-154">Wake on LAN for Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="5d0b5-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="5d0b5-155">Microsoft Surface USB-C для Ethernet и USB-адаптер</span><span class="sxs-lookup"><span data-stu-id="5d0b5-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="5d0b5-156">Адаптер Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="5d0b5-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
