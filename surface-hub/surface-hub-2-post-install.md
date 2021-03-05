---
title: Настройка Windows 10 Pro или Корпоративная на Surface Hub 2
description: В этой статье содержатся рекомендации по обеспечению наилучшего опыта при использовании персонализированного большого сенсорного экрана и пера компьютера.
keywords: Surface Hub, Windows 10, настольный компьютер, установка, конфигурация
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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393595"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="57a45-104">Настройка Windows 10 Pro или Корпоративная на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="57a45-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="57a45-105">После завершения процесса установки перехода на Windows 10 Pro или Enterprise можно выполнить следующие действия по настройке приложений и параметров на surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="57a45-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="57a45-106">Эти действия рекомендуется для обеспечения наилучшего опыта при использовании этого персонализированного большого сенсорного экрана и пера компьютера.</span><span class="sxs-lookup"><span data-stu-id="57a45-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="57a45-107">При выполнении этих действий может оказаться полезным использовать проводную или беспроводную клавиатуру и мышь.</span><span class="sxs-lookup"><span data-stu-id="57a45-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="57a45-108">Настройка параметров системы</span><span class="sxs-lookup"><span data-stu-id="57a45-108">Configure system settings</span></span>

1. <span data-ttu-id="57a45-109">Во входе в учетную запись с локальными привилегиями администратора на устройстве.</span><span class="sxs-lookup"><span data-stu-id="57a45-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="57a45-110">На присоединив устройствах Azure AD пользователь, который выполняет присоединиться к Azure AD, автоматически добавляется в локализованную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="57a45-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="57a45-111">Глобальные администраторы Azure AD и администраторы устройств Azure AD также <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> являются локальными администраторами. </a></span><span class="sxs-lookup"><span data-stu-id="57a45-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="57a45-112">Вы можете ввести **чистых администраторов** локальных групп по командной подсказке, чтобы перечислить учетные записи, которые имеют права локального администратора.</span><span class="sxs-lookup"><span data-stu-id="57a45-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="57a45-113">Переименование устройства с использованием удобного имени, например: **username-SHub-Desktop.**</span><span class="sxs-lookup"><span data-stu-id="57a45-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="57a45-114">Выберите \*\*\*\*  >  **Учетные записи параметров**начните  >  \*\*\*\*  >  **синхронизировать параметры** и отключить **параметры Синхронизации.**</span><span class="sxs-lookup"><span data-stu-id="57a45-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="57a45-115">Параметры, используемые здесь, предназначены для обеспечения наилучшего сенсорного экрана на большом экране, поэтому вам может не потребоваться синхронизировать другие устройства.</span><span class="sxs-lookup"><span data-stu-id="57a45-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="57a45-116">Перезагрузите устройство.</span><span class="sxs-lookup"><span data-stu-id="57a45-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="57a45-117">Включить сенсорную клавиатуру и сенсорную панель</span><span class="sxs-lookup"><span data-stu-id="57a45-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="57a45-118">Выберите **Начните**параметров устройств ввода и включить Показать сенсорную клавиатуру, когда не в режиме планшета и нет клавиатуры,  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\* **присоединенной.**</span><span class="sxs-lookup"><span data-stu-id="57a45-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="57a45-119">Нажмите и удерживайте или нажмите правой кнопкой мыши на панели задач, а затем выберите **кнопку Показать** сенсорную клавиатуру и **кнопку Show touchpad**.</span><span class="sxs-lookup"><span data-stu-id="57a45-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="57a45-120">Сенсорная клавиатура полезна для прямого ввода пользователя, а виртуальная сенсорная панель помогает с точными выборами, наведении на экране подсказки или в качестве альтернативы нажатию и удержанию правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="57a45-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="57a45-121">См. следующий пример.</span><span class="sxs-lookup"><span data-stu-id="57a45-121">See the following example.</span></span>

      ![Параметры касания](images/touch.png)

3. <span data-ttu-id="57a45-123">Настройка сенсорной клавиатуры на QWERTY и плавающей.</span><span class="sxs-lookup"><span data-stu-id="57a45-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="57a45-124">Выберите **значок Клавиатура** на панели задач, чтобы показать сенсорную клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="57a45-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="57a45-125">На сенсорной клавиатуре выберите значок клавиатуры в левом верхнем углу, чтобы открыть параметры клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="57a45-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="57a45-126">Выберите следующий тип клавиатуры в верхней строке, чтобы включить QWERTY, а последний вариант на втором ряду для обеспечения плавающего, что очень полезно на этом большом экране.</span><span class="sxs-lookup"><span data-stu-id="57a45-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="57a45-127">См. следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="57a45-127">See the following examples.</span></span>

       ![Параметры клавиатуры](images/kbd.png)
 
