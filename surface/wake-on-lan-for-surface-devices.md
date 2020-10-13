---
title: Пробуждение по локальной сети для устройств Surface (Surface)
description: Узнайте, как использовать функцию Wake on LAN для удаленного пробуждения устройств для выполнения задач управления или обслуживания, а также для автоматического включения решений для управления, даже если питание устройств отключено.
keywords: обновление, развертывание, драйвер, WOL, пробуждение по сети
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114617"
---
# <span data-ttu-id="3a1bb-104">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="3a1bb-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="3a1bb-105">Устройства Surface, которые работают под управлением Windows 10, версия 1607 (также известная как Windows 10 годовщина) или более поздней версии, и используют адаптер Surface Ethernet для подключения к проводной сети, поддерживающие пробуждение через ЛОКАЛЬную сеть (WOL) в режиме ожидания с подключением.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="3a1bb-106">С помощью WOL вы можете удаленно вывести устройства из спящего режима для выполнения задач управления или обслуживания или включения решений для управления (например, Диспетчер конфигураций конечных точек Майкрософт) автоматически.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="3a1bb-107">Например, вы можете развернуть приложения на устройствах Surface, которые были закреплены с помощью стыковочного узла Surface или Surface Pro 3, используя Диспетчер конфигурации конечных точек (Microsoft Endpoint Configuration Manager) во время пустого офиса.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="3a1bb-108">Для поддержки WOL устройства Surface должны быть подключены к сети переменного тока и в режиме ожидания с подключением.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="3a1bb-109">WOL невозможно с устройств, которые находятся в спящем режиме или выключены.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="3a1bb-110">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="3a1bb-110">Supported devices</span></span>

<span data-ttu-id="3a1bb-111">Для WOL поддерживаются следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="3a1bb-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="3a1bb-112">Ethernet-адаптер Surface</span><span class="sxs-lookup"><span data-stu-id="3a1bb-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="3a1bb-113">USB-адаптер Surface и USB</span><span class="sxs-lookup"><span data-stu-id="3a1bb-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="3a1bb-114">Док-станция Surface.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-114">Surface Dock</span></span>
* <span data-ttu-id="3a1bb-115">Стыковочный узел Surface для Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="3a1bb-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="3a1bb-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="3a1bb-116">Surface 3</span></span>
* <span data-ttu-id="3a1bb-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="3a1bb-117">Surface Pro 3</span></span>
* <span data-ttu-id="3a1bb-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="3a1bb-118">Surface Pro 4</span></span>
* <span data-ttu-id="3a1bb-119">Surface Pro (5-го поколения)</span><span class="sxs-lookup"><span data-stu-id="3a1bb-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="3a1bb-120">Surface Pro (5-го поколения) с дополнительным LTE</span><span class="sxs-lookup"><span data-stu-id="3a1bb-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="3a1bb-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="3a1bb-121">Surface Book</span></span>
* <span data-ttu-id="3a1bb-122">Surface ноутбук (1-го поколения)</span><span class="sxs-lookup"><span data-stu-id="3a1bb-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="3a1bb-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="3a1bb-123">Surface Pro 6</span></span>
* <span data-ttu-id="3a1bb-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="3a1bb-124">Surface Book 2</span></span>
* <span data-ttu-id="3a1bb-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="3a1bb-125">Surface Laptop 2</span></span>
* <span data-ttu-id="3a1bb-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="3a1bb-126">Surface Go</span></span>
* <span data-ttu-id="3a1bb-127">Surface Go с функцией LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="3a1bb-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="3a1bb-128">Surface Studio 2 (Дополнительные сведения о Surface Studio 2)</span><span class="sxs-lookup"><span data-stu-id="3a1bb-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="3a1bb-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3a1bb-129">Surface Pro 7</span></span>
* <span data-ttu-id="3a1bb-130">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="3a1bb-130">Surface Laptop 3</span></span>
* <span data-ttu-id="3a1bb-131">Ноутбук Surface Go</span><span class="sxs-lookup"><span data-stu-id="3a1bb-131">Surface Laptop Go</span></span>

## <span data-ttu-id="3a1bb-132">Драйвер WOL</span><span class="sxs-lookup"><span data-stu-id="3a1bb-132">WOL driver</span></span>

