---
title: Развертывание набора средств диагностики Surface для бизнеса
description: В этой статье объясняется, как использовать набор средств диагностики Surface для бизнеса.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 05/11/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 9233ca1f7e32e2017424e9fb6ceb0556de9d37bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834299"
---
# <span data-ttu-id="ae803-103">Развертывание набора средств диагностики Surface для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ae803-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="ae803-104">Набор средств Microsoft Surface Diagnostic Toolkit для бизнеса (SDT) позволяет ИТ-администраторам быстро находить, устранять проблемы с оборудованием, программным обеспечением и встроенными микрокодом с помощью устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="ae803-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="ae803-105">Вы можете выполнять диапазон диагностических тестов и восстановление программного обеспечения в дополнение к получению сведений о работоспособности устройств и руководство по устранению проблем.</span><span class="sxs-lookup"><span data-stu-id="ae803-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="ae803-106">В частности, SDT для бизнеса позволяет:</span><span class="sxs-lookup"><span data-stu-id="ae803-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="ae803-107">Настройте пакет.</span><span class="sxs-lookup"><span data-stu-id="ae803-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="ae803-108">Запустите приложение с помощью команд.</span><span class="sxs-lookup"><span data-stu-id="ae803-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="ae803-109">Запустите несколько тестов оборудования, чтобы устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="ae803-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="ae803-110">Создание журналов для анализа проблем.</span><span class="sxs-lookup"><span data-stu-id="ae803-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="ae803-111">Получите подробный отчет о сравнении устройств и оптимальной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ae803-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="ae803-112">Основные сценарии и загружаемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="ae803-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="ae803-113">Чтобы запустить SDT для бизнеса, скачайте компоненты, указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="ae803-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="ae803-114">Режим</span><span class="sxs-lookup"><span data-stu-id="ae803-114">Mode</span></span> |  <span data-ttu-id="ae803-115">Основные сценарии</span><span class="sxs-lookup"><span data-stu-id="ae803-115">Primary scenarios</span></span> | <span data-ttu-id="ae803-116">Скачать</span><span class="sxs-lookup"><span data-stu-id="ae803-116">Download</span></span> | <span data-ttu-id="ae803-117">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ae803-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="ae803-118">Режим рабочего стола</span><span class="sxs-lookup"><span data-stu-id="ae803-118">Desktop mode</span></span> |  <span data-ttu-id="ae803-119">Помощь пользователям в работе SDT на устройствах Surface для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="ae803-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="ae803-120">Создание настраиваемого пакета для развертывания на одном или нескольких устройствах Surface, позволяющих пользователям выбирать конкретные журналы для сбора и анализа.</span><span class="sxs-lookup"><span data-stu-id="ae803-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="ae803-121">SDT распространяемый пакет MSI:</span><span class="sxs-lookup"><span data-stu-id="ae803-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="ae803-122">Набор средств диагностики Surface (Майкрософт) для бизнес-установки</span><span class="sxs-lookup"><span data-stu-id="ae803-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="ae803-123">Поверхностные инструменты для ИТ</span><span class="sxs-lookup"><span data-stu-id="ae803-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="ae803-124">Использование набора средств диагностики Surface в классическом режиме</span><span class="sxs-lookup"><span data-stu-id="ae803-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="ae803-125">Командная строка</span><span class="sxs-lookup"><span data-stu-id="ae803-125">Command line</span></span> |  <span data-ttu-id="ae803-126">Непосредственное устранение неполадок с устройством Surface с помощью стандартных средств, таких как Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ae803-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="ae803-127">Она включает следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ae803-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="ae803-128">сбор всех файлов журнала</span><span class="sxs-lookup"><span data-stu-id="ae803-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="ae803-129">запускает диагностику работоспособности с помощью анализатора соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="ae803-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="ae803-130">Проверка центра обновления Windows на наличие отсутствующих микропрограмм или обновлений драйверов.</span><span class="sxs-lookup"><span data-stu-id="ae803-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="ae803-131">Проверка гарантийной информации.</span><span class="sxs-lookup"><span data-stu-id="ae803-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="ae803-132">Приложение консоли SDT:</span><span class="sxs-lookup"><span data-stu-id="ae803-132">SDT console app:</span></span><br><span data-ttu-id="ae803-133">Консоль приложения "Диагностика Surface" (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ae803-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="ae803-134">Поверхностные инструменты для ИТ</span><span class="sxs-lookup"><span data-stu-id="ae803-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="ae803-135">Запуск средства диагностики Surface Toolkit с помощью команд</span><span class="sxs-lookup"><span data-stu-id="ae803-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="ae803-136">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="ae803-136">Supported devices</span></span> 

