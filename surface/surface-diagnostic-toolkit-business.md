---
title: Развертывание набора средств диагностики Surface для бизнеса
description: В этом разделе объясняется, как использовать surface Diagnostic набор средств для бизнеса.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271583"
---
# <span data-ttu-id="217d6-103">Развертывание набора средств диагностики Surface для бизнеса</span><span class="sxs-lookup"><span data-stu-id="217d6-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="217d6-104">Microsoft Surface Diagnostic набор средств for Business (SDT) позволяет ИТ-администраторам быстро изучать, устранять неполадки с оборудованием, программным обеспечением и микропрограммами на устройствах Surface, а также устранять их.</span><span class="sxs-lookup"><span data-stu-id="217d6-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="217d6-105">Вы можете выполнить ряд диагностических тестов и средств восстановления программного обеспечения в дополнение к получению анализа состояния устройства и инструкций по устранению проблем.</span><span class="sxs-lookup"><span data-stu-id="217d6-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="217d6-106">В частности, SDT для бизнеса позволяет:</span><span class="sxs-lookup"><span data-stu-id="217d6-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="217d6-107">Настройте пакет.</span><span class="sxs-lookup"><span data-stu-id="217d6-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="217d6-108">Запустите приложение с помощью команд.</span><span class="sxs-lookup"><span data-stu-id="217d6-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="217d6-109">Чтобы устранить неполадки, запустите несколько аппаратных тестов.</span><span class="sxs-lookup"><span data-stu-id="217d6-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="217d6-110">Создание журналов для анализа проблем.</span><span class="sxs-lookup"><span data-stu-id="217d6-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="217d6-111">Получите подробный отчет, сравнивающий устройство с оптимальной конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="217d6-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="217d6-112">Основные сценарии и ресурсы загрузки</span><span class="sxs-lookup"><span data-stu-id="217d6-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="217d6-113">Чтобы запустить SDT для бизнеса, скачайте компоненты, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="217d6-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="217d6-114">Режим</span><span class="sxs-lookup"><span data-stu-id="217d6-114">Mode</span></span> |  <span data-ttu-id="217d6-115">Основные сценарии</span><span class="sxs-lookup"><span data-stu-id="217d6-115">Primary scenarios</span></span> | <span data-ttu-id="217d6-116">Скачать</span><span class="sxs-lookup"><span data-stu-id="217d6-116">Download</span></span> | <span data-ttu-id="217d6-117">Подробнее</span><span class="sxs-lookup"><span data-stu-id="217d6-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="217d6-118">Режим рабочего стола</span><span class="sxs-lookup"><span data-stu-id="217d6-118">Desktop mode</span></span> |  <span data-ttu-id="217d6-119">Помощь пользователям в запуске SDT на устройствах Surface для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="217d6-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="217d6-120">Создайте пользовательский пакет для развертывания на одном или более устройствах Surface, чтобы пользователи выбирали определенные журналы для сбора и анализа.</span><span class="sxs-lookup"><span data-stu-id="217d6-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="217d6-121">Распространяемый пакет MSI SDT:</span><span class="sxs-lookup"><span data-stu-id="217d6-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="217d6-122">Установщик microsoft Surface Diagnostic набор средств для бизнеса</span><span class="sxs-lookup"><span data-stu-id="217d6-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="217d6-123">Поверхностные инструменты для ИТ</span><span class="sxs-lookup"><span data-stu-id="217d6-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="217d6-124">Использование средства диагностики Surface набор средств в настольном режиме</span><span class="sxs-lookup"><span data-stu-id="217d6-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="217d6-125">Командная строка</span><span class="sxs-lookup"><span data-stu-id="217d6-125">Command line</span></span> |  <span data-ttu-id="217d6-126">Напрямую устранять неполадки с устройствами Surface удаленно без участия пользователя с помощью стандартных средств, таких как Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="217d6-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="217d6-127">Он включает следующие команды:</span><span class="sxs-lookup"><span data-stu-id="217d6-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="217d6-128">собирает все файлы журнала</span><span class="sxs-lookup"><span data-stu-id="217d6-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="217d6-129">запускает диагностику состояния с помощью анализатора лучших практик.</span><span class="sxs-lookup"><span data-stu-id="217d6-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="217d6-130">проверяет Обновление Windows на наличие отсутствующих обновлений для микропрограмм или драйверов.</span><span class="sxs-lookup"><span data-stu-id="217d6-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="217d6-131">проверяет сведения о гарантии.</span><span class="sxs-lookup"><span data-stu-id="217d6-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="217d6-132">Консольное приложение SDT:</span><span class="sxs-lookup"><span data-stu-id="217d6-132">SDT console app:</span></span><br><span data-ttu-id="217d6-133">Консоль приложения диагностики Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="217d6-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="217d6-134">Поверхностные инструменты для ИТ</span><span class="sxs-lookup"><span data-stu-id="217d6-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="217d6-135">Запуск диагностики Surface набор средств с помощью команд</span><span class="sxs-lookup"><span data-stu-id="217d6-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="217d6-136">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="217d6-136">Supported devices</span></span> 

