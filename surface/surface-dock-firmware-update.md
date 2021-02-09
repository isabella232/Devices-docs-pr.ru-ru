---
title: Обновление микропрограммы Microsoft Surface Dock 1
description: В этой статье объясняется, как использовать Microsoft Surface Dock Firmware Update для установки и управления микропрограммой на исходной док-станции Surface 1. При установке на устройстве Surface он обновляет устройства док-станции Surface 1, подключенные к устройству Surface.
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319213"
---
# <span data-ttu-id="a2cdc-104">Обновление микропрограммы док-станции Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2cdc-105">Эта статья содержит технические инструкции для ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="a2cdc-106">Если вы — домашний пользователь, см. информацию об обновлении по док-станции [Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)на сайте поддержки   Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="a2cdc-107">Инструкции на сайте поддержки такие же, как в общих шагах по установке ниже, но в этой статье приведены дополнительные сведения для мониторинга, проверки и развертывания обновления на нескольких устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="a2cdc-108">В этой статье объясняется, как использовать Microsoft Surface Dock Firmware Update для установки и управления микропрограммой на исходной док-станции Surface 1.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="a2cdc-109">При установке на устройстве Surface он обновляет устройства док-станции Surface 1, подключенные к устройству Surface.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="a2cdc-110">Эта статья не относится к док-станции Surface 2, которая автоматически получает обновления через Обновление Windows или с помощью Microsoft Endpoint Configuration Manager или других средств развертывания MSI.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="a2cdc-111">Дополнительные узнать см. в новых [новых функциях док-станции Surface.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="a2cdc-112">Это средство перемежает предыдущее средство Microsoft Surface Dock Updater, ранее доступное для скачивания в составе средств Surface для ИТ-служб.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="a2cdc-113">Предыдущее средство называлось Surface_Dock_Updater_vx.xx.xxx.x.msi (где x указывает номер версии) и больше не доступно для скачивания и не должно использоваться.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="a2cdc-114">Установка обновления микропрограмм док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="a2cdc-115">В этом разделе описано, как вручную установить обновление микропрограмм.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="a2cdc-116">Корпорация Майкрософт периодически выпускает новые версии обновления микропрограмм док-станции Surface.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="a2cdc-117">MSI-файл не обновляется самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="a2cdc-118">Если вы развернули MSI на устройства Surface и выпущена новая версия микропрограммы, потребуется развернуть новую версию.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="a2cdc-119">Скачайте и установите [microsoft Surface Dock Firmware Update.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="a2cdc-120">Для обновления требуется устройство Surface под управлением Windows 10 версии 1803 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="a2cdc-121">При установке MSI-файла может потребоваться перезапустить Surface.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="a2cdc-122">Однако для выполнения обновления перезагрузка не требуется.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="a2cdc-123">Отсоедините устройство Surface от док-станции Surface, подождите около 5 секунд и снова подключите устройство.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="a2cdc-124">Обновление микропрограмм док-станции Surface автоматически обновляет док-станцию в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="a2cdc-125">Процесс может занять несколько минут и будет продолжен, даже если его прерывать.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="a2cdc-126">Мониторинг обновления микропрограмм док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="a2cdc-127">Этот раздел является необязательным и содержит обзор отслеживания установки обновления микропрограмм.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="a2cdc-128">Для отслеживания обновления:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-128">To monitor the update:</span></span>

