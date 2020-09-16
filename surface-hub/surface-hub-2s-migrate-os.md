---
title: Переход на Windows 10 Pro или Корпоративная в Surface Hub 2
description: В этой статье описывается процесс перехода с Windows 10 на Surface Hub 2 на Windows 10 Pro или Windows 10 Enterprise.
keywords: Surface Hub для настольных ПК, Surface HUB
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/15/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d36f42485107dd84be08c20291b36540662503da
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016458"
---
# <span data-ttu-id="bf994-104">Переход на Windows 10 Pro или Корпоративная в Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="bf994-105">Введение</span><span class="sxs-lookup"><span data-stu-id="bf994-105">Introduction</span></span>

<span data-ttu-id="bf994-106">Surface Hub 2S предварительно установлен в Windows 10 Team, настроенный выпуск Windows 10, разработанный для упрощения совместной работы в средах для собраний.</span><span class="sxs-lookup"><span data-stu-id="bf994-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="bf994-107">Теперь у вас есть возможность работать с Windows 10 Pro или Enterprise, чтобы использовать Surface Hub 2, как и любые другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="bf994-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="bf994-108">В отличие от обычного обновления или миграции, этот процесс требует подписаться на предварительное описание процедуры, как описано на этой странице.</span><span class="sxs-lookup"><span data-stu-id="bf994-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="bf994-109">Прежде чем продолжить, прочтите [компоненты решения](#solution-components) и [процесс миграции и установки](#migration-and-installation-workflow-summary) .</span><span class="sxs-lookup"><span data-stu-id="bf994-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>