<span data-ttu-id="217d6-137">SDT для бизнеса поддерживается на устройствах Surface 3 и более поздних, в том числе:</span><span class="sxs-lookup"><span data-stu-id="217d6-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="217d6-138">Surface Book — все поколения</span><span class="sxs-lookup"><span data-stu-id="217d6-138">Surface Book - all generations</span></span>
- <span data-ttu-id="217d6-139">Surface Go — все поколения</span><span class="sxs-lookup"><span data-stu-id="217d6-139">Surface Go - all generations</span></span>
- <span data-ttu-id="217d6-140">Surface Laptop — все поколения</span><span class="sxs-lookup"><span data-stu-id="217d6-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="217d6-141">Surface Pro 3 и более поздние</span><span class="sxs-lookup"><span data-stu-id="217d6-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="217d6-142">Surface Pro X — все поколения</span><span class="sxs-lookup"><span data-stu-id="217d6-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="217d6-143">Surface Studio — все поколения</span><span class="sxs-lookup"><span data-stu-id="217d6-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="217d6-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="217d6-144">Surface 3 LTE</span></span>
- <span data-ttu-id="217d6-145">Surface 3</span><span class="sxs-lookup"><span data-stu-id="217d6-145">Surface 3</span></span>


## <span data-ttu-id="217d6-146">Установка surface Diagnostic набор средств для бизнеса</span><span class="sxs-lookup"><span data-stu-id="217d6-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="217d6-147">Чтобы создать пакет SDT, который можно распространить среди пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="217d6-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="217d6-148">Во sign in to your Surface device using the Administrator account.</span><span class="sxs-lookup"><span data-stu-id="217d6-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="217d6-149">Скачайте пакет установщика Windows SDT (MSI) со страницы загрузки [средств Surface для](https://www.microsoft.com/download/details.aspx?id=46703) ИТ-пользователей и скопируйте его в предпочтительное расположение на устройстве Surface, например на компьютере.</span><span class="sxs-lookup"><span data-stu-id="217d6-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="217d6-150">Появится мастер настройки SDT, как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="217d6-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="217d6-151">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="217d6-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="217d6-152">Если мастер настройки не появляется, убедитесь, что вы вписались в учетную запись администратора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="217d6-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Добро пожаловать в мастер настройки набор средств Surface Diagnostic набор средств](images/sdt-1.png)

    *<span data-ttu-id="217d6-154">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="217d6-154">Figure 1.</span></span> <span data-ttu-id="217d6-155">Мастер настройки набор средств Surface Diagnostic набор средств</span><span class="sxs-lookup"><span data-stu-id="217d6-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="217d6-156">Когда появится мастер установки SDT, нажмите **кнопку "Далее"** и примите лицензионное соглашение с конечным пользователем (EULA)</span><span class="sxs-lookup"><span data-stu-id="217d6-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="217d6-157">При желании на экране "Параметры установки" измените расположение установки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="217d6-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="217d6-158">В области "Тип установки" выберите **"Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="217d6-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="217d6-159">Стандартный параметр позволяет пользователям запускать средство диагностики непосредственно на своем устройстве Surface, если они вписались на свое устройство с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="217d6-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Параметры установки: расширенные](images/sdt-install.png)

