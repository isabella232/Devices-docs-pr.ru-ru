---
title: Как включить клавиатуру Surface Laptop во время развертывания MDT
description: При использовании MDT для развертывания Windows 10 на ноутбуках Surface необходимо импортировать драйверы клавиатуры для использования в среде Windows PE.
keywords: поверхность Windows 10, автоматизация, настройка, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312065"
---
# <span data-ttu-id="2cedd-104">Как включить клавиатуру Surface Laptop во время развертывания MDT</span><span class="sxs-lookup"><span data-stu-id="2cedd-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="2cedd-105">В этой статье посвящен подход к развертыванию, использующий Microsoft Deployment набор средств (MDT).</span><span class="sxs-lookup"><span data-stu-id="2cedd-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="2cedd-106">Эти сведения также можно применить к другим методикам развертывания.</span><span class="sxs-lookup"><span data-stu-id="2cedd-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="2cedd-107">На большинстве типов устройств Surface клавиатура должна работать во время установки Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="2cedd-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="2cedd-108">Тем не менее, surface Laptop требует некоторых дополнительных драйверов, чтобы включить клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="2cedd-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="2cedd-109">Для устройств Surface Laptop (1-е поколения) и Surface Laptop 2 необходимо подготовить структуру папок и профили выбора, позволяющие указать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI.</span><span class="sxs-lookup"><span data-stu-id="2cedd-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="2cedd-110">Дополнительные сведения об этой структуре папок см. в подстроке "Развертывание образа Windows 10 с помощью [MDT: шаг 5. Подготовка](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)репозитория драйверов".</span><span class="sxs-lookup"><span data-stu-id="2cedd-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="2cedd-111">При использовании драйверов клавиатуры для Surface Laptop 2 и Surface Laptop 3 в одном экземпляре загрузки Windows PE может потребоваться вручную сбросить микропрограммы, если клавиатура или сенсорная панель не работают в Windows PE:</span><span class="sxs-lookup"><span data-stu-id="2cedd-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="2cedd-112">Нажмите и удерживайте кнопку питания в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="2cedd-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="2cedd-113">Если вы подключены к блоку питания (PSU), нажимайте и удерживайте кнопку питания, пока не увидите свет в конце кнопки PSU, прежде чем снова включите ее.</span><span class="sxs-lookup"><span data-stu-id="2cedd-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cedd-114">Если вы развертываете образ Windows 10 на ноутбуке Surface с предустановленным режимом Windows 10 в S-режиме, см. KB [4032347.](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Проблемы при развертывании Windows на устройства Surface с предустановленной Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="2cedd-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="2cedd-115">Чтобы добавить драйверы клавиатуры в профиль выбора, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2cedd-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="2cedd-116">Скачайте последний MSI-файл Surface Laptop из соответствующих мест:</span><span class="sxs-lookup"><span data-stu-id="2cedd-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="2cedd-117">Драйверы и микропрограммы ноутбука Surface (1-е поколения)</span><span class="sxs-lookup"><span data-stu-id="2cedd-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="2cedd-118">Драйверы и микропрограммы Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="2cedd-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="2cedd-119">Surface Laptop 3 с процессорными драйверами и микропрограммами Intel</span><span class="sxs-lookup"><span data-stu-id="2cedd-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="2cedd-120">Извлеките содержимое MSI-файла Surface Laptop в папку, которую можно легко найти (например, c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="2cedd-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="2cedd-121">Чтобы извлечь содержимое, откройте окно командной подсказки с повышенными повышенными уровнями и запустите команду из следующего примера:</span><span class="sxs-lookup"><span data-stu-id="2cedd-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="2cedd-122">Откройте Deployment Workbench и разкройте узел **"Папки** развертывания" и обную папку развертывания, а затем перейдите в папку **WindowsPEX64.**</span><span class="sxs-lookup"><span data-stu-id="2cedd-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Изображение расположения папки WindowsPEX64 в Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="2cedd-124">Щелкните правой кнопкой **мыши папку WindowsPEX64** и выберите **"Импорт драйверов".**</span><span class="sxs-lookup"><span data-stu-id="2cedd-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="2cedd-125">Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки драйверов в папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="2cedd-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2cedd-126">Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="2cedd-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="2cedd-127">Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен.</span><span class="sxs-lookup"><span data-stu-id="2cedd-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="2cedd-128">Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="2cedd-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="2cedd-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="2cedd-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="2cedd-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2cedd-133">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="2cedd-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2cedd-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2cedd-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2cedd-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2cedd-138">Чтобы поддерживать Surface Laptop 2, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="2cedd-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="2cedd-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="2cedd-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="2cedd-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="2cedd-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="2cedd-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="2cedd-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="2cedd-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2cedd-146">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="2cedd-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2cedd-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="2cedd-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="2cedd-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2cedd-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2cedd-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2cedd-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2cedd-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2cedd-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2cedd-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2cedd-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="2cedd-154">Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="2cedd-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2cedd-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2cedd-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2cedd-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2cedd-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2cedd-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2cedd-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2cedd-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2cedd-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2cedd-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="2cedd-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2cedd-163">Импорт следующих папок позволит использовать полную клавиатуру, trackpad и сенсорные функции в PE для Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2cedd-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="2cedd-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-165">SerialIOI2C</span></span>
    - <span data-ttu-id="2cedd-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-166">SerialIOSPI</span></span>
    - <span data-ttu-id="2cedd-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2cedd-167">SerialIOUART</span></span>
    - <span data-ttu-id="2cedd-168">itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-168">itouch</span></span>
    - <span data-ttu-id="2cedd-169">Микросхем</span><span class="sxs-lookup"><span data-stu-id="2cedd-169">Chipset</span></span>
    - <span data-ttu-id="2cedd-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="2cedd-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="2cedd-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="2cedd-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="2cedd-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="2cedd-172">ManagementEngine</span></span>
    - <span data-ttu-id="2cedd-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="2cedd-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="2cedd-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="2cedd-174">SurfaceBattery</span></span>
    - <span data-ttu-id="2cedd-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="2cedd-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="2cedd-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2cedd-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="2cedd-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2cedd-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="2cedd-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="2cedd-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="2cedd-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2cedd-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="2cedd-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="2cedd-180">SurfaceService</span></span>
    - <span data-ttu-id="2cedd-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="2cedd-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="2cedd-182">Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="2cedd-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="2cedd-183">Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен.</span><span class="sxs-lookup"><span data-stu-id="2cedd-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="2cedd-184">Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="2cedd-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="2cedd-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2cedd-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2cedd-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2cedd-189">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="2cedd-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2cedd-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2cedd-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2cedd-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2cedd-194">Чтобы поддерживать Surface Laptop 2, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="2cedd-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="2cedd-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="2cedd-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2cedd-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2cedd-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="2cedd-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="2cedd-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="2cedd-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="2cedd-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2cedd-202">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="2cedd-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2cedd-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2cedd-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2cedd-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2cedd-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2cedd-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2cedd-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2cedd-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2cedd-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2cedd-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2cedd-210">Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2cedd-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="2cedd-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2cedd-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2cedd-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2cedd-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2cedd-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2cedd-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2cedd-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2cedd-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2cedd-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2cedd-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2cedd-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2cedd-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2cedd-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2cedd-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="2cedd-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2cedd-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="2cedd-219">Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2cedd-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="2cedd-220">Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2cedd-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="2cedd-221">Убедитесь, что папка WindowsPEX64 теперь содержит импортируемые драйверы.</span><span class="sxs-lookup"><span data-stu-id="2cedd-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="2cedd-222">Папка должна быть похожа на следующую:</span><span class="sxs-lookup"><span data-stu-id="2cedd-222">The folder should resemble the following:</span></span>  

   ![Изображение новых импортируемых драйверов в папке WindowsPEX64 deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="2cedd-224">Настройте профиль выбора, использующий папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="2cedd-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="2cedd-225">Профиль выбора должен иметь следующий сходство:</span><span class="sxs-lookup"><span data-stu-id="2cedd-225">The selection profile should resemble the following:</span></span>  

   ![Изображение папки WindowsPEX64, выбранной в составе профиля выбора](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="2cedd-227">Настройте свойства Windows PE для share развертывания MDT, чтобы использовать новый профиль выбора следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2cedd-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="2cedd-228">Для **платформы**выберите **x64**.</span><span class="sxs-lookup"><span data-stu-id="2cedd-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="2cedd-229">Для **профиля Selection**выберите новый профиль.</span><span class="sxs-lookup"><span data-stu-id="2cedd-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="2cedd-230">Выберите **"Включить все драйверы" из профиля выбора.**</span><span class="sxs-lookup"><span data-stu-id="2cedd-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Изображение свойств Windows PE из обоймы развертывания MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="2cedd-232">Убедитесь, что вы настроили оставшиеся драйверы Surface Laptop с помощью профиля выбора или переменной **DriverGroup001.**</span><span class="sxs-lookup"><span data-stu-id="2cedd-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="2cedd-233">Для ноутбуков Surface (1-е поколения) модель **— Surface Laptop.**</span><span class="sxs-lookup"><span data-stu-id="2cedd-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="2cedd-234">Оставшиеся драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, как показано на рисунке, который следует за этим списком.</span><span class="sxs-lookup"><span data-stu-id="2cedd-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="2cedd-235">Для Surface Laptop 2 **моделью является Surface Laptop 2.**</span><span class="sxs-lookup"><span data-stu-id="2cedd-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="2cedd-236">Оставшиеся драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="2cedd-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="2cedd-237">Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2cedd-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="2cedd-238">Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2cedd-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Изображение обычных драйверов Surface Laptop (1-го поколения) в папке Surface Laptop deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="2cedd-240">Настроив обную долю развертывания MDT для использования нового профиля выбора и связанных параметров, продолжите процесс развертывания, как описано в описании развертывания образа Windows 10 с помощью [MDT: шаг 6. Создание](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)последовательности задач развертывания.</span><span class="sxs-lookup"><span data-stu-id="2cedd-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
