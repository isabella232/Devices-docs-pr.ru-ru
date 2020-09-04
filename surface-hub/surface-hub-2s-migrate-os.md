---
title: Переход на Windows 10 Pro или Корпоративная в Surface Hub 2
description: В этой статье описывается процесс перехода с Windows 10 на Surface Hub 2 на Windows 10 Pro или Windows 10 Enterprise.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: a114a9200a58a848f2480de965f268cee71cebae
ms.sourcegitcommit: c74835239cf4e304af59465fb6fc785de4a0c5cc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "10994605"
---
# <span data-ttu-id="c76e1-104">Переход на Windows 10 Pro или Корпоративная в Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="c76e1-105">Введение</span><span class="sxs-lookup"><span data-stu-id="c76e1-105">Introduction</span></span>

<span data-ttu-id="c76e1-106">Surface Hub 2S предварительно установлен в Windows 10 Team, настроенный выпуск Windows 10, разработанный для упрощения совместной работы в средах для собраний.</span><span class="sxs-lookup"><span data-stu-id="c76e1-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="c76e1-107">Теперь у вас есть возможность работать с Windows 10 Pro или Enterprise, чтобы использовать Surface Hub 2, как и любые другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="c76e1-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="c76e1-108">В отличие от обычного обновления или миграции, этот процесс требует подписаться на предварительное описание процедуры, как описано на этой странице.</span><span class="sxs-lookup"><span data-stu-id="c76e1-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="c76e1-109">Прежде чем продолжить, проанализируйте [компоненты решения](#solution-components) и [Рабочий процесс миграции](#migration-workflow-summary) .</span><span class="sxs-lookup"><span data-stu-id="c76e1-109">Review the [Solution components](#solution-components) and [Migration workflow](#migration-workflow-summary) before proceeding.</span></span>