7. <span data-ttu-id="217d6-161">Нажмите **кнопку** "Далее", а затем нажмите **кнопку "Установить".**</span><span class="sxs-lookup"><span data-stu-id="217d6-161">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="217d6-162">Установка с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="217d6-162">Installing using the command line</span></span>
<span data-ttu-id="217d6-163">При желании можно установить SDT в командной панели и установить настраиваемый флаг для установки средства в режиме администрирования.</span><span class="sxs-lookup"><span data-stu-id="217d6-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="217d6-164">SDT содержит следующие флаги вариантов установки:</span><span class="sxs-lookup"><span data-stu-id="217d6-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="217d6-165">отправляет данные телеметрии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="217d6-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="217d6-166">Флаг принимается для `0` отключения или `1` включения.</span><span class="sxs-lookup"><span data-stu-id="217d6-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="217d6-167">Значение по умолчанию — `1` отправка телеметрии.</span><span class="sxs-lookup"><span data-stu-id="217d6-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="217d6-168">настраивает средство для установки в режиме администрирования.</span><span class="sxs-lookup"><span data-stu-id="217d6-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="217d6-169">Флаг принимается для `0` режима клиента или для `1` ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="217d6-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="217d6-170">Значение по умолчанию— `0`.</span><span class="sxs-lookup"><span data-stu-id="217d6-170">The default value is `0`.</span></span>

### <span data-ttu-id="217d6-171">Чтобы установить SDT из командной строки:</span><span class="sxs-lookup"><span data-stu-id="217d6-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="217d6-172">Откройте командную подсказку и введите:</span><span class="sxs-lookup"><span data-stu-id="217d6-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="217d6-173">Пример.</span><span class="sxs-lookup"><span data-stu-id="217d6-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="217d6-174">Поиск SDT на устройстве Surface</span><span class="sxs-lookup"><span data-stu-id="217d6-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="217d6-175">SDT и консоль приложения SDT установлены `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` по</span><span class="sxs-lookup"><span data-stu-id="217d6-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="217d6-176">Помимо EXE-файла, SDT устанавливает JSON-файл и admin.dll (modules\admin.dll), как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="217d6-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![список установленных файлов SDT в проводнике](images/sdt-2.png)

*<span data-ttu-id="217d6-178">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="217d6-178">Figure 2.</span></span> <span data-ttu-id="217d6-179">Файлы, установленные SDT</span><span class="sxs-lookup"><span data-stu-id="217d6-179">Files installed by SDT</span></span>*

## <span data-ttu-id="217d6-180">Подготовка пакета SDT к распространению</span><span class="sxs-lookup"><span data-stu-id="217d6-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="217d6-181">Создание пользовательского пакета позволяет нацелить средство на определенные известные проблемы.</span><span class="sxs-lookup"><span data-stu-id="217d6-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="217d6-182">Нажмите **кнопку "> выполнить",** введите **Surface,** а затем выберите **"Surface Diagnostic набор средств for Business".**</span><span class="sxs-lookup"><span data-stu-id="217d6-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="217d6-183">Когда средство откроется, нажмите **кнопку "Создать настраиваемый пакет",** как показано на рисунке 3.</span><span class="sxs-lookup"><span data-stu-id="217d6-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Создание настраиваемого пакета](images/sdt-3.png)

    *<span data-ttu-id="217d6-185">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="217d6-185">Figure 3.</span></span> <span data-ttu-id="217d6-186">Создание пользовательского пакета</span><span class="sxs-lookup"><span data-stu-id="217d6-186">Create custom package</span></span>*

### <span data-ttu-id="217d6-187">Языковые параметры и параметры телеметрии</span><span class="sxs-lookup"><span data-stu-id="217d6-187">Language and telemetry settings</span></span>

  <span data-ttu-id="217d6-188">При создании пакета можно выбрать языковые параметры или отказаться от отправки данных телеметрии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="217d6-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="217d6-189">По умолчанию SDT отправляет телеметрию корпорации Майкрософт, которая используется для улучшения приложения в соответствии с заявлением [о конфиденциальности Корпорации Майкрософт.](https://privacy.microsoft.com/privacystatement)</span><span class="sxs-lookup"><span data-stu-id="217d6-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="217d6-190">Если вы хотите отклоировать, при создании пользовательского пакета необходимо сойтись с этого, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="217d6-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="217d6-191">Или сняйте **параметры отправки** телеметрии в Корпорацию Майкрософт на странице **"Параметры** установки" во время установки SDT.</span><span class="sxs-lookup"><span data-stu-id="217d6-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="217d6-192">Этот параметр не влияет на минимальную телеметрию, которая автоматически хранится на серверах Майкрософт при запуске тестов и восстановлений, для чего требуется подключение к Интернету, например обновление Windows и восстановление программного обеспечения, а также предоставление обратной связи с помощью кнопок "Смайлик" или "Нажми и работай" на панели инструментов приложения.</span><span class="sxs-lookup"><span data-stu-id="217d6-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Выбор языка и параметров телеметрии](images/sdt-4.png)

