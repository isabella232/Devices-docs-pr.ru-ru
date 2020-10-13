---
title: Пробуждение по локальной сети для устройств Surface (Surface)
description: Узнайте, как использовать функцию Wake on LAN для удаленного пробуждения устройств для выполнения задач управления или обслуживания, а также для автоматического включения решений для управления, даже если питание устройств отключено.
keywords: обновление, развертывание, драйвер, WOL, пробуждение по сети
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114617"
---
# Пробуждение по локальной сети для устройств Surface

Устройства Surface, которые работают под управлением Windows 10, версия 1607 (также известная как Windows 10 годовщина) или более поздней версии, и используют адаптер Surface Ethernet для подключения к проводной сети, поддерживающие пробуждение через ЛОКАЛЬную сеть (WOL) в режиме ожидания с подключением. С помощью WOL вы можете удаленно вывести устройства из спящего режима для выполнения задач управления или обслуживания или включения решений для управления (например, Диспетчер конфигураций конечных точек Майкрософт) автоматически. Например, вы можете развернуть приложения на устройствах Surface, которые были закреплены с помощью стыковочного узла Surface или Surface Pro 3, используя Диспетчер конфигурации конечных точек (Microsoft Endpoint Configuration Manager) во время пустого офиса.

>[!NOTE]
>Для поддержки WOL устройства Surface должны быть подключены к сети переменного тока и в режиме ожидания с подключением. WOL невозможно с устройств, которые находятся в спящем режиме или выключены.

## Поддерживаемые устройства

Для WOL поддерживаются следующие устройства:

* Ethernet-адаптер Surface
* USB-адаптер Surface и USB
* Док-станция Surface.
* Стыковочный узел Surface для Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5-го поколения)
* Surface Pro (5-го поколения) с дополнительным LTE
* Surface Book
* Surface ноутбук (1-го поколения)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go с функцией LTE Advanced
* Surface Studio 2 (Дополнительные сведения о Surface Studio 2)
* Surface Pro 7
* Surface ноутбук 3
* Ноутбук Surface Go

## Драйвер WOL

Для включения поддержки WOL на Surface Devices требуется определенный драйвер для адаптера Ethernet Surface. Этот драйвер не входит в стандартный драйвер и пакет встроенного по для устройств Surface — вы должны скачать и установить его отдельно. Драйвер WOL для Surface (SurfaceWOL.msi) можно загрузить на странице [Surface Tools для IT](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки Майкрософт.

Вы можете запустить этот файл установщика Microsoft Windows (MSI) на устройстве Surface, чтобы установить драйвер WOL для Surface, или распространить его на Surface Devices с помощью решения для развертывания приложения, например диспетчера конфигураций конечных точек Microsoft. Чтобы включить драйвер WOL при развертывании, можно установить MSI-файл как приложение в процессе развертывания. Вы также можете извлечь файлы драйвера WOL для Surface, чтобы включить их в процесс развертывания. Например, вы можете включить их в общий доступ к развертыванию Microsoft Deployment Toolkit (MDT). Дополнительные сведения о развертывании Surface с помощью MDT [для развертывания Windows 10 на Surface Devices можно получить с помощью Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).

> [!NOTE]
> Во время установки SurfaceWOL.msi для следующего раздела реестра задано значение 1, что позволяет легко идентифицировать системы, в которых установлен драйвер WOL. Если вы решили извлечь и установить эти драйверы отдельно во время развертывания, этот раздел реестра не будет настроен, и его необходимо будет настроить вручную или с помощью сценария.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Чтобы извлечь содержимое SurfaceWOL.msi, используйте параметр административной установки MSIExec (**/a**), как показано в приведенном ниже примере, чтобы извлечь содержимое в папку C:\WOL\.

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Инструкции для Surface Studio 2

Чтобы включить WOL в Surface Studio 2, необходимо выполнить описанные ниже действия.

1. Создайте следующие разделы реестра:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Выполните следующую команду:

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Использование зоны WOL

Драйвер WOL в Surface соответствует стандарту WOL, так как устройство Woken специальной связью по сети, известной как пакет Magic. Пакет Magic состоит из шести байт 255 (или FF в шестнадцатеричном формате), за которым следует 16 повторений MAC-адреса целевого компьютера. Вы можете ознакомиться с дополнительными сведениями о пакете Magic и стандарт WOL на [Википедии](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Для отправки Magic Packet и пробуждения устройства с помощью WOL необходимо знать MAC-адрес оконечного устройства и адаптера Ethernet. Так как пакет Magic не использует протокол IP-сети, невозможно использовать IP-адрес или DNS-имя устройства.

Многие решения для управления, например Configuration Manager, предоставляют встроенную поддержку WOL. Кроме того, существует множество решений, в том числе приложений Microsoft Store, модулей PowerShell, приложений сторонних разработчиков и сторонних решений для управления, которые позволяют отправлять волшебные пакеты для пробуждения устройства. Например, можно использовать [модуль PowerShell Wake on LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) в центре сценариев TechNet. 

>[!NOTE]
>После того как устройство будет Woken с помощью Magic Packet, оно вернется в спящий режим, если приложение не препятствует переходу в спящий режим, или если раздел реестра AllowSystemRequiredPowerRequests не настроен на 1, что позволяет приложениям предотвращать переход в спящий режим. Дополнительные сведения об этом разделе реестра можно найти в разделе [драйвер WOL](#wol-driver) этой статьи.
