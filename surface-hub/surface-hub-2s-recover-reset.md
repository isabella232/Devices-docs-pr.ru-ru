---
title: Сброс и восстановление для Surface Hub 2S
description: Узнайте, как восстановить и сбросить Surface Hub 2S.
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
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304812"
---
# <span data-ttu-id="acb0d-104">Сброс и восстановление для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="acb0d-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="acb0d-105">Если у вас возникли проблемы с Surface Hub 2S, вы можете восстановить заводские настройки устройства или восстановить его с помощью USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="acb0d-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="acb0d-106">Для начала во sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="acb0d-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="acb0d-107">Сброс устройства</span><span class="sxs-lookup"><span data-stu-id="acb0d-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="acb0d-108">Убедитесь, что ключ BitLocker доступен перед сбросом устройства, так как он вам будет предложен позже.</span><span class="sxs-lookup"><span data-stu-id="acb0d-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="acb0d-109">Дополнительные узнать [см. в окнах "Сохранение ключа BitLocker".](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="acb0d-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="acb0d-110">Чтобы сбросить устройство, выберите **"Начало работы".**</span><span class="sxs-lookup"><span data-stu-id="acb0d-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="acb0d-111">Когда **появится окно "Готово к сбросу"** для этого устройства, выберите **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="acb0d-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="acb0d-112">Когда концентратор перезагружается в раздел восстановления, вам будет предложено ввести ключ BitLocker.</span><span class="sxs-lookup"><span data-stu-id="acb0d-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="acb0d-113">Пропуск этого запроса приведет к сбойу сброса.</span><span class="sxs-lookup"><span data-stu-id="acb0d-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="acb0d-114">После ввода ключа BitLocker концентратор переустановит операционную систему из раздела восстановления.</span><span class="sxs-lookup"><span data-stu-id="acb0d-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="acb0d-115">Это может занять до одного часа.</span><span class="sxs-lookup"><span data-stu-id="acb0d-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="acb0d-116">Чтобы перенастроить устройство, запустите первую программу установки.</span><span class="sxs-lookup"><span data-stu-id="acb0d-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="acb0d-117">Если вы управляете устройством с помощью Microsoft Intune или другого решения для управления мобильными устройствами, удалите и удалите предыдущую запись, а затем повторно зарегистрировать новое устройство.</span><span class="sxs-lookup"><span data-stu-id="acb0d-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="acb0d-118">Дополнительные сведения см. в руководстве "Удаление устройств с помощью [стирки",](https://docs.microsoft.com/intune/devices-wipe)"Удаление из эксплуатации" или ручное удаление устройства.</span><span class="sxs-lookup"><span data-stu-id="acb0d-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Reset and recovery for Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="acb0d-120">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="acb0d-120">Figure 1.</span></span> <span data-ttu-id="acb0d-121">Сброс и восстановление для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="acb0d-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="acb0d-122">Восстановление Surface Hub 2S с помощью USB-накопителя</span><span class="sxs-lookup"><span data-stu-id="acb0d-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="acb0d-123">Новые возможности Surface Hub 2S теперь можно переустановить с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="acb0d-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="acb0d-124">Восстановление с USB-накопителя</span><span class="sxs-lookup"><span data-stu-id="acb0d-124">Recovery from a USB drive</span></span>

<span data-ttu-id="acb0d-125">С помощью Surface Hub 2S можно переустановить устройство с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="acb0d-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="acb0d-126">Это позволяет переустановить устройство до заводских настроек, если вы потеряли ключ BitLocker или у вас больше нет учетных данных администратора в приложении "Параметры".</span><span class="sxs-lookup"><span data-stu-id="acb0d-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="acb0d-127">Используйте usb-накопитель 3.0 с 8 ГБ или 16 ГБ памяти в формате FAT32.</span><span class="sxs-lookup"><span data-stu-id="acb0d-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="acb0d-128">На отдельном компьютере скачайте zip-файл для восстановления с веб-сайта [Surface Recovery,](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) а затем вернись к этим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="acb0d-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="acb0d-129">Разорвите загруженный файл в корневой папке USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="acb0d-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="acb0d-130">Подключите USB-накопитель к любому порту USB-C или USB-A на Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="acb0d-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="acb0d-131">Отключите устройство:</span><span class="sxs-lookup"><span data-stu-id="acb0d-131">Turn off the device:</span></span>

   1. <span data-ttu-id="acb0d-132">Нажав кнопку "Громкость вниз", нажмите кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="acb0d-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="acb0d-133">Продолжайте нажимать обе кнопки, пока не увидите логотип Windows.</span><span class="sxs-lookup"><span data-stu-id="acb0d-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="acb0d-134">Отпустите кнопку питания, но продолжайте удерживать кнопку "Громкость вниз", пока не начнется пользовательский интерфейс установки.</span><span class="sxs-lookup"><span data-stu-id="acb0d-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Use Volume down and power buttons to initiate recovery*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="acb0d-136">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="acb0d-136">Figure 2.</span></span> <span data-ttu-id="acb0d-137">Кнопки громкости и питания</span><span class="sxs-lookup"><span data-stu-id="acb0d-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="acb0d-138">На экране выбора языка выберите язык отображения для Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="acb0d-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="acb0d-139">Выберите **"Восстановить с диска"** и **"Полностью**очистить диск", а затем выберите **"Восстановить".**</span><span class="sxs-lookup"><span data-stu-id="acb0d-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="acb0d-140">Если вам будет предложено вводить ключ BitLocker, выберите **"Пропустить этот диск".**</span><span class="sxs-lookup"><span data-stu-id="acb0d-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="acb0d-141">Surface Hub 2S перезагружается несколько раз и занимает около 30 минут для завершения процесса восстановления.</span><span class="sxs-lookup"><span data-stu-id="acb0d-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="acb0d-142">Когда появится первый экран установки, удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="acb0d-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="acb0d-143">обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="acb0d-143">Contact Support</span></span>

<span data-ttu-id="acb0d-144">Если у вас возникли вопросы или вам нужна помощь, вы можете [создать запрос в службу поддержки.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="acb0d-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
