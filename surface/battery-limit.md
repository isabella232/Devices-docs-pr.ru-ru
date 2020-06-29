---
title: Параметр лимита батареи (Surface)
description: Лимит батареи — это параметр UEFI, который изменяет способ оплаты батареи устройства Surface и может продлить долговечность.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835987"
---
# <span data-ttu-id="08c33-103">Параметр ограничения батареи</span><span class="sxs-lookup"><span data-stu-id="08c33-103">Battery Limit setting</span></span>

<span data-ttu-id="08c33-104">Параметр "лимит батареи" — это параметр UEFI, который изменяет способ оплаты батареи устройства Surface и может продлить долговечность.</span><span class="sxs-lookup"><span data-stu-id="08c33-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="08c33-105">Этот параметр рекомендуется использовать в случаях, когда устройство постоянно подключено к питанию, например, если устройства интегрированы в решения для киоска.</span><span class="sxs-lookup"><span data-stu-id="08c33-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="08c33-106">Как работает предел батареи</span><span class="sxs-lookup"><span data-stu-id="08c33-106">How Battery Limit works</span></span>

<span data-ttu-id="08c33-107">Установка ограничения для устройства на уровне заряда батареи изменяет протокол для зазарядки батареи устройства.</span><span class="sxs-lookup"><span data-stu-id="08c33-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="08c33-108">При включении ограничения батареи заряд батареи будет ограничен до 50% от максимальной емкости.</span><span class="sxs-lookup"><span data-stu-id="08c33-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="08c33-109">Это ограничение будет отображено в Windows в соответствии с уровнем заряда.</span><span class="sxs-lookup"><span data-stu-id="08c33-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="08c33-110">Таким образом, это означает, что батарея оплачивается до 50% и не будет взиматься за пределы этого ограничения.</span><span class="sxs-lookup"><span data-stu-id="08c33-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="08c33-111">Если вы включите ограничение батареи, а на устройстве больше 50%, значок батареи показывает, что устройство подключено к сети, но не достигнет размера 50% от максимальной зарядки.</span><span class="sxs-lookup"><span data-stu-id="08c33-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="08c33-112">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="08c33-112">Supported devices</span></span>
<span data-ttu-id="08c33-113">Параметр UEFI ограничения батареи встроен в последние устройства Surface, включая Surface Pro 7 и Surface 3.</span><span class="sxs-lookup"><span data-stu-id="08c33-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="08c33-114">Для более ранних устройств требуется [Обновление встроенного по UEFI для Surface](manage-surface-driver-and-firmware-updates.md), которое можно получить с помощью центра обновления Windows или с помощью драйвера MSI и пакетов микропрограмм на [сайте поддержки Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span><span class="sxs-lookup"><span data-stu-id="08c33-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="08c33-115">Установите флажок [включить ограничение для батареи для устройств Surface, которые должны быть подключены в течение длительного периода времени](https://support.microsoft.com/help/4464941) для определенной версии UEFI Surface, требуемой для каждого поддерживаемого устройства.</span><span class="sxs-lookup"><span data-stu-id="08c33-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="08c33-116">Включение ограничения батареи в UEFI Surface (Surface Pro 4 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="08c33-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="08c33-117">Параметр лимита заряда батареи UEFI Surface можно настроить с помощью функции UEFI Surface (**питание + громкость** при включении устройства).</span><span class="sxs-lookup"><span data-stu-id="08c33-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="08c33-118">Выберите **Конфигурация загрузки**, а **затем в**разделе **Дополнительные параметры**установите переключатель **включить режим ограничения заряда** .</span><span class="sxs-lookup"><span data-stu-id="08c33-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Снимок экрана: дополнительные параметры](images/enable-bl.png) 

## <span data-ttu-id="08c33-120">Включение ограничения на батарею на Surface Go и Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="08c33-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="08c33-121">Параметр лимита заряда батареи можно настроить, загрузя на UEFI Surface (**питание + громкость** при включении устройства).</span><span class="sxs-lookup"><span data-stu-id="08c33-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="08c33-122">Выберите **Конфигурация загрузки**, а затем в разделе **режим киоска**переместите ползунок вправо, чтобы **включить**функцию "ограничить батарею".</span><span class="sxs-lookup"><span data-stu-id="08c33-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Снимок экрана: лимит батареи в режиме киоска в области переходов](images/go-batterylimit.png) 

## <span data-ttu-id="08c33-124">Включение ограничения батареи в UEFI Surface (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="08c33-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="08c33-125">Параметр лимита заряда батареи UEFI Surface можно настроить с помощью функции UEFI Surface (**питание + громкость** при включении устройства).</span><span class="sxs-lookup"><span data-stu-id="08c33-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="08c33-126">Выберите **режим киоска**, нажмите кнопку **предел для батареи**и выберите пункт **включена**.</span><span class="sxs-lookup"><span data-stu-id="08c33-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Снимок экрана: дополнительные параметры](images/enable-bl-sp3.png) 

![Снимок экрана: дополнительные параметры](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="08c33-129">Включение ограничения на батарею с помощью встроенного в корпоративный режим управления Surface (SEMM) или Surface Pro 3 сценарии оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="08c33-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="08c33-130">Лимит батареи UEFI Surface также доступен для настройки с помощью следующих способов:</span><span class="sxs-lookup"><span data-stu-id="08c33-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="08c33-131">Surface Pro 4 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="08c33-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="08c33-132">Конфигуратор UEFI Surface (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="08c33-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="08c33-133">Сценарии PowerShell для диспетчера UEFI Surface (SEMM_Powershell.zip) в [инструментах Surface для IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="08c33-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="08c33-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="08c33-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="08c33-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="08c33-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="08c33-136">Использование конфигуратора UEFI Surface (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="08c33-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="08c33-137">Чтобы настроить режим ограничения заряда батареи, настройте параметры **перекрытия** на странице конфигурации **дополнительных параметров** в SEMM (Surface Pro 4 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="08c33-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Снимок экрана: дополнительные параметры](images/semm-bl.png)

### <span data-ttu-id="08c33-139">Использование сценариев PowerShell диспетчера UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="08c33-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="08c33-140">Функция ограничения батареи контролируется с помощью следующего параметра:</span><span class="sxs-lookup"><span data-stu-id="08c33-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="08c33-141">**Описание**: Активная схема управления для шаблона использования батареи</span><span class="sxs-lookup"><span data-stu-id="08c33-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="08c33-142">**По умолчанию**:</span><span class="sxs-lookup"><span data-stu-id="08c33-142">**Default**:</span></span>  `0` 

<span data-ttu-id="08c33-143">Установите этот флажок, чтобы `1` включить ограничение заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="08c33-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="08c33-144">Использование средств микропрограмм Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="08c33-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="08c33-145">Функция ограничения батареи контролируется с помощью следующего параметра:</span><span class="sxs-lookup"><span data-stu-id="08c33-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="08c33-146">**Name (имя**): BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="08c33-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="08c33-147">**Описание**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="08c33-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="08c33-148">**Текущее значение**:</span><span class="sxs-lookup"><span data-stu-id="08c33-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="08c33-149">**Значение по умолчанию**:</span><span class="sxs-lookup"><span data-stu-id="08c33-149">**Default Value**:</span></span> `0`

<span data-ttu-id="08c33-150">**Предлагаемое значение**:</span><span class="sxs-lookup"><span data-stu-id="08c33-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="08c33-151">Установите этот флажок, чтобы `1` включить ограничение заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="08c33-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="08c33-152">Чтобы настроить этот параметр, необходимо использовать [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="08c33-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

