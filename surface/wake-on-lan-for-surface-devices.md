---
title: Wake On LAN для устройств Surface (Surface)
description: Узнайте, как использовать Локальное устройство Wake On, чтобы удаленно разбудить устройства для выполнения задач управления или обслуживания, или включить решения управления автоматически, даже если устройства отключены.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
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
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271126"
---
# <span data-ttu-id="6c40c-104">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="6c40c-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="6c40c-105">Устройства Surface под названием Windows 10 версии 1607 (также известные как юбилейное обновление Windows 10) или более поздней версии и используют адаптер Surface Ethernet для подключения к проводной сети, могут подключаться по локальной сети (WOL) из режимов ожидания с подключением.</span><span class="sxs-lookup"><span data-stu-id="6c40c-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="6c40c-106">С помощью WOL вы можете удаленно разбудить устройства для выполнения задач управления или обслуживания или включить решения управления (например, Microsoft Endpoint Configuration Manager) автоматически.</span><span class="sxs-lookup"><span data-stu-id="6c40c-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="6c40c-107">Например, вы можете развернуть приложения на устройствах Surface, остающихся закрепленными на док-станции Surface или док-станции Surface Pro 3, с помощью Microsoft Endpoint Configuration Manager в середине дня, когда офис пуст.</span><span class="sxs-lookup"><span data-stu-id="6c40c-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="6c40c-108">Устройства Surface должны быть подключены к сети переменного тока и в режиме ожидания с подключением (спящий режим) для поддержки WOL.</span><span class="sxs-lookup"><span data-stu-id="6c40c-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="6c40c-109">WOL невозможен на устройствах, которые находятся в режиме гибернации или отключены.</span><span class="sxs-lookup"><span data-stu-id="6c40c-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="6c40c-110">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="6c40c-110">Supported devices</span></span>

<span data-ttu-id="6c40c-111">Для WOL поддерживаются следующие устройства:</span><span class="sxs-lookup"><span data-stu-id="6c40c-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="6c40c-112">Адаптер Ethernet для Surface</span><span class="sxs-lookup"><span data-stu-id="6c40c-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="6c40c-113">От Surface USB-C к Ethernet и USB-адаптеру</span><span class="sxs-lookup"><span data-stu-id="6c40c-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="6c40c-114">Док-станция Surface.</span><span class="sxs-lookup"><span data-stu-id="6c40c-114">Surface Dock</span></span>
* <span data-ttu-id="6c40c-115">Док-станция Surface для Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="6c40c-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="6c40c-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="6c40c-116">Surface 3</span></span>
* <span data-ttu-id="6c40c-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="6c40c-117">Surface Pro 3</span></span>
* <span data-ttu-id="6c40c-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="6c40c-118">Surface Pro 4</span></span>
* <span data-ttu-id="6c40c-119">Surface Pro (5-е поколения)</span><span class="sxs-lookup"><span data-stu-id="6c40c-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="6c40c-120">Surface Pro (5-е поколения) с LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="6c40c-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="6c40c-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="6c40c-121">Surface Book</span></span>
* <span data-ttu-id="6c40c-122">Surface Laptop (1-е поколения)</span><span class="sxs-lookup"><span data-stu-id="6c40c-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="6c40c-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="6c40c-123">Surface Pro 6</span></span>
* <span data-ttu-id="6c40c-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="6c40c-124">Surface Book 2</span></span>
* <span data-ttu-id="6c40c-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="6c40c-125">Surface Laptop 2</span></span>
* <span data-ttu-id="6c40c-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="6c40c-126">Surface Go</span></span>
* <span data-ttu-id="6c40c-127">Surface Go с функцией LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="6c40c-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="6c40c-128">Surface Studio 2 (см. инструкции по Surface Studio 2 ниже)</span><span class="sxs-lookup"><span data-stu-id="6c40c-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="6c40c-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="6c40c-129">Surface Pro 7</span></span>
* <span data-ttu-id="6c40c-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="6c40c-130">Surface Laptop 3</span></span>
* <span data-ttu-id="6c40c-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="6c40c-131">Surface Laptop Go</span></span>
* <span data-ttu-id="6c40c-132">Surface Pro 7 и более</span><span class="sxs-lookup"><span data-stu-id="6c40c-132">Surface Pro 7+</span></span>

## <span data-ttu-id="6c40c-133">Драйвер WOL</span><span class="sxs-lookup"><span data-stu-id="6c40c-133">WOL driver</span></span>