<span data-ttu-id="c76e1-110">Вы запускаете миграцию из Windows 10 с помощью отдельного компьютера и средства для загрузки, а также средство для настройки **UEFI** — для создания пакета, содержащего новый параметр UEFI, применяемый к Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="c76e1-110">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="c76e1-111">Конфигуратор UEFI Surface выступает в качестве интерфейса в режиме корпоративного управления Surface (SEMM), предназначенного для централизованного управления параметрами микропрограмм на устройствах Surface в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="c76e1-111">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="c76e1-112">Чтобы узнать больше о SEMM, ознакомьтесь с [документацией по режиму корпоративного управления Surface (Майкрософт](https://docs.microsoft.com/surface/surface-enterprise-management-mode)).</span><span class="sxs-lookup"><span data-stu-id="c76e1-112">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="c76e1-113">Компоненты решения</span><span class="sxs-lookup"><span data-stu-id="c76e1-113">Solution Components</span></span>

- <span data-ttu-id="c76e1-114">Surface Hub 2S на устройстве с операционной системой Windows 10 Teams</span><span class="sxs-lookup"><span data-stu-id="c76e1-114">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="c76e1-115">Отдельное устройство под управлением Windows 10</span><span class="sxs-lookup"><span data-stu-id="c76e1-115">Separate device running Windows 10</span></span>
- <span data-ttu-id="c76e1-116">Инструмент конфигуратора UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c76e1-116">Surface UEFI Configurator tool</span></span>
- <span data-ttu-id="c76e1-117">Образ операционной системы Windows 10 Pro или Enterprise, версия 1903 или более поздняя</span><span class="sxs-lookup"><span data-stu-id="c76e1-117">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="c76e1-118">Два USB-накопителя с объемом памяти 16 ГБ, формат FAT32</span><span class="sxs-lookup"><span data-stu-id="c76e1-118">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="c76e1-119">Драйверы и микропрограммы для Windows 10 Pro и Enterprise на Surface Hub 2, установщик Windows. MSI-файл</span><span class="sxs-lookup"><span data-stu-id="c76e1-119">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="c76e1-120">Подключение к Интернету</span><span class="sxs-lookup"><span data-stu-id="c76e1-120">Internet connection</span></span>
- <span data-ttu-id="c76e1-121">Решение для обработки изображений (необязательно)</span><span class="sxs-lookup"><span data-stu-id="c76e1-121">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="c76e1-122">Сводка рабочего процесса миграции</span><span class="sxs-lookup"><span data-stu-id="c76e1-122">Migration workflow summary</span></span>

| <span data-ttu-id="c76e1-123">Шаг</span><span class="sxs-lookup"><span data-stu-id="c76e1-123">Step</span></span>  | <span data-ttu-id="c76e1-124">Действие</span><span class="sxs-lookup"><span data-stu-id="c76e1-124">Action</span></span>                                                                                                 | <span data-ttu-id="c76e1-125">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c76e1-125">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c76e1-126">1,1</span><span class="sxs-lookup"><span data-stu-id="c76e1-126">1</span></span> | [<span data-ttu-id="c76e1-127">Проверка версии UEFI на Surface Hub 2 соответствует минимальным требованиям</span><span class="sxs-lookup"><span data-stu-id="c76e1-127">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="c76e1-128">Убедитесь в том, что версия UEFI — 694.2938.768.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c76e1-128">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="c76e1-129">2</span><span class="sxs-lookup"><span data-stu-id="c76e1-129">2</span></span> | [<span data-ttu-id="c76e1-130">Загрузка драйверов и микропрограммного обеспечения конфигуратора UEFI Surface и Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-130">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="c76e1-131">Загрузите [Конфигуратор UEFI Surface](https://www.microsoft.com/download/details.aspx?id=46703) из средства Surface для него и установите его на отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c76e1-131">Download [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT and install it on a separate PC.</span></span> <span data-ttu-id="c76e1-132">Загрузите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974) и сохраните его для использования на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="c76e1-132">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="c76e1-133">Трехконтактный</span><span class="sxs-lookup"><span data-stu-id="c76e1-133">3</span></span> | [<span data-ttu-id="c76e1-134">Подготовка SEMM сертификата</span><span class="sxs-lookup"><span data-stu-id="c76e1-134">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="c76e1-135">Подготовка необходимого сертификата для запуска конфигуратора поверхности UEFI или использование текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="c76e1-135">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="c76e1-136">четырехпроцессорном</span><span class="sxs-lookup"><span data-stu-id="c76e1-136">4</span></span> | [<span data-ttu-id="c76e1-137">Создание пакета SEMM</span><span class="sxs-lookup"><span data-stu-id="c76e1-137">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="c76e1-138">Запустите конфигуратор UEFI Surface, чтобы создать пакет SEMM на USB-накопителе, который будет содержать необходимые файлы конфигурации для применения на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="c76e1-138">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="c76e1-139">Скопируйте эти файлы пакета SEMM в папку на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c76e1-139">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="c76e1-140">5</span><span class="sxs-lookup"><span data-stu-id="c76e1-140">5</span></span> | [<span data-ttu-id="c76e1-141">Подготовка USB-накопителя, содержащего образ Windows 10, пакет SEMM и драйверы и микропрограммы для Windows 10 Pro и Enterprise на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-141">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="c76e1-142">Создайте один USB-накопитель (под названием **BOOTME** в этом примере), содержащий образ Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c76e1-142">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="c76e1-143">Добавьте свои драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2 (шаг 2) и SEMM файлы пакета (шаг 4) на диск **BOOTME** .</span><span class="sxs-lookup"><span data-stu-id="c76e1-143">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="c76e1-144">152</span><span class="sxs-lookup"><span data-stu-id="c76e1-144">6</span></span> | [<span data-ttu-id="c76e1-145">Обновление UEFI на Surface Hub 2S для включения миграции ОС</span><span class="sxs-lookup"><span data-stu-id="c76e1-145">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="c76e1-146">Используйте диск **BOOTME** для загрузки Surface Hub 2 в меню UEFI и установите пакет SEMM.</span><span class="sxs-lookup"><span data-stu-id="c76e1-146">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="c76e1-147">5-7</span><span class="sxs-lookup"><span data-stu-id="c76e1-147">7</span></span> | [<span data-ttu-id="c76e1-148">Установка Windows 10 Pro или Enterprise версии 1903 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c76e1-148">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="c76e1-149">Используйте диск **BOOTME** для установки **Windows 10 Pro или Enterprise** версии 1903 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c76e1-149">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="c76e1-150">No8</span><span class="sxs-lookup"><span data-stu-id="c76e1-150">8</span></span> | [<span data-ttu-id="c76e1-151">Установка драйверов и встроенного по для Windows 10 Pro и Enterprise на Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-151">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="c76e1-152">Чтобы убедиться в том, что на вашем устройстве установлены последние обновления и драйверы, установите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="c76e1-152">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="c76e1-153">@</span><span class="sxs-lookup"><span data-stu-id="c76e1-153">9</span></span> | [<span data-ttu-id="c76e1-154">Полная настройка Surface Hub 2S как персонального устройства для повышения производительности</span><span class="sxs-lookup"><span data-stu-id="c76e1-154">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="c76e1-155">Включите набор рекомендуемых параметров и приложений, чтобы оптимизировать использование Surface Hub 2S в качестве персонального устройства для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="c76e1-155">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="c76e1-156">Проверка версии UEFI на Surface Hub 2 соответствует минимальным требованиям</span><span class="sxs-lookup"><span data-stu-id="c76e1-156">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="c76e1-157">Минимальная версия UEFI, необходимая перед переносом Surface Hub из Windows 10 Team на Настольный компьютер с Windows 10, **694.2938.768.0**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-157">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="c76e1-158">Чтобы проверить текущую версию UEFI на вашем компьютере, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c76e1-158">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="c76e1-159">На начальном экране Surface Hub 2S выберите **Пуск** и откройте **SurfaceApp** (поверхность "**все приложения**  >  **Surface**").</span><span class="sxs-lookup"><span data-stu-id="c76e1-159">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

1. <span data-ttu-id="c76e1-160">Выберите **рабочую область** , чтобы отобразить сведения о Surface Hub, в том числе текущую версию UEFI на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c76e1-160">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="c76e1-161">Если версия UEFI — **694.2938.768.0** или более поздней, как показано ниже, UEFI может создать пакет SEMM для включения миграции операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c76e1-161">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

   <span data-ttu-id="c76e1-162">! [Открыть Sur</span><span class="sxs-lookup"><span data-stu-id="c76e1-162">![Open Sur</span></span>
1. <span data-ttu-id="c76e1-163">Если версия UEFI более ранней, чем & приложение 6face выберите Surface] (Images/shm-fig1.png) 94.2938.768.0, вам нужно будет получить текущую версию с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="c76e1-163">If the UEFI version is earlier than version 6face App & select Your Surface](images/shm-fig1.png) 94.2938.768.0, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="c76e1-164">Чтобы обновить UEFI из центра обновления Windows, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c76e1-164">To update UEFI from Windows Update:</span></span>**
1. <span data-ttu-id="c76e1-165">На Surface Hub 2 Войдите в систему как **Администратор**, перейдите на вкладку **все**  >  **Параметры**приложений, >  **Обновите**центр  >  **обновления Windows** и установите все обновления, а затем перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="c76e1-165">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="c76e1-166">Проверьте версию UEFI с помощью приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="c76e1-166">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="c76e1-167">Примечание. Если вы не знаете имя пользователя или пароль администратора, вам нужно будет сбросить это устройство.</span><span class="sxs-lookup"><span data-stu-id="c76e1-167">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="c76e1-168">Дополнительные сведения можно найти в статье [Сброс и восстановление Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span><span class="sxs-lookup"><span data-stu-id="c76e1-168">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="c76e1-169">Повторите эти действия, пока не будет установлена версия UEFI **694.2938.768.0** или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c76e1-169">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="c76e1-170">Если вы по-прежнему не видите обновленную UEFI после нескольких попыток, ознакомьтесь с **журналом обновлений** и найдите все случаи, в которых произошел сбой установки встроенного по.</span><span class="sxs-lookup"><span data-stu-id="c76e1-170">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="c76e1-171">Может потребоваться сброс устройства (обновление**параметров**  >  **& восстановление системы безопасности**  >  **Reset device**).</span><span class="sxs-lookup"><span data-stu-id="c76e1-171">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="c76e1-172">Загрузка драйверов и микропрограммного обеспечения конфигуратора UEFI Surface и Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-172">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="c76e1-173">На отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="c76e1-173">On a separate PC:</span></span>

- <span data-ttu-id="c76e1-174">Скачайте и установите [Конфигуратор UEFI Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703) из инструментальных средств Surface.</span><span class="sxs-lookup"><span data-stu-id="c76e1-174">Download and install Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="c76e1-175">Конфигуратор UEFI Surface нельзя запустить на Surface Hub 2, пока установлена Windows 10 Teams.</span><span class="sxs-lookup"><span data-stu-id="c76e1-175">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="c76e1-176">Загрузите [драйвер Surface Hub 2 драйверы и микропрограммное обеспечение Windows Installer. MSI-файл](https://www.microsoft.com/download/details.aspx?id=101974) , который будет применяться при установке новой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c76e1-176">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="c76e1-177">Подготовка SEMM сертификата</span><span class="sxs-lookup"><span data-stu-id="c76e1-177">Prepare SEMM certificate</span></span>

<span data-ttu-id="c76e1-178">Если вы используете конфигуратор UEFI Surface в первый раз, вам потребуется подготовить сертификат.</span><span class="sxs-lookup"><span data-stu-id="c76e1-178">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="c76e1-179">Этот сертификат гарантирует, что после регистрации устройства в SEMM для изменения параметров UEFI можно использовать только пакеты, созданные с помощью утвержденного сертификата.</span><span class="sxs-lookup"><span data-stu-id="c76e1-179">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="c76e1-180">Способ получения сертификата может отличаться в зависимости от размера или сложности вашей организации:</span><span class="sxs-lookup"><span data-stu-id="c76e1-180">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="c76e1-181">Крупная корпоративная организация обычно поддерживает собственную инфраструктуру сертификатов для создания сертификатов на стандартную методику обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="c76e1-181">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="c76e1-182">Компании среднего размера и другие пользователи могут получить сертификат от сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="c76e1-182">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="c76e1-183">Это рекомендуемый вариант для организаций, у которых нет достаточных экспертов или специальных групп ИТ – безопасности.</span><span class="sxs-lookup"><span data-stu-id="c76e1-183">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="c76e1-184">Кроме того, вы можете создать самозаверенный сертификат с помощью сценария PowerShell в следующей документации: Surface Management в соответствии с [требованиями сертификата в режиме управления предприятием](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="c76e1-184">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="c76e1-185">Вы также можете использовать PowerShell для создания собственного сертификата в соответствии с приведенной ниже документацией: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="c76e1-185">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).</span></span>

<span data-ttu-id="c76e1-186">Для проверки подписи файлов конфигурации перед применением параметров UEFI необходимо обеспечить защиту пакета SEMM с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="c76e1-186">The SEMM package must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="c76e1-187">Дополнительные сведения можно найти в статье Руководство по [режиму управления предприятием в Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .</span><span class="sxs-lookup"><span data-stu-id="c76e1-187">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="c76e1-188">Создание пакета SEMM</span><span class="sxs-lookup"><span data-stu-id="c76e1-188">Create SEMM package</span></span>

1. <span data-ttu-id="c76e1-189">Откройте **Конфигуратор UEFI Surface** и нажмите кнопку **начать**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-189">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![Открытие конфигуратора UEFI Surface](images/shm-fig2.png)
   
2. <span data-ttu-id="c76e1-191">Выберите **устройства Surface** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-191">Select **Surface Devices** and then select **Next**.</span></span>

   ![Выбор устройств Surface](images/shm-fig3.png)
  
3. <span data-ttu-id="c76e1-193">Выберите **пакет конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-193">Select **Configuration Package**.</span></span>

   ![Выберите пакет конфигурации.](images/shm-fig4.png)
  
4. <span data-ttu-id="c76e1-195">Выберите **Защита сертификата**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-195">Select **Certificate Protection**.</span></span>

   ![Выбор защиты сертификата](images/shm-fig5.png)

5. <span data-ttu-id="c76e1-197">Вам будет предложено добавить PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="c76e1-197">You will be prompted to add your certificate .pfx file.</span></span>

   ![Вам будет предложено добавить сертификат.](images/shm-fig6.png)
   
6. <span data-ttu-id="c76e1-199">Введите **пароль сертификата** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-199">Enter your **Certificate password** and select **OK**.</span></span>

   ![Введите пароль сертификата и нажмите кнопку ОК.](images/shm-fig7.png)

7. <span data-ttu-id="c76e1-201">Нажмите кнопку **Защита паролем** , чтобы добавить пароль для UEFI Surface.</span><span class="sxs-lookup"><span data-stu-id="c76e1-201">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="c76e1-202">Этот пароль потребуется при загрузке с UEFI.</span><span class="sxs-lookup"><span data-stu-id="c76e1-202">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="c76e1-203">**Настоятельно рекомендуется** установить пароль UEFI, который будет использоваться на Surface Hub 2s.</span><span class="sxs-lookup"><span data-stu-id="c76e1-203">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![Нажмите "Защита паролем"](images/shm-fig8.png)
   
8. <span data-ttu-id="c76e1-205">Задайте **пароль UEFI** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-205">Set a **UEFI password** and select **OK**.</span></span>

   ![Введите пароль UEFI](images/shm-fig9.png)

   > [!IMPORTANT]
   > <span data-ttu-id="c76e1-207">Запишите пароль.</span><span class="sxs-lookup"><span data-stu-id="c76e1-207">Make a note of your password.</span></span> <span data-ttu-id="c76e1-208">Если вы забудете или потеряли свой пароль, процесс восстановления не будет завершен.</span><span class="sxs-lookup"><span data-stu-id="c76e1-208">If you forget or lose your password, there is no recovery process.</span></span> 

9. <span data-ttu-id="c76e1-209">Выберите **Surface Hub 2** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-209">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![Выберите Surface Hub 2S](images/shm-fig10.png)
   
10. <span data-ttu-id="c76e1-211">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-211">Select **Next**.</span></span>

    ![Нажмите кнопку Далее.](images/shm-fig10a.png)

11. <span data-ttu-id="c76e1-213">Чтобы разрешить установку Windows 10 Pro или Enterprise, выберите **EnableOsMigration.**</span><span class="sxs-lookup"><span data-stu-id="c76e1-213">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![Выбор включения миграции операционной системы](images/shm-fig11.png)
    
12. <span data-ttu-id="c76e1-215">Установите для параметра **EnableOSMigration** значение **вкл** ., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-215">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![Установите флажок Включить миграцию ОС на включен](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="c76e1-217">После применения пакета SEMM все параметры UEFI выводятся серым цветом (заблокировано) в меню UEFI на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c76e1-217">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="c76e1-218">Сюда входят значения по умолчанию для других параметров, например IPv6 для загрузки PXE.</span><span class="sxs-lookup"><span data-stu-id="c76e1-218">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="c76e1-219">Чтобы изменить параметры UEFI, необходимо применить другой пакет SEMM или отменить регистрацию устройства в SEMM.</span><span class="sxs-lookup"><span data-stu-id="c76e1-219">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="c76e1-220">Сохранение пакета SEMM на USB-накопитель</span><span class="sxs-lookup"><span data-stu-id="c76e1-220">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="c76e1-221">Подключите USB-накопитель к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c76e1-221">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="c76e1-222">Выберите пункт **Hub 2** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-222">Choose **Hub 2S** and then select **Next**.</span></span>

   ![Выберите USB](images/shm-fig13.png)
   
2. <span data-ttu-id="c76e1-224">Нажмите кнопку **построить**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-224">Select **Build**.</span></span>

   ![Нажмите кнопку "построить".](images/shm-fig14.png)

3. <span data-ttu-id="c76e1-226">Запишите снимок экрана, а затем нажмите кнопку **завершить**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-226">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="c76e1-227">Ваш пакет SEMM готов и содержит SEMM пакет **DfciUpdate. DFI** и текстовый файл с отпечаткой SEMM (последние два символа отпечатка сертификата).</span><span class="sxs-lookup"><span data-stu-id="c76e1-227">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![Нажмите кнопку завершить.](images/shm-fig15.png)
   
4. <span data-ttu-id="c76e1-229">Сохраните последние 2 символа отпечатка сертификата, необходимые для активации SEMM, когда вы примените пакет на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="c76e1-229">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="c76e1-230">Подготовка флэш-накопителя USB, содержащего образы Windows 10, пакет SEMM и драйверы и микропрограммы Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-230">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="c76e1-231">Вы можете установить образ Windows 10 Pro или Enterprise (версии 1903 или более поздней) с помощью одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c76e1-231">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="c76e1-232">Текущее решение для обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="c76e1-232">Your current imaging solution.</span></span>

- <span data-ttu-id="c76e1-233">[Ускоритель развертывания Surface](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) позволяет создать загружаемый образ Windows 10, который может включать все текущие обновления Windows 10, Office, другие приложения, которые вы можете выбрать, а также необходимые драйверы и микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="c76e1-233">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="c76e1-234">Флэш-накопитель USB с Windows 10 Pro или корпоративным образом, а также установка  [драйверов и встроенного по для Windows 10 Pro и Enterprise на Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="c76e1-234">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 

<span data-ttu-id="c76e1-235">В этой статье описывается создание USB-накопителя с установочного носителя и добавление файлов пакета SEMM, драйверов и микропрограмм для Windows 10 Pro и Enterprise на Surface Hub 2. MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="c76e1-235">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="c76e1-236">Если вы используете другие способы развертывания, перейдите к следующему разделу: [Обновление UEFI на Surface Hub 2S для включения миграции ОС](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span><span class="sxs-lookup"><span data-stu-id="c76e1-236">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="c76e1-237">После установки вам понадобится действующая лицензия для Windows 10 Pro или Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c76e1-237">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="c76e1-238">Для создания установки Windows 10 Pro следуйте инструкциям на странице [Загрузка Windows 10](https://www.microsoft.com/software-download/windows10) , чтобы воспользоваться средством для **создания мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="c76e1-238">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="c76e1-239">Чтобы скачать Windows 10 корпоративную, перейдите в [центр обслуживания для корпоративного лицензирования Майкрософт.](https://www.microsoft.com/licensing/servicecenter/default.aspx)..</span><span class="sxs-lookup"><span data-stu-id="c76e1-239">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="c76e1-240">Вставьте новый **USB-** накопитель.</span><span class="sxs-lookup"><span data-stu-id="c76e1-240">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="c76e1-241">Запустите средство **создания мультимедиа** , выберите пункт **Создание установочного носителя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-241">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![Создание установочного носителя](images/shm-fig16.png)
   
3. <span data-ttu-id="c76e1-243">Выберите язык, Windows 10 и 64-разрядная версия (x64), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-243">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![Выберите язык, Windows 10 и 64-разрядный & нажмите кнопку Далее.](images/shm-fig17.png)
   
4. <span data-ttu-id="c76e1-245">Выберите флэш- **накопитель USB** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-245">Select **USB flash drive** and select **Next**.</span></span>

   ![Выберите флэш-накопитель USB и нажмите кнопку Далее.](images/shm-fig18.png)
   
5. <span data-ttu-id="c76e1-247">Когда загрузка завершится, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-247">When the download completes, select **Finish**.</span></span>

   ![Нажмите кнопку Готово.](images/shm-fig19.png)
   
6. <span data-ttu-id="c76e1-249">Скопируйте файлы пакета SEMM и драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI на флэш-накопитель USB (**BOOTME**), содержащий образ Windows 10:</span><span class="sxs-lookup"><span data-stu-id="c76e1-249">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI to the USB flash drive (**BOOTME**) containing your Windows 10 image:</span></span>

    - <span data-ttu-id="c76e1-250">DfciUpdate.dfi</span><span class="sxs-lookup"><span data-stu-id="c76e1-250">DfciUpdate.dfi</span></span>
    - <span data-ttu-id="c76e1-251">Текстовый файл с отпечатком SEMM.</span><span class="sxs-lookup"><span data-stu-id="c76e1-251">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="c76e1-252">(В этом примере: SurfaceUEFI_2020Aug25_1058.txt)</span><span class="sxs-lookup"><span data-stu-id="c76e1-252">(In this example: SurfaceUEFI_2020Aug25_1058.txt)</span></span>
    - <span data-ttu-id="c76e1-253">Драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span><span class="sxs-lookup"><span data-stu-id="c76e1-253">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="c76e1-254">Обновление UEFI на Surface Hub 2S для включения миграции ОС</span><span class="sxs-lookup"><span data-stu-id="c76e1-254">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

<span data-ttu-id="c76e1-255">Используйте диск **BOOTME** для установки файлов пакета SEMM и обновления UEFI, что позволяет Surface Hub работать под управлением Windows 10 Pro или Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c76e1-255">Use your **BOOTME** drive to install the SEMM package files and update the UEFI, enabling Surface Hub to run Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="c76e1-256">После этого загрузитесь с **BOOTME** диска, чтобы установить Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c76e1-256">Then boot from the **BOOTME** drive to install Windows 10.</span></span>

1. <span data-ttu-id="c76e1-257">Вставьте **BOOTME** диск с файлами пакета SEMM, драйверами и встроенным по для Windows 10 Pro и Enterprise на Surface Hub 2. MSI и Windows 10 устанавливают установочные файлы на USB-порт Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="c76e1-257">Insert your **BOOTME** drive containing SEMM package files, Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI, and Windows 10 install files into the USB-A port on Surface Hub 2S.</span></span>  

2. <span data-ttu-id="c76e1-258">Чтобы загрузить UEFI, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c76e1-258">To boot into UEFI:</span></span>

   1. <span data-ttu-id="c76e1-259">Сначала отключите (выключить) Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="c76e1-259">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="c76e1-260">Нажмите и удерживайте **Громкость +** и нажмите и отпустите кнопку **Power** .</span><span class="sxs-lookup"><span data-stu-id="c76e1-260">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="c76e1-261">Продолжайте удерживать **том +** до тех пор, пока не появится меню UEFI.</span><span class="sxs-lookup"><span data-stu-id="c76e1-261">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![Сохранить holdling том + до тех пор, пока не появится меню UEFI](images/shm-fig20.png)
      
3. <span data-ttu-id="c76e1-263">После перезапуска устройства введите пароль UEFI, созданный ранее (настоятельно рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="c76e1-263">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![После перезапуска устройства введите paassword UEFI.](images/shm-fig22.png)
   
4. <span data-ttu-id="c76e1-265">В меню UEFI выберите пункт **Управление**  >  **установкой с USB**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-265">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![Выберите Управление & установку с USB](images/shm-fig21.png)
   
5. <span data-ttu-id="c76e1-267">Нажмите кнопку **Перезапустить сейчас**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c76e1-267">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="c76e1-268">Устройство будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="c76e1-268">The device will shut down.</span></span>

   ![Нажмите кнопку Перезапустить сейчас](images/shm-fig25.png)
   
6. <span data-ttu-id="c76e1-270">Нажмите и отпустите кнопку Power, и на экране появится красный экран с предложением активировать режим корпоративного управления Surface.</span><span class="sxs-lookup"><span data-stu-id="c76e1-270">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="c76e1-271">Введите свой **отпечаток сертификата**, пароль для **параметров UEFI** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c76e1-271">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![Введите отпечаток сертификата на 2 символа](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="c76e1-273">После активации SEMM на устройстве будет применен новый параметр UEFI **EnableOSMigration** .</span><span class="sxs-lookup"><span data-stu-id="c76e1-273">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="c76e1-274">Вы больше не сможете получить доступ к группе Windows 10, и вам придется перейти к следующему этапу и установить Windows 10 Pro или Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c76e1-274">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="c76e1-275">Устройство будет перезагружено, отобразится белый 4-квадрат в середине экрана, а затем снова отключить.</span><span class="sxs-lookup"><span data-stu-id="c76e1-275">The device will reboot, display the white 4-square in the middle of the screen, and then again turn off.</span></span>

### <span data-ttu-id="c76e1-276">Установка Windows 10 Pro или Enterprise</span><span class="sxs-lookup"><span data-stu-id="c76e1-276">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="c76e1-277">Если ваш загрузочный диск с Windows 10 Pro или Корпоративная версия не входит в USB-порт Surface Hub 2, вставьте его, а затем нажмите и отпустите кнопку Power.</span><span class="sxs-lookup"><span data-stu-id="c76e1-277">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="c76e1-278">При запуске устройства появится белый 4-квадрат в центре экрана, а затем вы увидите вращающийся круг под логотипом с четырьмя квадратиками.</span><span class="sxs-lookup"><span data-stu-id="c76e1-278">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="c76e1-279">Если устройство не загружается автоматически с USB-накопителя, отключите его (отключите шнур питания и снова подключите его), нажмите и отпустите кнопку питания, а затем нажмите и удерживайте кнопку прокрутки, пока не увидите вращающийся круг ниже белого из четырех квадратиков.</span><span class="sxs-lookup"><span data-stu-id="c76e1-279">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in),  press and release the power button and then press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![Загрузка Windows 10 с USB](images/shm-fig26.png)
   
4. <span data-ttu-id="c76e1-281">При запуске программы установки в окне приветствия (OOBE) следуйте инструкциям по установке Windows 10 Pro или Enterprise (версии 1903 или более поздней).</span><span class="sxs-lookup"><span data-stu-id="c76e1-281">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="c76e1-282">Установка драйверов и микропрограммного обеспечения Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="c76e1-282">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="c76e1-283">Чтобы убедиться в том, что на вашем устройстве установлены последние обновления и драйверы, установите [драйверы и встроенное по для Windows 10 Pro и Enterprise на Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="c76e1-283">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="c76e1-284">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c76e1-284">Next steps</span></span>

<span data-ttu-id="c76e1-285">Чтобы полностью настроить Surface Hub 2S в качестве персонального устройства для повышения производительности, ознакомьтесь с [Разстройкой Windows 10 Pro или Enterprise на Surface Hub 2](surface-hub-2-post-install.md).</span><span class="sxs-lookup"><span data-stu-id="c76e1-285">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="c76e1-286">Если после выполнения действий, описанных в этом документе, перенос устройства на Windows 10 Pro или Enterprise для Surface Hub 2 завершается неудачей, обратитесь в [службу поддержки Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="c76e1-286">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

