---
title: Настройка Windows 10 Pro или Корпоративная на Surface Hub 2
description: В этой статье приводятся рекомендации по обеспечению оптимальной работы при использовании персональных экранных касаний и компьютеров с перьевым интерфейсом.
keywords: Surface Hub, Windows 10, классическое приложение, установка, Настройка
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 10/21/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 25705f889f70e3d12dfef690c34e03d98254725e
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133184"
---
# <span data-ttu-id="ba6a5-104">Настройка Windows 10 Pro или Корпоративная на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="ba6a5-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="ba6a5-105">После того как вы завершите процесс установки на Windows 10 Pro или Enterprise, вы можете выполнить указанные ниже действия, чтобы настроить приложения и параметры на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="ba6a5-106">Эти действия рекомендуются для обеспечения оптимальной работы при использовании такого персонального сенсорного экрана и компьютера с перьевым интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="ba6a5-107">При выполнении этих действий может оказаться полезным использование проводной или беспроводной клавиатуры и мыши.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="ba6a5-108">Настройка параметров системы</span><span class="sxs-lookup"><span data-stu-id="ba6a5-108">Configure system settings</span></span>

1. <span data-ttu-id="ba6a5-109">Войдите в систему с помощью учетной записи, обладающей правами локального администратора на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="ba6a5-110">На устройствах, подключенных к Azure AD, пользователь, выполняющий присоединение к Azure AD, автоматически добавляется в локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="ba6a5-111">Глобальные администраторы Azure Active Directory и Администраторы устройств Azure Active Directory [также являются локальными администраторами](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    
    - <span data-ttu-id="ba6a5-112">Чтобы получить список учетных записей с правами локального администратора, введите в командной строке команду **net localgroup Administrators** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="ba6a5-113">Переименуйте устройство, используя понятное имя, например: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="ba6a5-114">Выберите **Start**  >  **Параметры**запуска  >  **учетные записи**  >  **синхронизируйте параметры** и отключите **Параметры синхронизации** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="ba6a5-115">Используемые здесь параметры предназначены для обеспечения наилучшего сенсорного ввода, поэтому вам может потребоваться синхронизация других устройств.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="ba6a5-116">Перезагрузите устройство.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-116">Reboot the device.</span></span>

## <span data-ttu-id="ba6a5-117">Включение сенсорной клавиатуры и сенсорной панели</span><span class="sxs-lookup"><span data-stu-id="ba6a5-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="ba6a5-118">Нажмите и удерживайте или щелкните правой кнопкой мыши панель задач и выберите пункт **Показать сенсорную клавиатуру** и **Показать кнопку сенсорной панели**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="ba6a5-119">Сенсорная клавиатура удобна для ввода данных пользователем, а виртуальная сенсорная панель — для точного выбора, наведения всплывающих подсказок или в качестве альтернативы нажатию и удержанию щелчка правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="ba6a5-120">См. следующий пример.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-120">See the following example.</span></span>

      ![Параметры сенсорного ввода](images/touch.png)

2. <span data-ttu-id="ba6a5-122">Настройте сенсорную клавиатуру на QWERTY и плавающую.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="ba6a5-123">Щелкните значок **клавиатуры** на панели задач, чтобы показать сенсорную клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="ba6a5-124">На сенсорной клавиатуре щелкните значок клавиатуры в левом верхнем углу, чтобы открыть меню Параметры клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="ba6a5-125">Выберите в верхней строке рядом с параметром последний тип клавиатуры, чтобы включить функцию QWERTY, а последний вариант во второй строке — для включения режима с плавающей точкой, что очень полезно для этого большого экрана.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="ba6a5-126">См. следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-126">See the following examples.</span></span>

      ![Параметры клавиатуры](images/kbd.png)
 
3. <span data-ttu-id="ba6a5-128">Настройка параметров экранной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-128">Configure the soft keyboard settings.</span></span>


    1. <span data-ttu-id="ba6a5-129">Щелкните значок " **Параметры** " на сенсорной клавиатуре или найдите и откройте **Параметры ввода**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![Параметры экранной клавиатуры](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="ba6a5-131">Включите все параметры в разделе Орфография, ввод и сенсорная клавиатура.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="ba6a5-132">В следующем примере показан элемент сенсорной панели, который полезен для навигации и выбора параметров.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="ba6a5-133">Экранная клавиатура используется для поиска в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Использование сенсорной панели](images/store.png)

## <span data-ttu-id="ba6a5-135">Настройка клавиатуры и мыши Bluetooth (опционально)</span><span class="sxs-lookup"><span data-stu-id="ba6a5-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="ba6a5-136">Подключите клавиатуру и мышь, если вы используете устройство в качестве основного устройства Windows, или часто используете его для ввода или точности.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="ba6a5-137">Если устройство Surface Hub находится рядом с компьютером, вы можете использовать [мышь без границ](https://aka.ms/mm) для эффективного перемещения между Surface HUB и компьютером.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="ba6a5-138">Дополнительные сведения можно найти в [статье Загрузка Microsoft из области "некоторая мышь без границ](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/)".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="ba6a5-139">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ba6a5-139">OneDrive for Business</span></span>

<span data-ttu-id="ba6a5-140">С помощью [OneDrive для бизнеса](https://docs.microsoft.com/onedrive/onedrive) можно легко предоставлять общий доступ к средствам, журналам и другим файлам между всеми рабочими устройствами.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="ba6a5-141">OneDrive предоставляет доступ к рабочим файлам между ноутбуками, рабочим столом Surface HUB и мобильными устройствами, управляемыми с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="ba6a5-142">Файлы можно редактировать на любом устройстве, при этом все подключенные к ним устройства будут обновлены с учетом изменений.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="ba6a5-143">Учитывая размер SSD Surface Hub (128 ГБ), если вы настроили OneDrive на настольном устройстве Surface Hub, убедитесь, что в качестве конфигурации по умолчанию сохраняются файлы в Интернете и они загружаются по мере использования.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="ba6a5-144">Чтобы настроить OneDrive для загрузки файлов только при необходимости, установите параметр " **файлы по запросу** ", чтобы **сэкономить место и загрузить файлы по мере их использования**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="ba6a5-145">Дополнительные сведения можно найти [в разделе запросы и Настройка состояний файлов по запросу в Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Параметры OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="ba6a5-147">Вы также можете повторить эти действия, чтобы настроить личное хранилище OneDrive, но не забудьте сэкономить место на диске и загружать только нужные файлы.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="ba6a5-148">SharePoint и Teams</span><span class="sxs-lookup"><span data-stu-id="ba6a5-148">SharePoint and Teams</span></span>

<span data-ttu-id="ba6a5-149">Файлы канала SharePoint и Teams также могут синхронизироваться локально с настольными устройствами, такими как ноутбуки и Surface Hub, с помощью подсистемы синхронизации OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="ba6a5-150">Синхронизация внутренних корпоративных файлов с локальным диском с помощью приложения синхронизации OneDrive:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="ba6a5-151">Перейдите на сайт SharePoint и перейдите к каталогу документов верхнего уровня для файлов, которые вы хотите просмотреть или изменить на локальном устройстве.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="ba6a5-152">Нажмите кнопку " **синхронизировать** " в верхней части ленты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="ba6a5-153">Нажмите кнопку " **Открыть** " в контекстном меню. **этот сайт пытается открыть Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="ba6a5-154">Убедитесь, что файлы SharePoint синхронизируются с локальным диском, щелкнув значок OneDrive в правом нижнем углу панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="ba6a5-155">Убедитесь в том, что в конфигурации хранить файлы в Интернете и загружать файлы только по мере использования.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="ba6a5-156">Откройте проводник.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-156">Open file explorer.</span></span>
    2. <span data-ttu-id="ba6a5-157">Перейдите к разделу "и щелкните его правой кнопкой мыши в \*\*Microsoft \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="ba6a5-158">Нажмите кнопку **освободить место**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="ba6a5-159">В столбце Status (состояние) будет отображаться состояние файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="ba6a5-160">Дополнительные сведения можно найти в разделе [Синхронизация файлов SharePoint с клиентом синхронизации OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
    
6. <span data-ttu-id="ba6a5-161">Файлы канала Teams хранятся на сайтах SharePoint, с одинаковыми функциями документов SharePoint, включая журнал версий и синхронизируя их с вашими локальными настольными устройствами.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="ba6a5-162">Чтобы синхронизировать файлы канала группы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-162">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="ba6a5-163">Перейдите к нужному каналу Teams и откройте вкладку **файлы** в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-163">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="ba6a5-164">Нажмите кнопку **синхронизировать**. Начнется синхронизация файлов, и они будут видны в проводнике на \*\*рабочем столе \ Microsoft \<name of the Teams Channel\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="ba6a5-165">Выполните те же действия, что и при синхронизации сайтов SharePoint, чтобы сохранить файлы в облаке и загрузить их только при использовании, нажав и удерживая ее, щелкнув правой кнопкой мыши в проводнике и выбрав в контекстном меню команду **освободить место**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="ba6a5-166">Параметры пера Surface HUB</span><span class="sxs-lookup"><span data-stu-id="ba6a5-166">Surface Hub pen settings</span></span>

**<span data-ttu-id="ba6a5-167">Связывание пера Surface Hub Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ba6a5-167">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="ba6a5-168">Связывание пера для поддержания актуальности микропрограммы для перьевого ввода и получение сведений о зарядах батареи на странице параметров устройства Bluetooth или в приложении Surface.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-168">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="ba6a5-169">Нажмите **Start**кнопку  >  **Параметры**запуска  >  **устройств**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-169">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="ba6a5-170">Нажмите кнопку **Добавить Bluetooth или другое устройство**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-170">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="ba6a5-171">Выберите **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-171">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="ba6a5-172">Удалите кнопку с хвостовиком пера и стабилизации видеоизображения, чтобы отключить соединение с батареей.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-172">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="ba6a5-173">Установите ограничение и удерживайте ее, пока не мигает индикатор связывания.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-173">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="ba6a5-174">На вкладке Surface Hub (параметры Bluetooth) выберите пункт **перо Surface Hub 2**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-174">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="ba6a5-175">Завершите операцию связывания.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-175">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="ba6a5-176">Если связывание не прошло успешно, вы можете снова попытаться связать перо.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-176">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="ba6a5-177">Если это не помогло, вы можете проверить, оплачивается ли заряд батареи, убедившись в том, что перо работает в приложении "доска".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-177">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="ba6a5-178">В противном случае замените батарею и попробуйте снова связать перо.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-178">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="ba6a5-179">При необходимости перезагрузите устройство и попробуйте еще раз.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-179">If necessary, reboot the device and then try again.</span></span>

<span data-ttu-id="ba6a5-180">**Настройка ярлыков пера** У пера Surface Hub есть кнопка контекстной клавиатуры иногда называется "хвостовик щелчка".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-180">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="ba6a5-181">Для настройки сочетаний клавиш необходимо сначала связать перо, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-181">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="ba6a5-182">Найдите перо и выберите пункт **перо & параметры Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-182">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="ba6a5-183">В нижней части страницы щелкните ярлыки пера, чтобы открыть диалоговое окно, показанное ниже.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-183">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

![Сочетания клавиш для рукописного ввода](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="ba6a5-185">Настройка камеры</span><span class="sxs-lookup"><span data-stu-id="ba6a5-185">Camera configuration</span></span>

<span data-ttu-id="ba6a5-186">Вы можете подключить камеру в верхней или на обеих сторонах устройства.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-186">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="ba6a5-187">Размещайте камеру в нужном месте, чтобы оптимизировать угол камеры, если вы используете концентратор с настольным компьютером, а не с тележкой, или близко к концентратору.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-187">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="ba6a5-188">Камера не выполняет автоматический поворот, поэтому для поворота камеры вручную необходимо иметь 2mm шестнадцатеричный ключ.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-188">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="ba6a5-189">Дополнительные сведения о том, как подключить камеру и повернуть камеру вручную, можно найти в разделе [Surface Hub 2S ориентация камеры](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-189">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="ba6a5-190">Конфигурация Windows Hello</span><span class="sxs-lookup"><span data-stu-id="ba6a5-190">Windows Hello configuration</span></span>

<span data-ttu-id="ba6a5-191">Surface Hub 2 с Windows 10 Корпоративная поддерживает полный набор классических приложений Win32 и параметров биометрического Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-191">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="ba6a5-192">Программа для чтения отпечатков пальцев (Surface Hub 2) может быть подключена к любому порту USB-C на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-192">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="ba6a5-193">Заказать Surface Hub 2 Reader или просмотреть технические характеристики можно в разделе [основные компоненты для Windows 10 Pro и Enterprise на Surface Hub 2](surface-hub-2-essential-add-ons.md).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-193">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see [Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2](surface-hub-2-essential-add-ons.md).</span></span> 

<span data-ttu-id="ba6a5-194">После вставки средства чтения отпечатков пальцев **нажмите кнопку**  >  **Параметры**  >  входа для**учетных записей**,  >  **Sign-in options**  >  чтобы зарегистрировать отпечаток пальца, в**Windows Hello** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-194">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="ba6a5-195">Использовать сертифицированное устройство Windows Hello для распознавания лицом.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-195">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="ba6a5-196">Камера Surface Hub 2 не поддерживает распознавание лиц в Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-196">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="ba6a5-197">Включение значка сочетания клавиш на экране блокировки на панели задач</span><span class="sxs-lookup"><span data-stu-id="ba6a5-197">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="ba6a5-198">Чтобы добавить на панель задач значок, включающий режим односенсорной блокировки экрана, аналогичный сочетанию клавиш Windows-L:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-198">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="ba6a5-199">Нажмите и удерживайте или щелкните правой кнопкой мыши на рабочем столе и выберите команду **создать**  >  **ярлык**для  >  **Browse**  >  **настольного компьютера**, затем кнопку  >  **ОК**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-199">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="ba6a5-200">Введите имя для ярлыка, например " **заблокировать мой компьютер**", а затем нажмите кнопку **"Готово"**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-200">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="ba6a5-201">Щелкните правой кнопкой мыши или нажмите и удерживайте созданный ярлык на рабочем столе и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-201">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="ba6a5-202">На вкладке **ярлык** введите в поле **Target** следующее: **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="ba6a5-202">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="ba6a5-203">Нажмите кнопку **изменить значок** и перейдите к **C:\Windows\System32\imageres.dll** и выберите нужный значок.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-203">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="ba6a5-204">См. приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-204">See the following example:</span></span>

    ![Выбор значка](images/lock.png)
    
1.  <span data-ttu-id="ba6a5-206">Нажмите кнопку **ОК** , чтобы сохранить ярлык.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-206">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="ba6a5-207">Щелкните правой кнопкой мыши или коснитесь и удерживайте ярлык и выберите **закрепить на панели задач**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-207">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="ba6a5-208">После того как вы зазакреплены на панели задач ярлык для блокировки, вы можете удалить ее с рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-208">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="ba6a5-209">Приложения</span><span class="sxs-lookup"><span data-stu-id="ba6a5-209">Applications</span></span>

### <span data-ttu-id="ba6a5-210">Обновление установленных приложений</span><span class="sxs-lookup"><span data-stu-id="ba6a5-210">Update installed apps</span></span>

<span data-ttu-id="ba6a5-211">Чтобы обновить все установленные приложения из магазина, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-211">To update all installed Store apps:</span></span>

1. <span data-ttu-id="ba6a5-212">Откройте приложение Microsoft Store и выберите пункт **другие** многоточия в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-212">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="ba6a5-213">Выберите **Загрузки и обновления**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-213">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="ba6a5-214">Нажмите **Получить обновления**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-214">Select **Get updates**.</span></span>

### <span data-ttu-id="ba6a5-215">Доска (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ba6a5-215">Microsoft Whiteboard</span></span>

<span data-ttu-id="ba6a5-216">Чтобы установить доску Microsoft, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-216">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="ba6a5-217">Щелкните значок " **Рабочая область Windows Ink** " в правом правом углу панели задач и скачайте **доску**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-217">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Рабочая область для рукописного ввода](images/ink.png) 

<span data-ttu-id="ba6a5-219">Кроме того, вы можете установить доску из Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-219">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="ba6a5-220">Откройте приложение Microsoft Store и найдите **доску**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-220">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="ba6a5-221">Выберите **нет, спасибо** , чтобы войти и использовать на разных устройствах.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-221">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="ba6a5-222">Закрепите доску на панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-222">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="ba6a5-223">Приложение Surface</span><span class="sxs-lookup"><span data-stu-id="ba6a5-223">Surface app</span></span>

1. <span data-ttu-id="ba6a5-224">В Microsoft Store выполните поиск по **поверхности**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-224">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="ba6a5-225">Настройте фильтр " **доступно** для всех" на **всех устройствах**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-225">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="ba6a5-226">Установите приложение **Surface** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-226">Install the **Surface** app.</span></span> <span data-ttu-id="ba6a5-227">Это первое приложение, указанное в списке.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-227">This should be the first app listed.</span></span> <span data-ttu-id="ba6a5-228">Для установки приложения может потребоваться связать MSA с магазином.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-228">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="ba6a5-229">Закрепите приложение **Surface** на панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-229">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="ba6a5-230">Набросок на фрагменте экрана</span><span class="sxs-lookup"><span data-stu-id="ba6a5-230">Snip & Sketch</span></span>

1. <span data-ttu-id="ba6a5-231">Откройте приложение **фрагмент & наброска** и закрепите его на панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-231">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="ba6a5-232">Щелкните многоточие в правом верхнем углу и выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-232">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="ba6a5-233">В меню " **Параметры**" включите параметр " **автоматически копировать в буфер обмена**", " **сохранять фрагменты**" и " **несколько окон** " (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-233">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="ba6a5-234">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="ba6a5-234">Microsoft Office</span></span>

1. <span data-ttu-id="ba6a5-235">Откройте [портал Office](https://portal.office.com/account#installs) и установите нужные приложения.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-235">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>

2. <span data-ttu-id="ba6a5-236">Закрепите нужные приложения Office на панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-236">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="ba6a5-237">Если на компьютере установлено приложение Outlook, убедитесь, что в качестве OST-файла Outlook сохраняется только Последнее два кэша недель.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-237">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="ba6a5-238">Это значительно сокращает время использования диска и настройку.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-238">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="ba6a5-239">Нажмите **кнопку**  >  **Параметры учетной записи** и выберите свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-239">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="ba6a5-240">Нажмите кнопку **изменить** и установите ползунок **использовать режим кэширования Exchange** равным 14 дням.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-240">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="ba6a5-241">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba6a5-241">Microsoft Teams</span></span>

1. <span data-ttu-id="ba6a5-242">Скачайте и установите [Microsoft Teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-242">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>

2. <span data-ttu-id="ba6a5-243">Настройте параметры для автоматически запускаемого приложения (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-243">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="ba6a5-244">Закрепите команды на панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-244">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="ba6a5-245">Рекомендуется уменьшить количество уведомлений групп на устройстве, чтобы избежать отвлекающих (необязательных).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-245">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Уведомления Teams](images/teams.png)

### <span data-ttu-id="ba6a5-247">Подключить приложение</span><span class="sxs-lookup"><span data-stu-id="ba6a5-247">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba6a5-248">В Windows 10 версии 2004 и более поздних версий приложение Connect for Wireless для беспроводной связи по протоколу Miracast не устанавливается по умолчанию, но доступно для использования в качестве дополнительной функции.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-248">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="ba6a5-249">Если вы установили (или обновили версию до) Windows версии 2004 или более поздней, на экране "Настройка" вы можете увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-249">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Проецирование на этот компьютер](images/sh2-project.png) 


1. <span data-ttu-id="ba6a5-251">Чтобы установить приложение на странице "проецирование на этот компьютер", выберите **Дополнительные функции**  >  **добавьте функцию** , а затем установите приложение для **беспроводного дисплея** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-251">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="ba6a5-252">**На некоторых устройствах с Windows и Android на этот компьютер может быть переноситься, если вы скажите "ОК**", выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-252">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="ba6a5-253">**Доступно везде, где** устройство не входит в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-253">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="ba6a5-254">В противном случае выберите пункт **доступно везде в защищенных сетях**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-254">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="ba6a5-255">В разделе **запрашивать проект для этого компьютера**выбирайте **только первый раз**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-255">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="ba6a5-256">В разделе **требовать ПИН-код для связывания**выберите пункт **никогда**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-256">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="ba6a5-257">Чтобы запустить приложение и закрепить его на панели задач, выполните поиск **подключения**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-257">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="ba6a5-258">Откройте приложение.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-258">Open the app.</span></span> <span data-ttu-id="ba6a5-259">Когда приложение открыто, щелкните правой кнопкой мыши значок подключить приложение на панели задач и выберите команду **закрепить на панели задач**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-259">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="ba6a5-260">Затем закройте приложение Connect.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-260">Then close the Connect app.</span></span> <span data-ttu-id="ba6a5-261">Приложение **Project для этого компьютера** может работать только в том случае, если оно запущено хотя бы один раз.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-261">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="ba6a5-262">Рекомендуемая конфигурация, если она не включена в корпоративную сеть:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-262">Recommended configuration when not on the corporate network:</span></span>

![Параметры на домашней странице](images/project1.png)

<span data-ttu-id="ba6a5-264">Рекомендуемая конфигурация в корпоративной сети:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-264">Recommended configuration on the corporate network:</span></span>

![Параметры на рабочем процессе](images/project2.png)

### <span data-ttu-id="ba6a5-266">Ваш телефон</span><span class="sxs-lookup"><span data-stu-id="ba6a5-266">Your Phone</span></span>

<span data-ttu-id="ba6a5-267">Ваше приложение для **телефона** установлено по умолчанию в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-267">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="ba6a5-268">Если он отсутствует, вы также можете установить его из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-268">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="ba6a5-269">Сведения о настройке приложения можно найти в разделе [Настройка телефона в Windows 10 и синхронизация данных между компьютером и телефоном](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-269">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="ba6a5-270">Кроме того [, вы узнаете, как устранить распространенные проблемы с приложением для телефонов в Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-270">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="ba6a5-271">Зоны с суперным узором</span><span class="sxs-lookup"><span data-stu-id="ba6a5-271">Super Fancy Zones</span></span>

<span data-ttu-id="ba6a5-272">С помощью **супер зоны** пользователи смогут расположить окна для максимального свободного места.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-272">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="ba6a5-273">Теперь она включена в средства [PowerToy](https://github.com/microsoft/PowerToys/releases) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-273">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="ba6a5-274">Браузер EDGE Chromium</span><span class="sxs-lookup"><span data-stu-id="ba6a5-274">Edge Chromium browser</span></span>

<span data-ttu-id="ba6a5-275">Скачайте и установите новый [Обозреватель Edge Chromium](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-275">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="ba6a5-276">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="ba6a5-276">Additional settings</span></span>

### <span data-ttu-id="ba6a5-277">Щелкните стрелку, чтобы запустить доску</span><span class="sxs-lookup"><span data-stu-id="ba6a5-277">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="ba6a5-278">Найдите **перо** и выберите пункт **перо & параметры Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-278">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="ba6a5-279">В нижней части страницы в разделе **сочетания клавиш** **выберите один раз** в Microsoft " **доска**".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-279">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="ba6a5-280">Управление питанием</span><span class="sxs-lookup"><span data-stu-id="ba6a5-280">Power management</span></span>

<span data-ttu-id="ba6a5-281">Для оптимальной работы с Windows 10 Pro или Enterprise на Surface Hub доступно несколько параметров электросети.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-281">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="ba6a5-282">Сюда входят тайм-аут экрана и компьютеров, а также их взаимодействие с встроенным обнаружением присутствия (допплеровского), экранной заставкой и парольной защитой, а также при необходимости для настройки параметров электрополитики, предназначенных для настольных компьютеров и пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-282">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="ba6a5-283">Windows 10 Pro или Enterprise на Surface Hub 2 — переход на экран с помощью сенсорного ввода, мыши и сочетаний клавиш, а также встроенной функции обнаружения сотрудников (допплеровского).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-283">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="ba6a5-284">Обнаружение сотрудников по умолчанию включено, но если нужно, его можно отключить в UEFI, переключив параметр устройства в средстве конфигуратора UEFI Surface как часть начальной миграции или создав и применяя позже пакет конфигурации UEFI.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-284">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="ba6a5-285">Управление питанием: параметры экрана и спящего режима в ПК</span><span class="sxs-lookup"><span data-stu-id="ba6a5-285">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="ba6a5-286">Выберите **Start**  >  **Параметры**запуска  >  **система**  >  **Power & спящего режима**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-286">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="ba6a5-287">Установите для ползунка режима электросети значение **наилучшее быстродействие**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-287">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="ba6a5-288">Настраивайте значения экрана и спящего режима, а также пропуски обнаружение обнаружения присутствия допплеровского, которое выводит устройство из спящего режима при обнаружении перемещения.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-288">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="ba6a5-289">Таким образом, рекомендуется установить отключение экрана **через 2 часа** , после чего компьютер будет выключен **через 4 часа.**</span><span class="sxs-lookup"><span data-stu-id="ba6a5-289">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="ba6a5-290">Управление электропитанием: экранная заставка</span><span class="sxs-lookup"><span data-stu-id="ba6a5-290">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="ba6a5-291">Найдите **экран блокировки** и откройте **Параметры экрана блокировки**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-291">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="ba6a5-292">Настройте **Параметры времени ожидания экрана** и **Параметры экранной заставки** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-292">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="ba6a5-293">Рекомендуемые значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-293">Recommended default values are:</span></span>

   - <span data-ttu-id="ba6a5-294">Экранная заставка (нет) или заставка по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-294">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="ba6a5-295">Дождитесь "время на 15 минут".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-295">Wait” time to 15 minutes.</span></span>
   - <span data-ttu-id="ba6a5-296">При возобновлении экрана входа в систему.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-296">On resume, display logon screen.</span></span>


**<span data-ttu-id="ba6a5-297">Управление питанием: групповая политика</span><span class="sxs-lookup"><span data-stu-id="ba6a5-297">Power Management: Group Policy</span></span>**

<span data-ttu-id="ba6a5-298">Перед выполнением описанной ниже процедуры проверяйте свой ИТ-отдел на утверждение, чтобы исключить из глобальной политики управления питанием устройство Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-298">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="ba6a5-299">Некоторые параметры управления электропитанием могут отключить функцию обнаружения присутствия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-299">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="ba6a5-300">Найдите **центр программного обеспечения** и откройте его.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-300">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="ba6a5-301">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-301">Select **Options**.</span></span>

3. <span data-ttu-id="ba6a5-302">Разверните элемент **Управление электропитанием**  и выберите **не применять параметры электроуправления ПИТАНИЕм из ИТ-отдела на этот компьютер**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-302">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Параметры программного обеспечения](images/soft-cntr.png)

### <span data-ttu-id="ba6a5-304">Контроль памяти</span><span class="sxs-lookup"><span data-stu-id="ba6a5-304">Storage Sense</span></span>

<span data-ttu-id="ba6a5-305">Surface Hub 2 имеет твердотельный накопитель емкостью 128 ГБ для локального хранилища, поэтому необходимо продумать использование мер хранения для сохранения во время использования в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-305">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="ba6a5-306">Чтобы настроить контроль хранилища, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-306">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="ba6a5-307">Найдите **Параметры хранилища**, которые находятся в разделе **Параметры системы**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-307">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="ba6a5-308">В разделе **Параметры**выберите **включить контроль хранилища** , чтобы открыть страницу параметры **хранилища** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-308">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="ba6a5-309">Включите функцию хранения данных **.**</span><span class="sxs-lookup"><span data-stu-id="ba6a5-309">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="ba6a5-310">Выберите команду **настроить контроль хранилища или запустите его сейчас** и настройте параметры для сохранения файлов в оперативном режиме (из-за ограничения места на диске).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-310">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="ba6a5-311">Рекомендуемые параметры:</span><span class="sxs-lookup"><span data-stu-id="ba6a5-311">Recommended settings:</span></span>

- <span data-ttu-id="ba6a5-312">Запустите контроль хранилища = каждый день.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-312">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="ba6a5-313">Удаление временных файлов, которые не используют мои приложения = каждые 14 дней (по крайней мере).</span><span class="sxs-lookup"><span data-stu-id="ba6a5-313">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="ba6a5-314">Удаление файлов из папки "загрузок" в течение более 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-314">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="ba6a5-315">OneDrive: контент станет доступен только в том случае, если он не открыт дольше, чем 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-315">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="ba6a5-316">Режим планшета</span><span class="sxs-lookup"><span data-stu-id="ba6a5-316">Tablet mode</span></span>

<span data-ttu-id="ba6a5-317">Включите режим планшета, если это требуется для специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-317">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="ba6a5-318">Параметры звука</span><span class="sxs-lookup"><span data-stu-id="ba6a5-318">Sound settings</span></span>

1. <span data-ttu-id="ba6a5-319">Найдите **Параметры звуковых файлов** и откройте страницу.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-319">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="ba6a5-320">Выберите **Панель управления звуком** справа и откройте вкладку **звуки** .</span><span class="sxs-lookup"><span data-stu-id="ba6a5-320">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="ba6a5-321">В разделе **Программные события** настройте **Подключение устройства** и **Отключение устройства** от " **нет**".</span><span class="sxs-lookup"><span data-stu-id="ba6a5-321">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="ba6a5-322">Уведомления о тишине</span><span class="sxs-lookup"><span data-stu-id="ba6a5-322">Silence notifications</span></span>

1. <span data-ttu-id="ba6a5-323">Найдите **помощь по фокусу** и откройте эту страницу.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-323">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="ba6a5-324">Выберите **только будильники**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-324">Select **Alarms Only**.</span></span> <span data-ttu-id="ba6a5-325">Всплывающие окна уведомлений не будут постоянными.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-325">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="ba6a5-326">Очистка диска</span><span class="sxs-lookup"><span data-stu-id="ba6a5-326">Disk Cleanup</span></span>

1. <span data-ttu-id="ba6a5-327">Выполните поиск по запросу **очистки диска** и откройте это приложение.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-327">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="ba6a5-328">В разделе **файлы для удаления**выберите файлы, которые вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-328">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="ba6a5-329">Также выберите команду **Очистить системные файлы**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-329">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="ba6a5-330">Завершение и проверка</span><span class="sxs-lookup"><span data-stu-id="ba6a5-330">Complete and verify</span></span>

1. <span data-ttu-id="ba6a5-331">Проверяйте и установите все обновления для Windows.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-331">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="ba6a5-332">Обновление групповой политики</span><span class="sxs-lookup"><span data-stu-id="ba6a5-332">Update Group Policy</span></span>

   1. <span data-ttu-id="ba6a5-333">В командной строке с повышенными привилегиями введите **gpupdate/Force/Boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-333">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="ba6a5-334">Перезагрузите устройство.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-334">Reboot the device.</span></span>

4. <span data-ttu-id="ba6a5-335">Проверка приложений панели задач.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-335">Verify taskbar apps.</span></span>

   - <span data-ttu-id="ba6a5-336">Подключить приложение</span><span class="sxs-lookup"><span data-stu-id="ba6a5-336">Connect App</span></span>
   - <span data-ttu-id="ba6a5-337">Значок замка</span><span class="sxs-lookup"><span data-stu-id="ba6a5-337">Lock Icon</span></span>
   - <span data-ttu-id="ba6a5-338">Набросок на фрагменте экрана</span><span class="sxs-lookup"><span data-stu-id="ba6a5-338">Snip & Sketch</span></span>
   - <span data-ttu-id="ba6a5-339">Teams (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ba6a5-339">Teams (if applicable)</span></span>
   - <span data-ttu-id="ba6a5-340">Приложения Office (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ba6a5-340">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="ba6a5-341">Приложение Surface</span><span class="sxs-lookup"><span data-stu-id="ba6a5-341">Surface App</span></span>
   - <span data-ttu-id="ba6a5-342">Доска</span><span class="sxs-lookup"><span data-stu-id="ba6a5-342">Whiteboard</span></span>
    
5. <span data-ttu-id="ba6a5-343">Проверка обнаружения присутствия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-343">Verify presence detection.</span></span>

   - <span data-ttu-id="ba6a5-344">В области уведомлений отображается зеленый значок обнаружения присутствия.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-344">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="ba6a5-345">Убедитесь в том, что для этого компьютера включено проецирование на этот компьютер с помощью приложения Connect.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-345">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="ba6a5-346">После того как вы настраиваете  **Project для настройки этого компьютера** , запустите приложение Connect хотя бы один раз.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-346">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="ba6a5-347">(Следовательно, приложение Connect не нужно запускать для проецирования на Surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="ba6a5-347">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="ba6a5-348">Проверьте параметры электросети и режима сна.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-348">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="ba6a5-349">Экранная заставка: 15 минут, значение (нет), пояснение или пустой; Убедитесь, что флажок Требовать пароль установлен.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-349">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="ba6a5-350">Экран: отключение **через 2 часа**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-350">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="ba6a5-351">ПК: отключение  **через 4 часа**.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-351">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="ba6a5-352">Проверка работоспособности Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-352">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="ba6a5-353">Убедитесь, что параметры синхронизации отключены.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-353">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="ba6a5-354">Проверка загрузочных приложений.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-354">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="ba6a5-355">После установки и настройки Windows 10 Surface Hub 2 можно управлять точно так же, как и любое другое устройство с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba6a5-355">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="ba6a5-356">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ba6a5-356">Related topics</span></span>

[<span data-ttu-id="ba6a5-357">Переход на Windows 10 Pro или Корпоративная в Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="ba6a5-357">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
