---
title: Обновление встроенного по Microsoft Surface Dock — технические сведения для ИТ-администраторов
description: В этой статье объясняется, как использовать обновление встроенного по Surface Dock для обновления микропрограммы Surface Dock. После установки на устройстве Surface она будет обновлять все стыковочные устройства, подключенные к устройству Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 8/05/2020
ms.openlocfilehash: 331d5122c6c64a99dad48ff6e5a90f38ce3d4ed4
ms.sourcegitcommit: 603bcb41dc1b7dd92d3bab1601fa6336480e1218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "10916030"
---
# <span data-ttu-id="ee8e0-104">Обновление встроенного по Surface Dock (Майкрософт): технические сведения для администраторов ИТ</span><span class="sxs-lookup"><span data-stu-id="ee8e0-104">Microsoft Surface Dock Firmware Update: Technical information for IT admins</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee8e0-105">В этой статье содержатся технические инструкции для ИТ – администраторов.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="ee8e0-106">Если вы являетесь домашним пользователем, ознакомьтесь [со сведениями о том, как обновить встроенное по Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   на сайте службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="ee8e0-107">Инструкции на сайте поддержки совпадают с общими инструкциями по установке, но в этой статье приведены дополнительные сведения для мониторинга, проверки и развертывания обновления на нескольких устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="ee8e0-108">В этой статье объясняется, как использовать обновление встроенного по Surface Dock для обновления микропрограммы Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-108">This article explains how to use Microsoft Surface Dock Firmware Update to update Surface Dock firmware.</span></span> <span data-ttu-id="ee8e0-109">После установки на устройстве Surface она будет обновлять все стыковочные устройства, подключенные к устройству Surface.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="ee8e0-110">Это средство заменяет более раннюю версию средства обновления Microsoft Surface Dock, ранее выпущенную для загрузки в составе средств Surface для него.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="ee8e0-111">Более ранний инструмент назывался Surface_Dock_Updater_vx.xx.xxx.x.msi (где x указывает номер версии) и больше не доступен для загрузки и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="ee8e0-112">Установка обновления встроенного по для Surface Dock</span><span class="sxs-lookup"><span data-stu-id="ee8e0-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="ee8e0-113">В этом разделе объясняется, как установить обновление встроенного по вручную.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="ee8e0-114">Корпорация Майкрософт периодически выпускает новые версии обновления встроенного по для Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="ee8e0-115">Файл MSI не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="ee8e0-116">Если вы развернули MSI для устройств Surface и вы выпустили новую версию микропрограммы, вам потребуется развернуть новую версию.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="ee8e0-117">Скачайте и установите [Обновление встроенного по Surface Dock (Майкрософт](https://www.microsoft.com/download/details.aspx?id=46703)).</span><span class="sxs-lookup"><span data-stu-id="ee8e0-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="ee8e0-118">Для установки обновления требуется устройство Surface под управлением Windows 10 версии 1803 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="ee8e0-119">Установка MSI-файла может подать запрос на перезапуск Surface.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="ee8e0-120">Однако перезагрузка не требуется для выполнения обновления.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="ee8e0-121">Отключите устройство Surface от стыковочного устройства (с помощью адаптера электросети), подождите 5 секунд, а затем снова подключитесь.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-121">Disconnect your Surface device from the Surface Dock (using the power adapter), wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="ee8e0-122">Обновление встроенного по для Surface Dock автоматически обновит закрепление в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="ee8e0-123">Процесс может занять несколько минут и продолжаться, даже если он будет прерван.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="ee8e0-124">Мониторинг обновления встроенного по закрепляемого по на Surface</span><span class="sxs-lookup"><span data-stu-id="ee8e0-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="ee8e0-125">Этот раздел является необязательным и содержит общие сведения о том, как следить за установкой обновления встроенного по.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="ee8e0-126">Для наблюдения за обновлением выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-126">To monitor the update:</span></span>