<span data-ttu-id="3a1bb-133">Для включения поддержки WOL на Surface Devices требуется определенный драйвер для адаптера Ethernet Surface.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-133">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="3a1bb-134">Этот драйвер не входит в стандартный драйвер и пакет встроенного по для устройств Surface — вы должны скачать и установить его отдельно.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-134">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="3a1bb-135">Драйвер WOL для Surface (SurfaceWOL.msi) можно загрузить на странице [Surface Tools для IT](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-135">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="3a1bb-136">Вы можете запустить этот файл установщика Microsoft Windows (MSI) на устройстве Surface, чтобы установить драйвер WOL для Surface, или распространить его на Surface Devices с помощью решения для развертывания приложения, например диспетчера конфигураций конечных точек Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-136">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3a1bb-137">Чтобы включить драйвер WOL при развертывании, можно установить MSI-файл как приложение в процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-137">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="3a1bb-138">Вы также можете извлечь файлы драйвера WOL для Surface, чтобы включить их в процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-138">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="3a1bb-139">Например, вы можете включить их в общий доступ к развертыванию Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="3a1bb-139">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="3a1bb-140">Дополнительные сведения о развертывании Surface с помощью MDT [для развертывания Windows 10 на Surface Devices можно получить с помощью Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span><span class="sxs-lookup"><span data-stu-id="3a1bb-140">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="3a1bb-141">Во время установки SurfaceWOL.msi для следующего раздела реестра задано значение 1, что позволяет легко идентифицировать системы, в которых установлен драйвер WOL.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-141">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="3a1bb-142">Если вы решили извлечь и установить эти драйверы отдельно во время развертывания, этот раздел реестра не будет настроен, и его необходимо будет настроить вручную или с помощью сценария.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-142">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="3a1bb-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="3a1bb-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="3a1bb-144">Чтобы извлечь содержимое SurfaceWOL.msi, используйте параметр административной установки MSIExec (**/a**), как показано в приведенном ниже примере, чтобы извлечь содержимое в папку C:\WOL\.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-144">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="3a1bb-145">Инструкции для Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="3a1bb-145">Surface Studio 2 instructions</span></span>

<span data-ttu-id="3a1bb-146">Чтобы включить WOL в Surface Studio 2, необходимо выполнить описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-146">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="3a1bb-147">Создайте следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="3a1bb-147">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="3a1bb-148">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a1bb-148">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="3a1bb-149">Использование зоны WOL</span><span class="sxs-lookup"><span data-stu-id="3a1bb-149">Using Surface WOL</span></span>

<span data-ttu-id="3a1bb-150">Драйвер WOL в Surface соответствует стандарту WOL, так как устройство Woken специальной связью по сети, известной как пакет Magic.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-150">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="3a1bb-151">Пакет Magic состоит из шести байт 255 (или FF в шестнадцатеричном формате), за которым следует 16 повторений MAC-адреса целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-151">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="3a1bb-152">Вы можете ознакомиться с дополнительными сведениями о пакете Magic и стандарт WOL на [Википедии](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="3a1bb-152">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="3a1bb-153">Для отправки Magic Packet и пробуждения устройства с помощью WOL необходимо знать MAC-адрес оконечного устройства и адаптера Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-153">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="3a1bb-154">Так как пакет Magic не использует протокол IP-сети, невозможно использовать IP-адрес или DNS-имя устройства.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-154">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="3a1bb-155">Многие решения для управления, например Configuration Manager, предоставляют встроенную поддержку WOL.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-155">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="3a1bb-156">Кроме того, существует множество решений, в том числе приложений Microsoft Store, модулей PowerShell, приложений сторонних разработчиков и сторонних решений для управления, которые позволяют отправлять волшебные пакеты для пробуждения устройства.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-156">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="3a1bb-157">Например, можно использовать [модуль PowerShell Wake on LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) в центре сценариев TechNet.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-157">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="3a1bb-158">После того как устройство будет Woken с помощью Magic Packet, оно вернется в спящий режим, если приложение не препятствует переходу в спящий режим, или если раздел реестра AllowSystemRequiredPowerRequests не настроен на 1, что позволяет приложениям предотвращать переход в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-158">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="3a1bb-159">Дополнительные сведения об этом разделе реестра можно найти в разделе [драйвер WOL](#wol-driver) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="3a1bb-159">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