<span data-ttu-id="6c40c-134">Чтобы включить поддержку WOL на устройствах Surface, требуется определенный драйвер для адаптера Ethernet Surface.</span><span class="sxs-lookup"><span data-stu-id="6c40c-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="6c40c-135">Этот драйвер не включен в стандартный пакет драйверов и микропрограмм для устройств Surface. Его необходимо скачать и установить отдельно.</span><span class="sxs-lookup"><span data-stu-id="6c40c-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="6c40c-136">Вы можете скачать драйвер Surface WOL (SurfaceWOL.msi) со страницы ["Инструменты Surface для ИТ-технологий"](https://www.microsoft.com/download/details.aspx?id=46703) в Центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6c40c-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="6c40c-137">Вы можете запустить этот установщик Microsoft Windows (MSI) на устройстве Surface для установки драйвера Surface WOL или распространить его на устройства Surface с помощью решения развертывания приложений, например Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6c40c-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="6c40c-138">Чтобы включить драйвер Surface WOL во время развертывания, можно установить MSI-файл как приложение во время процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="6c40c-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="6c40c-139">Вы также можете извлечь файлы драйверов Surface WOL, чтобы включить их в процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="6c40c-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="6c40c-140">Например, их можно включить в обную набор средств microsoft Deployment набор средств (MDT).</span><span class="sxs-lookup"><span data-stu-id="6c40c-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="6c40c-141">Вы можете узнать больше о развертывании Surface с помощью MDT в развертывании [Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)на устройствах Surface с помощью Microsoft Deployment набор средств.</span><span class="sxs-lookup"><span data-stu-id="6c40c-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="6c40c-142">Во время установки SurfaceWOL.msi для следующего реестра устанавливается значение 1, что позволяет легко определить системы, в которых установлен драйвер WOL.</span><span class="sxs-lookup"><span data-stu-id="6c40c-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="6c40c-143">Если вы решили извлечь и установить эти драйверы отдельно во время развертывания, этот раздел реестра не будет настроен и должен быть настроен вручную или с помощью скрипта.</span><span class="sxs-lookup"><span data-stu-id="6c40c-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="6c40c-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="6c40c-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="6c40c-145">Чтобы извлечь содержимое SurfaceWOL.msi, используйте параметр административной установки MSIExec (**/a),** как показано в следующем примере, чтобы извлечь содержимое в папку C:\WOL\:</span><span class="sxs-lookup"><span data-stu-id="6c40c-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="6c40c-146">Инструкции по Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="6c40c-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="6c40c-147">Чтобы включить WOL на Surface Studio 2, необходимо использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="6c40c-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="6c40c-148">Создайте следующие ключи реестра:</span><span class="sxs-lookup"><span data-stu-id="6c40c-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="6c40c-149">Запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6c40c-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="6c40c-150">Использование Surface WOL</span><span class="sxs-lookup"><span data-stu-id="6c40c-150">Using Surface WOL</span></span>

<span data-ttu-id="6c40c-151">Драйвер Surface WOL соответствует стандарту WOL, в результате чего устройство находится в безопасности благодаря специальной сетевой связи, известной как пакет "чудо-пакет".</span><span class="sxs-lookup"><span data-stu-id="6c40c-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="6c40c-152">Пакет содержит 6 bytes of 255 (or FF in hexadecimal), за которым следует 16 повторений MAC-адреса конечного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6c40c-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="6c40c-153">Вы можете узнать больше о пакете и [](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)стандарте WOL в Википедии.</span><span class="sxs-lookup"><span data-stu-id="6c40c-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="6c40c-154">Чтобы отправить пакет с помощью WOL, необходимо знать MAC-адрес целевого устройства и адаптер Ethernet.</span><span class="sxs-lookup"><span data-stu-id="6c40c-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="6c40c-155">Поскольку пакет не использует протокол IP-сети, невозможно использовать IP-адрес или DNS-имя устройства.</span><span class="sxs-lookup"><span data-stu-id="6c40c-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="6c40c-156">Многие решения управления, такие как Configuration Manager, обеспечивают встроенную поддержку WOL.</span><span class="sxs-lookup"><span data-stu-id="6c40c-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="6c40c-157">Кроме того, существует множество решений, включая приложения Microsoft Store, модули PowerShell, сторонние приложения и сторонние решения для управления, позволяющие отправить пакет для запуска устройства.</span><span class="sxs-lookup"><span data-stu-id="6c40c-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="6c40c-158">Например, можно использовать модуль [PowerShell Wake On LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) из центра скриптов TechNet.</span><span class="sxs-lookup"><span data-stu-id="6c40c-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="6c40c-159">После того как устройство было перезахвачено с помощью пакетов , устройство вернется в спящий режим, если приложение не активно предотвращает спящий режим в системе или если для ключа реестра AllowSystemRequiredPowerRequests не настроено значение 1, что позволяет приложениям предотвратить спящий режим.</span><span class="sxs-lookup"><span data-stu-id="6c40c-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="6c40c-160">Дополнительные сведения об этом разделе реестра см. в разделе драйверов [WOL](#wol-driver) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="6c40c-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
