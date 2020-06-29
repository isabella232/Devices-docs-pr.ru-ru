---
title: Сброс и восстановление Surface Hub 2S
description: Сведения о том, как восстановить и сбросить Surface Hub 2S.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835315"
---
# <span data-ttu-id="4e66d-104">Сброс и восстановление Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4e66d-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="4e66d-105">Если у вас возникли проблемы с Surface Hub 2S, вы можете сбросить параметры устройства на заводские настройки или восстановить его с помощью USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="4e66d-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="4e66d-106">Чтобы начать, войдите в Surface Hub 2 с учетными данными администратора, откройте приложение **Параметры** , выберите **Обновить & безопасность**, а затем выберите **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="4e66d-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="4e66d-107">Сброс параметров устройства</span><span class="sxs-lookup"><span data-stu-id="4e66d-107">Reset the device</span></span>

1. <span data-ttu-id="4e66d-108">Чтобы сбросить устройство, нажмите кнопку **Начало работы**.</span><span class="sxs-lookup"><span data-stu-id="4e66d-108">To reset the device, select **Get Started**.</span></span>
2. <span data-ttu-id="4e66d-109">Когда появится окно " **Готово для сброса этого устройства** ", нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="4e66d-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
  >[!NOTE]
  ><span data-ttu-id="4e66d-110">Surface Hub 2. переустанавливает операционную систему из раздела восстановления.</span><span class="sxs-lookup"><span data-stu-id="4e66d-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="4e66d-111">Для завершения может потребоваться до одного часа.</span><span class="sxs-lookup"><span data-stu-id="4e66d-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="4e66d-112">Чтобы изменить конфигурацию устройства, запустите программу установки первого раза.</span><span class="sxs-lookup"><span data-stu-id="4e66d-112">To reconfigure the device, run the first-time Setup program.</span></span>
4. <span data-ttu-id="4e66d-113">Если вы управляете устройством с помощью Microsoft Intune или другого решения для управления мобильными устройствами, выйдите из нее и удалите предыдущую запись, а затем повторно зарегистрируйте новое устройство.</span><span class="sxs-lookup"><span data-stu-id="4e66d-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="4e66d-114">Дополнительные сведения можно найти в разделе [Удаление устройств с помощью очистки, снятия с учета и отмены регистрации устройства вручную](https://docs.microsoft.com/intune/devices-wipe).</span><span class="sxs-lookup"><span data-stu-id="4e66d-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

![\* Сброс и восстановление Surface Hub 2S \*](images/sh2-reset.png)<br>
*<span data-ttu-id="4e66d-116">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="4e66d-116">Figure 1.</span></span> <span data-ttu-id="4e66d-117">Сброс и восстановление Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4e66d-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="4e66d-118">Восстановление Surface Hub 2S с помощью диска восстановления USB</span><span class="sxs-lookup"><span data-stu-id="4e66d-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="4e66d-119">Новая возможность в Surface Hub 2. Теперь вы можете переустановить устройство с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="4e66d-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="4e66d-120">Восстановление с USB-накопителя</span><span class="sxs-lookup"><span data-stu-id="4e66d-120">Recovery from a USB drive</span></span>

<span data-ttu-id="4e66d-121">Используя Surface Hub 2S, вы можете переустановить устройство с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="4e66d-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="4e66d-122">Таким образом, вы можете переустановить устройство на заводские настройки, если вы потеряли ключ BitLocker, или если у вас больше нет учетных данных администратора для приложения "Параметры".</span><span class="sxs-lookup"><span data-stu-id="4e66d-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="4e66d-123">Используйте диск USB 3,0 с объемом памяти 8 ГБ или 16 ГБ в формате FAT32.</span><span class="sxs-lookup"><span data-stu-id="4e66d-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="4e66d-124">На отдельном компьютере Скачайте на [веб-сайт восстановления](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) и вернитесь к этим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="4e66d-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 
1. <span data-ttu-id="4e66d-125">Распакуйте скачанный файл в корневой каталог USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="4e66d-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  
1. <span data-ttu-id="4e66d-126">Подключите USB-накопитель к любому порту USB – C или USB-A на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="4e66d-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>
1. <span data-ttu-id="4e66d-127">Отключите устройство:</span><span class="sxs-lookup"><span data-stu-id="4e66d-127">Turn off the device:</span></span>
   1. <span data-ttu-id="4e66d-128">Удерживая нажатой кнопку "Громкость", нажмите кнопку Power.</span><span class="sxs-lookup"><span data-stu-id="4e66d-128">While holding down the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="4e66d-129">Продолжайте удерживать обе кнопки, пока не увидите логотип Windows.</span><span class="sxs-lookup"><span data-stu-id="4e66d-129">Keep holding both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="4e66d-130">Отпустите кнопку Power, но продолжайте хранить том, пока не начнется установка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4e66d-130">Release the Power button but continue to hold the Volume until the Install UI begins.</span></span>

    ![\* Начало восстановления с помощью кнопок "уменьшить громкость" и "включить" \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="4e66d-132">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="4e66d-132">Figure 2.</span></span> <span data-ttu-id="4e66d-133">Громкость и кнопки управления электропереключателем</span><span class="sxs-lookup"><span data-stu-id="4e66d-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="4e66d-134">На экране выбора языка выберите язык интерфейса для Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="4e66d-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>
1. <span data-ttu-id="4e66d-135">Выберите команду **восстановить с диска** и **полностью Очистите диск**, а затем нажмите кнопку **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="4e66d-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="4e66d-136">Если вам будет предложено ввести ключ BitLocker, выберите **пропустить этот диск**.</span><span class="sxs-lookup"><span data-stu-id="4e66d-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="4e66d-137">Surface Hub 2 перезагружаются несколько минут и займет около 30 мин, чтобы завершить процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="4e66d-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="4e66d-138">После появления экрана установки в первый раз удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="4e66d-138">When the first-time setup screen appears,remove the USB drive.</span></span>

## <span data-ttu-id="4e66d-139">Обратиться в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="4e66d-139">Contact Support</span></span>

<span data-ttu-id="4e66d-140">Если у вас возникли вопросы или вам нужна помощь, вы можете [создать запрос в службу поддержки](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="4e66d-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