1. <span data-ttu-id="a2cdc-129">Откройте окно просмотра событий, перейдите в приложение "Журналы \*\*\*\* **Windows>",** а затем в области "Действия" в правой области щелкните "Фильтр текущего журнала", \*\*\*\* введите **SurfaceDockFwUpdate** рядом с источниками событий **и**нажмите кнопку **"ОК"**.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="a2cdc-130">Введите следующую команду в командной области с повышенными уровнями:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="a2cdc-131">Установите обновление, как описано в [следующем разделе](#install-the-surface-dock-firmware-update) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="a2cdc-132">Событие 2007 со следующим текстом означает успешное обновление: обновление микропрограммы **завершено. hr=0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="a2cdc-133">Если обновление не прошло успешно, то событие 2007 будет отображаться как событие **ошибки,** а не **"Сведения".**</span><span class="sxs-lookup"><span data-stu-id="a2cdc-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="a2cdc-134">Кроме того, версия, зарегистрированная в реестре Windows, не будет текущей.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="a2cdc-135">После завершения обновления обновленные значения DWORD будут отображаться в реестре Windows, соответствующем текущей версии средства.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="a2cdc-136">Подробные [сведения см. в](#versions-reference) справочном разделе "Версии" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="a2cdc-137">Например:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-137">For example:</span></span>

    - <span data-ttu-id="a2cdc-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="a2cdc-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="a2cdc-140">Если вы видите в тексте события "Не удается найти описание для события xxxx из источника SurfaceDockFwUpdate", это ожидаемое и может быть проигнорировано.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="a2cdc-141">См. также следующие разделы в этой статье:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="a2cdc-142">Проверка завершения обновления микропрограмм</span><span class="sxs-lookup"><span data-stu-id="a2cdc-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="a2cdc-143">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="a2cdc-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="a2cdc-144">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="a2cdc-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="a2cdc-145">Справочник по версиям</span><span class="sxs-lookup"><span data-stu-id="a2cdc-145">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="a2cdc-146">Сетевое развертывание</span><span class="sxs-lookup"><span data-stu-id="a2cdc-146">Network deployment</span></span>

<span data-ttu-id="a2cdc-147">Команды установщика Windows (Msiexec.exe) можно использовать для развертывания обновления микропрограмм док-станции Surface на нескольких устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="a2cdc-148">При использовании Microsoft Endpoint Configuration Manager или другого средства развертывания введите следующий синтаксис, чтобы убедиться, что установка происходит в тихом режиме:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="a2cdc-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="a2cdc-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="a2cdc-150">Например:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="a2cdc-151">По умолчанию файл журнала не создается.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-151">A log file is not created by default.</span></span> <span data-ttu-id="a2cdc-152">Чтобы создать файл журнала, необходимо указать "/l*v [путь]". Например: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="a2cdc-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="a2cdc-153">Дополнительные сведения можно найти в [документации по вариантам командной строки.](https://docs.microsoft.com/windows/win32/msi/command-line-options)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2cdc-154">Если вы хотите обновить док-станцию Surface любым другим способом, обратитесь к сведениям об обновлении док-станции [Surface.](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="a2cdc-155">Развертывание Intune</span><span class="sxs-lookup"><span data-stu-id="a2cdc-155">Intune deployment</span></span>

<span data-ttu-id="a2cdc-156">Вы можете использовать Intune для распространения обновления микропрограмм док-станции Surface на устройства.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="a2cdc-157">Сначала необходимо преобразовать MSI-файл в формат .intunewin, как описано в следующей документации: [intune Standalone —](https://docs.microsoft.com/intune/apps/apps-win32-app-management)управление приложениями Win32.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="a2cdc-158">Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-158">Use the following command:</span></span>
  - **<span data-ttu-id="a2cdc-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="a2cdc-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="a2cdc-160">Проверка завершения обновления микропрограммы</span><span class="sxs-lookup"><span data-stu-id="a2cdc-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="a2cdc-161">Микропрограмма док-станции Surface состоит из двух компонентов:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="a2cdc-162">**Component10:** Микроуровне контроллера (MCU)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="a2cdc-163">**Component20:** Прошивка порта отображения (DP).</span><span class="sxs-lookup"><span data-stu-id="a2cdc-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="a2cdc-164">Успешное завершение обновления микропрограмм док-станции Surface приводит к новым значениям ключа реестра для этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="a2cdc-165">Чтобы проверить обновления:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-165">To verify updates:</span></span>**

1. <span data-ttu-id="a2cdc-166">Откройте Regedit и перейдите к следующему пути реестра:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="a2cdc-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="a2cdc-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="a2cdc-168">Найди ключи реестра: **Component10CurrentFwVersion и Component20CurrentFwVersion,** которые ссылаются на программное обеспечение, которое в настоящее время находится на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Процесс установки обновления микропрограмм док-станции Surface](images/regeditDock.png)

3. <span data-ttu-id="a2cdc-170">Убедитесь, что новые значения ключей реестра соответствуют обновленным значениям ключа реестра, указанным в справочнике "Версии" в конце этого документа.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="a2cdc-171">Если значения совпадают, то микропрограмма была успешно обновлена.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="a2cdc-172">Если не удается проверить, просмотрите советы по регистрации событий и устранению неполадок в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="a2cdc-173">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="a2cdc-173">Event logging</span></span>

**<span data-ttu-id="a2cdc-174">Таблица1.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-174">Table 1.</span></span> <span data-ttu-id="a2cdc-175">Файлы журнала для обновления микропрограмм док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="a2cdc-176">Log</span><span class="sxs-lookup"><span data-stu-id="a2cdc-176">Log</span></span>                              | <span data-ttu-id="a2cdc-177">Расположение</span><span class="sxs-lookup"><span data-stu-id="a2cdc-177">Location</span></span>                               | <span data-ttu-id="a2cdc-178">Заметки</span><span class="sxs-lookup"><span data-stu-id="a2cdc-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a2cdc-179">Журнал обновления микропрограмм док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="a2cdc-180">Должен быть указан путь (см. примечание)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="a2cdc-181">В более ранних версиях этого средства записыты события в журналы приложений и служб\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="a2cdc-182">Журнал установки устройств с Windows</span><span class="sxs-lookup"><span data-stu-id="a2cdc-182">Windows Device Install log</span></span>       | <span data-ttu-id="a2cdc-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="a2cdc-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="a2cdc-184">Дополнительные сведения об использовании журнала установки устройств можно найти в документации [по журналу SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="a2cdc-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="a2cdc-185">Таблица2.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-185">Table 2.</span></span> <span data-ttu-id="a2cdc-186">ИД журнала событий для обновления микропрограмм док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="a2cdc-187">События регистрируются в журнале событий приложений.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="a2cdc-188">Примечание. В более ранних версиях этого средства события записыылись в журналы приложений и служб\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="a2cdc-189">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a2cdc-189">Event ID</span></span> | <span data-ttu-id="a2cdc-190">Тип события</span><span class="sxs-lookup"><span data-stu-id="a2cdc-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="a2cdc-191">2001</span><span class="sxs-lookup"><span data-stu-id="a2cdc-191">2001</span></span>     | <span data-ttu-id="a2cdc-192">Обновление микропрограмм док-станции запущено.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="a2cdc-193">2002</span><span class="sxs-lookup"><span data-stu-id="a2cdc-193">2002</span></span>     | <span data-ttu-id="a2cdc-194">Обновление микропрограммы док-станции пропущено, так как известно, что док-станция обновлена.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="a2cdc-195">2003</span><span class="sxs-lookup"><span data-stu-id="a2cdc-195">2003</span></span>     | <span data-ttu-id="a2cdc-196">Не удалось получить версию микропрограммы док-станции.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="a2cdc-197">2004</span><span class="sxs-lookup"><span data-stu-id="a2cdc-197">2004</span></span>     | <span data-ttu-id="a2cdc-198">Запрос версии микропрограммы.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="a2cdc-199">2005</span><span class="sxs-lookup"><span data-stu-id="a2cdc-199">2005</span></span>     | <span data-ttu-id="a2cdc-200">Не удалось запустить обновление по док-станции.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="a2cdc-201">2006</span><span class="sxs-lookup"><span data-stu-id="a2cdc-201">2006</span></span>     | <span data-ttu-id="a2cdc-202">Не удалось отправить пары предложений и полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="a2cdc-203">2007</span><span class="sxs-lookup"><span data-stu-id="a2cdc-203">2007</span></span>     | <span data-ttu-id="a2cdc-204">Обновление микропрограмм завершено.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="a2cdc-205">2008</span><span class="sxs-lookup"><span data-stu-id="a2cdc-205">2008</span></span>     | <span data-ttu-id="a2cdc-206">Телеметрия док-станции BEGIN.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="a2cdc-207">2011</span><span class="sxs-lookup"><span data-stu-id="a2cdc-207">2011</span></span>     | <span data-ttu-id="a2cdc-208">Телеметрия док-станции END.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-208">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="a2cdc-209">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="a2cdc-209">Troubleshooting tips</span></span>

- <span data-ttu-id="a2cdc-210">Полностью отключите питание док-станции Surface от питания переменного тока, чтобы сбросить док-станцию Surface.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="a2cdc-211">Отключите все периферийные устройства, кроме док-станции Surface.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="a2cdc-212">Удалить все текущие обновления микропрограмм док-станции Surface, а затем установить последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="a2cdc-213">Убедитесь, что док-станция Surface отключена, а затем предопустите достаточно времени для завершения обновления, отслеживаемого с помощью led-монитора в порте Ethernet док-станции.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="a2cdc-214">Подождите, пока led не перестанет мигать, прежде чем отключать док-станцию Surface от питания.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="a2cdc-215">Подключите док-станцию Surface к другому устройству, чтобы узнать, может ли она обновить док-станцию.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="a2cdc-216">Справочник по версиям</span><span class="sxs-lookup"><span data-stu-id="a2cdc-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="a2cdc-217">Файл установки выпущен в следующем формате \*\* именования: \*\*Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(например, Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) и устанавливается по умолчанию в папку C:\Program Files\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="a2cdc-218">Версия 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="a2cdc-219">Дата выпуска: 4 августа 2020 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="a2cdc-220">Эта версия обновления микропрограммы док-станции Surface включает исправления ошибок и поддержку:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="a2cdc-221">Обновление док-станции Surface 1 с помощью Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="a2cdc-222">Если вы работаете с Surface Pro X, скачайте . Сборка ARM64.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="a2cdc-223">Для всех остальных устройств используйте сборку AMD64.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="a2cdc-224">Значения ключей реестра</span><span class="sxs-lookup"><span data-stu-id="a2cdc-224">Registry key values</span></span>

<span data-ttu-id="a2cdc-225">Значения реестра, которые указывают состояние обновлений микропрограмм, не изменились по сравнению с предыдущей версией этого средства:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="a2cdc-226">Component10CurrentFwVersion обновлен до **версии 4ac3970.**</span><span class="sxs-lookup"><span data-stu-id="a2cdc-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="a2cdc-227">Component20CurrentFwVersion обновлен до **версии 4a1d570.**</span><span class="sxs-lookup"><span data-stu-id="a2cdc-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <span data-ttu-id="a2cdc-228">Версия 1.42.139</span><span class="sxs-lookup"><span data-stu-id="a2cdc-228">Version 1.42.139</span></span> 
*<span data-ttu-id="a2cdc-229">Дата выпуска: 18 сентября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="a2cdc-230">Эта версия, в Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, обновляет микропрограммы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="a2cdc-231">Обновленные значения ключей реестра</span><span class="sxs-lookup"><span data-stu-id="a2cdc-231">Updated registry key values</span></span>

- <span data-ttu-id="a2cdc-232">Component10CurrentFwVersion обновлен до **версии 4ac3970.**</span><span class="sxs-lookup"><span data-stu-id="a2cdc-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="a2cdc-233">Component20CurrentFwVersion обновлен до **версии 4a1d570.**</span><span class="sxs-lookup"><span data-stu-id="a2cdc-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="a2cdc-234">Он добавляет поддержку Surface Pro 7 и Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="a2cdc-235">Устаревшие версии</span><span class="sxs-lookup"><span data-stu-id="a2cdc-235">Legacy versions</span></span>

### <span data-ttu-id="a2cdc-236">Версия 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="a2cdc-237">Дата выпуска: 10 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="a2cdc-238">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="a2cdc-239">Добавление поддержки Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="a2cdc-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="a2cdc-240">Добавление поддержки surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="a2cdc-240">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="a2cdc-241">Версия 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="a2cdc-242">Дата выпуска: 26 июля 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="a2cdc-243">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="a2cdc-244">Повышение надежности обновления</span><span class="sxs-lookup"><span data-stu-id="a2cdc-244">Increase update reliability</span></span>
- <span data-ttu-id="a2cdc-245">Добавление поддержки Surface Go</span><span class="sxs-lookup"><span data-stu-id="a2cdc-245">Add support for Surface Go</span></span>

### <span data-ttu-id="a2cdc-246">Версия 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="a2cdc-247">Дата выпуска: 29 января 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="a2cdc-248">В этой версии Surface Dock Updater добавлена поддержка следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="a2cdc-249">обновление встроенного ПО основного чипсета док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="a2cdc-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="a2cdc-250">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="a2cdc-251">Повышенная стабильность внешних мониторов при использовании с Surface Book или Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="a2cdc-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="a2cdc-252">Кроме того, установка этой версии средства обновления Surface Dock на устройствах Surface Book, включает следующее:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="a2cdc-253">обновление встроенного ПО Surface Book Base;</span><span class="sxs-lookup"><span data-stu-id="a2cdc-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="a2cdc-254">поддержка обновления встроенного ПО док-станции Surface с улучшениями, предназначенными для устройств Surface Book.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="a2cdc-255">Версия 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="a2cdc-256">Дата выпуска: 3 ноября 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="a2cdc-257">В этой версии Surface Dock Updater добавлена поддержка следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a2cdc-258">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="a2cdc-259">Устраняет проблему передачи звука через пассивные адаптеры порта дисплея</span><span class="sxs-lookup"><span data-stu-id="a2cdc-259">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="a2cdc-260">Версия 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="a2cdc-261">Дата выпуска: 19 июня 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="a2cdc-262">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a2cdc-263">ноутбук Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-263">Surface Laptop</span></span>
* <span data-ttu-id="a2cdc-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a2cdc-264">Surface Pro</span></span>

### <span data-ttu-id="a2cdc-265">Версия 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="a2cdc-266">Дата выпуска: 7 апреля 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="a2cdc-267">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a2cdc-268">обновление встроенного ПО порта дисплея док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="a2cdc-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="a2cdc-269">требуется Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-269">Requires Windows 10</span></span>

### <span data-ttu-id="a2cdc-270">Версия 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="a2cdc-271">Дата выпуска: 21 октября 2016 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="a2cdc-272">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a2cdc-273">обновление для встроенного ПО USB док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="a2cdc-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="a2cdc-274">повышенная надежность порта Ethernet, звукового и USB-портов.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="a2cdc-275">Версия 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="a2cdc-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="a2cdc-276">Дата выпуска: 26 апреля 2016 г.</span><span class="sxs-lookup"><span data-stu-id="a2cdc-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="a2cdc-277">В этой версии Surface Dock Updater добавлена поддержка следующих возможностей:</span><span class="sxs-lookup"><span data-stu-id="a2cdc-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a2cdc-278">обновление встроенного ПО основного чипсета док-станции Surface;</span><span class="sxs-lookup"><span data-stu-id="a2cdc-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="a2cdc-279">обновление встроенного ПО порта дисплея док-станции Surface</span><span class="sxs-lookup"><span data-stu-id="a2cdc-279">Update for Surface Dock DisplayPort firmware</span></span>

