---
title: Wake On LAN для устройств Surface (Surface)
description: Узнайте, как использовать Локальное устройство Wake On, чтобы удаленно разбудить устройства для выполнения задач управления или обслуживания, или включить решения управления автоматически, даже если устройства отключены.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
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
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271126"
---
# Пробуждение по локальной сети для устройств Surface

Устройства Surface под названием Windows 10 версии 1607 (также известные как юбилейное обновление Windows 10) или более поздней версии и используют адаптер Surface Ethernet для подключения к проводной сети, могут подключаться по локальной сети (WOL) из режимов ожидания с подключением. С помощью WOL вы можете удаленно разбудить устройства для выполнения задач управления или обслуживания или включить решения управления (например, Microsoft Endpoint Configuration Manager) автоматически. Например, вы можете развернуть приложения на устройствах Surface, остающихся закрепленными на док-станции Surface или док-станции Surface Pro 3, с помощью Microsoft Endpoint Configuration Manager в середине дня, когда офис пуст.

>[!NOTE]
>Устройства Surface должны быть подключены к сети переменного тока и в режиме ожидания с подключением (спящий режим) для поддержки WOL. WOL невозможен на устройствах, которые находятся в режиме гибернации или отключены.

## Поддерживаемые устройства

Для WOL поддерживаются следующие устройства:

* Адаптер Ethernet для Surface
* От Surface USB-C к Ethernet и USB-адаптеру
* Док-станция Surface.
* Док-станция Surface для Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5-е поколения)
* Surface Pro (5-е поколения) с LTE Advanced
* Surface Book
* Surface Laptop (1-е поколения)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go с функцией LTE Advanced
* Surface Studio 2 (см. инструкции по Surface Studio 2 ниже)
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop Go
* Surface Pro 7 и более

## Драйвер WOL

Чтобы включить поддержку WOL на устройствах Surface, требуется определенный драйвер для адаптера Ethernet Surface. Этот драйвер не включен в стандартный пакет драйверов и микропрограмм для устройств Surface. Его необходимо скачать и установить отдельно. Вы можете скачать драйвер Surface WOL (SurfaceWOL.msi) со страницы ["Инструменты Surface для ИТ-технологий"](https://www.microsoft.com/download/details.aspx?id=46703) в Центре загрузки Майкрософт.

Вы можете запустить этот установщик Microsoft Windows (MSI) на устройстве Surface для установки драйвера Surface WOL или распространить его на устройства Surface с помощью решения развертывания приложений, например Microsoft Endpoint Configuration Manager. Чтобы включить драйвер Surface WOL во время развертывания, можно установить MSI-файл как приложение во время процесса развертывания. Вы также можете извлечь файлы драйверов Surface WOL, чтобы включить их в процесс развертывания. Например, их можно включить в обную набор средств microsoft Deployment набор средств (MDT). Вы можете узнать больше о развертывании Surface с помощью MDT в развертывании [Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)на устройствах Surface с помощью Microsoft Deployment набор средств.

> [!NOTE]
> Во время установки SurfaceWOL.msi для следующего реестра устанавливается значение 1, что позволяет легко определить системы, в которых установлен драйвер WOL. Если вы решили извлечь и установить эти драйверы отдельно во время развертывания, этот раздел реестра не будет настроен и должен быть настроен вручную или с помощью скрипта.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Чтобы извлечь содержимое SurfaceWOL.msi, используйте параметр административной установки MSIExec (**/a),** как показано в следующем примере, чтобы извлечь содержимое в папку C:\WOL\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Инструкции по Surface Studio 2

Чтобы включить WOL на Surface Studio 2, необходимо использовать следующую процедуру.

1. Создайте следующие ключи реестра:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Запустите следующую команду:

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Использование Surface WOL

Драйвер Surface WOL соответствует стандарту WOL, в результате чего устройство находится в безопасности благодаря специальной сетевой связи, известной как пакет "чудо-пакет". Пакет содержит 6 bytes of 255 (or FF in hexadecimal), за которым следует 16 повторений MAC-адреса конечного компьютера. Вы можете узнать больше о пакете и [](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)стандарте WOL в Википедии.

>[!NOTE]
>Чтобы отправить пакет с помощью WOL, необходимо знать MAC-адрес целевого устройства и адаптер Ethernet. Поскольку пакет не использует протокол IP-сети, невозможно использовать IP-адрес или DNS-имя устройства.

Многие решения управления, такие как Configuration Manager, обеспечивают встроенную поддержку WOL. Кроме того, существует множество решений, включая приложения Microsoft Store, модули PowerShell, сторонние приложения и сторонние решения для управления, позволяющие отправить пакет для запуска устройства. Например, можно использовать модуль [PowerShell Wake On LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) из центра скриптов TechNet. 

>[!NOTE]
>После того как устройство было перезахвачено с помощью пакетов , устройство вернется в спящий режим, если приложение не активно предотвращает спящий режим в системе или если для ключа реестра AllowSystemRequiredPowerRequests не настроено значение 1, что позволяет приложениям предотвратить спящий режим. Дополнительные сведения об этом разделе реестра см. в разделе драйверов [WOL](#wol-driver) этой статьи.
