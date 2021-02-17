---
title: Использование средства восстановления Surface Hub
description: Использование средства восстановления Surface Hub для повторного создания образа SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: управление Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339370"
---
# <span data-ttu-id="6ef2f-104">Использование средства восстановления Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6ef2f-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="6ef2f-105">Средство [восстановления Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) помогает вам повторно сделать образ твердого накопителя Surface Hub (SSD) с помощью настольного устройства с Windows 10, не вызывая поддержку и не заменяя SSD.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="6ef2f-106">С помощью этого средства можно повторно издать SSD с неизвестным паролем администратора, ошибками загрузки, которые не удалось выполнить облачное восстановление, или для устройства с более старой версией операционной системы.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="6ef2f-107">Средство не исправит физически поврежденные SSD.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="6ef2f-108">Для повторного создания образа SSD Surface Hub с помощью средства восстановления необходимо удалить SSD с Surface Hub, подключить диск к кабелю USB-SATA, а затем подключить кабель к настольному компьютеру, на котором установлено средство восстановления.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="6ef2f-109">Дополнительные сведения о том, как удалить существующий диск с Surface Hub, см. в подмене [SSD Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef2f-110">Не позволяйте устройству переходить в спящий режим или прерывать загрузку файла изображения.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="6ef2f-111">Если средству не удалось повторно сконструировать диск, обратитесь в службу поддержки [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="6ef2f-112">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="6ef2f-112">Prerequisites</span></span>

### <span data-ttu-id="6ef2f-113">Обязательное</span><span class="sxs-lookup"><span data-stu-id="6ef2f-113">Mandatory</span></span>

- <span data-ttu-id="6ef2f-114">Хост-компьютер под управлением 64-битной версии Windows 10 версии 1607 или выше.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="6ef2f-115">Доступ к Интернету</span><span class="sxs-lookup"><span data-stu-id="6ef2f-115">Internet access</span></span>
- <span data-ttu-id="6ef2f-116">Открытие USB-порта 2.0 или более большого порта</span><span class="sxs-lookup"><span data-stu-id="6ef2f-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="6ef2f-117">Кабель USB-SATA</span><span class="sxs-lookup"><span data-stu-id="6ef2f-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="6ef2f-118">10 ГБ свободного места на хост-компьютере</span><span class="sxs-lookup"><span data-stu-id="6ef2f-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="6ef2f-119">SSD поставляются с Surface Hub или SSD, предоставляемыми службой поддержки в качестве замены.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="6ef2f-120">SSD, не предоставленные корпорацией Майкрософт, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="6ef2f-121">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="6ef2f-121">Recommended</span></span>

- <span data-ttu-id="6ef2f-122">Высокоскоростное подключение к Интернету</span><span class="sxs-lookup"><span data-stu-id="6ef2f-122">High-speed Internet connection</span></span>
- <span data-ttu-id="6ef2f-123">Открытие порта USB 3.0</span><span class="sxs-lookup"><span data-stu-id="6ef2f-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="6ef2f-124">Кабель USB 3.0 или более высокого уровня с USB-SATA</span><span class="sxs-lookup"><span data-stu-id="6ef2f-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="6ef2f-125">Средство создания образа было протестировано с помощью следующей модели кабелей:</span><span class="sxs-lookup"><span data-stu-id="6ef2f-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="6ef2f-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="6ef2f-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="6ef2f-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="6ef2f-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="6ef2f-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="6ef2f-128">Ugreen 20231</span></span>

## <span data-ttu-id="6ef2f-129">Скачивание средства восстановления Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6ef2f-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="6ef2f-130">Средство восстановления Surface Hub доступно для скачивания из средств \*\* \*\*Surface Hub для [ИТ-SurfaceHub_Recovery_v2.7.139.0.msi.](https://www.microsoft.com/download/details.aspx?id=52210)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.7.139.0.msi**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef2f-131">Эта версия, выпущенная 11 февраля 2021 г., заменяет более ранную сборку, которая больше не работает.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-131">This version, released Feb 11, 2021, replaces the earlier build, which is no longer functional.</span></span> <span data-ttu-id="6ef2f-132">Если вы скачали это средство ранее, пожалуйста, вы можете удалить его и установить текущую версию.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-132">If you downloaded this tool previously, please uninstall it and install the current version.</span></span>