1. <span data-ttu-id="ee8e0-127">Откройте окно просмотра событий, перейдите в раздел " **журналы > приложение**", а затем в разделе **действия** на правой панели щелкните **фильтр текущего журнала**, введите **SurfaceDockFwUpdate** рядом с разделом " **источники событий**" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="ee8e0-128">Введите следующую команду в командной строке с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="ee8e0-129">Установите обновление, как описано в [следующем разделе](#install-the-surface-dock-firmware-update) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="ee8e0-130">Событие 2007 со следующим текстом указывает на успешное обновление: **Обновление встроенного по завершено. hr = 0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="ee8e0-131">Если обновление не прошло успешно, событие с кодом 2007 будет отображаться как событие **ошибки** , а не как **сведения**.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="ee8e0-132">Кроме того, версия, указанная в реестре Windows, не будет актуальной.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="ee8e0-133">После завершения обновления в реестре Windows появится обновленные значения DWORD, соответствующие текущей версии средства.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="ee8e0-134">Подробные сведения приведены в разделе [Справочник по версиям](#versions-reference) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="ee8e0-135">Например:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-135">For example:</span></span>
    - <span data-ttu-id="ee8e0-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="ee8e0-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="ee8e0-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="ee8e0-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="ee8e0-138">Если вы видите сообщение "описание для идентификатора события XXXX из исходного SurfaceDockFwUpdate не найдено" в тексте события, это ожидается и может быть проигнорировано.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="ee8e0-139">Кроме того, в этой статье вы узнаете о следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="ee8e0-140">Проверка завершения обновления встроенного по</span><span class="sxs-lookup"><span data-stu-id="ee8e0-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="ee8e0-141">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="ee8e0-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="ee8e0-142">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ee8e0-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="ee8e0-143">Справочник по версиям</span><span class="sxs-lookup"><span data-stu-id="ee8e0-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="ee8e0-144">Развертывание по сети</span><span class="sxs-lookup"><span data-stu-id="ee8e0-144">Network deployment</span></span>

<span data-ttu-id="ee8e0-145">Вы можете использовать команды установщика Windows (Msiexec.exe) для развертывания обновления встроенного по для Surface Dock на нескольких устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="ee8e0-146">При использовании диспетчера конфигураций конечных точек Microsoft или другого средства развертывания введите следующий синтаксис, чтобы убедиться, что установка не выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="ee8e0-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="ee8e0-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="ee8e0-148">Например:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="ee8e0-149">Файл журнала по умолчанию не создается.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-149">A log file is not created by default.</span></span> <span data-ttu-id="ee8e0-150">Чтобы создать файл журнала, необходимо добавить "/l*v [путь]". Например: Msiexec.exe/i \<path to msi file\> /l*v%WINDIR%\logs\ SurfaceDockFWI. log»</span><span class="sxs-lookup"><span data-stu-id="ee8e0-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="ee8e0-151">Дополнительные сведения можно найти в документации по [параметрам командной строки](https://docs.microsoft.com/windows/win32/msi/command-line-options) .</span><span class="sxs-lookup"><span data-stu-id="ee8e0-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee8e0-152">Если вы хотите, чтобы подложка Surface обновлялась с помощью любого другого метода, ознакомьтесь со сведениями о том, как [Обновить стыковочный узел Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) .</span><span class="sxs-lookup"><span data-stu-id="ee8e0-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="ee8e0-153">Развертывание Intune</span><span class="sxs-lookup"><span data-stu-id="ee8e0-153">Intune deployment</span></span>

<span data-ttu-id="ee8e0-154">Вы можете использовать Intune для распространения обновления встроенного по Surface Dock на ваши устройства.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="ee8e0-155">Сначала необходимо преобразовать MSI-файл в формат intunewin, как описано в следующей документации: [центр управления приложениями в Skype standalone-Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="ee8e0-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="ee8e0-156">Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-156">Use the following command:</span></span>
  - **<span data-ttu-id="ee8e0-157">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="ee8e0-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="ee8e0-158">Проверка завершения обновления встроенного по</span><span class="sxs-lookup"><span data-stu-id="ee8e0-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="ee8e0-159">Встроенное по Surface Dock состоит из двух компонентов:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="ee8e0-160">**Component10:** Встроенное по модуля Micro Controller (MCU)</span><span class="sxs-lookup"><span data-stu-id="ee8e0-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="ee8e0-161">**Component20:** Встроенное по порта (DP).</span><span class="sxs-lookup"><span data-stu-id="ee8e0-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="ee8e0-162">Успешное завершение обновления встроенного по для Surface Dock приводит к новым значениям раздела реестра для этих компонентов микропрограмм.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="ee8e0-163">Чтобы проверить наличие обновлений, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-163">To verify updates:</span></span>**

1. <span data-ttu-id="ee8e0-164">Откройте программу regedit и перейдите к следующему разделу реестра:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="ee8e0-165">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="ee8e0-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="ee8e0-166">Найдите разделы реестра: **Component10CurrentFwVersion и Component20CurrentFwVersion**, которые ссылаются на микропрограмму, установленную в настоящее время на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Процесс установки обновления встроенного по для Surface Dock](images/regeditDock.png)

3. <span data-ttu-id="ee8e0-168">Убедитесь, что новые значения в реестре соответствуют обновленным значениям раздела реестра, указанным в ссылке версии в конце документа.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="ee8e0-169">Если значения совпадают, микропрограмма успешно обновлена.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="ee8e0-170">Если не удается проверить, ознакомьтесь с разделом журнал событий и советы по устранению неполадок в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="ee8e0-171">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="ee8e0-171">Event logging</span></span>

**<span data-ttu-id="ee8e0-172">Таблица1.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-172">Table 1.</span></span> <span data-ttu-id="ee8e0-173">Файлы журнала для обновления встроенного по для Surface Dock</span><span class="sxs-lookup"><span data-stu-id="ee8e0-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="ee8e0-174">Log</span><span class="sxs-lookup"><span data-stu-id="ee8e0-174">Log</span></span>                              | <span data-ttu-id="ee8e0-175">Местонахождение</span><span class="sxs-lookup"><span data-stu-id="ee8e0-175">Location</span></span>                               | <span data-ttu-id="ee8e0-176">Заметки</span><span class="sxs-lookup"><span data-stu-id="ee8e0-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ee8e0-177">Журнал обновлений встроенного по для Surface Dock</span><span class="sxs-lookup"><span data-stu-id="ee8e0-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="ee8e0-178">Необходимо указать путь (см. Примечание)</span><span class="sxs-lookup"><span data-stu-id="ee8e0-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="ee8e0-179">Более ранними версиями этого средства были написаны события для приложений и служб Logs\Microsoft Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="ee8e0-180">Журнал установки устройств Windows</span><span class="sxs-lookup"><span data-stu-id="ee8e0-180">Windows Device Install log</span></span>       | <span data-ttu-id="ee8e0-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="ee8e0-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="ee8e0-182">Дополнительные сведения об использовании журнала установки устройств можно найти в документации [Setupapi Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) .</span><span class="sxs-lookup"><span data-stu-id="ee8e0-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="ee8e0-183">Таблица2.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-183">Table 2.</span></span> <span data-ttu-id="ee8e0-184">Идентификаторы журнала событий для обновления встроенного по для Surface Dock</span><span class="sxs-lookup"><span data-stu-id="ee8e0-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="ee8e0-185">События записываются в журнал событий приложений.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="ee8e0-186">Примечание. более ранними версиями этого средства были написаны события для приложений и служб Logs\Microsoft Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="ee8e0-187">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ee8e0-187">Event ID</span></span> | <span data-ttu-id="ee8e0-188">Тип события</span><span class="sxs-lookup"><span data-stu-id="ee8e0-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="ee8e0-189">2001</span><span class="sxs-lookup"><span data-stu-id="ee8e0-189">2001</span></span>     | <span data-ttu-id="ee8e0-190">Обновление встроенного по Dock запущено.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="ee8e0-191">2002</span><span class="sxs-lookup"><span data-stu-id="ee8e0-191">2002</span></span>     | <span data-ttu-id="ee8e0-192">Обновление встроенного по Dock пропущено, так как Dock имеет актуальную версию.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="ee8e0-193">2003</span><span class="sxs-lookup"><span data-stu-id="ee8e0-193">2003</span></span>     | <span data-ttu-id="ee8e0-194">Обновление встроенного по Dock не удалось получить версию встроенного по.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="ee8e0-195">2004</span><span class="sxs-lookup"><span data-stu-id="ee8e0-195">2004</span></span>     | <span data-ttu-id="ee8e0-196">Запросите версию микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="ee8e0-197">2005</span><span class="sxs-lookup"><span data-stu-id="ee8e0-197">2005</span></span>     | <span data-ttu-id="ee8e0-198">Встроенное по Dock не удалось запустить обновление.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="ee8e0-199">2006</span><span class="sxs-lookup"><span data-stu-id="ee8e0-199">2006</span></span>     | <span data-ttu-id="ee8e0-200">Не удалось отправить пары предложения и полезных данных.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="ee8e0-201">2007</span><span class="sxs-lookup"><span data-stu-id="ee8e0-201">2007</span></span>     | <span data-ttu-id="ee8e0-202">Обновление встроенного по завершилось.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="ee8e0-203">2008</span><span class="sxs-lookup"><span data-stu-id="ee8e0-203">2008</span></span>     | <span data-ttu-id="ee8e0-204">НАЧАТЬ телеметрию Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="ee8e0-205">2011</span><span class="sxs-lookup"><span data-stu-id="ee8e0-205">2011</span></span>     | <span data-ttu-id="ee8e0-206">Телеметрическая подброска.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="ee8e0-207">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ee8e0-207">Troubleshooting tips</span></span>

- <span data-ttu-id="ee8e0-208">Вы можете полностью отключить питание от устройства Surface Dock из разъема переменного тока, чтобы сбросить док Surface.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="ee8e0-209">Разъедините все периферийные устройства, кроме док Surface.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="ee8e0-210">Удалите все текущие обновления встроенного по стыковочного узла Surface, а затем установите последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="ee8e0-211">Убедитесь в том, что стыковочный узел не подключен к сети, а затем подождите, пока обновление завершится с помощью индикатора на порте Ethernet Dock.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="ee8e0-212">Дождитесь, пока индикатор не перестанет мигать, прежде чем отключать Surface Dock из Power.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="ee8e0-213">Подключите стыковочный модуль Surface на другом устройстве, чтобы узнать, может ли она обновить док-станция.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="ee8e0-214">Справочник по версиям</span><span class="sxs-lookup"><span data-stu-id="ee8e0-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="ee8e0-215">Файл установки освобождается в следующем формате: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) и по умолчанию устанавливается в папку C:\Program Files\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="ee8e0-216">Версия 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-216">Version 1.53.139.0</span></span>
*<span data-ttu-id="ee8e0-217">Дата выпуска: 4 августа 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-217">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="ee8e0-218">Эта версия обновления встроенного по для Surface Dock включает исправления ошибок и поддержку:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-218">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="ee8e0-219">Обновление Dock Surface 1 с помощью Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-219">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ee8e0-220">Если вы используете Surface Pro X, скачайте файл. Сборка ARM64.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-220">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="ee8e0-221">Для всех остальных устройств используйте сборку AMD64.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-221">For all other devices, use the AMD64 build.</span></span> 
 


### <span data-ttu-id="ee8e0-222">Версия 1.42.139</span><span class="sxs-lookup"><span data-stu-id="ee8e0-222">Version 1.42.139</span></span> 
*<span data-ttu-id="ee8e0-223">Дата выпуска: Сентябрь 18 2019</span><span class="sxs-lookup"><span data-stu-id="ee8e0-223">Release Date: September 18 2019</span></span>*

<span data-ttu-id="ee8e0-224">Эта версия, содержащаяся в Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, обновляет микропрограммы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-224">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="ee8e0-225">Обновлены значения разделов реестра:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-225">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="ee8e0-226">Component10CurrentFwVersion обновлен до **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="ee8e0-227">Component20CurrentFwVersion обновлен до **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="ee8e0-228">Она добавляет поддержку для планшетов Surface Pro 7 и Surface 3.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-228">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="ee8e0-229">Устаревшие версии</span><span class="sxs-lookup"><span data-stu-id="ee8e0-229">Legacy versions</span></span>

### <span data-ttu-id="ee8e0-230">Версия 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-230">Version 2.23.139.0</span></span>
*<span data-ttu-id="ee8e0-231">Дата выпуска: 10 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-231">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="ee8e0-232">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-232">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="ee8e0-233">Добавление поддержки для Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="ee8e0-233">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="ee8e0-234">Добавление поддержки для портативного компьютера Surface 2</span><span class="sxs-lookup"><span data-stu-id="ee8e0-234">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="ee8e0-235">Версия 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-235">Version 2.22.139.0</span></span>
*<span data-ttu-id="ee8e0-236">Дата выпуска: 26 июля 2018</span><span class="sxs-lookup"><span data-stu-id="ee8e0-236">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="ee8e0-237">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-237">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="ee8e0-238">Повышение надежности обновления</span><span class="sxs-lookup"><span data-stu-id="ee8e0-238">Increase update reliability</span></span>
- <span data-ttu-id="ee8e0-239">Добавление поддержки Surface Go</span><span class="sxs-lookup"><span data-stu-id="ee8e0-239">Add support for Surface Go</span></span>

### <span data-ttu-id="ee8e0-240">Версия 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-240">Version 2.12.136.0</span></span>
*<span data-ttu-id="ee8e0-241">Дата выпуска: 29 января 2018 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-241">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="ee8e0-242">В этой версии Surface Dock Updater добавлена поддержка следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-242">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="ee8e0-243">обновление встроенного ПО основного чипсета док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="ee8e0-243">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="ee8e0-244">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="ee8e0-244">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="ee8e0-245">Повышенная стабильность внешних мониторов при использовании с Surface Book или Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="ee8e0-245">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="ee8e0-246">Кроме того, установка этой версии средства обновления Surface Dock на устройствах Surface Book, включает следующее:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-246">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="ee8e0-247">обновление встроенного ПО Surface Book Base;</span><span class="sxs-lookup"><span data-stu-id="ee8e0-247">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="ee8e0-248">поддержка обновления встроенного ПО док-станции Surface с улучшениями, предназначенными для устройств Surface Book.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-248">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="ee8e0-249">Версия 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-249">Version 2.9.136.0</span></span>
*<span data-ttu-id="ee8e0-250">Дата выпуска: 3 ноября 2017 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-250">Release date: November 3, 2017</span></span>*

<span data-ttu-id="ee8e0-251">В этой версии Surface Dock Updater добавлена поддержка следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-251">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ee8e0-252">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="ee8e0-252">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="ee8e0-253">Устраняет проблему передачи звука через пассивные адаптеры порта дисплея</span><span class="sxs-lookup"><span data-stu-id="ee8e0-253">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="ee8e0-254">Версия 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-254">Version 2.1.15.0</span></span>
*<span data-ttu-id="ee8e0-255">Дата выпуска: 19 июня 2017 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-255">Release date: June 19, 2017</span></span>*

<span data-ttu-id="ee8e0-256">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-256">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ee8e0-257">ноутбук Surface</span><span class="sxs-lookup"><span data-stu-id="ee8e0-257">Surface Laptop</span></span>
* <span data-ttu-id="ee8e0-258">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="ee8e0-258">Surface Pro</span></span>

### <span data-ttu-id="ee8e0-259">Версия 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-259">Version 2.1.6.0</span></span>
*<span data-ttu-id="ee8e0-260">Дата выпуска: 7 апреля 2017 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-260">Release date: April 7, 2017</span></span>*

<span data-ttu-id="ee8e0-261">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-261">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ee8e0-262">обновление встроенного ПО порта дисплея док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="ee8e0-262">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="ee8e0-263">требуется Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-263">Requires Windows 10</span></span>

### <span data-ttu-id="ee8e0-264">Версия 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-264">Version 2.0.22.0</span></span>
*<span data-ttu-id="ee8e0-265">Дата выпуска: 21 октября 2016 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-265">Release date: October 21, 2016</span></span>*

<span data-ttu-id="ee8e0-266">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-266">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ee8e0-267">обновление для встроенного ПО USB док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="ee8e0-267">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="ee8e0-268">повышенная надежность порта Ethernet, звукового и USB-портов.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-268">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="ee8e0-269">Версия 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="ee8e0-269">Version 1.0.8.0</span></span>
*<span data-ttu-id="ee8e0-270">Дата выпуска: 26 апреля 2016 г.</span><span class="sxs-lookup"><span data-stu-id="ee8e0-270">Release date: April 26, 2016</span></span>*

<span data-ttu-id="ee8e0-271">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="ee8e0-271">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ee8e0-272">обновление встроенного ПО основного чипсета док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="ee8e0-272">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="ee8e0-273">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="ee8e0-273">Update for Surface Dock DisplayPort firmware</span></span>

