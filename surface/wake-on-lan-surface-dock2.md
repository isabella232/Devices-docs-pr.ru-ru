---
title: Пробуждение по локальной сети с использованием Surface Dock 2
description: Surface Dock 2 обеспечивает лучшую поддержку wake on LAN (WOL), позволяя администраторам удаленно разбудить устройства и автоматически выполнять задачи управления.
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
ms.openlocfilehash: 09982dff2e44ffc2ebe9b890588e5a62a3259cf5
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338492"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>Пробуждение по локальной сети с использованием Surface Dock 2

Чтобы поддерживать устройства в полной мере в курсе, ИТ-администраторы должны иметь возможность управлять устройствами, когда они не используются, как правило, во время ночных окон обслуживания. Surface Dock 2 обеспечивает лучшую поддержку wake on LAN (WOL), позволяя администраторам удаленно разбудить устройства Surface и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или других сторонних решений.

## <a name="requirements"></a>Требования

Устройства должны иметь проводное подключение к Surface Dock 2 и оставаться подключенными к ac Power.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2.](images/surface-dock2-angled.png)

> [!NOTE]
> Устройства для пробуждения, подключенные к Surface Dock 2, не требуют использования режима управления Enterprise Surface (SEMM) или включения параметров политики UEFI.
 
## <a name="supported-surface-devices"></a>Поддерживаемые устройства Surface

- Surface Laptop 4 (процессоры Intel)
- Surface Laptop 4 (процессоры AMD)
- Surface Laptop 3 (процессоры Intel)
- Surface Pro 8
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go (все поколения)
- Surface Laptop Go
- Surface Book 3
- Surface Laptop Studio

Surface Dock 2 обеспечивает поддержку WOL для устройств в следующих состояниях мощности:

- Режим ожидания с подключением
- Hibernation (состояние питания S4)
- Отключение (состояние питания S5 "soft off")

Дополнительные дополнительные информацию о состояниях власти см. в [дополнительных подробной информации о состояниях power system](/windows/win32/power/system-power-states).

## <a name="how-it-works"></a>Принцип работы

Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby. Устройства могут быть в состоянии питания в режиме спячки (S4) или отключении (S5) в зависимости от параметров питания, настроенных на устройстве. ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface. Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние Microsoft Store, предоставляют встроенную поддержку WOL.

Чтобы включить WOL на устройствах без Surface Dock 2, см.:

- [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>Подробнее

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Пробуждение по локальной сети для устройств Surface](wake-on-lan-for-surface-devices.md)
- [Состояния power system](/windows/win32/power/system-power-states)

