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
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836895"
---
# <span data-ttu-id="e5ab6-104">Использование средства восстановления Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e5ab6-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="e5ab6-105">[Средство восстановления Surface Hub (Майкрософт](https://www.microsoft.com/download/details.aspx?id=52210) ) помогает воссоздать образ твердотельного накопителя (SSD) Surface Hub с помощью настольного устройства с Windows 10 без вызова поддержки или замены твердотельного накопителя.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="e5ab6-106">С помощью этого инструмента можно переобразировать твердотельный SSD с неизвестным паролем администратора, ошибки загрузки, не удалось завершить восстановление облака или на устройство с более ранней версией операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="e5ab6-107">Средство не будет исправлено физически поврежденных твердотельных накопителей.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="e5ab6-108">Для повторного создания образа Surface Hub с помощью средства восстановления необходимо удалить SSD из Surface Hub, подключить диск к кабелю USB-to-SATA и подключить кабель к классическому компьютеру, на котором установлено средство восстановления.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="e5ab6-109">Дополнительные сведения о том, как удалить существующий диск из Surface Hub, можно найти в разделе [Замена SSD Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="e5ab6-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5ab6-110">Не разрешать устройству переходить в режим сна или прерывать загрузку файла изображения.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="e5ab6-111">Если средство не удается выполнить в reimaging диска, обратитесь в [службу поддержки Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="e5ab6-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="e5ab6-112">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="e5ab6-112">Prerequisites</span></span>

### <span data-ttu-id="e5ab6-113">Обязательное</span><span class="sxs-lookup"><span data-stu-id="e5ab6-113">Mandatory</span></span>

- <span data-ttu-id="e5ab6-114">Host PC с 64-разрядной версией Windows 10, версией 1607 или более новой.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="e5ab6-115">Доступ к Интернету</span><span class="sxs-lookup"><span data-stu-id="e5ab6-115">Internet access</span></span>
- <span data-ttu-id="e5ab6-116">Открыть порт USB 2,0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e5ab6-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="e5ab6-117">Кабель с ИНТЕРФЕЙСом SATA</span><span class="sxs-lookup"><span data-stu-id="e5ab6-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="e5ab6-118">10 ГБ свободного места на главном компьютере</span><span class="sxs-lookup"><span data-stu-id="e5ab6-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="e5ab6-119">Службы SSDs поставляются с Surface HUB или твердотельным накопителем, предоставленным поддержкой в качестве замены.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="e5ab6-120">SSDs, не предоставленные корпорацией Майкрософт, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="e5ab6-121">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="e5ab6-121">Recommended</span></span>

- <span data-ttu-id="e5ab6-122">Высокоскоростное подключение к Интернету</span><span class="sxs-lookup"><span data-stu-id="e5ab6-122">High-speed Internet connection</span></span>
- <span data-ttu-id="e5ab6-123">Открыть порт USB 3,0</span><span class="sxs-lookup"><span data-stu-id="e5ab6-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="e5ab6-124">Кабель USB-SATA 3,0 или выше</span><span class="sxs-lookup"><span data-stu-id="e5ab6-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="e5ab6-125">Средство обработки изображений было протестировано со следующими моделями и кабелями:</span><span class="sxs-lookup"><span data-stu-id="e5ab6-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="e5ab6-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="e5ab6-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="e5ab6-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="e5ab6-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="e5ab6-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="e5ab6-128">Ugreen 20231</span></span>

## <span data-ttu-id="e5ab6-129">Скачать средство восстановления Surface HUB</span><span class="sxs-lookup"><span data-stu-id="e5ab6-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="e5ab6-130">Средство восстановления Surface Hub доступно для загрузки из [средств Surface Hub для него](https://www.microsoft.com/download/details.aspx?id=52210) под **SurfaceHub_Recovery_v1.14.137.0.msi**именем файла.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="e5ab6-131">Чтобы начать загрузку, нажмите кнопку **скачать**, выберите в списке пункт **SurfaceHub_Recovery_v1.14.137.0.msi** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="e5ab6-132">В раскрывающемся меню выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e5ab6-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="e5ab6-133">Нажмите кнопку **выполнить** , чтобы начать установку немедленно.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="e5ab6-134">Нажмите кнопку **сохранить** , чтобы скопировать файл на компьютер для дальнейшей установки.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="e5ab6-135">Установите средство восстановления Surface Hub на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="e5ab6-136">Запустите средство восстановления Surface HUB</span><span class="sxs-lookup"><span data-stu-id="e5ab6-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="e5ab6-137">На главном компьютере нажмите кнопку **Пуск** , прокрутите список в алфавитном порядке слева и выберите ярлык средства восстановления.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Ярлык средства восстановления Surface Hub (Майкрософт)](images/shrt-shortcut.png)

