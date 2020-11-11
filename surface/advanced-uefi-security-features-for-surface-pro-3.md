---
title: Расширенные функции безопасности UEFI для Surface Pro 3
description: В этой статье описано, как установить и настроить обновление UEFI версии 3.11.760.0, чтобы включить дополнительные параметры безопасности для устройств Surface Pro 3.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: безопасность, функции, настройка, оборудование, устройство, специальный, сценарий, обновление
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163187"
---
# <span data-ttu-id="274fb-104">Расширенные функции безопасности UEFI для Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="274fb-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="274fb-105">В этой статье описано, как установить и настроить обновление UEFI версии 3.11.760.0, чтобы включить дополнительные параметры безопасности для устройств Surface Pro 3.</span><span class="sxs-lookup"><span data-stu-id="274fb-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="274fb-106">Для более точной настройки безопасности устройств Surface обновление UEFI v3.11.760.0 предоставляет дополнительные параметры безопасности, которые позволяют вам отключать определенные аппаратные устройства и предотвращать запуск с этих устройств.</span><span class="sxs-lookup"><span data-stu-id="274fb-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="274fb-107">После установки обновления UEFI на устройство его можно настроить вручную или автоматически, запустив сценарий.</span><span class="sxs-lookup"><span data-stu-id="274fb-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="274fb-108">Установка обновления UEFI вручную</span><span class="sxs-lookup"><span data-stu-id="274fb-108">Manually install the UEFI update</span></span>


