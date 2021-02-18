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
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342979"
---
# <span data-ttu-id="5dd25-104">Сброс и восстановление для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="5dd25-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="5dd25-105">Если у вас возникли проблемы с Surface Hub 2S, вы можете восстановить заводские настройки устройства или восстановить его с помощью USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="5dd25-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="5dd25-106">Для начала во sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="5dd25-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="5dd25-107">Сброс устройства</span><span class="sxs-lookup"><span data-stu-id="5dd25-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5dd25-108">Убедитесь, что ключ BitLocker доступен перед сбросом устройства, так как он вам будет предложен позже.</span><span class="sxs-lookup"><span data-stu-id="5dd25-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="5dd25-109">Дополнительные узнать [см. в окнах "Сохранение ключа BitLocker".](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="5dd25-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="5dd25-110">Чтобы сбросить устройство, выберите **"Начало работы".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="5dd25-111">Когда **появится окно "Готово к сбросу"** для этого устройства, выберите **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="5dd25-112">Когда концентратор перезагружается в раздел восстановления, вам будет предложено ввести ключ BitLocker.</span><span class="sxs-lookup"><span data-stu-id="5dd25-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="5dd25-113">Пропуск этого запроса приведет к сбойу сброса.</span><span class="sxs-lookup"><span data-stu-id="5dd25-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="5dd25-114">После ввода ключа BitLocker концентратор переустановит операционную систему из раздела восстановления.</span><span class="sxs-lookup"><span data-stu-id="5dd25-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="5dd25-115">Это может занять до одного часа.</span><span class="sxs-lookup"><span data-stu-id="5dd25-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="5dd25-116">Чтобы перенастроить устройство, запустите первую программу установки.</span><span class="sxs-lookup"><span data-stu-id="5dd25-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="5dd25-117">Если вы управляете устройством с помощью Microsoft Intune или другого решения для управления мобильными устройствами, удалите и удалите предыдущую запись, а затем повторно зарегистрировать новое устройство.</span><span class="sxs-lookup"><span data-stu-id="5dd25-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="5dd25-118">Дополнительные сведения см. в руководстве "Удаление устройств с помощью [стирки",](https://docs.microsoft.com/intune/devices-wipe)"Удаление" или "Ручная открепка устройства".</span><span class="sxs-lookup"><span data-stu-id="5dd25-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Reset and recovery for Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="5dd25-120">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="5dd25-120">Figure 1.</span></span> <span data-ttu-id="5dd25-121">Сброс и восстановление для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="5dd25-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="5dd25-122">Восстановление Surface Hub 2S с помощью USB-накопителя</span><span class="sxs-lookup"><span data-stu-id="5dd25-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="5dd25-123">Новые возможности Surface Hub 2S теперь можно переустановить с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="5dd25-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="5dd25-124">Восстановление с USB-накопителя</span><span class="sxs-lookup"><span data-stu-id="5dd25-124">Recovery from a USB drive</span></span>

<span data-ttu-id="5dd25-125">С помощью Surface Hub 2S можно переустановить устройство с помощью образа восстановления.</span><span class="sxs-lookup"><span data-stu-id="5dd25-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="5dd25-126">Это позволяет переустановить устройство до заводских настроек, если вы потеряли ключ BitLocker или у вас больше нет учетных данных администратора в приложении "Параметры".</span><span class="sxs-lookup"><span data-stu-id="5dd25-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="5dd25-127">Используйте usb-накопитель 3.0 с 8 ГБ или 16 ГБ памяти в формате FAT32.</span><span class="sxs-lookup"><span data-stu-id="5dd25-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="5dd25-128">На отдельном компьютере скачайте zip-файл для восстановления с веб-сайта [Surface Recovery,](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) а затем вернись к этим инструкциям.</span><span class="sxs-lookup"><span data-stu-id="5dd25-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="5dd25-129">В поле поиска на панели задач введите диск **восстановления,** а затем выберите **"Создать** диск восстановления" или "Диск **восстановления"** в результатах.</span><span class="sxs-lookup"><span data-stu-id="5dd25-129">In the search box on the taskbar, enter **recovery drive**, and then select **Create a recovery drive** or **Recovery Drive** from the results.</span></span> <span data-ttu-id="5dd25-130">Вам может потребоваться ввести пароль администратора или подтвердить свой выбор.</span><span class="sxs-lookup"><span data-stu-id="5dd25-130">You may need to enter an admin password or confirm your choice.</span></span>