<span data-ttu-id="ae803-137">SDT для бизнеса поддерживается на устройствах Surface 3 и более поздних версий, в том числе:</span><span class="sxs-lookup"><span data-stu-id="ae803-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="ae803-138">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="ae803-138">Surface Book 3</span></span>
- <span data-ttu-id="ae803-139">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="ae803-139">Surface Go 2</span></span>
- <span data-ttu-id="ae803-140">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ae803-140">Surface Pro X</span></span>
- <span data-ttu-id="ae803-141">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ae803-141">Surface Pro 7</span></span>
- <span data-ttu-id="ae803-142">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="ae803-142">Surface Laptop 3</span></span>
- <span data-ttu-id="ae803-143">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="ae803-143">Surface Pro 6</span></span>
- <span data-ttu-id="ae803-144">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="ae803-144">Surface Laptop 2</span></span>
- <span data-ttu-id="ae803-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="ae803-145">Surface Go</span></span>
- <span data-ttu-id="ae803-146">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="ae803-146">Surface Go with LTE</span></span>
- <span data-ttu-id="ae803-147">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="ae803-147">Surface Book 2</span></span>
- <span data-ttu-id="ae803-148">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="ae803-148">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="ae803-149">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="ae803-149">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="ae803-150">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="ae803-150">Surface Laptop</span></span>
- <span data-ttu-id="ae803-151">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="ae803-151">Surface Studio</span></span>
- <span data-ttu-id="ae803-152">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="ae803-152">Surface Studio 2</span></span>
- <span data-ttu-id="ae803-153">Surface Book</span><span class="sxs-lookup"><span data-stu-id="ae803-153">Surface Book</span></span>
- <span data-ttu-id="ae803-154">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="ae803-154">Surface Pro 4</span></span>
- <span data-ttu-id="ae803-155">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="ae803-155">Surface 3 LTE</span></span>
- <span data-ttu-id="ae803-156">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ae803-156">Surface 3</span></span>
- <span data-ttu-id="ae803-157">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="ae803-157">Surface Pro 3</span></span>

