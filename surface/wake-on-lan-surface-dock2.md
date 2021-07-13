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
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643855"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>Пробуждение по локальной сети с использованием Surface Dock 2

Чтобы поддерживать устройства в полной мере в курсе, ИТ-администраторы должны иметь возможность управлять устройствами, когда они не используются, как правило, во время ночных окон обслуживания. Surface Dock 2 обеспечивает лучшую поддержку wake on LAN (WOL), позволяя администраторам удаленно разбудить устройства и автоматически выполнять задачи управления с помощью Microsoft Endpoint Manager или других сторонних решений.

## <a name="requirements"></a>Требования

Устройства должны иметь проводное подключение к Surface Dock 2 и оставаться подключенными к ac Power.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a>Поддерживаемые устройства Surface

- Surface Laptop 4 (процессоры Intel)
- Surface Laptop 4 (процессоры AMD)
- Surface Laptop 3 (процессоры Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Go
- Surface Book 3

Surface Dock 2 обеспечивает поддержку WOL для устройств в следующих состояниях мощности:

- Режим ожидания с подключением
- Hibernation (состояние питания S4)
- Отключение (состояние питания S5 "soft off")

Дополнительные дополнительные информацию о состояниях власти [см.](/windows/win32/power/system-power-states)в этой информации.

## <a name="how-it-works"></a>Принцип работы

Если устройства Surface не используются, они введите состояние с низким питанием, известное как Modern Standby или Connected Standby. ИТ-администраторы могут удаленно запускать устройства с помощью запроса на пробуждение (волшебный пакет), который содержит адрес управления доступом к мультимедиа (MAC) целевого устройства Surface. Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние Microsoft Store, предоставляют встроенную поддержку WOL.

Чтобы включить WOL на устройствах без Surface Dock 2, см. в рубке [Wake on LAN для устройств Surface.](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>Подробнее

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Пробуждение по локальной сети для устройств Surface](wake-on-lan-for-surface-devices.md)
- [Состояния power system](/windows/win32/power/system-power-states)
- [Настройка wake на локальной сети — диспетчер конфигурации](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