<span data-ttu-id="274fb-109">Прежде чем можно будет настроить расширенные функции безопасности вашего устройства Surface, сначала необходимо установить обновление UEFI v3.11.760.0.</span><span class="sxs-lookup"><span data-stu-id="274fb-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="274fb-110">Это обновление устанавливается автоматически, если вы получаете обновления из Центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="274fb-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="274fb-111">Дополнительные сведения о том, как настроить Windows для автоматического обновления с помощью Центра обновления Windows, приведены в статье [Настройка и использование средства "Автоматическое обновление" в Windows](https://support.microsoft.com/kb/306525).</span><span class="sxs-lookup"><span data-stu-id="274fb-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="274fb-112">Обновления для UEFI на устройстве Surface Pro 3 входят в состав соответствующего пакета встроенного ПО и драйверов. Его можно скачать</span><span class="sxs-lookup"><span data-stu-id="274fb-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="274fb-113">на [странице Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) в Центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="274fb-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="274fb-114">Дополнительные сведения о пакетах встроенного ПО и драйверов см. в статье [Скачивание последних версий встроенного ПО и драйверов для устройств Surface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="274fb-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="274fb-115">Пакеты встроенного ПО и драйверов доступны как в автономном формате установщика Windows (MSI), так и в формате архива (ZIP).</span><span class="sxs-lookup"><span data-stu-id="274fb-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="274fb-116">Дополнительные сведения об этих форматах и обновлении драйверов с их помощью см. в статье [Управление обновлениями драйверов и встроенного ПО Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="274fb-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="274fb-117">Настройка дополнительных параметров безопасности вручную</span><span class="sxs-lookup"><span data-stu-id="274fb-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="274fb-118">Для входа в раздел настройки встроенного ПО на устройстве Surface выключите свое устройство, затем нажмите и удерживайте кнопку **увеличения громкости**, затем нажмите и отпустите **кнопку питания**, далее отпустите кнопку **увеличения громкости** после того, как начнется процесс запуска устройства.</span><span class="sxs-lookup"><span data-stu-id="274fb-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="274fb-119">После установки обновления v3.11.760.0 UEFI на устройстве Surface появится дополнительный элемент меню UEFI под названием **Расширенная безопасность устройства**.</span><span class="sxs-lookup"><span data-stu-id="274fb-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="274fb-120">При выборе этого меню отображаются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="274fb-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="274fb-121">Параметр</span><span class="sxs-lookup"><span data-stu-id="274fb-121">Option</span></span>         | <span data-ttu-id="274fb-122">Описание</span><span class="sxs-lookup"><span data-stu-id="274fb-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="274fb-123">Доступные настройки (те, которые по умолчанию, выделены полужирным шрифтом)</span><span class="sxs-lookup"><span data-stu-id="274fb-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="274fb-124">Сетевая загрузка</span><span class="sxs-lookup"><span data-stu-id="274fb-124">Network Boot</span></span>   | <span data-ttu-id="274fb-125">Включает или отключает возможности устройства Surface по загрузке из сети (также известной как загрузка PXE).</span><span class="sxs-lookup"><span data-stu-id="274fb-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="274fb-126">**Включен**, "Не загрузочный"</span><span class="sxs-lookup"><span data-stu-id="274fb-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="274fb-127">Боковой USB</span><span class="sxs-lookup"><span data-stu-id="274fb-127">Side USB</span></span>       | <span data-ttu-id="274fb-128">Включает или отключает USB-порт на боку устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="274fb-129">Кроме того порт USB можно включить, но запретить загрузку.</span><span class="sxs-lookup"><span data-stu-id="274fb-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="274fb-130">**Включен**, "Не загрузочный", "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="274fb-131">Порт стыковки</span><span class="sxs-lookup"><span data-stu-id="274fb-131">Docking Port</span></span>   | <span data-ttu-id="274fb-132">Включает и отключает порты на док-станции Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="274fb-133">Кроме того порт стыковки можно включить, заблокировав при этом возможность загрузки с любого порта USB или Ethernet на док-станции.</span><span class="sxs-lookup"><span data-stu-id="274fb-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="274fb-134">**Включен**, "Не загрузочный", "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="274fb-135">Передняя камера</span><span class="sxs-lookup"><span data-stu-id="274fb-135">Front Camera</span></span>   | <span data-ttu-id="274fb-136">Включает и отключает камеру на лицевой стороне устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="274fb-137">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="274fb-138">Задняя камера</span><span class="sxs-lookup"><span data-stu-id="274fb-138">Rear Camera</span></span>    | <span data-ttu-id="274fb-139">Включает и отключает камеру на тыльной стороне устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="274fb-140">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="274fb-141">Встроенное аудио</span><span class="sxs-lookup"><span data-stu-id="274fb-141">On Board Audio</span></span> | <span data-ttu-id="274fb-142">Включает и отключает звук на устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="274fb-143">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="274fb-144">microSD</span><span class="sxs-lookup"><span data-stu-id="274fb-144">microSD</span></span>        | <span data-ttu-id="274fb-145">Включает и отключает разъем microSD на устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="274fb-146">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="274fb-147">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="274fb-147">WiFi</span></span>           | <span data-ttu-id="274fb-148">Включает и отключает встроенный передатчик Wi-Fi устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="274fb-149">Это также отключает функцию Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="274fb-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="274fb-150">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="274fb-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="274fb-151">Bluetooth</span></span>      | <span data-ttu-id="274fb-152">Включает и отключает встроенный передатчик Bluetooth устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="274fb-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="274fb-153">**Включен**, "Отключен"</span><span class="sxs-lookup"><span data-stu-id="274fb-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="274fb-154">Автоматическая настройка дополнительных параметров безопасности</span><span class="sxs-lookup"><span data-stu-id="274fb-154">Automate additional security settings</span></span>


<span data-ttu-id="274fb-155">ИТ-специалист с правами администратора может автоматизировать настройку параметров UEFI, используя [инструменты для встроенного ПО Surface Pro 3 (476 КБ)](https://go.microsoft.com/fwlink/p/?LinkID=618038), доступные в Центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="274fb-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="274fb-156">Эти средства устанавливают сборку .NET, которую можно вызывать из любого пользовательского приложения или сценария.</span><span class="sxs-lookup"><span data-stu-id="274fb-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="274fb-157">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="274fb-157">Prerequisites</span></span>**

-   <span data-ttu-id="274fb-158">Приведенные ниже образцы сценариев используют ранее упомянутое расширение и, соответственно, здесь предполагается, что эти средства уже установлены на рассматриваемом устройстве.</span><span class="sxs-lookup"><span data-stu-id="274fb-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="274fb-159">Сценарии необходимо запускать с полномочиями администратора.</span><span class="sxs-lookup"><span data-stu-id="274fb-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="274fb-160">Если образцы сценариев не имеют цифровой подписи, перед их выполнением необходимо запустить команду Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx).</span><span class="sxs-lookup"><span data-stu-id="274fb-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="274fb-161">Образцы сценариев</span><span class="sxs-lookup"><span data-stu-id="274fb-161">Sample scripts</span></span>**

> [!NOTE]
> <span data-ttu-id="274fb-162">Пароль UEFI, используемый в образцах сценариев ниже, приведен в открытом тексте.</span><span class="sxs-lookup"><span data-stu-id="274fb-162">The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="274fb-163">Настоятельно рекомендуется сохранить сценарии в защищенном расположении и выполнять их в контролируемом окружении.</span><span class="sxs-lookup"><span data-stu-id="274fb-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="274fb-164">Показать все настраиваемые параметры:</span><span class="sxs-lookup"><span data-stu-id="274fb-164">Show all configurable options:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

<span data-ttu-id="274fb-165">Установить или изменить пароль UEFI:</span><span class="sxs-lookup"><span data-stu-id="274fb-165">Set or change UEFI password:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="274fb-166">Проверить состояние предлагаемых изменений:</span><span class="sxs-lookup"><span data-stu-id="274fb-166">Check status of proposed changes:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

<span data-ttu-id="274fb-167">Вернуть значения по умолчанию для UEFI:</span><span class="sxs-lookup"><span data-stu-id="274fb-167">Revert UEFI to default values:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

<span data-ttu-id="274fb-168">Интерпретация кода состояния</span><span class="sxs-lookup"><span data-stu-id="274fb-168">Status code interpretation</span></span>

-   <span data-ttu-id="274fb-169">00 — Предлагаемое обновление прошло успешно</span><span class="sxs-lookup"><span data-stu-id="274fb-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="274fb-170">02 — Одно из предлагаемых значений имело недопустимое значение</span><span class="sxs-lookup"><span data-stu-id="274fb-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="274fb-171">03 — Установлено предлагаемое значение, которое не распознано.</span><span class="sxs-lookup"><span data-stu-id="274fb-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="274fb-172">0F — Пароль снятия блокировки не соответствует заданному сейчас паролю</span><span class="sxs-lookup"><span data-stu-id="274fb-172">0F - The unlock password did not match currently set password</span></span>

 
