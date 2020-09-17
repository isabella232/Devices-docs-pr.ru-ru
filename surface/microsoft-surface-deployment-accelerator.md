---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator — это простое средство развертывания, с помощью которого организации могут быстро пересоздавать образы устройств Surface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: развертывание, установка, средство
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016560"
---
# <span data-ttu-id="10a89-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="10a89-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="10a89-105">Ускоритель развертывания Microsoft Surface (SDA) автоматизирует создание и настройку рекомендуемого опыта развертывания Майкрософт с помощью бесплатных средств развертывания Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10a89-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="10a89-106">В апреле 2020 для упрощения и автоматизации развертывания изображений Surface в корпоративной среде средство SDA позволяет создавать "Заводский" образ Windows, который можно настроить для организационных требований.</span><span class="sxs-lookup"><span data-stu-id="10a89-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="10a89-107">Открытый источник, управляемый сценарием SDA использует комплект средств оценки и развертывания Windows (ADK) для Windows 10, который упрощает создание образов Windows (WIM) в тестовых и рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="10a89-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="10a89-108">Если последнее приложение ADK еще не установлено, оно будет загружено и установлено при запуске средства SDA.</span><span class="sxs-lookup"><span data-stu-id="10a89-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="10a89-109">Полученное изображение точно соответствует конфигурации изображений восстановления исходного состояния системы (BMR), без предустановленных приложений, таких как Microsoft Office или приложение UWP Surface.</span><span class="sxs-lookup"><span data-stu-id="10a89-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="10a89-110">Требования</span><span class="sxs-lookup"><span data-stu-id="10a89-110">Requirements</span></span>

1. <span data-ttu-id="10a89-111">Съемный USB-диск с размером не менее 16 ГБ.</span><span class="sxs-lookup"><span data-stu-id="10a89-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="10a89-112">USB-накопитель будет отформатирован.</span><span class="sxs-lookup"><span data-stu-id="10a89-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="10a89-113">ISO-файл в Windows 10 Pro или Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="10a89-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="10a89-114">Средство создания мультимедиа можно использовать для загрузки Windows 10 и создания ISO-файла.</span><span class="sxs-lookup"><span data-stu-id="10a89-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="10a89-115">Дополнительные сведения можно найти в разделе [Загрузка Windows 10](https://www.microsoft.com/software-download/windows10).</span><span class="sxs-lookup"><span data-stu-id="10a89-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="10a89-116">Устройство под управлением Windows 10 версии 2004 или более поздней с доступом к Интернету.</span><span class="sxs-lookup"><span data-stu-id="10a89-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="10a89-117">Подробный список требований вы найдете в разделе [необходимые условия](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) в документе Readme.</span><span class="sxs-lookup"><span data-stu-id="10a89-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="10a89-118">Как запустить SDA</span><span class="sxs-lookup"><span data-stu-id="10a89-118">How to run the SDA</span></span>

**<span data-ttu-id="10a89-119">Чтобы запустить SDA, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="10a89-119">To run SDA:</span></span>**

1. <span data-ttu-id="10a89-120">Перейдите на [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="10a89-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="10a89-121">Ознакомьтесь с документацией по [readmeм](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .</span><span class="sxs-lookup"><span data-stu-id="10a89-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="10a89-122">На странице [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) нажмите кнопку **код** и выберите **загрузить ZIP** , чтобы сохранить файлы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="10a89-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="10a89-123">Щелкните ZIP-файл правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="10a89-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="10a89-124">На вкладке **Общие** установите флажок **разблокировать** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="10a89-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="10a89-125">Извлеките ZIP-файл в папку на жестком диске (например: C:\SDA).</span><span class="sxs-lookup"><span data-stu-id="10a89-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="10a89-126">Откройте запрос Windows PowerShell с повышенными привилегиями и настройте ExecutionPolicy для текущего сеанса, чтобы он был неограниченным.</span><span class="sxs-lookup"><span data-stu-id="10a89-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="10a89-127">Запустите сценарий SDA, указав параметры для своей среды.</span><span class="sxs-lookup"><span data-stu-id="10a89-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="10a89-128">Этот сценарий можно использовать для создания изображений для установки Windows 10 на различных устройствах Surface.</span><span class="sxs-lookup"><span data-stu-id="10a89-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="10a89-129">Полный список поддерживаемых устройств можно найти в [описании параметров устройства](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) в статье readme по sda.</span><span class="sxs-lookup"><span data-stu-id="10a89-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="10a89-130">Например, следующая команда создаст загрузочный USB-накопитель, который можно использовать для [установки Windows 10 на Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span><span class="sxs-lookup"><span data-stu-id="10a89-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="10a89-131">Ниже приведен пример выходных данных сценария.</span><span class="sxs-lookup"><span data-stu-id="10a89-131">Sample script output is below.</span></span>

   ![Запуск средства акселератора для развертывания Surface](images/sda1.png)

    <span data-ttu-id="10a89-133">Для выполнения сценария потребуется около 45 минут, но это может занять больше времени в зависимости от доступности ресурсов ЦП и дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="10a89-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="10a89-134">После создания образа Windows сценарий предложит вам вставить и подтвердить букву USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="10a89-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="10a89-135">USB-диск будет отформатирован, настроен как загрузочный и скопированы файлы, чтобы включить установку настраиваемого образа Windows 10 для устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="10a89-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="10a89-136">Вставьте USB-накопитель на устройство, на котором вы хотите установить Windows 10, и перезагрузите компьютер, чтобы начать установку Windows 10.</span><span class="sxs-lookup"><span data-stu-id="10a89-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="10a89-137">Загрузка с USB-порта должна быть включена в BIOS, при этом может потребоваться временно отключить безопасную загрузку.</span><span class="sxs-lookup"><span data-stu-id="10a89-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10a89-138">Загрузка с USB-накопителя начнется сразу же после установки Windows 10.</span><span class="sxs-lookup"><span data-stu-id="10a89-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="10a89-139">Перед вставкой USB и перезапуском убедитесь, что устройство готово к работе.</span><span class="sxs-lookup"><span data-stu-id="10a89-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="10a89-140">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="10a89-140">Related links</span></span>

 - [<span data-ttu-id="10a89-141">Средство развертывания исходного образа, выпущенное в GitHub</span><span class="sxs-lookup"><span data-stu-id="10a89-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="10a89-142">Скачивание и установка Windows ADK</span><span class="sxs-lookup"><span data-stu-id="10a89-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