<span data-ttu-id="6ef2f-133">Чтобы начать скачивание, нажмите кнопку "Скачать", **выберитеSurfaceHub_Recovery_v2.7.139.0.msi** списка и нажмите кнопку \*\*\*\* **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="6ef2f-133">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.7.139.0.msi**  from the list, and click **Next**.</span></span> <span data-ttu-id="6ef2f-134">Во всплываемом окнах выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="6ef2f-134">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="6ef2f-135">Нажмите **кнопку** "Выполнить", чтобы немедленно начать установку.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-135">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="6ef2f-136">Нажмите **кнопку** "Сохранить", чтобы скопировать загрузку на компьютер для более поздней установки.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-136">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="6ef2f-137">Установите средство восстановления Surface Hub на компьютере узла.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-137">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="6ef2f-138">Запуск средства восстановления Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6ef2f-138">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="6ef2f-139">На хост-компьютере выберите **кнопку** "Начните", прокрутите алфавитный список слева и выберите ярлык средства восстановления.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-139">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Ярлык средства восстановления Microsoft Surface Hub](images/shrt-shortcut.png)

2. <span data-ttu-id="6ef2f-141">Нажмите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-141">Click **Start**.</span></span>

    ![Кнопка запуска средства восстановления](images/shrt-start.png)


3. <span data-ttu-id="6ef2f-143">В **окне "Руководство"** нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="6ef2f-143">In the **Guidance** window, click **Next**.</span></span>

    ![Не разрешите компьютеру переходить в спящий режим](images/shrt-guidance.png)

4. <span data-ttu-id="6ef2f-145">В окне "Выбор изображения" щелкните **RS2** или его преемницу **20H2,** выберите "Продолжить", а затем выберите "Загрузить **изображение".** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6ef2f-145">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="6ef2f-146">![Изображение скачивания средства восстановления "Выбор ](images/shrt-select-image.png) ![ образа"](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-146">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="6ef2f-147">Время загрузки образа восстановления зависит от скорости подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-147">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="6ef2f-148">Для среднего корпоративного подключения загрузка файла изображения размером 8 ГБ может занять до часа.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-148">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Скачивание изображения](images/shrt-download.png)