## <span data-ttu-id="ae803-158">Установка набора средств диагностики Surface для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ae803-158">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="ae803-159">Чтобы создать пакет SDT, который вы можете распространять пользователям в своей организации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ae803-159">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="ae803-160">Войдите на устройство Surface с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="ae803-160">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="ae803-161">Скачайте пакет установщика Windows (MSI-файл) SDT на [странице Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) и скопируйте его в нужное место на устройстве Surface, например на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae803-161">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="ae803-162">Откроется мастер настройки SDT, как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="ae803-162">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="ae803-163">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae803-163">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="ae803-164">Если мастер настройки не отображается, убедитесь в том, что вы вошли в учетную запись администратора на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae803-164">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Добро пожаловать в мастер настройки средства диагностики Surface Toolkit](images/sdt-1.png)

    *<span data-ttu-id="ae803-166">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="ae803-166">Figure 1.</span></span> <span data-ttu-id="ae803-167">Мастер настройки набора средств диагностики Surface</span><span class="sxs-lookup"><span data-stu-id="ae803-167">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="ae803-168">Когда появится мастер настройки SDT, нажмите кнопку **Далее**, приняв условия лицензионного соглашения конечного пользователя (EULA)</span><span class="sxs-lookup"><span data-stu-id="ae803-168">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="ae803-169">На экране параметры установки измените расположение для установки по умолчанию (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="ae803-169">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="ae803-170">В разделе Тип настройки выберите пункт **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ae803-170">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="ae803-171">Стандартный параметр позволяет пользователям запускать средство диагностики прямо на устройстве Surface, если они вошли в систему с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="ae803-171">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Варианты установки: дополнительно](images/sdt-install.png)

7. <span data-ttu-id="ae803-173">Нажмите кнопку **Далее** , а затем — **установить**.</span><span class="sxs-lookup"><span data-stu-id="ae803-173">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="ae803-174">Установка с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="ae803-174">Installing using the command line</span></span>
<span data-ttu-id="ae803-175">При необходимости вы можете установить SDT в командной строке и установить настраиваемый флажок, чтобы установить средство в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="ae803-175">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="ae803-176">SDT включает следующие флаги параметров установки:</span><span class="sxs-lookup"><span data-stu-id="ae803-176">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="ae803-177">Отправка телеметрических данных в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae803-177">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="ae803-178">Этот флаг принимает состояние " `0` Отключено" или " `1` включено".</span><span class="sxs-lookup"><span data-stu-id="ae803-178">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="ae803-179">Значение по умолчанию — `1` Отправить телеметрию.</span><span class="sxs-lookup"><span data-stu-id="ae803-179">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="ae803-180">Настройка установки средства в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="ae803-180">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="ae803-181">Этот флаг принимается `0` для клиентского режима или `1` режима ИТ администратора.</span><span class="sxs-lookup"><span data-stu-id="ae803-181">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="ae803-182">Значение по умолчанию— `0`.</span><span class="sxs-lookup"><span data-stu-id="ae803-182">The default value is `0`.</span></span>

### <span data-ttu-id="ae803-183">Чтобы установить SDT из командной строки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ae803-183">To install SDT from the command line:</span></span>

1. <span data-ttu-id="ae803-184">Откройте командную команду и введите:</span><span class="sxs-lookup"><span data-stu-id="ae803-184">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="ae803-185">Пример.</span><span class="sxs-lookup"><span data-stu-id="ae803-185">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="ae803-186">Расположение SDT на устройстве Surface</span><span class="sxs-lookup"><span data-stu-id="ae803-186">Locating SDT on your Surface device</span></span>

<span data-ttu-id="ae803-187">Оба SDT и консоль приложения SDT устанавливаются по адресу `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="ae803-187">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="ae803-188">Помимо exe-файла, SDT устанавливает JSON-файл и файл admin.dll (modules\admin.dll), как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="ae803-188">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![список установленных файлов SDT в проводнике](images/sdt-2.png)

*<span data-ttu-id="ae803-190">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="ae803-190">Figure 2.</span></span> <span data-ttu-id="ae803-191">Файлы, установленные SDT</span><span class="sxs-lookup"><span data-stu-id="ae803-191">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="ae803-192">Подготовка пакета SDT для распространения</span><span class="sxs-lookup"><span data-stu-id="ae803-192">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="ae803-193">Создание настраиваемого пакета позволяет нацелить средство на конкретные известные проблемы.</span><span class="sxs-lookup"><span data-stu-id="ae803-193">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="ae803-194">Нажмите кнопку **пуск > выполнить**, введите **Surface** и щелкните **набор средств диагностики Surface для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ae803-194">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="ae803-195">Когда откроется средство, нажмите **создать настраиваемый пакет**, как показано на рис. 3.</span><span class="sxs-lookup"><span data-stu-id="ae803-195">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Параметр "создать пользовательский пакет"](images/sdt-3.png)

    *<span data-ttu-id="ae803-197">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="ae803-197">Figure 3.</span></span> <span data-ttu-id="ae803-198">Создание настраиваемого пакета</span><span class="sxs-lookup"><span data-stu-id="ae803-198">Create custom package</span></span>*

### <span data-ttu-id="ae803-199">Параметры языка и телеметрии</span><span class="sxs-lookup"><span data-stu-id="ae803-199">Language and telemetry settings</span></span>

  <span data-ttu-id="ae803-200">При создании пакета вы можете выбрать языковые параметры или отказаться от отправки сведений о телеметрии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae803-200">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="ae803-201">По умолчанию SDT отправляет телеметрию в корпорацию Майкрософт, которая используется для улучшения приложения в соответствии с заявлением [о конфиденциальности корпорации Майкрософт](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="ae803-201">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="ae803-202">Если вы хотите отклонить, снимите флажок при создании настраиваемого пакета, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ae803-202">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="ae803-203">Или снимите флажок **Отправить телеметрию в Microsoft** на странице **параметров установки** во время настройки SDT.</span><span class="sxs-lookup"><span data-stu-id="ae803-203">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="ae803-204">Этот параметр не влияет на минимальную телеметрию, которая автоматически хранится на серверах Microsoft при выполнении тестов и исправлений, требующих подключения к Интернету, таких как обновление Windows и восстановление программного обеспечения, и Отправка отзывов с помощью кнопок улыбки и frown на панели инструментов приложения.</span><span class="sxs-lookup"><span data-stu-id="ae803-204">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Выбор параметров языка и телеметрии](images/sdt-4.png)

*<span data-ttu-id="ae803-206">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="ae803-206">Figure 4.</span></span> <span data-ttu-id="ae803-207">Выбор параметров языка и телеметрии</span><span class="sxs-lookup"><span data-stu-id="ae803-207">Select language and telemetry settings</span></span>*


### <span data-ttu-id="ae803-208">Страница центра обновления Windows</span><span class="sxs-lookup"><span data-stu-id="ae803-208">Windows Update page</span></span>

<span data-ttu-id="ae803-209">Выберите подходящий вариант для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ae803-209">Select the option appropriate for your organization.</span></span> <span data-ttu-id="ae803-210">В большинстве организаций с несколькими пользователями обычно выбирается получение обновлений через службы Windows Server Update Services (WSUS), как показано на рисунке 5.</span><span class="sxs-lookup"><span data-stu-id="ae803-210">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="ae803-211">Если у вас есть локальные пакеты обновления для Windows или WSUS, введите путь нужным образом.</span><span class="sxs-lookup"><span data-stu-id="ae803-211">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Выберите пункт "обновить Windows"](images/sdt-5.png)

*<span data-ttu-id="ae803-213">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="ae803-213">Figure 5.</span></span> <span data-ttu-id="ae803-214">Параметр центра обновления Windows</span><span class="sxs-lookup"><span data-stu-id="ae803-214">Windows Update option</span></span>*

### <span data-ttu-id="ae803-215">Страница восстановления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="ae803-215">Software repair page</span></span>

<span data-ttu-id="ae803-216">Это позволяет выбрать или удалить параметр для запуска обновлений программы восстановления программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="ae803-216">This allows you to select or remove the option to run software repair updates.</span></span> 

![Выбор варианта восстановления программного обеспечения](images/sdt-6.png)

*<span data-ttu-id="ae803-218">Рисунок 6.</span><span class="sxs-lookup"><span data-stu-id="ae803-218">Figure 6.</span></span> <span data-ttu-id="ae803-219">Вариант восстановления программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="ae803-219">Software repair option</span></span>*

### <span data-ttu-id="ae803-220">Страница сбора журналов и сохранение пакета</span><span class="sxs-lookup"><span data-stu-id="ae803-220">Collecting logs and saving package page</span></span>

<span data-ttu-id="ae803-221">Вы можете использовать широкий диапазон журналов для разных приложений, драйверов, оборудования и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ae803-221">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="ae803-222">Щелкните соответствующую область и выберите в меню доступные журналы.</span><span class="sxs-lookup"><span data-stu-id="ae803-222">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="ae803-223">Затем вы можете сохранить пакет в точку распространения программного обеспечения или аналогичное расположение, к которому пользователи смогут получить доступ.</span><span class="sxs-lookup"><span data-stu-id="ae803-223">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Выбор параметров журнала](images/sdt-7.png)

*<span data-ttu-id="ae803-225">Рисунок 7.</span><span class="sxs-lookup"><span data-stu-id="ae803-225">Figure 7.</span></span> <span data-ttu-id="ae803-226">Параметр log и сохранение пакета</span><span class="sxs-lookup"><span data-stu-id="ae803-226">Log option and save package</span></span>*

## <span data-ttu-id="ae803-227">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ae803-227">Next steps</span></span>

- [<span data-ttu-id="ae803-228">Использование набора средств диагностики Surface для бизнеса в режиме настольного компьютера</span><span class="sxs-lookup"><span data-stu-id="ae803-228">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="ae803-229">Использование команд средства диагностики Surface для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ae803-229">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="ae803-230">Изменения и обновления</span><span class="sxs-lookup"><span data-stu-id="ae803-230">Changes and updates</span></span>

### <span data-ttu-id="ae803-231">Версия 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="ae803-231">Version 2.94.139.0</span></span>
*<span data-ttu-id="ae803-232">Дата выпуска: 11 мая 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ae803-232">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="ae803-233">В этой версии набора средств диагностики Surface для бизнеса добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ae803-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="ae803-234">Возможность пропуска центра обновления Windows для выполнения проверки оборудования.</span><span class="sxs-lookup"><span data-stu-id="ae803-234">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="ae803-235">Возможность получать уведомления о последних обновлениях версий</span><span class="sxs-lookup"><span data-stu-id="ae803-235">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="ae803-236">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="ae803-236">Surface Go 2</span></span>
- <span data-ttu-id="ae803-237">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="ae803-237">Surface Book 3</span></span>
- <span data-ttu-id="ae803-238">Показать индикатор хода выполнения</span><span class="sxs-lookup"><span data-stu-id="ae803-238">Show progress indicator</span></span>


### <span data-ttu-id="ae803-239">Версия 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="ae803-239">Version 2.43.139.0</span></span>
*<span data-ttu-id="ae803-240">Дата выпуска: 21 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="ae803-240">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="ae803-241">В этой версии набора средств диагностики Surface для бизнеса добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ae803-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="ae803-242">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ae803-242">Surface Pro 7</span></span>
- <span data-ttu-id="ae803-243">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="ae803-243">Surface Laptop 3</span></span>

### <span data-ttu-id="ae803-244">Версия 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="ae803-244">Version 2.42.139.0</span></span>
*<span data-ttu-id="ae803-245">Дата выпуска: 24 сентября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="ae803-245">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="ae803-246">В этой версии набора средств диагностики Surface для бизнеса добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ae803-246">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="ae803-247">Возможность скачивания отчетов об оборудовании.</span><span class="sxs-lookup"><span data-stu-id="ae803-247">Ability to download hardware reports.</span></span>
- <span data-ttu-id="ae803-248">Возможность обратиться в службу поддержки Майкрософт прямо из средства.</span><span class="sxs-lookup"><span data-stu-id="ae803-248">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="ae803-249">Версия 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="ae803-249">Version 2.41.139.0</span></span>
*<span data-ttu-id="ae803-250">Дата выпуска: 24 июня 2019 г.</span><span class="sxs-lookup"><span data-stu-id="ae803-250">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="ae803-251">В этой версии набора средств диагностики Surface для бизнеса добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ae803-251">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="ae803-252">Сведения о версии драйвера, включенные в журналы и отчет.</span><span class="sxs-lookup"><span data-stu-id="ae803-252">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="ae803-253">Возможность предоставления отзывов о приложении.</span><span class="sxs-lookup"><span data-stu-id="ae803-253">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="ae803-254">Версия 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="ae803-254">Version 2.36.139.0</span></span>
*<span data-ttu-id="ae803-255">Дата выпуска: 26 апреля 2019 г.</span><span class="sxs-lookup"><span data-stu-id="ae803-255">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="ae803-256">В этой версии набора средств диагностики Surface для бизнеса добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ae803-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="ae803-257">Параметр расширенной настройки для разблокировки возможностей администратора через пользовательский интерфейс установщика без необходимости настройки командной строки.</span><span class="sxs-lookup"><span data-stu-id="ae803-257">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="ae803-258">Улучшения специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="ae803-258">Accessibility improvements.</span></span>
- <span data-ttu-id="ae803-259">Параметры контроля яркости поверхности, включенные в журналы.</span><span class="sxs-lookup"><span data-stu-id="ae803-259">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="ae803-260">Ссылка на поддержку внешних мониторов в генераторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="ae803-260">External monitor compatibility support link in report generator.</span></span>
