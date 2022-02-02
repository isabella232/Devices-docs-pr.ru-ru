---
title: Параметр Ограничения батареи (Surface)
description: Ограничение заряда батареи — это параметр UEFI, который изменяет заряд батареи устройства Surface и может продлить его долговечность.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 9cf623a9a4b9d1a8d292cfa0cff25d2e57318db7
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338332"
---
# <a name="battery-limit-setting"></a>Параметр ограничения батареи

Параметр Battery Limit — это параметр UEFI, который изменяет заряд батареи устройства Surface и может продлить срок службы. Этот параметр рекомендуется использовать в тех случаях, когда устройство постоянно подключено к мощности, например при интеграции устройств в решения киосков.  

## <a name="how-battery-limit-works"></a>Как работает ограничение заряда батареи

Настройка устройства на пределе батареи изменяет протокол для зарядки батареи устройства. Когда включено ограничение заряда батареи, заряд батареи будет ограничен 50% от максимальной емкости. Уровень заряда, о чем Windows, будет отражать это ограничение. Таким образом, она показывает, что батарея заряжается до 50% и не будет заряжаться сверх этого предела. Если вы включаете ограничение заряда батареи, пока заряд устройства превышает 50%, значок Battery покажет, что устройство подключено, но разряжается до тех пор, пока устройство не достигнет 50% от максимальной емкости заряда.  

## <a name="supported-devices"></a>Поддерживаемые устройства

Параметр UEFI ограничения батареи встроен в устройства Surface по умолчанию, включая: 

- Surface Pro 7 и более поздней
- Surface Laptop 3 и более поздней
- Surface Book 3
- Surface Laptop Studio
- Surface Laptop Go
- Surface Studio 2
- Surface Laptop SE

 Более ранние устройства требуют обновления прошивки [Surface UEFI](manage-surface-driver-and-firmware-updates.md), доступной через Windows update или с помощью драйвера MSI и пакетов прошивки на сайте [surface Support](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). Проверьте [включить "Ограничение батареи" для устройств Surface](https://support.microsoft.com/help/4464941) , которые должны быть подключены в течение длительного времени для определенной версии Surface UEFI, необходимой для каждого поддерживаемого устройства.

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>Включение ограничения батареи в Surface UEFI (Surface Pro 4 и более поздней)

Параметр Surface UEFI Battery Limit можно настроить, загрузив в Surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **конфигурацию загрузки**, а затем, в **статье Расширенные параметры**, чтобы включить **режим ограничения батареи****.**  

![Параметры Ограничения заряда батареи.](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-all-generations"></a>Включение ограничения батареи на Surface Go (все поколения)

Параметр Surface Battery Limit можно настроить, загрузив в Surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **конфигурацию загрузки**, а затем в режиме **киоска** переместим ползунок вправо, чтобы установить ограничение батареи на **включено**.  

![Ограничение батареи в режиме киоска в Surface Go.](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>Включение ограничения батареи в Surface UEFI (Surface Pro 3)

Параметр Surface UEFI Battery Limit можно настроить, загрузив в Surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **режим киоска**, выберите **ограничение батареи** и выберите **включенную**.

![Снимок экрана расширенных параметров.](images/enable-bl-sp3.png)

![Расширенные параметры.](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>Включение ограничения батареи с помощью Enterprise режима управления surface (SEMM) или Surface Pro 3 скриптов powerShell прошивки

Ограничение батареи Surface UEFI также доступно для настройки с помощью следующих методов:

- Surface Pro 4 и более поздней
  - [Конфигуратор Microsoft Surface UEFI](surface-enterprise-management-mode.md)  
    - Сценарии Surface UEFI Manager Powershell (SEMM_Powershell.zip) в [Surface Tools для скачивания ИТ-услуг](https://www.microsoft.com/download/details.aspx?id=46703)

### <a name="using-microsoft-surface-uefi-configurator"></a>Использование конфигуратора Microsoft Surface UEFI

Чтобы настроить режим ограничения батареи, установите параметр **Переопределения** киоска на странице **advanced Параметры** конфигурации в SEMM (Surface Pro 4 и более поздней).

![Снимок экрана расширенных параметров.](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>Использование скриптов Surface UEFI Manager PowerShell

Элемент ограничения батареи управляется с помощью следующего параметра:  

`407 = Battery Profile`

**Описание**. Схема активного управления шаблоном использования батареи

**По умолчанию**:  `0`

Установите это, чтобы `1` включить ограничение батареи.