5. <span data-ttu-id="6ef2f-150">По завершению скачивания средство дает указание подключить диск SSD.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-150">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="6ef2f-151">Если средству не удается найти подключенный диск, существует вероятность того, что используемый кабель не сообщает windows имя SSD.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-151">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="6ef2f-152">Прежде чем продолжить, средство обработки изображений должно найти имя диска как "USB-устройство LITEON L CH-128V2S".</span><span class="sxs-lookup"><span data-stu-id="6ef2f-152">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="6ef2f-153">Дополнительные сведения о том, как удалить существующий диск с Surface Hub, см. в подмене [SSD Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-153">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Подключение SSD](images/shrt-drive.png)

6. <span data-ttu-id="6ef2f-155">Когда диск распознается, нажмите **кнопку "Начните",** чтобы начать процесс повторного создания образа.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-155">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="6ef2f-156">При предупреждении о том, что все данные на диске будут стираться, нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="6ef2f-156">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="6ef2f-157">Перед тем как применить системный образ к диску, SSD разделяется и форматирован.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-157">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="6ef2f-158">Копирование системных двухфайлов займет приблизительно 30 минут, но может занять больше времени в зависимости от скорости USB-шины, используемого кабеля или антивирусного программного обеспечения, установленного в системе.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-158">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="6ef2f-159">Устранение неполадок и распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="6ef2f-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="6ef2f-160">Проблема</span><span class="sxs-lookup"><span data-stu-id="6ef2f-160">Issue</span></span> | <span data-ttu-id="6ef2f-161">Заметки</span><span class="sxs-lookup"><span data-stu-id="6ef2f-161">Notes</span></span>
--- | ---
<span data-ttu-id="6ef2f-162">Средству не удается образ sSD</span><span class="sxs-lookup"><span data-stu-id="6ef2f-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="6ef2f-163">Убедитесь, что вы используете поставляемую по заводу SSD и один из протестных кабелей.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="6ef2f-164">Процесс переостановки выглядит остановленным или заблокированным</span><span class="sxs-lookup"><span data-stu-id="6ef2f-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="6ef2f-165">Можно закрыть и перезапустить средство восстановления Surface Hub, не влияя на SSD.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="6ef2f-166">Средство не распознает диск</span><span class="sxs-lookup"><span data-stu-id="6ef2f-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="6ef2f-167">Убедитесь, что SSD Surface Hub является Lite-On USB-устройством LITEON L CH-128V2S.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="6ef2f-168">Если диск распознается как другое именовающее устройство, текущий кабель несовместим.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="6ef2f-169">Попробуйте другой кабель или один из протестных кабеля, перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="6ef2f-170">Ошибка: -2147024809</span><span class="sxs-lookup"><span data-stu-id="6ef2f-170">Error: -2147024809</span></span> | <span data-ttu-id="6ef2f-171">Откройте диспетчер дисков и удалите разделы на диске Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="6ef2f-172">Отсоедините диск и подключим его к хост-компьютеру.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="6ef2f-173">Перезапустите средство создания образа еще раз.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="6ef2f-174">Если средству не удалось повторно сконструировать диск, обратитесь в службу поддержки [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="6ef2f-175">История версий</span><span class="sxs-lookup"><span data-stu-id="6ef2f-175">Version history</span></span>


### <span data-ttu-id="6ef2f-176">Версия 2.7.139.0</span><span class="sxs-lookup"><span data-stu-id="6ef2f-176">Version v2.7.139.0</span></span>

*<span data-ttu-id="6ef2f-177">Дата выпуска: 11 февраля 2021 г.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-177">Release date: February 11, 2021</span></span>*<br>
<span data-ttu-id="6ef2f-178">В этой версии средства восстановления Surface Hub добавлена поддержка следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="6ef2f-178">This version of Surface Hub Recovery Tool adds support for the following:</span></span>

- <span data-ttu-id="6ef2f-179">Обновление безопасности</span><span class="sxs-lookup"><span data-stu-id="6ef2f-179">Security update</span></span>


### <span data-ttu-id="6ef2f-180">Версия 2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="6ef2f-180">Version v2.0.139.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef2f-181">Эта версия больше не работает.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-181">This version is no longer functional.</span></span> <span data-ttu-id="6ef2f-182">Скачайте текущую версию, указанную выше.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-182">Please download the current version, listed above.</span></span> 

*<span data-ttu-id="6ef2f-183">Дата выпуска: 18 декабря 2020 г.</span><span class="sxs-lookup"><span data-stu-id="6ef2f-183">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="6ef2f-184">В этой версии средства восстановления Surface Hub добавлена поддержка следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="6ef2f-184">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="6ef2f-185">Обновление для поддержки Обновления Windows 10 для группы 2020 (20H2)</span><span class="sxs-lookup"><span data-stu-id="6ef2f-185">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="6ef2f-186">Улучшения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6ef2f-186">User experience improvements</span></span>
- <span data-ttu-id="6ef2f-187">Архитектурные изменения</span><span class="sxs-lookup"><span data-stu-id="6ef2f-187">Architectural changes</span></span>
- <span data-ttu-id="6ef2f-188">Добавления телеметрии</span><span class="sxs-lookup"><span data-stu-id="6ef2f-188">Telemetry additions</span></span>

