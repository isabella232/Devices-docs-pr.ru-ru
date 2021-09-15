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
ms.openlocfilehash: 66992ad10f157518edca2d738e55ec1108b06c4b
ms.sourcegitcommit: a5651e8c8f953fe3130dd476f4e06c16c172aaa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2021
ms.locfileid: "11939506"
---
# <a name="advanced-uefi-security-features-for-surface-pro-3"></a>Расширенные функции безопасности UEFI для Surface Pro 3


В этой статье описано, как установить и настроить обновление UEFI версии 3.11.760.0, чтобы включить дополнительные параметры безопасности для устройств Surface Pro 3.

Для более точной настройки безопасности устройств Surface обновление UEFI v3.11.760.0 предоставляет дополнительные параметры безопасности, которые позволяют вам отключать определенные аппаратные устройства и предотвращать запуск с этих устройств. После установки обновления UEFI на устройство его можно настроить вручную или автоматически, запустив сценарий.

## <a name="manually-install-the-uefi-update"></a>Установка обновления UEFI вручную


Прежде чем можно будет настроить расширенные функции безопасности вашего устройства Surface, сначала необходимо установить обновление UEFI v3.11.760.0. Это обновление устанавливается автоматически, если вы получаете обновления из Центра обновления Windows. Дополнительные сведения о том, как настроить Windows для автоматического обновления с помощью Центра обновления Windows, приведены в статье [Настройка и использование средства "Автоматическое обновление" в Windows](https://support.microsoft.com/kb/306525).

Обновления для UEFI на устройстве Surface Pro 3 входят в состав соответствующего пакета встроенного ПО и драйверов. Его можно скачать на [странице Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) в Центре загрузки Майкрософт. Дополнительные информацию о пакетах прошивки и драйверов вы можете узнать в скачать драйверы и прошивку [для Surface.](https://support.microsoft.com/help/4023482) Пакеты встроенного ПО и драйверов доступны как в автономном формате установщика Windows (MSI), так и в формате архива (ZIP). Вы можете узнать больше об этих двух форматах и о том, как их можно использовать для обновления драйверов в управлении и развертывании обновлений [драйверов и прошивки Surface.](manage-surface-driver-and-firmware-updates.md)

## <a name="manually-configure-additional-security-settings"></a>Настройка дополнительных параметров безопасности вручную


>[!NOTE]
>Для входа в раздел настройки встроенного ПО на устройстве Surface выключите свое устройство, затем нажмите и удерживайте кнопку **увеличения громкости**, затем нажмите и отпустите **кнопку питания**, далее отпустите кнопку **увеличения громкости** после того, как начнется процесс запуска устройства.

После установки обновления v3.11.760.0 UEFI на устройстве Surface появится дополнительный элемент меню UEFI под названием **Расширенная безопасность устройства**. При выборе этого меню отображаются следующие параметры.

| Параметр         | Описание                                                                                                                                                                          | Доступные настройки (те, которые по умолчанию, выделены полужирным шрифтом) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| Сетевая загрузка   | Включает или отключает возможности устройства Surface по загрузке из сети (также известной как загрузка PXE).                                                                            | **Включен**, "Не загрузочный"                   |
| Боковой USB       | Включает или отключает USB-порт на боку устройства Surface. Кроме того порт USB можно включить, но запретить загрузку.                                                | **Включен**, "Не загрузочный", "Отключен"         |
| Порт стыковки   | Включает и отключает порты на док-станции Surface. Кроме того порт стыковки можно включить, заблокировав при этом возможность загрузки с любого порта USB или Ethernet на док-станции. | **Включен**, "Не загрузочный", "Отключен"         |
| Передняя камера   | Включает и отключает камеру на лицевой стороне устройства Surface.                                                                                                                   | **Включен**, "Отключен"                       |
| Задняя камера    | Включает и отключает камеру на тыльной стороне устройства Surface.                                                                                                                    | **Включен**, "Отключен"                       |
| Встроенное аудио | Включает и отключает звук на устройстве Surface.                                                                                                                                     | **Включен**, "Отключен"                       |
| microSD        | Включает и отключает разъем microSD на устройстве Surface.                                                                                                                          | **Включен**, "Отключен"                       |
| Wi-Fi           | Включает и отключает встроенный передатчик Wi-Fi устройства Surface. Это также отключает функцию Bluetooth.                                                                              | **Включен**, "Отключен"                       |
| Bluetooth      | Включает и отключает встроенный передатчик Bluetooth устройства Surface.                                                                                                        | **Включен**, "Отключен"                       |

 

## <a name="automate-additional-security-settings"></a>Автоматическая настройка дополнительных параметров безопасности


ИТ-специалист с правами администратора может автоматизировать настройку параметров UEFI, используя [инструменты для встроенного ПО Surface Pro 3 (476 КБ)](https://go.microsoft.com/fwlink/p/?LinkID=618038), доступные в Центре загрузки Майкрософт. Эти средства устанавливают сборку .NET, которую можно вызывать из любого пользовательского приложения или сценария.

**Необходимые условия**

-   Приведенные ниже образцы сценариев используют ранее упомянутое расширение и, соответственно, здесь предполагается, что эти средства уже установлены на рассматриваемом устройстве.
-   Сценарии необходимо запускать с полномочиями администратора.
-   Если образцы сценариев не имеют цифровой подписи, перед их выполнением необходимо запустить команду Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx).

**Образцы сценариев**

> [!NOTE]
> Пароль UEFI, используемый в образцах сценариев ниже, приведен в открытом тексте. Настоятельно рекомендуется сохранить сценарии в защищенном расположении и выполнять их в контролируемом окружении.


Показать все настраиваемые параметры:

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

Установить или изменить пароль UEFI:

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

Проверить состояние предлагаемых изменений:

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

Вернуть значения по умолчанию для UEFI:

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

Интерпретация кода состояния

-   00 — Предлагаемое обновление прошло успешно
-   02 — Одно из предлагаемых значений имело недопустимое значение
-   03 — Установлено предлагаемое значение, которое не распознано.
-   0F — Пароль снятия блокировки не соответствует заданному сейчас паролю

 