*<span data-ttu-id="217d6-194">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="217d6-194">Figure 4.</span></span> <span data-ttu-id="217d6-195">Выбор языка и параметров телеметрии</span><span class="sxs-lookup"><span data-stu-id="217d6-195">Select language and telemetry settings</span></span>*


### <span data-ttu-id="217d6-196">Страница "Обновление Windows"</span><span class="sxs-lookup"><span data-stu-id="217d6-196">Windows Update page</span></span>

<span data-ttu-id="217d6-197">Выберите вариант, подходящий для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="217d6-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="217d6-198">Большинство организаций с несколькими пользователями обычно выбирают получение обновлений через cлужбы Windows Server Update Services (WSUS), как показано на рисунке 5.</span><span class="sxs-lookup"><span data-stu-id="217d6-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="217d6-199">При использовании локальных пакетов Обновления Windows или WSUS введите путь соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="217d6-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Выбор параметра "Обновление Windows"](images/sdt-5.png)

*<span data-ttu-id="217d6-201">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="217d6-201">Figure 5.</span></span> <span data-ttu-id="217d6-202">Параметр "Обновление Windows"</span><span class="sxs-lookup"><span data-stu-id="217d6-202">Windows Update option</span></span>*

### <span data-ttu-id="217d6-203">Страница восстановления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="217d6-203">Software repair page</span></span>

<span data-ttu-id="217d6-204">Это позволяет выбрать или удалить параметр для запуска обновлений для восстановления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="217d6-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![Выбор варианта восстановления программного обеспечения](images/sdt-6.png)

*<span data-ttu-id="217d6-206">Рисунок 6.</span><span class="sxs-lookup"><span data-stu-id="217d6-206">Figure 6.</span></span> <span data-ttu-id="217d6-207">Вариант восстановления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="217d6-207">Software repair option</span></span>*

### <span data-ttu-id="217d6-208">Сбор журналов и сохранение страницы пакета</span><span class="sxs-lookup"><span data-stu-id="217d6-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="217d6-209">Можно выбрать запуск широкого диапазона журналов в различных приложениях, драйверах, оборудовании и операционной системе.</span><span class="sxs-lookup"><span data-stu-id="217d6-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="217d6-210">Щелкните соответствующую область и выберите в меню доступных журналов.</span><span class="sxs-lookup"><span data-stu-id="217d6-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="217d6-211">Затем можно сохранить пакет в точке распространения программного обеспечения или эквивалентной точке, к которую пользователи могут получить доступ.</span><span class="sxs-lookup"><span data-stu-id="217d6-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Выбор параметров журнала](images/sdt-7.png)

*<span data-ttu-id="217d6-213">Рисунок 7.</span><span class="sxs-lookup"><span data-stu-id="217d6-213">Figure 7.</span></span> <span data-ttu-id="217d6-214">Параметр журнала и сохранение пакета</span><span class="sxs-lookup"><span data-stu-id="217d6-214">Log option and save package</span></span>*

## <span data-ttu-id="217d6-215">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="217d6-215">Next steps</span></span>

