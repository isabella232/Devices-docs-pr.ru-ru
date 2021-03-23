---
title: Пробуждение по локальной сети для устройств Surface
description: Узнайте, как можно использовать wake On LAN для удаленного пробуждения устройств для автоматического выполнения задач управления.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 9c3302616de97cf60b7d750948fed653456a7cba
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442893"
---
# <a name="wake-on-lan-for-surface-devices"></a>Пробуждение по локальной сети для устройств Surface

Устройства Surface, которые используют адаптер Surface Ethernet для подключения к проводной сети, могут использовать wake On LAN (WOL) из подключенного ожидания. С помощью WOL можно удаленно разбудить устройства и автоматически выполнять задачи управления с помощью решений управления, таких как Microsoft Endpoint Manager/Microsoft Intune.

## <a name="wol-supported-devices"></a>Устройства, поддерживаемые WOL

- Адаптер Surface Ethernet
- Surface USB-C для Ethernet и USB-адаптер
- Surface Dock 2
- Surface Pro 6 и более поздние
- Surface Book (все поколения)
- Surface Laptop (все поколения)
- Surface Go (все поколения)
- Surface Studio 2 (см. приложение)


## <a name="using-surface-wol"></a>Использование WOL Surface

ИТ-администраторы могут запускать устройства с помощью запроса на локальной сети (волшебный пакет), который содержит MAC-адрес компьютера целевого компьютера. Чтобы отправить волшебный пакет и разбудить устройство с помощью WOL, необходимо знать MAC-адрес целевого устройства и адаптер Ethernet. Так как волшебный пакет не использует протокол IP-сети, невозможно использовать IP-адрес или имя DNS устройства.

Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние приложения Microsoft Store, предоставляют встроенную поддержку WOL. Обратите внимание, что устройства должны быть в режиме подключенного режима ожидания (sleep) и подключаться к власти переменного тока. Дополнительные информацию о бодрствования устройствах с помощью диспетчера конфигурации конечной точки см. в этой ссылке [Configure Wake on LAN - Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)


### <a name="to-check-wol-is-enabled-on-your-device"></a>Проверка включения WOL на устройстве

1. На подключенной к Ethernet устройстве выберите сетевой адаптер и выберите **свойства.**

   > [!div class="mx-imgBorder"]
   > ![Адаптер Surface Ethernet](images/surface-ethernet.png)

2. Выберите **Configure**  >  **Advanced**.
3. Прокрутите **в современный автономный пакет WoL Magic Packet** и убедитесь, что **включен.**

     ![Проверка включения WOL на устройстве](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>Приложение: Surface Studio 2

Чтобы включить WOL на Surface Studio 2, используйте следующую процедуру.

1. Создайте следующие клавиши реестра:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Выполнить следующую команду

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>Подробнее

- [Microsoft Surface USB-C для Ethernet и USB-адаптер](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Адаптер Ethernet Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
