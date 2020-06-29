---
title: Включение клавиатуры Surface ноутбука в развертывание MDT
description: При использовании MDT для развертывания Windows 10 на компьютерах с контактными портативными компьютерами необходимо импортировать драйверы клавиатуры для использования в среде Windows PE.
keywords: поверхность Windows 10, Автоматизация, Настройка, MDT
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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834715"
---
# <span data-ttu-id="99449-104">Включение клавиатуры Surface ноутбука в развертывание MDT</span><span class="sxs-lookup"><span data-stu-id="99449-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="99449-105">В этой статье рассматривается подход к развертыванию, в котором используется Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="99449-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="99449-106">Эти сведения также можно применить к другим методологиям развертывания.</span><span class="sxs-lookup"><span data-stu-id="99449-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="99449-107">На большинстве типов устройств Surface клавиатура должна работать во время установки с помощью облегченного сенсорного ввода (LTI).</span><span class="sxs-lookup"><span data-stu-id="99449-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="99449-108">Тем не менее, для портативного компьютера Surface требуется наличие некоторых дополнительных драйверов для использования клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="99449-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="99449-109">Для устройств Surface (1-го и Surface) необходимо подготовить структуру папок и профили выбора, позволяющие указывать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI.</span><span class="sxs-lookup"><span data-stu-id="99449-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="99449-110">Дополнительные сведения об этой структуре папок можно найти в [статье Развертывание образа Windows 10 с помощью MDT: шаг 5: подготовка репозитория драйверов](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="99449-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="99449-111">В настоящее время вы не можете добавить драйверы клавиатуры для ноутбука Surface 2 и Surface 3 в одном экземпляре загрузки Windows PE из-за конфликта драйверов. Вместо этого используйте отдельные экземпляры.</span><span class="sxs-lookup"><span data-stu-id="99449-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99449-112">При развертывании образа Windows 10 на ноутбуке Surface с предварительно установленной операционной системой Windows 10 ознакомьтесь со статьей KB [4032347, возникающими при развертывании Windows на Surface Devices с предварительно установленной операционной системой Windows 10 в режиме s](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="99449-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="99449-113">Чтобы добавить драйверы клавиатуры в профиль выбора, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="99449-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="99449-114">Скачайте MSI-файл для портативного компьютера Surface из соответствующих местоположений:</span><span class="sxs-lookup"><span data-stu-id="99449-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="99449-115">Драйверы и встроенное по для ноутбука Surface (1-го поколения)</span><span class="sxs-lookup"><span data-stu-id="99449-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="99449-116">Драйверы и встроенное по для ноутбука Surface 2</span><span class="sxs-lookup"><span data-stu-id="99449-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="99449-117">ПК Surface 3 с драйверами и встроенным по для процессора Intel</span><span class="sxs-lookup"><span data-stu-id="99449-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="99449-118">Извлеките содержимое MSI-файла Surface, в папку, которую можно легко найти (например, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="99449-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="99449-119">Чтобы извлечь содержимое, откройте окно командной строки с повышенными привилегиями и выполните команду из следующего примера:</span><span class="sxs-lookup"><span data-stu-id="99449-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="99449-120">Откройте средство развертывания и разверните узел **Общие ресурсы развертывания** и общий доступ к развертыванию, а затем перейдите в папку **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="99449-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Изображение, которое показывает расположение папки WindowsPEX64 в Workbench для развертывания](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="99449-122">Щелкните правой кнопкой мыши папку **WindowsPEX64** и выберите команду **Импорт драйверов**.</span><span class="sxs-lookup"><span data-stu-id="99449-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="99449-123">Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки Drivers в папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="99449-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="99449-124">Проверьте скачанный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="99449-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="99449-125">Структура каталогов будет начинаться с SurfacePlatformInstaller (устаревших MSI-файлов) или SurfaceUpdate (более поздних MSI-файлов) в зависимости от того, когда был освобожден пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="99449-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="99449-126">Чтобы обеспечить поддержку ноутбука Surface (1-го поколения), импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="99449-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="99449-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="99449-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="99449-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="99449-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="99449-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="99449-131">Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:</span><span class="sxs-lookup"><span data-stu-id="99449-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="99449-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="99449-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="99449-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="99449-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="99449-136">Для поддержки портативного компьютера Surface 2 импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="99449-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="99449-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="99449-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="99449-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="99449-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="99449-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="99449-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="99449-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="99449-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="99449-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="99449-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="99449-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="99449-144">Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:</span><span class="sxs-lookup"><span data-stu-id="99449-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="99449-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="99449-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="99449-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="99449-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="99449-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="99449-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="99449-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="99449-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="99449-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="99449-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="99449-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="99449-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="99449-152">Для поддержки портативного компьютера Surface 3 с помощью процессора Intel импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="99449-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="99449-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="99449-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="99449-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="99449-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="99449-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="99449-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="99449-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="99449-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="99449-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="99449-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="99449-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="99449-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="99449-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="99449-161">Импорт следующих папок включает функцию полной клавиатуры, сенсорной панели и сенсорного ввода в PE для ноутбука Surface 3.</span><span class="sxs-lookup"><span data-stu-id="99449-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="99449-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="99449-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="99449-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="99449-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="99449-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="99449-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="99449-165">IclSerialIOUART</span></span>
- <span data-ttu-id="99449-166">itouch</span><span class="sxs-lookup"><span data-stu-id="99449-166">itouch</span></span>
- <span data-ttu-id="99449-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="99449-167">IclChipset</span></span>
- <span data-ttu-id="99449-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="99449-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="99449-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="99449-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="99449-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="99449-170">ManagementEngine</span></span>
- <span data-ttu-id="99449-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="99449-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="99449-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="99449-172">SurfaceBattery</span></span>
- <span data-ttu-id="99449-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="99449-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="99449-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="99449-174">SurfaceHidMini</span></span>
- <span data-ttu-id="99449-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="99449-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="99449-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="99449-176">SurfaceIntegration</span></span>
- <span data-ttu-id="99449-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="99449-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="99449-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="99449-178">SurfaceService</span></span>
- <span data-ttu-id="99449-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="99449-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="99449-180">Проверьте скачанный пакет MSI, чтобы определить формат и структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="99449-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="99449-181">Структура каталогов будет начинаться с SurfacePlatformInstaller (устаревших MSI-файлов) или SurfaceUpdate (более поздних MSI-файлов) в зависимости от того, когда был освобожден пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="99449-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="99449-182">Чтобы обеспечить поддержку ноутбука Surface (1-го поколения), импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="99449-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="99449-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="99449-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="99449-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="99449-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="99449-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="99449-187">Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:</span><span class="sxs-lookup"><span data-stu-id="99449-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="99449-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="99449-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="99449-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="99449-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="99449-192">Для поддержки портативного компьютера Surface 2 импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="99449-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="99449-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="99449-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="99449-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="99449-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="99449-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="99449-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="99449-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="99449-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="99449-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="99449-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="99449-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="99449-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="99449-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="99449-200">Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:</span><span class="sxs-lookup"><span data-stu-id="99449-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="99449-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="99449-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="99449-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="99449-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="99449-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="99449-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="99449-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="99449-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="99449-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="99449-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="99449-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="99449-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="99449-208">Для поддержки портативного компьютера Surface 3 с помощью процессора Intel импортируйте следующие папки:</span><span class="sxs-lookup"><span data-stu-id="99449-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="99449-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="99449-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="99449-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="99449-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="99449-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="99449-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="99449-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="99449-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="99449-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="99449-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="99449-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="99449-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="99449-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="99449-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="99449-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="99449-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="99449-217">Для портативного компьютера Surface 3 с процессором Intel модель — Surface ноутбука 3.</span><span class="sxs-lookup"><span data-stu-id="99449-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="99449-218">Оставшиеся драйверы для портативного компьютера Surface находятся в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 3.</span><span class="sxs-lookup"><span data-stu-id="99449-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="99449-219">Убедитесь, что в папке WindowsPEX64 есть импортированные драйверы.</span><span class="sxs-lookup"><span data-stu-id="99449-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="99449-220">Папка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99449-220">The folder should resemble the following:</span></span>  

   ![Изображение, в котором показаны только что импортированные драйверы в папке WindowsPEX64 в Workbench для развертывания.](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="99449-222">Настройте профиль выделения, использующий папку WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="99449-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="99449-223">Профиль выделения должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99449-223">The selection profile should resemble the following:</span></span>  

   ![Рисунок, на котором показана папка WindowsPEX64, выбранная в составе профиля выбора](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="99449-225">Настройте свойства Windows PE для общего доступа к развертыванию MDT, чтобы использовать новый профиль выделения, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="99449-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="99449-226">На вкладке **платформа**выберите **x64**.</span><span class="sxs-lookup"><span data-stu-id="99449-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="99449-227">Для **профиля выбора**выберите новый профиль.</span><span class="sxs-lookup"><span data-stu-id="99449-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="99449-228">Выберите **включить все драйверы из профиля выбора**.</span><span class="sxs-lookup"><span data-stu-id="99449-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Изображение, показывающее свойства общего доступа развертывания MDT для Windows PE](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="99449-230">Убедитесь, что вы настроили оставшиеся драйверы портативного компьютера Surface, используя либо профиль выделения, либо переменную **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="99449-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="99449-231">Для Surface ноутбука (1-го поколения) модель — это **ноутбук Surface**.</span><span class="sxs-lookup"><span data-stu-id="99449-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="99449-232">Оставшиеся драйверы для ноутбука на компьютере Surface должны находиться в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="99449-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="99449-233">Для ноутбука Surface 2 модель — **Surface ноутбука 2**.</span><span class="sxs-lookup"><span data-stu-id="99449-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="99449-234">Оставшиеся драйверы для ноутбука на компьютере Surface должны находиться в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 2.</span><span class="sxs-lookup"><span data-stu-id="99449-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="99449-235">Для портативного компьютера Surface 3 с процессором Intel модель — Surface ноутбука 3.</span><span class="sxs-lookup"><span data-stu-id="99449-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="99449-236">Оставшиеся драйверы для портативного компьютера Surface находятся в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 3.</span><span class="sxs-lookup"><span data-stu-id="99449-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Изображение стандартных драйверов ноутбука Surface (1-го поколения) в папке "ноутбук Surface" в Workbench для развертывания](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="99449-238">После того как вы настраиваете общий доступ к развертыванию MDT для использования нового профиля выбора и связанных параметров, продолжайте процесс развертывания, как описано в разделе [развертывание образа Windows 10 с помощью MDT: Step 6: Создание последовательности задач развертывания](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="99449-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