- [<span data-ttu-id="217d6-216">Использование набора средств диагностики Surface для бизнеса в режиме настольного компьютера</span><span class="sxs-lookup"><span data-stu-id="217d6-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="217d6-217">Использование средств диагностики Surface набор средств для бизнеса с помощью команд</span><span class="sxs-lookup"><span data-stu-id="217d6-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="217d6-218">Изменения и обновления</span><span class="sxs-lookup"><span data-stu-id="217d6-218">Changes and updates</span></span>

### <span data-ttu-id="217d6-219">Версия 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-219">Version 2.131.139.0</span></span>

<span data-ttu-id="217d6-220">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="217d6-221">Поддержка Surface Pro 7 и более</span><span class="sxs-lookup"><span data-stu-id="217d6-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="217d6-222">Беспробумная поддержка на Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="217d6-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="217d6-223">Улучшения безопасности</span><span class="sxs-lookup"><span data-stu-id="217d6-223">Security improvements</span></span>
- <span data-ttu-id="217d6-224">Улучшения инклюзивного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="217d6-224">Inclusive user experience improvements</span></span>

### <span data-ttu-id="217d6-225">Версия 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-225">Version 2.124.139.0</span></span>

<span data-ttu-id="217d6-226">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="217d6-227">Бесшовная интегрированная поддержка</span><span class="sxs-lookup"><span data-stu-id="217d6-227">Seamless integrated support</span></span>
- <span data-ttu-id="217d6-228">Сохранение всех результатов тестирования</span><span class="sxs-lookup"><span data-stu-id="217d6-228">Save all test results</span></span>
- <span data-ttu-id="217d6-229">Проверьте, создан ли пользовательский образ</span><span class="sxs-lookup"><span data-stu-id="217d6-229">Check if the image is custom created</span></span>
- <span data-ttu-id="217d6-230">Включить предупреждения от диспетчера устройств</span><span class="sxs-lookup"><span data-stu-id="217d6-230">Include warnings from device manager</span></span>
- <span data-ttu-id="217d6-231">Версия микропрограммы док-станции</span><span class="sxs-lookup"><span data-stu-id="217d6-231">Dock firmware version</span></span>
- <span data-ttu-id="217d6-232">Пометка дисков как потенциальных сбоев в тесте хранилища</span><span class="sxs-lookup"><span data-stu-id="217d6-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="217d6-233">Удаление ссылки на магазин</span><span class="sxs-lookup"><span data-stu-id="217d6-233">Remove store link</span></span> 

### <span data-ttu-id="217d6-234">Версия 2.121.139</span><span class="sxs-lookup"><span data-stu-id="217d6-234">Version 2.121.139</span></span>
*<span data-ttu-id="217d6-235">Дата выпуска: 31 июля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="217d6-236">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="217d6-237">Беспробумная поддержка</span><span class="sxs-lookup"><span data-stu-id="217d6-237">Seamless support experience</span></span>
- <span data-ttu-id="217d6-238">Исправления ошибок</span><span class="sxs-lookup"><span data-stu-id="217d6-238">Bug fixes</span></span>

### <span data-ttu-id="217d6-239">Версия 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="217d6-240">Дата выпуска: 11 мая 2020 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="217d6-241">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="217d6-242">Возможность пропустить Обновление Windows для проверки оборудования.</span><span class="sxs-lookup"><span data-stu-id="217d6-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="217d6-243">Возможность получения уведомлений о последнем обновлении версии</span><span class="sxs-lookup"><span data-stu-id="217d6-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="217d6-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="217d6-244">Surface Go 2</span></span>
- <span data-ttu-id="217d6-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="217d6-245">Surface Book 3</span></span>
- <span data-ttu-id="217d6-246">Показать индикатор хода выполнения</span><span class="sxs-lookup"><span data-stu-id="217d6-246">Show progress indicator</span></span>


### <span data-ttu-id="217d6-247">Версия 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="217d6-248">Дата выпуска: 21 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="217d6-249">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="217d6-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="217d6-250">Surface Pro 7</span></span>
- <span data-ttu-id="217d6-251">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="217d6-251">Surface Laptop 3</span></span>

### <span data-ttu-id="217d6-252">Версия 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="217d6-253">Дата выпуска: 24 сентября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="217d6-254">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="217d6-255">Возможность загрузки аппаратных отчетов.</span><span class="sxs-lookup"><span data-stu-id="217d6-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="217d6-256">Возможность обращаться в службу поддержки Майкрософт непосредственно из средства.</span><span class="sxs-lookup"><span data-stu-id="217d6-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="217d6-257">Версия 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="217d6-258">Дата выпуска: 24 июня 2019 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="217d6-259">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="217d6-260">Сведения о версии драйвера, включенные в журналы и отчеты.</span><span class="sxs-lookup"><span data-stu-id="217d6-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="217d6-261">Возможность предоставлять отзывы о приложении.</span><span class="sxs-lookup"><span data-stu-id="217d6-261">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="217d6-262">Версия 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="217d6-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="217d6-263">Дата выпуска: 26 апреля 2019 г.</span><span class="sxs-lookup"><span data-stu-id="217d6-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="217d6-264">Эта версия Surface Diagnostic набор средств для бизнеса добавляет поддержку следующих средств:</span><span class="sxs-lookup"><span data-stu-id="217d6-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="217d6-265">Дополнительный параметр установки для разблокировки возможностей администратора с помощью пользовательского интерфейса установщика без необходимости настройки командной строки.</span><span class="sxs-lookup"><span data-stu-id="217d6-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="217d6-266">Улучшения доступности.</span><span class="sxs-lookup"><span data-stu-id="217d6-266">Accessibility improvements.</span></span>
- <span data-ttu-id="217d6-267">Параметры управления яркостью поверхности, включенные в журналы.</span><span class="sxs-lookup"><span data-stu-id="217d6-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="217d6-268">Ссылка на поддержку совместимости внешнего монитора в генераторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="217d6-268">External monitor compatibility support link in report generator.</span></span>