1. <span data-ttu-id="5dd25-131">В поле **"Контроль учетных записей" выберите** **"Да".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-131">In the **User Account Control** box, select **Yes**.</span></span>

1. <span data-ttu-id="5dd25-132">Убедитесь, что **системные** файлы для архивации были восстановлены, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-132">Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.</span></span>

1. <span data-ttu-id="5dd25-133">Выберите USB-накопитель, а затем выберите **"> создать".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-133">Select your USB drive, and then select **Next > Create**.</span></span>  <span data-ttu-id="5dd25-134">Некоторые utilities необходимо скопировать на диск восстановления, поэтому это может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5dd25-134">Some utilities need to be copied to the recovery drive, so this might take a few minutes.</span></span>

1. <span data-ttu-id="5dd25-135">Когда диск восстановления будет готов, выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-135">When the recovery drive is ready, select **Finish**.</span></span>

1. <span data-ttu-id="5dd25-136">Дважды щелкните ZIP-файл образа восстановления, который вы ранее скачали, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="5dd25-136">Double-click the recovery image .zip file that you previously downloaded to open it.</span></span>

1. <span data-ttu-id="5dd25-137">Выберите все файлы из папки образа восстановления, скопируйте их в корневой файл USB-накопителя, а затем выберите "Заменить файлы в месте **назначения".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-137">Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.</span></span>

1. <span data-ttu-id="5dd25-138">После завершения копирования файлов выберите \*\*\*\* значок "Безопасно удалить оборудование и извлечение мультимедиа" на панели задач и удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="5dd25-138">Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar, and remove your USB drive.</span></span>

1. <span data-ttu-id="5dd25-139">Подключите USB-накопитель к любому порту USB-C или USB-A на Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="5dd25-139">Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S.</span></span>

1. <span data-ttu-id="5dd25-140">Отключите концентратор и затем с помощью указанных далее действий загрузите его с USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="5dd25-140">Turn off the Hub and then take these steps to boot from the USB drive:</span></span>

   1. <span data-ttu-id="5dd25-141">Нажав кнопку "Громкость вниз", нажмите кнопку питания.</span><span class="sxs-lookup"><span data-stu-id="5dd25-141">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="5dd25-142">Продолжайте нажимать обе кнопки, пока не увидите логотип Windows.</span><span class="sxs-lookup"><span data-stu-id="5dd25-142">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="5dd25-143">Отпустите кнопку питания, но продолжайте удерживать кнопку "Громкость вниз", пока не начнется пользовательский интерфейс установки.</span><span class="sxs-lookup"><span data-stu-id="5dd25-143">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Use Volume down and power buttons to initiate recovery*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="5dd25-145">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="5dd25-145">Figure 2.</span></span> <span data-ttu-id="5dd25-146">Кнопки громкости и питания</span><span class="sxs-lookup"><span data-stu-id="5dd25-146">Volume and Power buttons</span></span>*

1. <span data-ttu-id="5dd25-147">На экране выбора языка выберите язык отображения для Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="5dd25-147">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="5dd25-148">Выберите **"Восстановить с диска"** и **"Полностью**очистить диск", а затем выберите **"Восстановить".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-148">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="5dd25-149">Если вам будет предложено вводить ключ BitLocker, выберите **"Пропустить этот диск".**</span><span class="sxs-lookup"><span data-stu-id="5dd25-149">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="5dd25-150">Surface Hub 2S перезагружается несколько раз и занимает около 30 минут для завершения процесса восстановления.</span><span class="sxs-lookup"><span data-stu-id="5dd25-150">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="5dd25-151">После первого экрана установки удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="5dd25-151">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="5dd25-152">обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="5dd25-152">Contact Support</span></span>

<span data-ttu-id="5dd25-153">Если у вас возникли вопросы или вам нужна помощь, вы можете [создать запрос в службу поддержки.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="5dd25-153">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