> [!NOTE]
> <span data-ttu-id="bf994-110">После установки Windows 10 Pro или Enterprise вам потребуется новая лицензия, которая будет отделена от имеющейся лицензии на Windows 10 Team.</span><span class="sxs-lookup"><span data-stu-id="bf994-110">When you install Windows 10 Pro or Enterprise, you will need a new licence separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="bf994-111">Вы запускаете миграцию из Windows 10 с помощью отдельного компьютера и средства для загрузки, а также средство для настройки **UEFI** — для создания пакета, содержащего новый параметр UEFI, применяемый к Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="bf994-111">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="bf994-112">Конфигуратор UEFI Surface выступает в качестве интерфейса в режиме корпоративного управления Surface (SEMM), предназначенного для централизованного управления параметрами микропрограмм на устройствах Surface в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="bf994-112">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="bf994-113">Чтобы узнать больше о SEMM, ознакомьтесь с [документацией по режиму корпоративного управления Surface (Майкрософт](https://docs.microsoft.com/surface/surface-enterprise-management-mode)).</span><span class="sxs-lookup"><span data-stu-id="bf994-113">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="bf994-114">Компоненты решения</span><span class="sxs-lookup"><span data-stu-id="bf994-114">Solution Components</span></span>

- <span data-ttu-id="bf994-115">Surface Hub 2S на устройстве с операционной системой Windows 10 Teams</span><span class="sxs-lookup"><span data-stu-id="bf994-115">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="bf994-116">Отдельное устройство под управлением Windows 10</span><span class="sxs-lookup"><span data-stu-id="bf994-116">Separate device running Windows 10</span></span>
- <span data-ttu-id="bf994-117">Инструмент конфигуратора UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="bf994-117">Surface UEFI Configurator tool</span></span>
- <span data-ttu-id="bf994-118">Образ операционной системы Windows 10 Pro или Enterprise, версия 1903 или более поздняя</span><span class="sxs-lookup"><span data-stu-id="bf994-118">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="bf994-119">Два USB-накопителя с объемом памяти 16 ГБ, формат FAT32</span><span class="sxs-lookup"><span data-stu-id="bf994-119">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="bf994-120">Драйверы и микропрограммы для Windows 10 Pro и Enterprise на Surface Hub 2, установщик Windows. MSI-файл</span><span class="sxs-lookup"><span data-stu-id="bf994-120">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="bf994-121">Подключение к Интернету</span><span class="sxs-lookup"><span data-stu-id="bf994-121">Internet connection</span></span>
- <span data-ttu-id="bf994-122">Решение для обработки изображений (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bf994-122">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="bf994-123">Общие сведения о рабочем процессе для миграции и установки</span><span class="sxs-lookup"><span data-stu-id="bf994-123">Migration and installation workflow summary</span></span>

| <span data-ttu-id="bf994-124">Шаг</span><span class="sxs-lookup"><span data-stu-id="bf994-124">Step</span></span>  | <span data-ttu-id="bf994-125">Действие</span><span class="sxs-lookup"><span data-stu-id="bf994-125">Action</span></span>                                                                                                 | <span data-ttu-id="bf994-126">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bf994-126">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="bf994-127">1,1</span><span class="sxs-lookup"><span data-stu-id="bf994-127">1</span></span> | [<span data-ttu-id="bf994-128">Проверка версии UEFI на Surface Hub 2 соответствует минимальным требованиям</span><span class="sxs-lookup"><span data-stu-id="bf994-128">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="bf994-129">Убедитесь в том, что версия UEFI — 694.2938.768.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bf994-129">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="bf994-130">2</span><span class="sxs-lookup"><span data-stu-id="bf994-130">2</span></span> | [<span data-ttu-id="bf994-131">Загрузка драйверов и микропрограммного обеспечения конфигуратора UEFI Surface и Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-131">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="bf994-132">Загрузите [Конфигуратор UEFI Surface](https://www.microsoft.com/download/details.aspx?id=46703) из средства Surface для него и установите его на отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf994-132">Download [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT and install it on a separate PC.</span></span> <span data-ttu-id="bf994-133">Загрузите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974) и сохраните его для использования на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="bf994-133">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="bf994-134">Трехконтактный</span><span class="sxs-lookup"><span data-stu-id="bf994-134">3</span></span> | [<span data-ttu-id="bf994-135">Подготовка SEMM сертификата</span><span class="sxs-lookup"><span data-stu-id="bf994-135">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="bf994-136">Подготовка необходимого сертификата для запуска конфигуратора поверхности UEFI или использование текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="bf994-136">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="bf994-137">четырехпроцессорном</span><span class="sxs-lookup"><span data-stu-id="bf994-137">4</span></span> | [<span data-ttu-id="bf994-138">Создание пакета SEMM</span><span class="sxs-lookup"><span data-stu-id="bf994-138">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="bf994-139">Запустите конфигуратор UEFI Surface, чтобы создать пакет SEMM на USB-накопителе, который будет содержать необходимые файлы конфигурации для применения на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="bf994-139">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="bf994-140">Скопируйте эти файлы пакета SEMM в папку на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf994-140">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="bf994-141">5</span><span class="sxs-lookup"><span data-stu-id="bf994-141">5</span></span> | [<span data-ttu-id="bf994-142">Подготовка USB-накопителя, содержащего образ Windows 10, пакет SEMM и драйверы и микропрограммы для Windows 10 Pro и Enterprise на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-142">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="bf994-143">Создайте один USB-накопитель (под названием **BOOTME** в этом примере), содержащий образ Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bf994-143">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="bf994-144">Добавьте свои драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2 (шаг 2) и SEMM файлы пакета (шаг 4) на диск **BOOTME** .</span><span class="sxs-lookup"><span data-stu-id="bf994-144">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="bf994-145">152</span><span class="sxs-lookup"><span data-stu-id="bf994-145">6</span></span> | [<span data-ttu-id="bf994-146">Обновление UEFI на Surface Hub 2S для включения миграции ОС</span><span class="sxs-lookup"><span data-stu-id="bf994-146">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="bf994-147">Используйте диск **BOOTME** для загрузки Surface Hub 2 в меню UEFI и установите пакет SEMM.</span><span class="sxs-lookup"><span data-stu-id="bf994-147">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="bf994-148">5-7</span><span class="sxs-lookup"><span data-stu-id="bf994-148">7</span></span> | [<span data-ttu-id="bf994-149">Установка Windows 10 Pro или Enterprise версии 1903 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bf994-149">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="bf994-150">Используйте диск **BOOTME** для установки **Windows 10 Pro или Enterprise** версии 1903 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bf994-150">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="bf994-151">No8</span><span class="sxs-lookup"><span data-stu-id="bf994-151">8</span></span> | [<span data-ttu-id="bf994-152">Установка драйверов и встроенного по для Windows 10 Pro и Enterprise на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-152">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="bf994-153">Чтобы убедиться в том, что на вашем устройстве установлены последние обновления и драйверы, установите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="bf994-153">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="bf994-154">@</span><span class="sxs-lookup"><span data-stu-id="bf994-154">9</span></span> | [<span data-ttu-id="bf994-155">Полная настройка Surface Hub 2S как персонального устройства для повышения производительности</span><span class="sxs-lookup"><span data-stu-id="bf994-155">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="bf994-156">Включите набор рекомендуемых параметров и приложений, чтобы оптимизировать использование Surface Hub 2S в качестве персонального устройства для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="bf994-156">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="bf994-157">Проверка версии UEFI на Surface Hub 2 соответствует минимальным требованиям</span><span class="sxs-lookup"><span data-stu-id="bf994-157">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="bf994-158">Минимальная версия UEFI, необходимая перед переносом Surface Hub из Windows 10 Team на Настольный компьютер с Windows 10, **694.2938.768.0**.</span><span class="sxs-lookup"><span data-stu-id="bf994-158">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="bf994-159">Чтобы проверить текущую версию UEFI на вашем компьютере, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf994-159">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="bf994-160">На начальном экране Surface Hub 2S выберите **Пуск** и откройте **SurfaceApp** (поверхность "**все приложения**  >  **Surface**").</span><span class="sxs-lookup"><span data-stu-id="bf994-160">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="bf994-161">Выберите **рабочую область** , чтобы отобразить сведения о Surface Hub, в том числе текущую версию UEFI на устройстве.</span><span class="sxs-lookup"><span data-stu-id="bf994-161">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="bf994-162">Если версия UEFI — **694.2938.768.0** или более поздней, как показано ниже, UEFI может создать пакет SEMM для включения миграции операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bf994-162">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![Открыть приложение Surface & выберите поверхность](images/shm-fig1.png)
 
3. <span data-ttu-id="bf994-164">Если версия UEFI более ранняя, чем версия **694.2938.768.0**, необходимо получить текущую версию с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="bf994-164">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="bf994-165">Чтобы обновить UEFI из центра обновления Windows, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf994-165">To update UEFI from Windows Update:</span></span>**
1. <span data-ttu-id="bf994-166">На Surface Hub 2 Войдите в систему как **Администратор**, перейдите на вкладку **все**  >  **Параметры**приложений, >  **Обновите**центр  >  **обновления Windows** и установите все обновления, а затем перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="bf994-166">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="bf994-167">Проверьте версию UEFI с помощью приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="bf994-167">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="bf994-168">Примечание. Если вы не знаете имя пользователя или пароль администратора, вам нужно будет сбросить это устройство.</span><span class="sxs-lookup"><span data-stu-id="bf994-168">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="bf994-169">Дополнительные сведения можно найти в статье [Сброс и восстановление Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span><span class="sxs-lookup"><span data-stu-id="bf994-169">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="bf994-170">Повторите эти действия, пока не будет установлена версия UEFI **694.2938.768.0** или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bf994-170">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="bf994-171">Если вы по-прежнему не видите обновленную UEFI после нескольких попыток, ознакомьтесь с **журналом обновлений** и найдите все случаи, в которых произошел сбой установки встроенного по.</span><span class="sxs-lookup"><span data-stu-id="bf994-171">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="bf994-172">Может потребоваться сброс устройства (обновление**параметров**  >  **& восстановление системы безопасности**  >  **Reset device**).</span><span class="sxs-lookup"><span data-stu-id="bf994-172">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="bf994-173">Загрузка драйверов и микропрограммного обеспечения конфигуратора UEFI Surface и Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-173">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="bf994-174">На отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="bf994-174">On a separate PC:</span></span>

- <span data-ttu-id="bf994-175">Скачайте и установите [Конфигуратор UEFI Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703) из инструментальных средств Surface.</span><span class="sxs-lookup"><span data-stu-id="bf994-175">Download and install Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="bf994-176">Конфигуратор UEFI Surface нельзя запустить на Surface Hub 2, пока установлена Windows 10 Teams.</span><span class="sxs-lookup"><span data-stu-id="bf994-176">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="bf994-177">Загрузите [драйвер Surface Hub 2 драйверы и микропрограммное обеспечение Windows Installer. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974) , который будет применяться при установке новой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bf994-177">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="bf994-178">Подготовка SEMM сертификата</span><span class="sxs-lookup"><span data-stu-id="bf994-178">Prepare SEMM certificate</span></span>

<span data-ttu-id="bf994-179">Если вы используете конфигуратор UEFI Surface в первый раз, вам потребуется подготовить сертификат.</span><span class="sxs-lookup"><span data-stu-id="bf994-179">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="bf994-180">Этот сертификат гарантирует, что после регистрации устройства в SEMM для изменения параметров UEFI можно использовать только пакеты, созданные с помощью утвержденного сертификата.</span><span class="sxs-lookup"><span data-stu-id="bf994-180">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="bf994-181">Способ получения сертификата может отличаться в зависимости от размера или сложности вашей организации:</span><span class="sxs-lookup"><span data-stu-id="bf994-181">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="bf994-182">Крупная корпоративная организация обычно поддерживает собственную инфраструктуру сертификатов для создания сертификатов на стандартную методику обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="bf994-182">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="bf994-183">Компании среднего размера и другие пользователи могут получить сертификат от сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="bf994-183">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="bf994-184">Это рекомендуемый вариант для организаций, у которых нет достаточных экспертов или специальных групп ИТ – безопасности.</span><span class="sxs-lookup"><span data-stu-id="bf994-184">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="bf994-185">Кроме того, вы можете создать самозаверенный сертификат с помощью сценария PowerShell в следующей документации: Surface Management в соответствии с [требованиями сертификата в режиме управления предприятием](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="bf994-185">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="bf994-186">Вы также можете использовать PowerShell для создания собственного сертификата в соответствии с приведенной ниже документацией: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span><span class="sxs-lookup"><span data-stu-id="bf994-186">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

<span data-ttu-id="bf994-187">Для проверки подписи файлов конфигурации перед применением параметров UEFI необходимо обеспечить защиту пакета SEMM с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="bf994-187">The SEMM package must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="bf994-188">Дополнительные сведения можно найти в статье Руководство по [режиму управления предприятием в Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .</span><span class="sxs-lookup"><span data-stu-id="bf994-188">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="bf994-189">Создание пакета SEMM</span><span class="sxs-lookup"><span data-stu-id="bf994-189">Create SEMM package</span></span>

1. <span data-ttu-id="bf994-190">Откройте **Конфигуратор UEFI Surface** и нажмите кнопку **начать**.</span><span class="sxs-lookup"><span data-stu-id="bf994-190">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![Открытие конфигуратора UEFI Surface](images/shm-fig2.png)
   
2. <span data-ttu-id="bf994-192">Выберите **устройства Surface** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-192">Select **Surface Devices** and then select **Next**.</span></span>

   ![Выбор устройств Surface](images/shm-fig3.png)
  
3. <span data-ttu-id="bf994-194">Выберите **пакет конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="bf994-194">Select **Configuration Package**.</span></span>

   ![Выберите пакет конфигурации.](images/shm-fig4.png)
  
4. <span data-ttu-id="bf994-196">Выберите **Защита сертификата**.</span><span class="sxs-lookup"><span data-stu-id="bf994-196">Select **Certificate Protection**.</span></span>

   ![Выбор защиты сертификата](images/shm-fig5.png)

5. <span data-ttu-id="bf994-198">Вам будет предложено добавить PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="bf994-198">You will be prompted to add your certificate .pfx file.</span></span>

   ![Вам будет предложено добавить сертификат.](images/shm-fig6.png)
   
6. <span data-ttu-id="bf994-200">Введите **пароль сертификата** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bf994-200">Enter your **Certificate password** and select **OK**.</span></span>

   ![Введите пароль сертификата и нажмите кнопку ОК.](images/shm-fig7.png)

7. <span data-ttu-id="bf994-202">Нажмите кнопку **Защита паролем** , чтобы добавить пароль для UEFI Surface.</span><span class="sxs-lookup"><span data-stu-id="bf994-202">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="bf994-203">Этот пароль потребуется при загрузке с UEFI.</span><span class="sxs-lookup"><span data-stu-id="bf994-203">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="bf994-204">**Настоятельно рекомендуется** установить пароль UEFI, который будет использоваться на Surface Hub 2s.</span><span class="sxs-lookup"><span data-stu-id="bf994-204">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![Нажмите "Защита паролем"](images/shm-fig8.png)
   
8. <span data-ttu-id="bf994-206">Задайте **пароль UEFI** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bf994-206">Set a **UEFI password** and select **OK**.</span></span>

   ![Введите пароль UEFI](images/shm-fig9.png)

   > [!IMPORTANT]
   > <span data-ttu-id="bf994-208">Запишите пароль.</span><span class="sxs-lookup"><span data-stu-id="bf994-208">Make a note of your password.</span></span> <span data-ttu-id="bf994-209">Если вы забудете или потеряли свой пароль, процесс восстановления не будет завершен.</span><span class="sxs-lookup"><span data-stu-id="bf994-209">If you forget or lose your password, there is no recovery process.</span></span> 

9. <span data-ttu-id="bf994-210">Выберите **Surface Hub 2** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-210">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![Выберите Surface Hub 2S](images/shm-fig10.png)
   
10. <span data-ttu-id="bf994-212">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-212">Select **Next**.</span></span>

    ![Нажмите кнопку Далее.](images/shm-fig10a.png)

11. <span data-ttu-id="bf994-214">Чтобы разрешить установку Windows 10 Pro или Enterprise, выберите **EnableOsMigration.**</span><span class="sxs-lookup"><span data-stu-id="bf994-214">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![Выбор включения миграции операционной системы](images/shm-fig11.png)
    
12. <span data-ttu-id="bf994-216">Установите для параметра **EnableOSMigration** значение **вкл** ., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-216">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![Установите флажок Включить миграцию ОС на включен](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="bf994-218">После применения пакета SEMM все параметры UEFI выводятся серым цветом (заблокировано) в меню UEFI на устройстве.</span><span class="sxs-lookup"><span data-stu-id="bf994-218">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="bf994-219">Сюда входят значения по умолчанию для других параметров, например IPv6 для загрузки PXE.</span><span class="sxs-lookup"><span data-stu-id="bf994-219">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="bf994-220">Чтобы изменить параметры UEFI, необходимо применить другой пакет SEMM или отменить регистрацию устройства в SEMM.</span><span class="sxs-lookup"><span data-stu-id="bf994-220">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="bf994-221">Сохранение пакета SEMM на USB-накопитель</span><span class="sxs-lookup"><span data-stu-id="bf994-221">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="bf994-222">Подключите USB-накопитель к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="bf994-222">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="bf994-223">Выберите пункт **Hub 2** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-223">Choose **Hub 2S** and then select **Next**.</span></span>

   ![Выберите USB](images/shm-fig13.png)
   
2. <span data-ttu-id="bf994-225">Нажмите кнопку **построить**.</span><span class="sxs-lookup"><span data-stu-id="bf994-225">Select **Build**.</span></span>

   ![Нажмите кнопку "построить".](images/shm-fig14.png)

3. <span data-ttu-id="bf994-227">Запишите снимок экрана, а затем нажмите кнопку **завершить**.</span><span class="sxs-lookup"><span data-stu-id="bf994-227">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="bf994-228">Ваш пакет SEMM готов и содержит SEMM пакет **DfciUpdate. DFI** и текстовый файл с отпечаткой SEMM (последние два символа отпечатка сертификата).</span><span class="sxs-lookup"><span data-stu-id="bf994-228">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![Нажмите кнопку завершить.](images/shm-fig15.png)
   
4. <span data-ttu-id="bf994-230">Сохраните последние 2 символа отпечатка сертификата, необходимые для активации SEMM, когда вы примените пакет на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="bf994-230">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="bf994-231">Подготовка флэш-накопителя USB, содержащего образы Windows 10, пакет SEMM и драйверы и микропрограммы Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-231">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="bf994-232">Вы можете установить образ Windows 10 Pro или Enterprise (версии 1903 или более поздней) с помощью одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="bf994-232">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="bf994-233">Текущее решение для обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="bf994-233">Your current imaging solution.</span></span>

- <span data-ttu-id="bf994-234">[Ускоритель развертывания Surface](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) позволяет создать загружаемый образ Windows 10, который может включать все текущие обновления Windows 10, Office, другие приложения, которые вы можете выбрать, а также необходимые драйверы и микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="bf994-234">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="bf994-235">Флэш-накопитель USB с Windows 10 Pro или корпоративным образом, а также установка  [драйверов и встроенного по для Windows 10 Pro и Enterprise на Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="bf994-235">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 

<span data-ttu-id="bf994-236">В этой статье описывается создание USB-накопителя с установочного носителя и добавление файлов пакета SEMM, драйверов и микропрограмм для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="bf994-236">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="bf994-237">Если вы используете другие способы развертывания, перейдите к следующему разделу: [Обновление UEFI на Surface Hub 2S для включения миграции ОС](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span><span class="sxs-lookup"><span data-stu-id="bf994-237">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="bf994-238">После установки вам понадобится действующая лицензия для Windows 10 Pro или Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bf994-238">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="bf994-239">Для создания установки Windows 10 Pro следуйте инструкциям на странице [Загрузка Windows 10](https://www.microsoft.com/software-download/windows10) , чтобы воспользоваться средством для **создания мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="bf994-239">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="bf994-240">Чтобы скачать Windows 10 корпоративную, перейдите в [центр обслуживания для корпоративного лицензирования Майкрософт.](https://www.microsoft.com/licensing/servicecenter/default.aspx)..</span><span class="sxs-lookup"><span data-stu-id="bf994-240">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="bf994-241">Вставьте новый **USB-** накопитель.</span><span class="sxs-lookup"><span data-stu-id="bf994-241">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="bf994-242">Запустите средство **создания мультимедиа** , выберите пункт **Создание установочного носителя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-242">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![Создание установочного носителя](images/shm-fig16.png)
   
3. <span data-ttu-id="bf994-244">Выберите язык, Windows 10 и 64-разрядная версия (x64), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-244">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![Выберите язык, Windows 10 и 64-разрядный & нажмите кнопку Далее.](images/shm-fig17.png)
   
4. <span data-ttu-id="bf994-246">Выберите флэш- **накопитель USB** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bf994-246">Select **USB flash drive** and select **Next**.</span></span>

   ![Выберите флэш-накопитель USB и нажмите кнопку Далее.](images/shm-fig18.png)
   
5. <span data-ttu-id="bf994-248">Когда загрузка завершится, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bf994-248">When the download completes, select **Finish**.</span></span>

   ![Нажмите кнопку Готово.](images/shm-fig19.png)
   
6. <span data-ttu-id="bf994-250">Скопируйте файлы пакета SEMM и драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI на флэш-накопитель USB (**BOOTME**), содержащий образ Windows 10:</span><span class="sxs-lookup"><span data-stu-id="bf994-250">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI to the USB flash drive (**BOOTME**) containing your Windows 10 image:</span></span>

    - <span data-ttu-id="bf994-251">DfciUpdate.dfi</span><span class="sxs-lookup"><span data-stu-id="bf994-251">DfciUpdate.dfi</span></span>
    - <span data-ttu-id="bf994-252">Текстовый файл с отпечатком SEMM.</span><span class="sxs-lookup"><span data-stu-id="bf994-252">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="bf994-253">(В этом примере: SurfaceUEFI_2020Aug25_1058.txt)</span><span class="sxs-lookup"><span data-stu-id="bf994-253">(In this example: SurfaceUEFI_2020Aug25_1058.txt)</span></span>
    - <span data-ttu-id="bf994-254">Драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span><span class="sxs-lookup"><span data-stu-id="bf994-254">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="bf994-255">Обновление UEFI на Surface Hub 2S для включения миграции ОС</span><span class="sxs-lookup"><span data-stu-id="bf994-255">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

<span data-ttu-id="bf994-256">Используйте диск **BOOTME** для установки файлов пакета SEMM и обновления UEFI, что позволяет Surface Hub работать под управлением Windows 10 Pro или Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bf994-256">Use your **BOOTME** drive to install the SEMM package files and update the UEFI, enabling Surface Hub to run Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="bf994-257">После этого загрузитесь с **BOOTME** диска, чтобы установить Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bf994-257">Then boot from the **BOOTME** drive to install Windows 10.</span></span>

1. <span data-ttu-id="bf994-258">Вставьте **BOOTME** диск с файлами пакета SEMM, драйверами и встроенным по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI и Windows 10 устанавливают установочные файлы на USB-порт Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="bf994-258">Insert your **BOOTME** drive containing SEMM package files, Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI, and Windows 10 install files into the USB-A port on Surface Hub 2S.</span></span>  

2. <span data-ttu-id="bf994-259">Чтобы загрузить UEFI, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf994-259">To boot into UEFI:</span></span>

   1. <span data-ttu-id="bf994-260">Сначала отключите (выключить) Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="bf994-260">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="bf994-261">Нажмите и удерживайте **Громкость +** и нажмите и отпустите кнопку **Power** .</span><span class="sxs-lookup"><span data-stu-id="bf994-261">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="bf994-262">Продолжайте удерживать **том +** до тех пор, пока не появится меню UEFI.</span><span class="sxs-lookup"><span data-stu-id="bf994-262">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![Сохранить holdling том + до тех пор, пока не появится меню UEFI](images/shm-fig20.png)
      
3. <span data-ttu-id="bf994-264">После перезапуска устройства введите пароль UEFI, созданный ранее (настоятельно рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="bf994-264">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![После перезапуска устройства введите paassword UEFI.](images/shm-fig22.png)
   
4. <span data-ttu-id="bf994-266">В меню UEFI выберите пункт **Управление**  >  **установкой с USB**.</span><span class="sxs-lookup"><span data-stu-id="bf994-266">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![Выберите Управление & установку с USB](images/shm-fig21.png)
   
5. <span data-ttu-id="bf994-268">Нажмите кнопку **Перезапустить сейчас**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bf994-268">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="bf994-269">После этого устройство будет перезагружено и отобразится в центре экрана с четырьмя квадратными квадратиками, а затем закроется.</span><span class="sxs-lookup"><span data-stu-id="bf994-269">The device will reboot and display the white 4-square logo in the middle of screen and then it will shut down.</span></span>

   ![Нажмите кнопку Перезапустить сейчас](images/shm-fig25.png)
   
6. <span data-ttu-id="bf994-271">Нажмите и отпустите кнопку Power, и на экране появится красный экран с предложением активировать режим корпоративного управления Surface.</span><span class="sxs-lookup"><span data-stu-id="bf994-271">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="bf994-272">Введите свой **отпечаток сертификата**, пароль для **параметров UEFI** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bf994-272">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![Введите отпечаток сертификата на 2 символа](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="bf994-274">После активации SEMM на устройстве будет применен новый параметр UEFI **EnableOSMigration** .</span><span class="sxs-lookup"><span data-stu-id="bf994-274">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="bf994-275">Вы больше не сможете получить доступ к группе Windows 10, и вам придется перейти к следующему этапу и установить Windows 10 Pro или Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bf994-275">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="bf994-276">Устройство будет перезагружено, отобразится белый логотип в центре экрана, а затем снова закроется</span><span class="sxs-lookup"><span data-stu-id="bf994-276">The device will reboot, display the white 4-square logo in the middle of the screen, and then again it will shut down</span></span>

### <span data-ttu-id="bf994-277">Установка Windows 10 Pro или Enterprise</span><span class="sxs-lookup"><span data-stu-id="bf994-277">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="bf994-278">Если ваш загрузочный диск с Windows 10 Pro или Корпоративная версия не входит в USB-порт Surface Hub 2, вставьте его, а затем нажмите и отпустите кнопку Power.</span><span class="sxs-lookup"><span data-stu-id="bf994-278">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="bf994-279">При запуске устройства появится белый 4-квадрат в центре экрана, а затем вы увидите вращающийся круг под логотипом с четырьмя квадратиками.</span><span class="sxs-lookup"><span data-stu-id="bf994-279">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="bf994-280">Если устройство не загружается с USB-накопителя автоматически, включите его (отключите шнур питания и снова подключите его).</span><span class="sxs-lookup"><span data-stu-id="bf994-280">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="bf994-281">После того как вы включите шнур питания, устройство будет загружаться через несколько секунд на 4-квадратный логотип в середине экрана, а также можно нажать и отпустить кнопку питания, чтобы снова включить устройство.</span><span class="sxs-lookup"><span data-stu-id="bf994-281">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="bf994-282">Сразу же после того, как вы увидите в середине экрана логотип с четырьмя квадратиками, нажмите и удерживайте кнопку вниз, пока не увидите значок вращающегося кружка ниже белого квадрата.</span><span class="sxs-lookup"><span data-stu-id="bf994-282">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![Загрузка Windows 10 с USB](images/shm-fig26.png)
   
4. <span data-ttu-id="bf994-284">При запуске программы установки в окне приветствия (OOBE) следуйте инструкциям по установке Windows 10 Pro или Enterprise (версии 1903 или более поздней).</span><span class="sxs-lookup"><span data-stu-id="bf994-284">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="bf994-285">Установка драйверов и микропрограммного обеспечения Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="bf994-285">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="bf994-286">Чтобы убедиться в том, что на вашем устройстве установлены последние обновления и драйверы, установите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="bf994-286">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="bf994-287">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="bf994-287">Next steps</span></span>

<span data-ttu-id="bf994-288">Чтобы полностью настроить Surface Hub 2S в качестве персонального устройства для повышения производительности, ознакомьтесь с [Разстройкой Windows 10 Pro или Enterprise на Surface Hub 2](surface-hub-2-post-install.md).</span><span class="sxs-lookup"><span data-stu-id="bf994-288">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="bf994-289">Если после выполнения действий, описанных в этом документе, перенос устройства на Windows 10 Pro или Enterprise для Surface Hub 2 завершается неудачей, обратитесь в [службу поддержки Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="bf994-289">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="bf994-290">Возврат к команде Windows 10</span><span class="sxs-lookup"><span data-stu-id="bf994-290">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="bf994-291">Если вы хотите восстановить устройство в рамках команды Windows 10, ознакомьтесь со [сведениями сброс и восстановление Surface Hub 2S](surface-hub-2s-recover-reset.md)</span><span class="sxs-lookup"><span data-stu-id="bf994-291">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)</span></span>

## <span data-ttu-id="bf994-292">Журнал версий</span><span class="sxs-lookup"><span data-stu-id="bf994-292">Version history</span></span>

| <span data-ttu-id="bf994-293">Версия</span><span class="sxs-lookup"><span data-stu-id="bf994-293">Version</span></span> | <span data-ttu-id="bf994-294">Дата</span><span class="sxs-lookup"><span data-stu-id="bf994-294">Date</span></span>               | <span data-ttu-id="bf994-295">Описание</span><span class="sxs-lookup"><span data-stu-id="bf994-295">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="bf994-296">v.</span><span class="sxs-lookup"><span data-stu-id="bf994-296">v.</span></span> <span data-ttu-id="bf994-297">1,1</span><span class="sxs-lookup"><span data-stu-id="bf994-297">1.1</span></span>  | <span data-ttu-id="bf994-298">15 сентября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="bf994-298">September 15, 2020</span></span> | <span data-ttu-id="bf994-299">Помещено дополнительное примечание в разделе Введение в требования к лицензированию для установки новой ОС.</span><span class="sxs-lookup"><span data-stu-id="bf994-299">Placed additional note in the Introduction clarifying licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="bf994-300">v.</span><span class="sxs-lookup"><span data-stu-id="bf994-300">v.</span></span> <span data-ttu-id="bf994-301">1.0</span><span class="sxs-lookup"><span data-stu-id="bf994-301">1.0</span></span>  | <span data-ttu-id="bf994-302">1 сентября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="bf994-302">September 1, 2020</span></span>  | <span data-ttu-id="bf994-303">Новая статья</span><span class="sxs-lookup"><span data-stu-id="bf994-303">New article</span></span>                                                                                           |
