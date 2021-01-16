---
title: Параметр ограничения заряда батареи (Surface)
description: Ограничение заряда батареи — это параметр UEFI, который изменяет способ зарядки батареи устройства Surface и может продлить срок его действия.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271146"
---
# <span data-ttu-id="1f990-103">Параметр ограничения батареи</span><span class="sxs-lookup"><span data-stu-id="1f990-103">Battery Limit setting</span></span>

<span data-ttu-id="1f990-104">Параметр ограничения заряда батареи — это параметр UEFI, который изменяет способ заряда батареи устройства Surface и может продлить срок его действия.</span><span class="sxs-lookup"><span data-stu-id="1f990-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="1f990-105">Этот параметр рекомендуется в тех случаях, когда устройство постоянно подключено к сети, например при интеграции устройств в решения киоска.</span><span class="sxs-lookup"><span data-stu-id="1f990-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="1f990-106">Как работает ограничение заряда батареи</span><span class="sxs-lookup"><span data-stu-id="1f990-106">How Battery Limit works</span></span>

<span data-ttu-id="1f990-107">Установка на устройстве ограничения заряда батареи изменяет протокол для зарядки батареи устройства.</span><span class="sxs-lookup"><span data-stu-id="1f990-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="1f990-108">Если включено ограничение заряда батареи, заряд батареи будет ограничен 50 % от максимальной емкости.</span><span class="sxs-lookup"><span data-stu-id="1f990-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="1f990-109">Уровень заряда, сообщаемой в Windows, отражает это ограничение.</span><span class="sxs-lookup"><span data-stu-id="1f990-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="1f990-110">Таким образом, будет видно, что заряд батареи составляет до 50 % и не будет отвечать за это ограничение.</span><span class="sxs-lookup"><span data-stu-id="1f990-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="1f990-111">Если вы включаете ограничение заряда батареи, когда заряд устройства превышает 50 %, значок батареи будет показывать, что устройство подключено к подключению, но отключается, пока устройство не достигнет 50 % от максимальной емкости заряда.</span><span class="sxs-lookup"><span data-stu-id="1f990-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="1f990-112">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="1f990-112">Supported devices</span></span>

<span data-ttu-id="1f990-113">Параметр UEFI ограничения заряда батареи встроен в новейшие устройства Surface, включая Surface Pro 7+, Surface Pro 7 и Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="1f990-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="1f990-114">Более ранним устройствам требуется обновление [микропрограммы UEFI Surface,](manage-surface-driver-and-firmware-updates.md)доступное через Обновление Windows или с помощью драйверов MSI и пакетов микропрограмм на сайте [поддержки Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="1f990-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="1f990-115">Проверьте [, включить "Ограничение](https://support.microsoft.com/help/4464941) заряда батареи" для устройств Surface, которые должны быть подключены в течение длительного времени для определенной версии UEFI Surface, необходимой для каждого поддерживаемого устройства.</span><span class="sxs-lookup"><span data-stu-id="1f990-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="1f990-116">Включение ограничения заряда батареи в Surface UEFI (Surface Pro 4 и более поздних)</span><span class="sxs-lookup"><span data-stu-id="1f990-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="1f990-117">Параметр ограничения заряда батареи UEFI Surface можно настроить путем загрузки в Surface UEFI (**Power + Vol Up** при включаемом устройстве).</span><span class="sxs-lookup"><span data-stu-id="1f990-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="1f990-118">Выберите **конфигурацию загрузки,** а затем в \*\*\*\* области **"Дополнительные**параметры" в меню "Включить режим ограничения заряда" **вкл.**</span><span class="sxs-lookup"><span data-stu-id="1f990-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Дополнительные параметры ограничения заряда батареи](images/enable-bl.png) 

## <span data-ttu-id="1f990-120">Включение ограничения заряда батареи на Surface Go и Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="1f990-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="1f990-121">Параметр ограничения заряда батареи Surface можно настроить, загрузив surface UEFI (**Power + Vol Up** при включаемом устройстве).</span><span class="sxs-lookup"><span data-stu-id="1f990-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="1f990-122">Выберите **конфигурацию загрузки,** а затем в режиме терминала переместим ползунок вправо, чтобы установить для ограничения заряда батареи **включено.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1f990-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Ограничение заряда батареи в режиме терминала в Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="1f990-124">Включение ограничения заряда батареи в Surface UEFI (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="1f990-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="1f990-125">Параметр ограничения заряда батареи UEFI Surface можно настроить путем загрузки в Surface UEFI (**Power + Vol Up** при включаемом устройстве).</span><span class="sxs-lookup"><span data-stu-id="1f990-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="1f990-126">Выберите **режим терминала,** выберите **ограничение заряда**батареи, а затем выберите **"Включено".**</span><span class="sxs-lookup"><span data-stu-id="1f990-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Снимок экрана: дополнительные параметры](images/enable-bl-sp3.png) 

![Дополнительные параметры](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="1f990-129">Включение ограничения заряда батареи с помощью скриптов PowerShell для режима управления Surface Enterprise (SEMM) или Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="1f990-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="1f990-130">Ограничение заряда батареи UEFI Surface также доступно для настройки с помощью следующих методов:</span><span class="sxs-lookup"><span data-stu-id="1f990-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="1f990-131">Surface Pro 4 и более поздние</span><span class="sxs-lookup"><span data-stu-id="1f990-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="1f990-132">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="1f990-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="1f990-133">Сценарии Powershell диспетчера UEFI Surface (SEMM_Powershell.zip) в [средствах Surface для загрузки ИТ-отдела](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="1f990-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="1f990-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="1f990-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="1f990-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="1f990-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="1f990-136">Использование Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="1f990-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="1f990-137">Чтобы настроить режим ограничения заряда батареи, установите \*\*\*\* параметр "Переопределения терминала" на странице "Дополнительные параметры" в SEMM (Surface Pro 4 и более поздних). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1f990-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Снимок экрана с расширенными настройками](images/semm-bl.png)

### <span data-ttu-id="1f990-139">Использование сценариев PowerShell диспетчера UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="1f990-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="1f990-140">Управление ограничением заряда батареи осуществляется с помощью следующего параметра:</span><span class="sxs-lookup"><span data-stu-id="1f990-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="1f990-141">**Описание:** схема активного управления для шаблона использования батареи</span><span class="sxs-lookup"><span data-stu-id="1f990-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="1f990-142">**По умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="1f990-142">**Default**:</span></span>  `0` 

<span data-ttu-id="1f990-143">Установите этот `1` режим, чтобы включить ограничение заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="1f990-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="1f990-144">Использование средств микропрограмм Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="1f990-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="1f990-145">Управление ограничением заряда батареи осуществляется с помощью следующего параметра:</span><span class="sxs-lookup"><span data-stu-id="1f990-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="1f990-146">**Name**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="1f990-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="1f990-147">**Описание:** BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="1f990-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="1f990-148">**Текущее значение:**</span><span class="sxs-lookup"><span data-stu-id="1f990-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="1f990-149">**Значение по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="1f990-149">**Default Value**:</span></span> `0`

<span data-ttu-id="1f990-150">**Предложенное значение:**</span><span class="sxs-lookup"><span data-stu-id="1f990-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="1f990-151">Установите этот `1` режим, чтобы включить ограничение заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="1f990-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="1f990-152">Чтобы настроить этот параметр, необходимо [ использовать ](https://www.microsoft.com/download/details.aspx?id=46703)SP3_Firmware_Powershell_Scripts.zip.</span><span class="sxs-lookup"><span data-stu-id="1f990-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

