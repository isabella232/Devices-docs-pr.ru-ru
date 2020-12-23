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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247311"
---
# <span data-ttu-id="a3d28-104">Как включить клавиатуру Surface Laptop во время развертывания MDT</span><span class="sxs-lookup"><span data-stu-id="a3d28-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="a3d28-105">В этой статье посвящен подход к развертыванию, использующий Microsoft Deployment набор средств (MDT).</span><span class="sxs-lookup"><span data-stu-id="a3d28-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="a3d28-106">Эти сведения также можно применить к другим методологиям развертывания.</span><span class="sxs-lookup"><span data-stu-id="a3d28-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="a3d28-107">На большинстве типов устройств Surface клавиатура должна работать во время установки Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="a3d28-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="a3d28-108">Тем не менее, surface Laptop требует некоторых дополнительных драйверов, чтобы включить клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="a3d28-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="a3d28-109">Для устройств Surface Laptop (1-е поколения) и Surface Laptop 2 необходимо подготовить структуру папок и профили выбора, позволяющие указать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI.</span><span class="sxs-lookup"><span data-stu-id="a3d28-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="a3d28-110">Дополнительные сведения об этой структуре папок см. в подстроке "Развертывание образа Windows 10 с помощью [MDT: шаг 5. Подготовка](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)репозитория драйверов".</span><span class="sxs-lookup"><span data-stu-id="a3d28-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a3d28-111">Если вы развертываете образ Windows 10 на ноутбуке Surface с предустановленным режимом Windows 10 в S-режиме, см. KB [4032347.](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Проблемы при развертывании Windows на устройства Surface с предустановленной Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="a3d28-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="a3d28-112">Чтобы добавить драйверы клавиатуры в профиль выбора, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a3d28-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="a3d28-113">Скачайте последний MSI-файл Surface Laptop из соответствующих мест:</span><span class="sxs-lookup"><span data-stu-id="a3d28-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="a3d28-114">Драйверы и микропрограммы ноутбука Surface (1-е поколения)</span><span class="sxs-lookup"><span data-stu-id="a3d28-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="a3d28-115">Драйверы и микропрограммы Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="a3d28-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="a3d28-116">Surface Laptop 3 с процессорными драйверами и микропрограммами Intel</span><span class="sxs-lookup"><span data-stu-id="a3d28-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="a3d28-117">Извлеките содержимое MSI-файла Surface Laptop в папку, которую можно легко найти (например, c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="a3d28-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="a3d28-118">Чтобы извлечь содержимое, откройте окно командной подсказки с повышенными повышенными уровнями и запустите команду из следующего примера:</span><span class="sxs-lookup"><span data-stu-id="a3d28-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="a3d28-119">Откройте Deployment Workbench и разкройте узел **"Папки** развертывания" и обную папку развертывания, а затем перейдите в папку **WindowsPEX64.**</span><span class="sxs-lookup"><span data-stu-id="a3d28-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Изображение расположения папки WindowsPEX64 в Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="a3d28-121">Щелкните правой кнопкой **мыши папку WindowsPEX64** и выберите **"Импорт драйверов".**</span><span class="sxs-lookup"><span data-stu-id="a3d28-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="a3d28-122">Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки драйверов в папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="a3d28-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a3d28-123">Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="a3d28-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="a3d28-124">Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен.</span><span class="sxs-lookup"><span data-stu-id="a3d28-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="a3d28-125">Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="a3d28-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="a3d28-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="a3d28-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="a3d28-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="a3d28-130">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="a3d28-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="a3d28-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="a3d28-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="a3d28-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="a3d28-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="a3d28-135">Для поддержки Surface Laptop 2 импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="a3d28-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="a3d28-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="a3d28-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="a3d28-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="a3d28-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="a3d28-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="a3d28-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="a3d28-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="a3d28-143">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="a3d28-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="a3d28-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="a3d28-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="a3d28-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="a3d28-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="a3d28-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="a3d28-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="a3d28-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="a3d28-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="a3d28-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="a3d28-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="a3d28-151">Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="a3d28-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="a3d28-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="a3d28-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="a3d28-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="a3d28-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="a3d28-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="a3d28-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="a3d28-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="a3d28-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="a3d28-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="a3d28-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="a3d28-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="a3d28-160">Импорт следующих папок позволит использовать полную клавиатуру, trackpad и сенсорные функции в PE для Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a3d28-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="a3d28-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="a3d28-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="a3d28-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="a3d28-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="a3d28-164">IclSerialIOUART</span></span>
- <span data-ttu-id="a3d28-165">itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-165">itouch</span></span>
- <span data-ttu-id="a3d28-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="a3d28-166">IclChipset</span></span>
- <span data-ttu-id="a3d28-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="a3d28-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="a3d28-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="a3d28-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="a3d28-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="a3d28-169">ManagementEngine</span></span>
- <span data-ttu-id="a3d28-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="a3d28-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="a3d28-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="a3d28-171">SurfaceBattery</span></span>
- <span data-ttu-id="a3d28-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="a3d28-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="a3d28-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="a3d28-173">SurfaceHidMini</span></span>
- <span data-ttu-id="a3d28-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="a3d28-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="a3d28-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="a3d28-175">SurfaceIntegration</span></span>
- <span data-ttu-id="a3d28-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="a3d28-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="a3d28-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="a3d28-177">SurfaceService</span></span>
- <span data-ttu-id="a3d28-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="a3d28-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="a3d28-179">Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="a3d28-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="a3d28-180">Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен.</span><span class="sxs-lookup"><span data-stu-id="a3d28-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="a3d28-181">Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="a3d28-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="a3d28-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="a3d28-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="a3d28-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="a3d28-186">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="a3d28-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="a3d28-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="a3d28-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="a3d28-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="a3d28-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="a3d28-191">Для поддержки Surface Laptop 2 импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="a3d28-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="a3d28-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="a3d28-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="a3d28-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="a3d28-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="a3d28-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="a3d28-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="a3d28-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="a3d28-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="a3d28-199">Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:</span><span class="sxs-lookup"><span data-stu-id="a3d28-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="a3d28-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="a3d28-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="a3d28-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="a3d28-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="a3d28-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="a3d28-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="a3d28-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="a3d28-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="a3d28-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="a3d28-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="a3d28-207">Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:</span><span class="sxs-lookup"><span data-stu-id="a3d28-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="a3d28-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="a3d28-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="a3d28-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="a3d28-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="a3d28-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="a3d28-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="a3d28-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="a3d28-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="a3d28-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="a3d28-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="a3d28-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="a3d28-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="a3d28-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="a3d28-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="a3d28-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="a3d28-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3d28-216">Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a3d28-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="a3d28-217">Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a3d28-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="a3d28-218">Убедитесь, что папка WindowsPEX64 теперь содержит импортируемые драйверы.</span><span class="sxs-lookup"><span data-stu-id="a3d28-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="a3d28-219">Папка должна быть похожа на следующую:</span><span class="sxs-lookup"><span data-stu-id="a3d28-219">The folder should resemble the following:</span></span>  

   ![Изображение новых импортируемых драйверов в папке WindowsPEX64 deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="a3d28-221">Настройте профиль выбора, использующий папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="a3d28-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="a3d28-222">Профиль выбора должен иметь следующий сходство:</span><span class="sxs-lookup"><span data-stu-id="a3d28-222">The selection profile should resemble the following:</span></span>  

   ![Изображение папки WindowsPEX64, выбранной в составе профиля выбора](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="a3d28-224">Настройте свойства Windows PE для share развертывания MDT, чтобы использовать новый профиль выбора следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a3d28-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="a3d28-225">Для **платформы**выберите **x64**.</span><span class="sxs-lookup"><span data-stu-id="a3d28-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="a3d28-226">Для **профиля Selection**выберите новый профиль.</span><span class="sxs-lookup"><span data-stu-id="a3d28-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="a3d28-227">Выберите **"Включить все драйверы" из профиля выбора.**</span><span class="sxs-lookup"><span data-stu-id="a3d28-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Изображение свойств Windows PE из обоймы развертывания MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="a3d28-229">Убедитесь, что вы настроили оставшиеся драйверы Surface Laptop с помощью профиля выбора или переменной **DriverGroup001.**</span><span class="sxs-lookup"><span data-stu-id="a3d28-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="a3d28-230">Для ноутбуков Surface (1-е поколения) **моделью является Surface Laptop.**</span><span class="sxs-lookup"><span data-stu-id="a3d28-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="a3d28-231">Оставшиеся драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, как показано на рисунке, который следует за этим списком.</span><span class="sxs-lookup"><span data-stu-id="a3d28-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="a3d28-232">Для Surface Laptop 2 **моделью является Surface Laptop 2.**</span><span class="sxs-lookup"><span data-stu-id="a3d28-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="a3d28-233">Остальные драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="a3d28-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="a3d28-234">Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a3d28-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="a3d28-235">Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a3d28-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Изображение обычных драйверов Surface Laptop (1-го поколения) в папке Surface Laptop deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="a3d28-237">Настроив обную долю развертывания MDT для использования нового профиля выбора и связанных параметров, продолжите процесс развертывания, как описано в описании развертывания образа Windows 10 с помощью [MDT: шаг 6. Создание](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)последовательности задач развертывания.</span><span class="sxs-lookup"><span data-stu-id="a3d28-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