4. <span data-ttu-id="57a45-129">Настройка параметров мягкой клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="57a45-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="57a45-130">Выберите **значок Параметры** на сенсорной клавиатуре или наведите и откройте **параметры ввода.**</span><span class="sxs-lookup"><span data-stu-id="57a45-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![параметры мягкой клавиатуры](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="57a45-132">Введите все параметры в клавиатуре Spelling, Typing и Touch.</span><span class="sxs-lookup"><span data-stu-id="57a45-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="57a45-133">В следующем примере показан трекпад, который полезен для навигации и выбора параметров.</span><span class="sxs-lookup"><span data-stu-id="57a45-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="57a45-134">Экранная клавиатура используется для поиска в Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="57a45-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Использование трекпада](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="57a45-136">Настройка Bluetooth клавиатуры и мыши (необязательно)</span><span class="sxs-lookup"><span data-stu-id="57a45-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="57a45-137">Подключите клавиатуру и мышь, если вы используете устройство в качестве основного устройства Windows или часто используете его для ввода текста или высокоточной работы.</span><span class="sxs-lookup"><span data-stu-id="57a45-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="57a45-138">Если устройство Surface Hub находится рядом с компьютером, вы можете с помощью мыши без границ плавно перемещаться между <a href="https://aka.ms/mm" target="_blank"> </a> Surface Hub и ПК.</span><span class="sxs-lookup"><span data-stu-id="57a45-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="57a45-139">Дополнительные сведения см. в <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> веб-сайте Microsoft download from The Garage: Mouse without Borders.</span><span class="sxs-lookup"><span data-stu-id="57a45-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="57a45-140">Пример макета панели задач</span><span class="sxs-lookup"><span data-stu-id="57a45-140">Example of Taskbar layout</span></span>

<span data-ttu-id="57a45-141">После выполнения нижеприводных действий по настройке и настройке Surface Hub 2 для Windows 10 Professional или Enterprise рекомендуется использовать закрепление наиболее используемых приложений в панели задач для быстрого запуска каждого приложения одним касанием.</span><span class="sxs-lookup"><span data-stu-id="57a45-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="57a45-142">Ниже приведен пример того, как может выглядеть панель задач:</span><span class="sxs-lookup"><span data-stu-id="57a45-142">Below is an example of what your taskbar could look like:</span></span>

 ![Макет панели задач](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="57a45-144">Обновление установленных приложений</span><span class="sxs-lookup"><span data-stu-id="57a45-144">Update installed apps</span></span>

<span data-ttu-id="57a45-145">Обновление всех установленных приложений Магазина:</span><span class="sxs-lookup"><span data-stu-id="57a45-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="57a45-146">Откройте приложение Microsoft Store и выберите **дополнительный** эллипсис в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="57a45-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="57a45-147">Выберите **загрузки и обновления.**</span><span class="sxs-lookup"><span data-stu-id="57a45-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="57a45-148">Выберите **Получить обновления**</span><span class="sxs-lookup"><span data-stu-id="57a45-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="57a45-149">Сканирование и установка всех обновлений Windows</span><span class="sxs-lookup"><span data-stu-id="57a45-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="57a45-150">После перехода на Windows 10 Профессиональный или Windows 10 Корпоративный, может быть обслуживание и обновления функций, доступных для установки.</span><span class="sxs-lookup"><span data-stu-id="57a45-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="57a45-151">Перейдите **к обновлению**  >  **параметров & безопасности** > и выберите Check for **updates**.</span><span class="sxs-lookup"><span data-stu-id="57a45-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="57a45-152">Если есть какие-либо обновления, установите их, перезагружайте и повторите процесс, пока не увидите следующее уведомление:</span><span class="sxs-lookup"><span data-stu-id="57a45-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Уведомление об обновлении Windows](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="57a45-154">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="57a45-154">OneDrive for Business</span></span>

<span data-ttu-id="57a45-155">Используйте <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive для бизнеса, чтобы легко обмениваться инструментами, журналами и другими </a> файлами между всеми вашими устройствами.</span><span class="sxs-lookup"><span data-stu-id="57a45-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="57a45-156">OneDrive позволяет обмениваться рабочими файлами между ноутбуками, настольными устройствами Surface Hub и мобильными устройствами с управлением Intune.</span><span class="sxs-lookup"><span data-stu-id="57a45-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="57a45-157">Файлы можно редактировать на любом устройстве, и все подключенные к сети устройства будут обновлены с помощью изменений.</span><span class="sxs-lookup"><span data-stu-id="57a45-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="57a45-158">Учитывая размер SSD Surface Hub (128 ГБ), если вы настраиваете OneDrive на рабочем столе Surface Hub, убедитесь, что конфигурация по умолчанию должна хранить файлы в Интернете и скачивать файлы при их использовании.</span><span class="sxs-lookup"><span data-stu-id="57a45-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="57a45-159">Чтобы настроить OneDrive для загрузки файлов только при необходимости, установите параметр **Files On-Demand** для сохранения пространства и загрузки файлов при **их использовании.**</span><span class="sxs-lookup"><span data-stu-id="57a45-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="57a45-160">Дополнительные сведения см. в <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> материалах "Запрос" и "Настройка состояния файлов по требованию" в </a> Windows.</span><span class="sxs-lookup"><span data-stu-id="57a45-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Параметры OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="57a45-162">Вы также можете повторить эти действия, чтобы настроить личный OneDrive, но не забудьте сохранить пространство диска и скачивать файлы только по мере их необходимости.</span><span class="sxs-lookup"><span data-stu-id="57a45-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="57a45-163">SharePoint и Teams</span><span class="sxs-lookup"><span data-stu-id="57a45-163">SharePoint and Teams</span></span>

<span data-ttu-id="57a45-164">Файлы каналов SharePoint и Teams также могут локально синхронизироваться с настольными устройствами, такими как ноутбуки и концентраторы Surface, с помощью двигателя синхронизации OneDrive.</span><span class="sxs-lookup"><span data-stu-id="57a45-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="57a45-165">Синхронизация внутренних корпоративных файлов с локальным диском с приложением синхронизации OneDrive:</span><span class="sxs-lookup"><span data-stu-id="57a45-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="57a45-166">Перейдите на сайт SharePoint и перейдите в каталог документов верхнего уровня для файлов, которые вам интересны для просмотра или редактирования с локального устройства.</span><span class="sxs-lookup"><span data-stu-id="57a45-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="57a45-167">Выберите **кнопку Sync** в верхней части ленты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="57a45-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="57a45-168">Выберите в **open** в **всплывающее всплывающее место Этот**сайт пытается открыть Microsoft OneDrive .</span><span class="sxs-lookup"><span data-stu-id="57a45-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="57a45-169">Убедитесь, что файлы SharePoint синхронизируются с локальным диском, выбрав значок OneDrive в правом нижнем справа от панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="57a45-170">Убедитесь, что конфигурация установлена для сохраняемой онлайн-загрузки файлов только при их использовании:</span><span class="sxs-lookup"><span data-stu-id="57a45-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="57a45-171">Откройте проводник файлов.</span><span class="sxs-lookup"><span data-stu-id="57a45-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="57a45-172">Перейдите вправо и вправо щелкните имя SharePoint; например, \*\*Contoso \<SharePoint Document Folder Name\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="57a45-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="57a45-173">Выберите **свободное пространство.**</span><span class="sxs-lookup"><span data-stu-id="57a45-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="57a45-174">Столбец Status отображает состояние файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="57a45-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="57a45-175">Дополнительные сведения см. в <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> раздел Синхронизация файлов SharePoint с клиентом синхронизации OneDrive. </a></span><span class="sxs-lookup"><span data-stu-id="57a45-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="57a45-176">Файлы каналов Teams хранятся на сайтах SharePoint с одинаковыми функциями документов SharePoint, включая историю версий и синхронизацию с локальными настольными устройствами.</span><span class="sxs-lookup"><span data-stu-id="57a45-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="57a45-177">Синхронизация файлов каналов Teams:</span><span class="sxs-lookup"><span data-stu-id="57a45-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="57a45-178">Перейдите к интересуемого канала Teams и выберите вкладку **Files** в верхней части.</span><span class="sxs-lookup"><span data-stu-id="57a45-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="57a45-179">Затем выберите **Синхронизация**. Файлы начнут синхронизироваться и будут видны в Проводнике файлов на рабочем столе \*\*\ Contoso \<name of the Teams Channel\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="57a45-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="57a45-180">Используйте ту же процедуру, что и для синхронизации сайтов SharePoint, чтобы хранить файлы в облаке и загружать их только при их использовании, нажав на кнопку и удерживая или щелкнув правой кнопкой мыши в проводнике файлов в имени канала teams, а затем выбрав свободное пространство **.**</span><span class="sxs-lookup"><span data-stu-id="57a45-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="57a45-181">Параметры пера Surface Hub</span><span class="sxs-lookup"><span data-stu-id="57a45-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="57a45-182">Соедините Bluetooth Surface Hub Pen</span><span class="sxs-lookup"><span data-stu-id="57a45-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="57a45-183">Соедините перо, чтобы сохранить прошивку пера в курсе, установите ярлыки пера и получите сведения о заряде батареи на странице параметров Bluetooth устройства или в приложении Surface:</span><span class="sxs-lookup"><span data-stu-id="57a45-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="57a45-184">Выберите **устройства**  >  **параметров**  >  **запуска**.</span><span class="sxs-lookup"><span data-stu-id="57a45-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="57a45-185">Выберите **Добавить Bluetooth или другое устройство.**</span><span class="sxs-lookup"><span data-stu-id="57a45-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="57a45-186">Выберите **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="57a45-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="57a45-187">Снимите кнопку пера и встряхните, чтобы отключить подключение к батарее.</span><span class="sxs-lookup"><span data-stu-id="57a45-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="57a45-188">Положите крышку обратно и нажмите и удерживайте крышку до тех пор, пока спарив светодиодные вспышки.</span><span class="sxs-lookup"><span data-stu-id="57a45-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="57a45-189">В параметрах Surface Hub Bluetooth выберите **Surface Hub 2 Pen.**</span><span class="sxs-lookup"><span data-stu-id="57a45-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="57a45-190">Выполните операцию сопряжения.</span><span class="sxs-lookup"><span data-stu-id="57a45-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="57a45-191">Если спарение не будет успешным, можно попытаться снова спарить перо.</span><span class="sxs-lookup"><span data-stu-id="57a45-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="57a45-192">Если это не работает, вы можете проверить, заряжена ли батарея, проверив работу пера в приложении Whiteboard.</span><span class="sxs-lookup"><span data-stu-id="57a45-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="57a45-193">Если нет, замените батарею, а затем попробуйте снова спарить перо.</span><span class="sxs-lookup"><span data-stu-id="57a45-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="57a45-194">При необходимости перезапустите устройство и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="57a45-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="57a45-195">**Настройка ярлыков пера** Ручка Surface Hub имеет кнопку ярлыка, иногда именуемую "щелчком хвоста".</span><span class="sxs-lookup"><span data-stu-id="57a45-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="57a45-196">Настройка ярлыков требует, чтобы сначала спарить перо, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="57a45-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="57a45-197">Поиск пера и **выбор параметров & Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="57a45-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="57a45-198">В нижней части страницы выберите ярлыки Pen, которые открывают диалоговое окно, показано здесь:</span><span class="sxs-lookup"><span data-stu-id="57a45-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Ярлыки пера](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="57a45-200">Конфигурация камеры</span><span class="sxs-lookup"><span data-stu-id="57a45-200">Camera configuration</span></span>

<span data-ttu-id="57a45-201">Вы можете установить камеру на верхней или с обеих сторон устройства.</span><span class="sxs-lookup"><span data-stu-id="57a45-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="57a45-202">Смонтируйте камеру в положение, чтобы оптимизировать угол камеры, если вы используете концентратор с настольной стойкой вместо корзины или находитесь в непосредственной близости от концентратора.</span><span class="sxs-lookup"><span data-stu-id="57a45-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="57a45-203">Камера не автоматически вращается, поэтому для ручного поворота камеры необходимо иметь 2-миллиметровую гексную клавишу.</span><span class="sxs-lookup"><span data-stu-id="57a45-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="57a45-204">Дополнительные сведения о том, как смонтировать камеру и вращать ее вручную, см. в инструкции по ориентации объектива <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> камеры Surface Hub 2S. </a></span><span class="sxs-lookup"><span data-stu-id="57a45-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="57a45-205">Конфигурация Windows Hello</span><span class="sxs-lookup"><span data-stu-id="57a45-205">Windows Hello configuration</span></span>

<span data-ttu-id="57a45-206">Surface Hub 2S под управлением Windows 10 Enterprise позволяет использовать полный набор настольных приложений Win32, а также биометрические параметры Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="57a45-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="57a45-207">Аксессуар Surface Hub 2 Fingerprint Reader можно подключить к любому порту USB-C на устройстве.</span><span class="sxs-lookup"><span data-stu-id="57a45-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="57a45-208">Чтобы заказать сканер отпечатков пальцев Surface Hub 2 или просмотреть технические спецификации, см. (surface-hub-2-essential-add-ons.md" target="_blank">Основные надстройки для Windows 10 Pro и Enterprise на Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="57a45-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="57a45-209">После вставки сканера \*\*\*\* отпечатков пальцев выберите параметры входных параметров учетных записей Параметров Параметров параметров  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\*  >  **Windows Hello Fingerprint** для регистрации отпечатков пальцев.</span><span class="sxs-lookup"><span data-stu-id="57a45-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="57a45-210">Используйте сертифицированное устройство Windows Hello для распознавания лиц.</span><span class="sxs-lookup"><span data-stu-id="57a45-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="57a45-211">Камера Surface Hub 2S не поддерживает распознавание лиц Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="57a45-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="57a45-212">Включить значок ярлыка экрана блокировки на панели задач</span><span class="sxs-lookup"><span data-stu-id="57a45-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="57a45-213">Добавление значка в панель задач, которая включает блокировку экрана одним касанием, аналогичную ярлыку клавиатуры Windows-L:</span><span class="sxs-lookup"><span data-stu-id="57a45-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="57a45-214">Нажмите кнопку и удерживайте или нажмите правой кнопкой мыши на рабочем столе, выберите **Новый**  >  **ярлык**  >  **Просмотр рабочего**  >  **стола**  >  **ОК**  >  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57a45-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="57a45-215">Укажи имя для такого ярлыка, как **блокировка компьютера,** а затем выберите **Finish**.</span><span class="sxs-lookup"><span data-stu-id="57a45-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="57a45-216">Щелкните правой кнопкой мыши или нажмите кнопку и удерживайте недавно созданный ярлык на рабочем столе и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="57a45-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="57a45-217">На **вкладке Ярлык** введите следующее в поле **Target:** **Rundll32.exe User32.dll,LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="57a45-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="57a45-218">Выберите **кнопку Значок** изменения и просмотрите **C:\Windows\System32\imageres.dll** и выберите значок для использования.</span><span class="sxs-lookup"><span data-stu-id="57a45-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="57a45-219">См. приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="57a45-219">See the following example:</span></span>

    ![Выбор значка](images/lock.png)
    
1.  <span data-ttu-id="57a45-221">Выберите **ОК,** чтобы сохранить ярлык.</span><span class="sxs-lookup"><span data-stu-id="57a45-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="57a45-222">Щелкните правой кнопкой мыши или нажмите кнопку и удерживайте ярлык и выберите **Пин-код в панель задач.**</span><span class="sxs-lookup"><span data-stu-id="57a45-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="57a45-223">После закрепления ярлыка блокировки на панели задач можно удалить его с рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="57a45-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="57a45-224">Приложения</span><span class="sxs-lookup"><span data-stu-id="57a45-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="57a45-225">Доска (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="57a45-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="57a45-226">Чтобы установить доску Microsoft:</span><span class="sxs-lookup"><span data-stu-id="57a45-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="57a45-227">Выберите **значок Рабочей** области Windows Ink в правом нижнем справа от панели задач и скачайте **доску**.</span><span class="sxs-lookup"><span data-stu-id="57a45-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Рабочее пространство ink](images/ink.png) 

<span data-ttu-id="57a45-229">Кроме того, вы можете установить доску из Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="57a45-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="57a45-230">Откройте приложение Microsoft Store и найди **доску.**</span><span class="sxs-lookup"><span data-stu-id="57a45-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="57a45-231">Выберите **Нет благодаря** входу и использованию на различных устройствах.</span><span class="sxs-lookup"><span data-stu-id="57a45-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="57a45-232">Прикрепить доску к панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="57a45-233">Приложение Surface</span><span class="sxs-lookup"><span data-stu-id="57a45-233">Surface app</span></span>

1. <span data-ttu-id="57a45-234">В Microsoft Store ищите **Surface.**</span><span class="sxs-lookup"><span data-stu-id="57a45-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="57a45-235">Установите **доступный фильтр для** **всех устройств.**</span><span class="sxs-lookup"><span data-stu-id="57a45-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="57a45-236">Установка **приложения Surface.**</span><span class="sxs-lookup"><span data-stu-id="57a45-236">Install the **Surface** app.</span></span> <span data-ttu-id="57a45-237">Это должно быть первое приложение в списке.</span><span class="sxs-lookup"><span data-stu-id="57a45-237">This should be the first app listed.</span></span> <span data-ttu-id="57a45-238">Для установки приложения может потребоваться связать MSA с Магазином.</span><span class="sxs-lookup"><span data-stu-id="57a45-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="57a45-239">Прикрепить **приложение Surface** к панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="57a45-240">Набросок на фрагменте экрана</span><span class="sxs-lookup"><span data-stu-id="57a45-240">Snip & Sketch</span></span>

1. <span data-ttu-id="57a45-241">Откройте приложение **Snip & Sketch** и прикрепить его к панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="57a45-242">Выберите эллипсис в правом верхнем углу, а затем выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="57a45-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="57a45-243">В **параметрах**включите автоматическую копию в **буфер обмена,** **сохраните**фрагменты и несколько **окон** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="57a45-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="57a45-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="57a45-244">Microsoft Office</span></span>

1. <span data-ttu-id="57a45-245">Откройте портал <a href="https://portal.office.com/account#installs" target="_blank"> Office и </a> установите нужные приложения.</span><span class="sxs-lookup"><span data-stu-id="57a45-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="57a45-246">Прикрепить нужные приложения Office к панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="57a45-247">Если outlook установлен, обязательно установите для Outlook OST только сохранение кэша последних двух недель.</span><span class="sxs-lookup"><span data-stu-id="57a45-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="57a45-248">Это позволит значительно сократить использование диска и время установки.</span><span class="sxs-lookup"><span data-stu-id="57a45-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="57a45-249">Выберите \*\*\*\*  >  **параметры учетной записи файла** и выберите учетную запись.</span><span class="sxs-lookup"><span data-stu-id="57a45-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="57a45-250">Выберите **Изменение** и установите ползунок для использования кэшного **режима Exchange до** 14 дней.</span><span class="sxs-lookup"><span data-stu-id="57a45-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="57a45-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57a45-251">Microsoft Teams</span></span>

1. <span data-ttu-id="57a45-252">Скачайте и установите <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft </a> Teams.</span><span class="sxs-lookup"><span data-stu-id="57a45-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="57a45-253">Настройка параметров для автоматического запуска приложения (необязательно).</span><span class="sxs-lookup"><span data-stu-id="57a45-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="57a45-254">Pin Teams to the taskbar.</span><span class="sxs-lookup"><span data-stu-id="57a45-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="57a45-255">Рассмотрите возможность уменьшения уведомлений Teams на устройстве, чтобы избежать отвлекающих факторов (необязательно).</span><span class="sxs-lookup"><span data-stu-id="57a45-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Уведомления teams](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="57a45-257">Подключение приложения</span><span class="sxs-lookup"><span data-stu-id="57a45-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57a45-258">В Windows 10 версии 2004 и более поздней версии приложение Connect для беспроводной проекции с помощью Miracast не установлено по умолчанию, но доступно в качестве необязательных функций.</span><span class="sxs-lookup"><span data-stu-id="57a45-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="57a45-259">Если вы установили (или обновили) Windows версии 2004 или более поздней версии, в параметрах projecting на этом экране КОМПЬЮТЕРА можно увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="57a45-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Project to this PC](images/sh2-project.png) 


1. <span data-ttu-id="57a45-261">Чтобы установить приложение на странице Параметры "Проецируемый \*\*\*\* на этот компьютер", выберите дополнительные функции Добавить функцию, а затем установить приложение  >  \*\*\*\* **Wireless Display.**</span><span class="sxs-lookup"><span data-stu-id="57a45-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="57a45-262">В некоторых устройствах Windows и Android можно проектов на этот компьютер, когда вы **говорите, что это нормально,** выберите:</span><span class="sxs-lookup"><span data-stu-id="57a45-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="57a45-263">**Доступно везде,** если устройство не находится в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="57a45-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="57a45-264">В противном случае **выберите Доступный везде в безопасных сетях**.</span><span class="sxs-lookup"><span data-stu-id="57a45-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="57a45-265">В **статье Ask to project to this PC**выберите только первый **раз**.</span><span class="sxs-lookup"><span data-stu-id="57a45-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="57a45-266">В **статье Require PIN-код для сопряжения**выберите **Never**.</span><span class="sxs-lookup"><span data-stu-id="57a45-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="57a45-267">Чтобы затем запустить приложение и прикрепить его к панели задач, поиск **подключения**.</span><span class="sxs-lookup"><span data-stu-id="57a45-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="57a45-268">Откройте приложение.</span><span class="sxs-lookup"><span data-stu-id="57a45-268">Open the app.</span></span> <span data-ttu-id="57a45-269">Пока приложение открыто, щелкните правой кнопкой мыши значок приложения Connect на панели задач и выберите **пин-код в панель задач.**</span><span class="sxs-lookup"><span data-stu-id="57a45-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="57a45-270">Затем закроем приложение Connect.</span><span class="sxs-lookup"><span data-stu-id="57a45-270">Then close the Connect app.</span></span> <span data-ttu-id="57a45-271">**Project to this PC** might not work unless the app has been run at least once.</span><span class="sxs-lookup"><span data-stu-id="57a45-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="57a45-272">Рекомендуемая конфигурация, если не в корпоративной сети:</span><span class="sxs-lookup"><span data-stu-id="57a45-272">Recommended configuration when not on the corporate network:</span></span>

![Параметры дома](images/project1.png)

<span data-ttu-id="57a45-274">Рекомендуемая конфигурация в корпоративной сети:</span><span class="sxs-lookup"><span data-stu-id="57a45-274">Recommended configuration on the corporate network:</span></span>

![Параметры на работе](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="57a45-276">Ваш телефон</span><span class="sxs-lookup"><span data-stu-id="57a45-276">Your Phone</span></span>

<span data-ttu-id="57a45-277">Приложение **Your Phone** установлено по умолчанию на Windows 10.</span><span class="sxs-lookup"><span data-stu-id="57a45-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="57a45-278">Если ее нет, ее также можно установить в магазине Windows.</span><span class="sxs-lookup"><span data-stu-id="57a45-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="57a45-279">Сведения о настройке приложения см. в приложении <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 и sync data between your PC and </a> phone.</span><span class="sxs-lookup"><span data-stu-id="57a45-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="57a45-280">См. также, как устранить <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> распространенные проблемы с приложением Телефон в Windows 10. </a></span><span class="sxs-lookup"><span data-stu-id="57a45-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="57a45-281">Необычные зоны</span><span class="sxs-lookup"><span data-stu-id="57a45-281">Fancy Zones</span></span>


<span data-ttu-id="57a45-282">**Fancy Zones** — это часть коллекции инструментов под названием <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> на GitHub.</span><span class="sxs-lookup"><span data-stu-id="57a45-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="57a45-283">Это отличный способ использовать экранную недвижимость на Surface Hub 2, дав вам возможность определять фиксированные макеты на дисплее ("зоны"), а затем выбрать, какое приложение будет работать в каждой зоне.</span><span class="sxs-lookup"><span data-stu-id="57a45-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="57a45-284">В [вики PowerToys](https://github.com/microsoft/PowerToys/wiki) есть инструкции по использованию и настройке каждого средства, включая [FancyZones.](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)</span><span class="sxs-lookup"><span data-stu-id="57a45-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="57a45-285">На высоком уровне после установки PowerToys можно выбрать или создать настраиваемый макет, а затем удерживать клавишу переноса вниз и перетаскивать или использовать клавиши клавиатуры для перемещения запущенного приложения в определенные зоны.</span><span class="sxs-lookup"><span data-stu-id="57a45-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="57a45-286">С помощью Bluetooth или USB-клавиатуры и мыши это поможет, или вы можете использовать сенсорную клавиатуру и сенсорную панель на экране.</span><span class="sxs-lookup"><span data-stu-id="57a45-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="57a45-287">Power toys tips</span><span class="sxs-lookup"><span data-stu-id="57a45-287">Power toys tips</span></span>**
- <span data-ttu-id="57a45-288">Чтобы получать уведомления о выпуске обновлений PowerToys в GitHub, щелкните кнопку "вход" в верхней части [страницы.](https://github.com/microsoft/PowerToys/releases)</span><span class="sxs-lookup"><span data-stu-id="57a45-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="57a45-289">После установки PowerToys вы можете получать уведомления Windows и/или загружать и устанавливать последние обновления, \*\*\*\* настраивая параметры PowerToys Для автоматического скачивания обновлений.</span><span class="sxs-lookup"><span data-stu-id="57a45-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="57a45-290">Чтобы добраться до параметров PowerToys, \*\*\*\* выберите вверх карат Запуск приложений на панели задач, а затем правой кнопкой мыши или нажмите кнопку и удерживайте значок PowerToys до тех пор, пока меню не появится.</span><span class="sxs-lookup"><span data-stu-id="57a45-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="57a45-291">Выберите параметры.</span><span class="sxs-lookup"><span data-stu-id="57a45-291">Select “Settings”.</span></span>
- <span data-ttu-id="57a45-292">В нижней части страницы параметров PowerToys автоматически **включите** обновления загрузки.</span><span class="sxs-lookup"><span data-stu-id="57a45-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="57a45-293">После выпуска обновления появится уведомление о том, когда необходимо установить обновление.</span><span class="sxs-lookup"><span data-stu-id="57a45-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="57a45-294">Браузер Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="57a45-294">Edge Chromium browser</span></span>

<span data-ttu-id="57a45-295">Скачайте и установите новый <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> браузер Edge Chromium. </a></span><span class="sxs-lookup"><span data-stu-id="57a45-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="57a45-296">Средство диагностики оборудования Surface Hub</span><span class="sxs-lookup"><span data-stu-id="57a45-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="57a45-297">Аппаратный <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> диагностический инструмент Surface Hub </a> доступен бесплатно в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="57a45-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="57a45-298">Этот инструмент предназначен для того, чтобы убедиться, что surface Hub выполняется в лучшем случае.</span><span class="sxs-lookup"><span data-stu-id="57a45-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="57a45-299">Он содержит тесты, чтобы определить, устарело ли ваше программное обеспечение и правильно ли настроено.</span><span class="sxs-lookup"><span data-stu-id="57a45-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="57a45-300">Интерактивные тесты позволяют подтвердить, что основные функциональные возможности работают в нужном режиме.</span><span class="sxs-lookup"><span data-stu-id="57a45-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="57a45-301">Если будут обнаружены проблемы, результаты можно сохранить и отправить группе поддержки Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="57a45-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="57a45-302">Щелкните по ссылке, чтобы установить ее в Microsoft Store, а затем прикрепите приложение к панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="57a45-303">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="57a45-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="57a45-304">Перо хвост выбрать для запуска доски</span><span class="sxs-lookup"><span data-stu-id="57a45-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="57a45-305">Поиск **пера** и **выбор параметров & Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="57a45-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="57a45-306">В нижней части страницы в соответствии с набором ярлыков **Pen** **Выберите** один раз в **Microsoft Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="57a45-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="57a45-307">Управление питанием</span><span class="sxs-lookup"><span data-stu-id="57a45-307">Power management</span></span>

<span data-ttu-id="57a45-308">Существует несколько параметров питания, которые можно получить с помощью Windows 10 Pro или Enterprise на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="57a45-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="57a45-309">Это включает в себя время отключения экрана и пк и их взаимодействие со встроенным обнаружением присутствия человека (Doppler), средствами защиты от сохранения экрана и паролем, а затем, если это уместно, чтобы передать параметры питания групповой политики, предназначенные для пользователей ноутбуков и настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="57a45-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="57a45-310">Windows 10 Pro или Enterprise на Surface Hub 2 не позволяет экрану спать при сенсорном, мыши и клавиатуре, а также при встроенном обнаружении заполняемости человека (Doppler).</span><span class="sxs-lookup"><span data-stu-id="57a45-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="57a45-311">Обнаружение заполняемости человека включено по умолчанию, но при желании его можно отключить в UEFI, переключив параметр устройства в средство Конфигуратора Surface UEFI либо в рамках первоначальной миграции, либо путем создания и применения более позднего пакета конфигурации UEFI.</span><span class="sxs-lookup"><span data-stu-id="57a45-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="57a45-312">Управление питанием: параметры сна на экране и ПК</span><span class="sxs-lookup"><span data-stu-id="57a45-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="57a45-313">Выберите \*\*\*\*  >  **Начните**  >  **параметры**  >  **системной & сна.**</span><span class="sxs-lookup"><span data-stu-id="57a45-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="57a45-314">Установите ползунок режима питания на **лучшую производительность.**</span><span class="sxs-lookup"><span data-stu-id="57a45-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="57a45-315">Настройка значений экрана и сна в ваших предпочтениях, а также учет обнаружения присутствия Doppler, которое пробуждает устройство при обнаружении движения.</span><span class="sxs-lookup"><span data-stu-id="57a45-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="57a45-316">Соответственно, в качестве наилучшей практики рекомендуется настроить отключение экрана через **2** часа, а компьютер отключить **через 4 часа.**</span><span class="sxs-lookup"><span data-stu-id="57a45-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="57a45-317">Управление питанием: за исключением экрана</span><span class="sxs-lookup"><span data-stu-id="57a45-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="57a45-318">Поиск **параметров экрана блокировки** и **открытых параметров экрана блокировки.**</span><span class="sxs-lookup"><span data-stu-id="57a45-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="57a45-319">Настройка **параметров времени сохранения экрана** и **параметров** сохранения экрана в ваших предпочтениях.</span><span class="sxs-lookup"><span data-stu-id="57a45-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="57a45-320">Рекомендуемые значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="57a45-320">Recommended default values are:</span></span>

   - <span data-ttu-id="57a45-321">За исключением экрана (Нет) или за исключением экрана по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="57a45-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="57a45-322">Время ожидания до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="57a45-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="57a45-323">В резюме отобразить экран логотипа.</span><span class="sxs-lookup"><span data-stu-id="57a45-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="57a45-324">Управление питанием: групповой политики</span><span class="sxs-lookup"><span data-stu-id="57a45-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="57a45-325">Перед выполнением следующей процедуры обратитесь в ИТ-отдел для утверждения, чтобы исключить устройство Surface Hub 2S из глобальной политики управления питанием.</span><span class="sxs-lookup"><span data-stu-id="57a45-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="57a45-326">Некоторые параметры управления питанием могут отключить функцию обнаружения присутствия.</span><span class="sxs-lookup"><span data-stu-id="57a45-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="57a45-327">Поиск центра **программного обеспечения и** его открытие.</span><span class="sxs-lookup"><span data-stu-id="57a45-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="57a45-328">Выбор **параметров**.</span><span class="sxs-lookup"><span data-stu-id="57a45-328">Select **Options**.</span></span>

3. <span data-ttu-id="57a45-329">**Расширь управление power и** выберите Не применяй параметры питания из моего **ИТ-отдела на этот компьютер.**</span><span class="sxs-lookup"><span data-stu-id="57a45-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Параметры программного обеспечения](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="57a45-331">Контроль памяти</span><span class="sxs-lookup"><span data-stu-id="57a45-331">Storage Sense</span></span>

<span data-ttu-id="57a45-332">Surface Hub 2 имеет SSD объемом 128 ГБ для локального хранения, поэтому необходимо учитывать использование мер по экономии хранилища во время нормального использования.</span><span class="sxs-lookup"><span data-stu-id="57a45-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="57a45-333">Чтобы настроить чувство хранилища:</span><span class="sxs-lookup"><span data-stu-id="57a45-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="57a45-334">Поиск **параметров хранения,** которые находятся в **параметрах System.**</span><span class="sxs-lookup"><span data-stu-id="57a45-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="57a45-335">В **параметрах**выберите **включив чувство хранилища,** чтобы открыть страницу **параметры** хранилища.</span><span class="sxs-lookup"><span data-stu-id="57a45-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="57a45-336">Включи чувство **хранения в включить**.</span><span class="sxs-lookup"><span data-stu-id="57a45-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="57a45-337">Выберите **Настройте чувство хранилища или** запустите его сейчас и настройте параметры, чтобы держать файлы в сети как можно больше (из-за ограниченного пространства диска).</span><span class="sxs-lookup"><span data-stu-id="57a45-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="57a45-338">Рекомендуемые параметры:</span><span class="sxs-lookup"><span data-stu-id="57a45-338">Recommended settings:</span></span>

- <span data-ttu-id="57a45-339">Запустите чувство хранилища = каждый день.</span><span class="sxs-lookup"><span data-stu-id="57a45-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="57a45-340">Удаление временных файлов, которые не используют мои приложения = Каждые 14 дней (по крайней мере).</span><span class="sxs-lookup"><span data-stu-id="57a45-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="57a45-341">Удаление файлов в папке Загрузки, если они были там более = 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57a45-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="57a45-342">OneDrive: Контент станет только в Интернете, если не будет открыт более = 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57a45-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="57a45-343">Режим планшета</span><span class="sxs-lookup"><span data-stu-id="57a45-343">Tablet mode</span></span>

<span data-ttu-id="57a45-344">Включаем режим Tablet, если это необходимо для потребностей в доступности.</span><span class="sxs-lookup"><span data-stu-id="57a45-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="57a45-345">Параметры звука</span><span class="sxs-lookup"><span data-stu-id="57a45-345">Sound settings</span></span>

1. <span data-ttu-id="57a45-346">Поиск **параметров звуков и** откройте эту страницу.</span><span class="sxs-lookup"><span data-stu-id="57a45-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="57a45-347">Выберите **панель управления звуком** справа и выберите вкладку **Звуки.**</span><span class="sxs-lookup"><span data-stu-id="57a45-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="57a45-348">В **соответствии с программным набором** **событий подключение к устройству** **и отключение устройства** к **No**.</span><span class="sxs-lookup"><span data-stu-id="57a45-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="57a45-349">Уведомления о тишине</span><span class="sxs-lookup"><span data-stu-id="57a45-349">Silence notifications</span></span>

1. <span data-ttu-id="57a45-350">Поиск помощи **Фокус и** откройте эту страницу.</span><span class="sxs-lookup"><span data-stu-id="57a45-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="57a45-351">Выберите **только сигналы тревоги**.</span><span class="sxs-lookup"><span data-stu-id="57a45-351">Select **Alarms Only**.</span></span> <span data-ttu-id="57a45-352">Это позволит избежать постоянных вылетов уведомлений.</span><span class="sxs-lookup"><span data-stu-id="57a45-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="57a45-353">Очистка диска</span><span class="sxs-lookup"><span data-stu-id="57a45-353">Disk Cleanup</span></span>

1. <span data-ttu-id="57a45-354">Поиск **очистки диска и** открытие этого приложения.</span><span class="sxs-lookup"><span data-stu-id="57a45-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="57a45-355">В **статье Файлы для удаления**выберите файлы, которые вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="57a45-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="57a45-356">Кроме **того, выберите Очистка системных файлов**.</span><span class="sxs-lookup"><span data-stu-id="57a45-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="57a45-357">Завершение и проверка</span><span class="sxs-lookup"><span data-stu-id="57a45-357">Complete and verify</span></span>

1. <span data-ttu-id="57a45-358">Сканирование и установка всех обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="57a45-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="57a45-359">Обновление групповой политики.</span><span class="sxs-lookup"><span data-stu-id="57a45-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="57a45-360">При повышенной командной подсказке введите **gpupdate /force/boot/wait:0**.</span><span class="sxs-lookup"><span data-stu-id="57a45-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="57a45-361">Перезагрузите устройство.</span><span class="sxs-lookup"><span data-stu-id="57a45-361">Restart the device.</span></span>

4. <span data-ttu-id="57a45-362">Проверка приложений панели задач.</span><span class="sxs-lookup"><span data-stu-id="57a45-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="57a45-363">Подключение приложения</span><span class="sxs-lookup"><span data-stu-id="57a45-363">Connect App</span></span>
   - <span data-ttu-id="57a45-364">Значок блокировки</span><span class="sxs-lookup"><span data-stu-id="57a45-364">Lock Icon</span></span>
   - <span data-ttu-id="57a45-365">Набросок на фрагменте экрана</span><span class="sxs-lookup"><span data-stu-id="57a45-365">Snip & Sketch</span></span>
   - <span data-ttu-id="57a45-366">Teams (если применимо)</span><span class="sxs-lookup"><span data-stu-id="57a45-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="57a45-367">Приложения Office (если применимо)</span><span class="sxs-lookup"><span data-stu-id="57a45-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="57a45-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="57a45-368">Surface App</span></span>
   - <span data-ttu-id="57a45-369">Доска</span><span class="sxs-lookup"><span data-stu-id="57a45-369">Whiteboard</span></span>
    
5. <span data-ttu-id="57a45-370">Проверка обнаружения присутствия.</span><span class="sxs-lookup"><span data-stu-id="57a45-370">Verify presence detection.</span></span>

   - <span data-ttu-id="57a45-371">Обнаружение присутствия будет зеленым значком в подносе системы.</span><span class="sxs-lookup"><span data-stu-id="57a45-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="57a45-372">Проверка включения проеции на этот компьютер с помощью приложения Connect.</span><span class="sxs-lookup"><span data-stu-id="57a45-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="57a45-373">После настройки  **параметров Project на этом компьютере** запустите приложение Connect По крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="57a45-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="57a45-374">(Впоследствии приложение Connect не нужно запускать, чтобы проектов в Surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="57a45-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="57a45-375">Проверка параметров питания и сна.</span><span class="sxs-lookup"><span data-stu-id="57a45-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="57a45-376">Сохранение экрана: 15 минут, задав (нет), Mystify или Blank; убедитесь, что выбрано поле для запроса пароля.</span><span class="sxs-lookup"><span data-stu-id="57a45-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="57a45-377">Экран: **отключить через 2 часа**.</span><span class="sxs-lookup"><span data-stu-id="57a45-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="57a45-378">PC. **Выключите через 4 часа.**</span><span class="sxs-lookup"><span data-stu-id="57a45-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="57a45-379">Проверка работы Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="57a45-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="57a45-380">Убедитесь, что синхронизация параметров отключена.</span><span class="sxs-lookup"><span data-stu-id="57a45-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="57a45-381">Проверка запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="57a45-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="57a45-382">После установки и настройки Windows 10 surface Hub 2S можно управлять так же, как и любым другим устройством Windows 10.</span><span class="sxs-lookup"><span data-stu-id="57a45-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57a45-383">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="57a45-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="57a45-384">Переход на Windows 10 Pro или Корпоративная в Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="57a45-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
