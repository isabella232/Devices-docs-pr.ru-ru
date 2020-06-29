---
title: Защита и управление Surface Hub 2S с помощью SEMM
description: Дополнительные сведения о защите Surface Hub 2S с помощью SEMM.
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835272"
---
# <span data-ttu-id="86bd9-104">Защита и администрирование Surface Hub 2S с помощью SEMM и UEFI</span><span class="sxs-lookup"><span data-stu-id="86bd9-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="86bd9-105">Новые возможности в Surface Hub 2. Вы можете использовать SEMM для управления параметрами UEFI устройства.</span><span class="sxs-lookup"><span data-stu-id="86bd9-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="86bd9-106">Используйте конфигуратор Microsoft Surface UEFI для управления следующими компонентами:</span><span class="sxs-lookup"><span data-stu-id="86bd9-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="86bd9-107">Проводная сеть</span><span class="sxs-lookup"><span data-stu-id="86bd9-107">Wired LAN</span></span>
- <span data-ttu-id="86bd9-108">Камеры</span><span class="sxs-lookup"><span data-stu-id="86bd9-108">Cameras</span></span>
- <span data-ttu-id="86bd9-109">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="86bd9-109">Bluetooth</span></span>
- <span data-ttu-id="86bd9-110">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="86bd9-110">Wi-Fi</span></span>
- <span data-ttu-id="86bd9-111">Датчик занятости</span><span class="sxs-lookup"><span data-stu-id="86bd9-111">Occupancy sensor</span></span>

<span data-ttu-id="86bd9-112">Используйте конфигуратор Microsoft Surface UEFI, чтобы включить или отключить следующие параметры UEFI:</span><span class="sxs-lookup"><span data-stu-id="86bd9-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="86bd9-113">Загрузка</span><span class="sxs-lookup"><span data-stu-id="86bd9-113">Boot</span></span>

    - <span data-ttu-id="86bd9-114">IPv6 для загрузки PXE</span><span class="sxs-lookup"><span data-stu-id="86bd9-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="86bd9-115">Альтернативная загрузка</span><span class="sxs-lookup"><span data-stu-id="86bd9-115">Alternate Boot</span></span>
    - <span data-ttu-id="86bd9-116">Блокировка порядка загрузки</span><span class="sxs-lookup"><span data-stu-id="86bd9-116">Boot Order Lock</span></span>
    - <span data-ttu-id="86bd9-117">USB-загрузка</span><span class="sxs-lookup"><span data-stu-id="86bd9-117">USB Boot</span></span>
- <span data-ttu-id="86bd9-118">Передняя страница UEFI</span><span class="sxs-lookup"><span data-stu-id="86bd9-118">UEFI Front Page</span></span>

    - <span data-ttu-id="86bd9-119">Устройства</span><span class="sxs-lookup"><span data-stu-id="86bd9-119">Devices</span></span>
    - <span data-ttu-id="86bd9-120">Загрузка</span><span class="sxs-lookup"><span data-stu-id="86bd9-120">Boot</span></span>
    - <span data-ttu-id="86bd9-121">Дата и время</span><span class="sxs-lookup"><span data-stu-id="86bd9-121">Date/Time</span></span>

## <span data-ttu-id="86bd9-122">Создание образа конфигурации UEFI</span><span class="sxs-lookup"><span data-stu-id="86bd9-122">Create UEFI configuration image</span></span>

<span data-ttu-id="86bd9-123">В отличие от других устройств Surface, вы не можете использовать MSI-файл или изображение Win PE для применения этих параметров на Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="86bd9-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="86bd9-124">Вместо этого необходимо создать USB-изображение для загрузки на устройство.</span><span class="sxs-lookup"><span data-stu-id="86bd9-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="86bd9-125">Чтобы создать файл конфигурации UEFI Surface Hub 2S, скачайте и установите последнюю версию конфигуратора UEFI Surface (Майкрософт) со страницы [инструменты Surface для IT](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="86bd9-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="86bd9-126">Дополнительные сведения об использовании UEFI и SEMM можно найти в [корпоративном режиме Microsoft Surface Management](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="86bd9-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="86bd9-127">Настройка UEFI на Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="86bd9-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="86bd9-128">Запустите конфигуратор UEFI и на первом экране выберите **пакет конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="86bd9-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* Запустите конфигуратор UEFI и выберите пакет конфигурации \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="86bd9-130">Чтобы добавить сертификат в пакет, необходимо иметь действительный сертификат с закрытым ключом в формате PFX-файла, чтобы подписать и защитить пакет.</span><span class="sxs-lookup"><span data-stu-id="86bd9-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="86bd9-131">Выберите **+ Защита сертификата.**</span><span class="sxs-lookup"><span data-stu-id="86bd9-131">Select **+ Certificate Protection.**</span></span> <br>
![\* Выберите + Защита сертификата \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="86bd9-133">Введите пароль закрытого ключа сертификата.</span><span class="sxs-lookup"><span data-stu-id="86bd9-133">Enter the certificate’s private key’s password.</span></span><br>
![\* Введите пароль для закрытого ключа сертификата \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="86bd9-135">После импорта закрытого ключа продолжайте создавать пакет.</span><span class="sxs-lookup"><span data-stu-id="86bd9-135">After importing the private key, continue creating the package.</span></span><br>
![\* Продолжить создание пакета \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="86bd9-137">Выберите **Hub** и **Surface Hub 2S** в качестве целевого объекта для пакета конфигурации UEFI.</span><span class="sxs-lookup"><span data-stu-id="86bd9-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* Выберите HUB и Surface Hub 2S в качестве цели для пакета конфигурации UEFI \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="86bd9-139">Выберите компоненты и параметры, которые вы хотите активировать или отключить на Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="86bd9-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* Выберите компоненты и параметры, которые вы хотите активировать или деактивировать \*](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="86bd9-141">Для экспорта файла используйте параметр USB.</span><span class="sxs-lookup"><span data-stu-id="86bd9-141">Use the USB option to export the file.</span></span><br>
![\* С помощью опции USB экспортировать файл \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="86bd9-143">Вставьте и выберите USB-накопитель, который вы хотите использовать для этого пакета.</span><span class="sxs-lookup"><span data-stu-id="86bd9-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="86bd9-144">USB-накопитель будет отформатирован и вы потеряли все имеющиеся на нем данные.</span><span class="sxs-lookup"><span data-stu-id="86bd9-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* Вставьте и выберите USB-накопитель для вашего пакета \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="86bd9-146">После успешного создания пакета конфигуратор будет отображать последние два символа отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="86bd9-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="86bd9-147">Эти символы понадобятся при импорте в конфигурацию на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="86bd9-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* Успешное конфигурирование пакета \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="86bd9-149">Загрузка UEFI</span><span class="sxs-lookup"><span data-stu-id="86bd9-149">To boot into UEFI</span></span>

<span data-ttu-id="86bd9-150">Выключите Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="86bd9-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="86bd9-151">Нажмите и удерживайте кнопку " **Громкость** " и нажмите кнопку **Power** .</span><span class="sxs-lookup"><span data-stu-id="86bd9-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="86bd9-152">Продолжайте удерживать нажатой кнопку вверх, пока не появится меню UEFI.</span><span class="sxs-lookup"><span data-stu-id="86bd9-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>
