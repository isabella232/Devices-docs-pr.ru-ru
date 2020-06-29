---
title: Использование набора средств диагностики Surface для бизнеса в режиме настольного компьютера
description: Как использовать SDT, чтобы помочь пользователям в вашей организации запускать средство для выявления проблем с устройством Surface и их диагностики.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834267"
---
# <span data-ttu-id="32915-103">Использование набора средств диагностики Surface для бизнеса в режиме настольного компьютера</span><span class="sxs-lookup"><span data-stu-id="32915-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="32915-104">В этой статье объясняется, как использовать набор средств диагностики Surface (SDT), чтобы помочь пользователям в вашей организации запустить средство для выявления проблем с устройством Surface и их диагностики.</span><span class="sxs-lookup"><span data-stu-id="32915-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with the Surface device.</span></span> <span data-ttu-id="32915-105">Успешное выполнение SDT может быстро определить, возникает ли причина ошибки, вызванная сбоем оборудования или пользователем.</span><span class="sxs-lookup"><span data-stu-id="32915-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="32915-106">Список поддерживаемых устройств Surface в SDT можно найти в [инструментальном средстве "развертывание Surface Diagnostic Toolkit для бизнеса](surface-diagnostic-toolkit-business.md)".</span><span class="sxs-lookup"><span data-stu-id="32915-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="32915-107">Направляйте пользователя установить [пакет SDT](surface-diagnostic-toolkit-business.md#create-custom-sdt) из точки распространения программного обеспечения или сетевого общего доступа.</span><span class="sxs-lookup"><span data-stu-id="32915-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="32915-108">После установки вы можете приступить к планированию пользователей с помощью серии тестов.</span><span class="sxs-lookup"><span data-stu-id="32915-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="32915-109">Начните с домашней страницы, с помощью которой пользователи могут ввести описание неполадки, и нажмите кнопку **продолжить**, как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="32915-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="32915-110">Запуск SDT в классическом режиме рабочего стола ](images/sdt-desk-1.png)
 *Рисунок 1. SDT в классическом режиме*</span><span class="sxs-lookup"><span data-stu-id="32915-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="32915-111">Когда SDT указывает на устройство с последними обновлениями, нажмите кнопку **продолжить** , чтобы перейти к каталогу доступных тестов, как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="32915-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="32915-112">Выберите один из SDT параметров ](images/sdt-desk-2.png)
 *на рисунке 2. Выбор из параметров SDT*</span><span class="sxs-lookup"><span data-stu-id="32915-112">Select from SDT options](images/sdt-desk-2.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="32915-113">Вы можете выбрать выполнение всех диагностических тестов.</span><span class="sxs-lookup"><span data-stu-id="32915-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="32915-114">Или, если вы уже подозреваете, что определенная проблема, например ошибка монитора или источника питания, нажмите кнопку **выбрать** , чтобы выбрать один из доступных тестов, и нажмите кнопку **выполнить**, как показано на рисунке 3.</span><span class="sxs-lookup"><span data-stu-id="32915-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="32915-115">В таблице ниже приведены подробные сведения о каждом тесте.</span><span class="sxs-lookup"><span data-stu-id="32915-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="32915-116">Щелкните "тестирование оборудования" ](images/sdt-desk-3.png)
 *на рисунке 3. Выбор тестов оборудования*</span><span class="sxs-lookup"><span data-stu-id="32915-116">Select hardware tests](images/sdt-desk-3.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="32915-117">Проверка оборудования</span><span class="sxs-lookup"><span data-stu-id="32915-117">Hardware test</span></span> | <span data-ttu-id="32915-118">Описание</span><span class="sxs-lookup"><span data-stu-id="32915-118">Description</span></span>
    --- | ---
    <span data-ttu-id="32915-119">Источник питания и батарея</span><span class="sxs-lookup"><span data-stu-id="32915-119">Power Supply and Battery</span></span> |  <span data-ttu-id="32915-120">Проверка работоспособности модуля питания в оптимальном варианте</span><span class="sxs-lookup"><span data-stu-id="32915-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="32915-121">Экран и звук</span><span class="sxs-lookup"><span data-stu-id="32915-121">Display and Sound</span></span>   | <span data-ttu-id="32915-122">Проверка яркости, зависания и исчезновения пикселов, динамиков и микрофона</span><span class="sxs-lookup"><span data-stu-id="32915-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="32915-123">Порты и аксессуары</span><span class="sxs-lookup"><span data-stu-id="32915-123">Ports and Accessories</span></span>   | <span data-ttu-id="32915-124">Проверка принадлежности, экрана и USB-соединения</span><span class="sxs-lookup"><span data-stu-id="32915-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="32915-125">Connectivity</span><span class="sxs-lookup"><span data-stu-id="32915-125">Connectivity</span></span> |  <span data-ttu-id="32915-126">Проверка подключения Bluetooth, беспроводного и LTE</span><span class="sxs-lookup"><span data-stu-id="32915-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="32915-127">Безопасность</span><span class="sxs-lookup"><span data-stu-id="32915-127">Security</span></span>    | <span data-ttu-id="32915-128">Проверка проблем, связанных с безопасностью</span><span class="sxs-lookup"><span data-stu-id="32915-128">Checks security related issues</span></span>
    <span data-ttu-id="32915-129">Сенсорный ввод</span><span class="sxs-lookup"><span data-stu-id="32915-129">Touch</span></span>   | <span data-ttu-id="32915-130">Проверка проблем, связанных с касанием</span><span class="sxs-lookup"><span data-stu-id="32915-130">Checks touch related issues</span></span>
    <span data-ttu-id="32915-131">Клавиатура и сенсорный ввод</span><span class="sxs-lookup"><span data-stu-id="32915-131">Keyboard and touch</span></span> |    <span data-ttu-id="32915-132">Проверка подключения и ввода обложки встроенной клавиатуры</span><span class="sxs-lookup"><span data-stu-id="32915-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="32915-133">Датчики</span><span class="sxs-lookup"><span data-stu-id="32915-133">Sensors</span></span> | <span data-ttu-id="32915-134">Проверка функционирования разных датчиков на устройстве</span><span class="sxs-lookup"><span data-stu-id="32915-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="32915-135">Оборудование</span><span class="sxs-lookup"><span data-stu-id="32915-135">Hardware</span></span> |  <span data-ttu-id="32915-136">Проверка проблем с различными аппаратными компонентами, такими как графическая плата и Камера</span><span class="sxs-lookup"><span data-stu-id="32915-136">Checks issues with different hardware components such as graphics card and camera</span></span>





<span id="multiple" />

## <span data-ttu-id="32915-137">Выполнение нескольких тестов оборудования для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="32915-137">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="32915-138">SDT разработан как интерактивный инструмент, выполняющий серию тестов.</span><span class="sxs-lookup"><span data-stu-id="32915-138">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="32915-139">Для каждого теста SDT предоставляет инструкции, обобщаются сведения о природе теста и о том, какие пользователи должны ожидать или искать, чтобы тест был выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="32915-139">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="32915-140">Например, чтобы диагностировать, правильно ли работает яркость экрана, SDT начинается с нуля и увеличивает яркость на 100 процентов, запрашивает у пользователя подтверждение (с ответом **Да** или **нет** ), что означает, что яркость работает должным образом, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="32915-140">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="32915-141">Если при каждом тестировании функции не работают должным образом и пользователь нажмет кнопку **нет**, SDT создает отчет о возможных причинах и способах их устранения.</span><span class="sxs-lookup"><span data-stu-id="32915-141">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="32915-142">Диагностика оборудования с ](images/sdt-desk-4.png)
 *рис. 4. Запуск диагностики оборудования*</span><span class="sxs-lookup"><span data-stu-id="32915-142">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="32915-143">Если яркость успешно настраивается от 0-100 процентов надлежащим образом, направляйте пользователя на кнопку **Да** , а затем нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="32915-143">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="32915-144">Если не удается настроить яркость с 0-100 процента на ожидаемую, направляйте пользователя на кнопку **нет** и нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="32915-144">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="32915-145">Пошаговое руководство пользователей по оставшимся тестам.</span><span class="sxs-lookup"><span data-stu-id="32915-145">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="32915-146">После того как вы закончите, SDT автоматически предоставляет сводный отчет высокого уровня, в том числе возможные причины возникновения проблем с оборудованием, а также рекомендации по его устранению.</span><span class="sxs-lookup"><span data-stu-id="32915-146">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="32915-147">Восстановление приложений</span><span class="sxs-lookup"><span data-stu-id="32915-147">Repairing applications</span></span>

<span data-ttu-id="32915-148">SDT позволяет диагностировать и восстанавливать приложения, которые могут вызывать проблемы, как показано на рисунке 5.</span><span class="sxs-lookup"><span data-stu-id="32915-148">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="32915-149">Выполнение восстановления ](images/sdt-desk-5.png)
 *на рисунке 5. Выполнение восстановления*</span><span class="sxs-lookup"><span data-stu-id="32915-149">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="32915-150">Создание журналов для анализа проблем</span><span class="sxs-lookup"><span data-stu-id="32915-150">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="32915-151">SDT предоставляет широкие возможности диагностики, поддерживающие ведение журнала, для разных приложений, драйверов, аппаратных средств и проблем операционной системы, как показано на рисунке 6.</span><span class="sxs-lookup"><span data-stu-id="32915-151">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="32915-152">Создание журналов ](images/sdt-desk-6.png)
 *на рисунке 6. Создание журналов*</span><span class="sxs-lookup"><span data-stu-id="32915-152">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="32915-153">Создание подробного отчета с сравнением и оптимальной конфигурацией устройства</span><span class="sxs-lookup"><span data-stu-id="32915-153">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="32915-154">На основе журналов SDT создает отчет о проблемах, возникающих на базе программного обеспечения и микропрограмм, которые можно сохранить в предпочтительном расположении.</span><span class="sxs-lookup"><span data-stu-id="32915-154">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="32915-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="32915-155">Related topics</span></span>

- [<span data-ttu-id="32915-156">Запуск набора средств диагностики Surface для бизнеса с помощью команд</span><span class="sxs-lookup"><span data-stu-id="32915-156">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

