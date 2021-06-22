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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613807"
---
# <a name="wake-on-lan-for-surface-devices"></a>Пробуждение по локальной сети для устройств Surface

Чтобы поддерживать устройства в полной мере в курсе, ИТ-администраторы должны иметь возможность управлять устройствами, когда они не используются, как правило, во время ночных окон обслуживания. Wake on LAN (WOL) позволяет администраторам удаленно разбудить устройства и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или сторонних решений.

## <a name="requirements"></a>Требования

Устройства должны быть подключены к власти переменного тока и иметь проводное подключение к одному из следующих совместимых адаптеров Ethernet:

- Адаптер Ethernet Surface USB 3.0 Gigabit
- Адаптер Surface Ethernet
- Surface USB-C для Ethernet и USB-адаптер
- Концентратор адаптеров для путешествий Microsoft USB-C
- Док-станция Surface.
- Surface Dock 2

> [!NOTE]
> Surface Dock 2 обеспечивает лучшую поддержку wake на локальной сети без необходимости дополнительной ИТ-конфигурации. Дополнительные дополнительные информации см. в [сайте Wake on LAN for Surface Dock 2.](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>Принцип работы

Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby. ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface. Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние Microsoft Store, предоставляют встроенную поддержку WOL. Дополнительные информацию о бодрствования устройствах с помощью диспетчера конфигурации конечной точки см. в этой ссылке [Configure Wake on LAN - Configuration Manager.](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

Поддержка wake на локальной сети зависит от состояния сна: подключенного ожидания или hibernation (состояние питания S4).

## <a name="connected-standby"></a>Подключенный режим ожидания

По умолчанию Windows 10 поддерживает wake на lan-устройствах Surface в подключенной режиме ожидания.

### <a name="supported-surface-devices---connected-standby"></a>Поддерживаемые устройства Surface — подключенное в режиме ожидания

- Surface Laptop 4 (только процессоры Intel)
- Surface Laptop 3 (только процессоры Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Go
- Surface Book 3

## <a name="hibernation"></a>Спячка

Чтобы разбудить устройства из режима Hibernation, необходимо включить параметр политики UEFI с помощью режима управления [surface Enterprise](surface-enterprise-management-mode.md) (SEMM) (не требуется для устройств, подключенных к Surface Dock 2).

### <a name="supported-surface-devices---hibernation"></a>Поддерживаемые устройства Surface - Hibernation

- Surface Laptop 4 (только процессоры Intel)
- Surface Laptop 3 (только процессоры Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop Go
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>Включить параметр Wake на локальной сети UEFI

Чтобы включить параметр Wake on LAN UEFI, необходимо записать целевые устройства в SEMM, создать пакет конфигурации и применить пакет к устройствам. Дополнительные сведения см. в разделе:

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Регистрация устройств Surface в SEMM и их настройка](enroll-and-configure-surface-devices-with-semm.md)

1. Загрузка и установка [**конфигуратора Surface UEFI.**](https://www.microsoft.com/download/details.aspx?id=46703)
2. Выберите **пакет**  >  **начните**  >  **настройку Create**+ Certificate  > **Protection**.
3. Перейдите **к расширенным настройкам** и включив **wake on lan-сайт** **в On**.
4. Примени пакет к целевым устройствам.

    > [!div class="mx-imgBorder"]
    > ![Включить wake на параметре политики LAN UEFI](images/wol-uefi.png)

## <a name="learn-more"></a>Подробнее

- [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C для Ethernet и USB-адаптер](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Адаптер Ethernet Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
