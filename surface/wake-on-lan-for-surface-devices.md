---
title: Пробуждение по локальной сети для устройств Surface
description: Устройства Surface, которые работают Windows 10 версии 1607 или более поздней версии и используют адаптер Surface Ethernet для подключения к проводной сети, способны будиться на локальной сети (WOL) из modern Standby.
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
ms.date: 11/30/2021
ms.openlocfilehash: eed1cbedea2a39207846301fa6b4f6c2b2f6dd56
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337912"
---
# <a name="wake-on-lan-for-surface-devices"></a>Пробуждение по локальной сети для устройств Surface 

Устройства Surface, Windows 10 версии 1607 или более поздней версии, способны выполнять wake On LAN (WOL) из современного standby (также известного как Подключенное standby). С помощью WOL ИТ-администраторы могут удаленно разбудить устройства и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или сторонних решений.

>[!NOTE]
>Чтобы поддерживать WOL, устройства Surface должны подключаться к власти переменного тока и использовать адаптер Surface Ethernet, подключенный к проводной сети.

## <a name="supported-devices"></a>Поддерживаемые устройства

Адаптеры Ethernet с поддержкой WOL:

- Адаптер Ethernet Surface USB 3.0 Gigabit 
- Адаптер Surface Ethernet
- Surface USB-C для Ethernet и USB-адаптер
- Surface Dock
- Surface Dock 2
- Станция док-станции surface для Surface Pro 3

Устройства Surface с поддержкой WOL:

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (5-й gen)
- Surface Pro (5th Gen) с LTE Advanced
- Surface Book (все поколения)
- Surface Laptop (все поколения)
- Surface Pro 6
- Surface Book 2
- Surface Go (все поколения)
- Surface Studio 2 (см. Surface Studio 2 инструкции ниже)
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Laptop Go
- Surface Laptop Studio


## <a name="using-wol"></a>Использование WOL 

Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby. ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface. Карта сетевого интерфейса назначения (NIC) сравнивает MAC-адрес с собственным перед пробуждением устройства. Если mac-адрес в запросе на пробуждение пакетов не совпадает с mac-адресом в пункте назначения NIC, NIC не разбудит устройство. Чтобы узнать больше, просмотрите [документацию источников wake](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>Современный режим ожидания

Современное режим ожидания начинается, когда пользователь заставляет систему входить во спящий режим или устройство переходит в спящий режим в зависимости от Windows параметров питания, установленных пользователем. Например, пользователь нажимает кнопку питания, закрывает крышку или выбирает Режим сна на кнопке питания в Windows меню . WOL работает по умолчанию для устройств Surface в современном режиме ожидания, Windows 10 версии 1607 или более поздней версии. Дополнительная конфигурация ИТ не требуется, за исключением Surface Studio 2.

## <a name="surface-studio-2-instructions"></a>Surface Studio 2 инструкции

Чтобы включить WOL Surface Studio 2, необходимо использовать следующую процедуру

1. Редактор open Registry (**StartSearch** > **** > **regedit.exe**) и создайте следующие клавиши реестра:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. Выполнить следующую команду

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> Если обновить версию Windows 10 на Surface Studio 2 (например, обновить с Windows 10 20H2 до 21H1), вам потребуется снова следовать этим инструкциям, чтобы включить WOL.


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>Для пробуждения от спячки (S4) или остановки (S5) 

- Для устройств, подключенных к Surface Dock 2, см. в руб. [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)