2. <span data-ttu-id="e5ab6-139">Нажмите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-139">Click **Start**.</span></span>

    ![Кнопка "Пуск" средства восстановления](images/shrt-start.png)

3. <span data-ttu-id="e5ab6-141">В окне **руководства** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-141">In the **Guidance** window, click **Next**.</span></span>

    ![Не разрешать компьютеру переходить в руководство по спящему режиму](images/shrt-guidance.png)

4. <span data-ttu-id="e5ab6-143">Нажмите кнопку **Да** , чтобы скачать изображение.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-143">click **Yes** to download the image.</span></span> <span data-ttu-id="e5ab6-144">Время загрузить образ восстановления зависит от скорости соединения с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="e5ab6-145">В среднем корпоративном подключении может потребоваться до часа, чтобы скачать файл изображения в 8 ГБ.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Загрузить изображение?](images/shrt-download.png)

5. <span data-ttu-id="e5ab6-147">После завершения загрузки средство предписывает вам подключить ТВЕРДОТЕЛЬный диск.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="e5ab6-148">Если средство не может найти подключенный диск, возможно, что используемый кабель не сообщает имя SSD с Windows.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="e5ab6-149">Для продолжения работы с образами необходимо найти имя диска как "LITEON L CH-128V2S USB".</span><span class="sxs-lookup"><span data-stu-id="e5ab6-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="e5ab6-150">Дополнительные сведения о том, как удалить существующий диск из Surface Hub, можно найти в разделе [Замена SSD Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="e5ab6-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Подключить твердотельный SSD](images/shrt-drive.png)

6. <span data-ttu-id="e5ab6-152">После распознавания диска нажмите кнопку **начать** , чтобы начать процесс создания образа.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="e5ab6-153">При появлении предупреждения о том, что все данные на диске будут удалены, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![Запуск повторной очистки для SSD](images/shrt-drive-start.png)

    <span data-ttu-id="e5ab6-155">Прежде чем приступать к применению образа системы к диску, SSD будет заново разбиваться на разделы и отформатированы.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="e5ab6-156">Копирование двоичных файлов системы займет около 30 минут, но может занять больше времени, в зависимости от скорости шины USB, используемого кабеля или антивирусной программы, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![Копирование завершено](images/shrt-done.png)

    ![Reimaging выполнена](images/shrt-complete.png)

## <span data-ttu-id="e5ab6-159">Устранение неполадок и распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="e5ab6-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="e5ab6-160">Проблема</span><span class="sxs-lookup"><span data-stu-id="e5ab6-160">Issue</span></span> | <span data-ttu-id="e5ab6-161">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5ab6-161">Notes</span></span>
--- | ---
<span data-ttu-id="e5ab6-162">Средство не может выобразировать SSD</span><span class="sxs-lookup"><span data-stu-id="e5ab6-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="e5ab6-163">Убедитесь в том, что вы используете Заводский комплект и один из протестированных кабелей.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="e5ab6-164">Процесс reimaging остановлен или заморожен</span><span class="sxs-lookup"><span data-stu-id="e5ab6-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="e5ab6-165">Вы можете безопасно закрыть и перезапустить средство восстановления Surface Hub без некорректного воздействия на SSD.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="e5ab6-166">Этот диск не распознается средством</span><span class="sxs-lookup"><span data-stu-id="e5ab6-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="e5ab6-167">Убедитесь, что SSD Surface Hub перечислены как облегченные диски, "LITEON L CH-128V2S USB".</span><span class="sxs-lookup"><span data-stu-id="e5ab6-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="e5ab6-168">Если диск распознается как другое именованное Устройство, ваш текущий кабель не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="e5ab6-169">Попробуйте другой кабель или один из перечисленных выше кабелей.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="e5ab6-170">Ошибка:-2147024809</span><span class="sxs-lookup"><span data-stu-id="e5ab6-170">Error: -2147024809</span></span> | <span data-ttu-id="e5ab6-171">Откройте диспетчер дисков и удалите разделы на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="e5ab6-172">Отключите и заново подключите диск к ведущему компьютеру.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="e5ab6-173">Снова запустите средство Imaging.</span><span class="sxs-lookup"><span data-stu-id="e5ab6-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="e5ab6-174">Если средство не удается выполнить в reimaging диска, обратитесь в [службу поддержки Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="e5ab6-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>
