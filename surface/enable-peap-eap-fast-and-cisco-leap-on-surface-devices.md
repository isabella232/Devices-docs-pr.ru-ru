---
title: Включение протоколов PEAP, EAP-FAST и Cisco LEAP на устройствах Surface
description: Узнайте, как включить поддержку протоколов PEAP, EAP-FAST и Cisco LEAP на устройстве Surface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: сеть, беспроводная, устройство, развертывание, проверка подлинности, протокол
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835971"
---
# <span data-ttu-id="89e37-104">Включение PEAP, EAP-FAST и Cisco LEAP на устройствах Surface</span><span class="sxs-lookup"><span data-stu-id="89e37-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="89e37-105">Узнайте, как включить поддержку протоколов PEAP, EAP-FAST и Cisco LEAP на устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="89e37-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="89e37-106">Если вы используете PEAP, EAP-FAST или Cisco LEAP в корпоративной сети, возможно, вы уже знаете, что эти 3 протокола беспроводной проверки подлинности не поддерживаются устройствами Surface с заводскими настройками.</span><span class="sxs-lookup"><span data-stu-id="89e37-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="89e37-107">Некоторые пользователи узнают это, когда пытаются подключиться к беспроводной сети; другие могут узнать об этом, когда сталкиваются невозможностью получения доступа к ресурсам в сети, например к общим файлам и внутренним сайтам.</span><span class="sxs-lookup"><span data-stu-id="89e37-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="89e37-108">Подробнее: [Протокол EAP](https://technet.microsoft.com/network/bb643147).</span><span class="sxs-lookup"><span data-stu-id="89e37-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="89e37-109">Можно добавить поддержку всех протоколов, запустив небольшой пакет MSI с USB-накопителя или из общей папки.</span><span class="sxs-lookup"><span data-stu-id="89e37-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="89e37-110">Для организаций, которые хотят включить поддержку EAP на Surface Devices, формат пакета MSI поддерживает развертывание с множеством средств управления и развертывания, таких как Microsoft Deployment Toolkit (MDT) и Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="89e37-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="89e37-111">Скачивание установочных файлов PEAP, EAP-FAST и Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="89e37-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="89e37-112">Можно скачать файлы установки MSI для PEAP, EAP-FAST и Cisco LEAP в одном архивном файле из Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="89e37-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="89e37-113">Для скачивания этого файла перейдите на страницу [Инструменты Surface для ИТ-специалистов](https://www.microsoft.com/download/details.aspx?id=46703) в Центре загрузки Майкрософт, нажмите **Скачать**, а затем выберите файл **Cisco EAP-Supplicant Installer.zip**.</span><span class="sxs-lookup"><span data-stu-id="89e37-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="89e37-114">Развертывание PEAP, EAP-FAST и Cisco LEAP с помощью MDT</span><span class="sxs-lookup"><span data-stu-id="89e37-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="89e37-115">Если вы уже выполняете развертывание Windows на устройства Surface в своей организации, можно легко и быстро добавить файлы установки для каждого протокола в общую папку развертывания и настроить автоматическую установку во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="89e37-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="89e37-116">Можно даже настроить последовательность задач, которая обновит ранее развернутые устройства Surface для обеспечения поддержки этих протоколов с использованием той же процедуры.</span><span class="sxs-lookup"><span data-stu-id="89e37-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="89e37-117">Чтобы включить поддержку протоколов PEAP, EAP-FAST и Cisco LEAP на тех устройствах Surface, где было выполнено развертывание, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="89e37-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="89e37-118">Скачайте и извлеките файлы установки для каждого протокола в отдельные папки в легкодоступном расположении.</span><span class="sxs-lookup"><span data-stu-id="89e37-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="89e37-119">Откройте Deployment Workbench MDT и разверните общую папку развертывания в папку **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="89e37-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="89e37-120">Выберите **Новое приложение** на панели **Действие**.</span><span class="sxs-lookup"><span data-stu-id="89e37-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="89e37-121">Выберите **Приложение с исходными файлами**, чтобы скопировать MSI-файлы в общую папку развертывания.</span><span class="sxs-lookup"><span data-stu-id="89e37-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="89e37-122">Выберите папку, созданную на шаге 1 для нужного протокола.</span><span class="sxs-lookup"><span data-stu-id="89e37-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="89e37-123">Задайте имя папки в общей папке развертывания, где будут храниться файлы установки.</span><span class="sxs-lookup"><span data-stu-id="89e37-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="89e37-124">Введите команду для развертывания приложения:</span><span class="sxs-lookup"><span data-stu-id="89e37-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="89e37-125">Для PEAP используйте **EAP-PEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="89e37-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="89e37-126">Для LEAP используйте **EAP-LEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="89e37-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="89e37-127">Для EAP-FAST используйте **EAP-FAST.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="89e37-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="89e37-128">Используйте параметры по умолчанию для завершения Мастера установки нового приложения.</span><span class="sxs-lookup"><span data-stu-id="89e37-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="89e37-129">Повторите действия с 3 по 8 для каждого необходимого протокола.</span><span class="sxs-lookup"><span data-stu-id="89e37-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="89e37-130">После выполнения вами этих действий для импорта 3 пакетов MSI как приложений в MDT они будут доступны для выделения на странице приложений в Мастере развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="89e37-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="89e37-131">Хотя в некоторых простых сценариях развертывания достаточно выбора обслуживающим персоналом каждого пакета во время развертывания, использование такого подхода не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="89e37-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="89e37-132">Такая методика повышает вероятность того, что специалист может попытаться применить эти пакеты на других компьютерах помимо устройств Surface, а также того, что устройство Surface может быть развернуто без поддержки EAP из-за человеческой ошибки.</span><span class="sxs-lookup"><span data-stu-id="89e37-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="89e37-133">Чтобы скрыть эти приложения на странице установки приложений, установите флажок \*\*Скрывать это приложение в Мастере развертывания \*\*в свойствах каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="89e37-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="89e37-134">После сокрытия приложений они не отображаются в виде дополнительных приложений во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="89e37-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="89e37-135">Для развертывания их в последовательности задач развертывания Surface необходимо явно назначить их для установки на отдельном этапе в последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="89e37-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="89e37-136">Чтобы указать протоколы, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="89e37-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="89e37-137">Откройте свойства последовательности задач развертывания Surface из MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="89e37-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="89e37-138">На вкладке **Последовательность задач** выберите действие **Установка приложений** в разделе **Восстановление состояния**.</span><span class="sxs-lookup"><span data-stu-id="89e37-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="89e37-139">Обычно он находится между действиями Центра обновления Windows до и после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="89e37-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="89e37-140">Используйте кнопку **Добавить**, чтобы создать новый этап **Установка приложения** из категории **Общие**.</span><span class="sxs-lookup"><span data-stu-id="89e37-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="89e37-141">Выберите **Установка одного приложения** на вкладке **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="89e37-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="89e37-142">Выберите нужный протокол EAP из списка.</span><span class="sxs-lookup"><span data-stu-id="89e37-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="89e37-143">Повторите действия со второго по пятое для каждого необходимого протокола.</span><span class="sxs-lookup"><span data-stu-id="89e37-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="89e37-144">Развертывание PEAP, EAP-FAST и Cisco LEAP с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="89e37-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="89e37-145">Для организаций, в которых управление устройствами Surface производится с помощью Configuration Manager, процедура развертывания поддержки протоколов PEAP, EAP-FAST и Cisco LEAP на устройствах Surface выполняется еще проще.</span><span class="sxs-lookup"><span data-stu-id="89e37-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="89e37-146">Просто импортируйте каждый MSI-файл как приложение из библиотеки программного обеспечения и настройте развертывание на коллекцию устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="89e37-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="89e37-147">Дополнительные сведения о том, как развернуть приложения с помощью Configuration Manager, приведены в статьях [Создание приложений в Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) и [Развертывание приложений в Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span><span class="sxs-lookup"><span data-stu-id="89e37-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





