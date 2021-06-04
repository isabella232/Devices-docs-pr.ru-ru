---
title: Параметр ограничения заряда батареи (Surface)
description: Ограничение заряда батареи — это параметр UEFI, который изменяет способ зарядки батареи устройства Surface и может продлить срок его действия.
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
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271146"
---
# Параметр ограничения батареи

Параметр ограничения заряда батареи — это параметр UEFI, который изменяет способ заряда батареи устройства Surface и может продлить срок его действия. Этот параметр рекомендуется в тех случаях, когда устройство постоянно подключено к сети, например при интеграции устройств в решения киоска.  

##  <a name="how-battery-limit-works"></a>Как работает ограничение заряда батареи

Установка на устройстве ограничения заряда батареи изменяет протокол для зарядки батареи устройства. Если включено ограничение заряда батареи, заряд батареи будет ограничен 50 % от максимальной емкости. Уровень заряда, сообщаемой в Windows, отражает это ограничение. Таким образом, будет видно, что заряд батареи составляет до 50 % и не будет отвечать за это ограничение. Если вы включаете ограничение заряда батареи, когда заряд устройства превышает 50 %, значок батареи будет показывать, что устройство подключено к подключению, но отключается, пока устройство не достигнет 50 % от максимальной емкости заряда.  

##  <a name="supported-devices"></a>Поддерживаемые устройства

Параметр UEFI ограничения заряда батареи встроен в новейшие устройства Surface, включая Surface Pro 7+, Surface Pro 7 и Surface Laptop 3. Более ранним устройствам требуется обновление [микропрограммы UEFI Surface,](manage-surface-driver-and-firmware-updates.md)доступное через Обновление Windows или с помощью драйверов MSI и пакетов микропрограмм на сайте [поддержки Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface) Проверьте [, включить "Ограничение](https://support.microsoft.com/help/4464941) заряда батареи" для устройств Surface, которые должны быть подключены в течение длительного времени для определенной версии UEFI Surface, необходимой для каждого поддерживаемого устройства. 

##  <a name="enabling-battery-limit-in-surface-uefi-(surface-pro-4-and-later)"></a>Включение ограничения заряда батареи в Surface UEFI (Surface Pro 4 и более поздних)

Параметр ограничения заряда батареи UEFI Surface можно настроить путем загрузки в Surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **конфигурацию загрузки,** а затем в **** области **"Дополнительные**параметры" в меню "Включить режим ограничения заряда" **вкл.**  

![Дополнительные параметры ограничения заряда батареи](images/enable-bl.png) 

##  <a name="enabling-battery-limit-on-surface-go-and-surface-go-2"></a>Включение ограничения заряда батареи на Surface Go и Surface Go 2
Параметр ограничения заряда батареи Surface можно настроить, загрузив surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **конфигурацию загрузки,** а затем в режиме терминала переместим ползунок вправо, чтобы установить для ограничения заряда батареи **включено.** ****  

![Ограничение заряда батареи в режиме терминала в Surface Go](images/go-batterylimit.png) 

##  <a name="enabling-battery-limit-in-surface-uefi-(surface-pro-3)"></a>Включение ограничения заряда батареи в Surface UEFI (Surface Pro 3)

Параметр ограничения заряда батареи UEFI Surface можно настроить путем загрузки в Surface UEFI (**Power + Vol Up** при включаемом устройстве). Выберите **режим терминала,** выберите **ограничение заряда**батареи, а затем выберите **"Включено".**

![Снимок экрана: дополнительные параметры](images/enable-bl-sp3.png) 

![Дополнительные параметры](images/enable-bl-sp3-2.png) 

##  <a name="enabling-battery-limit-using-surface-enterprise-management-mode-(semm)-or-surface-pro-3-firmware-powershell-scripts"></a>Включение ограничения заряда батареи с помощью скриптов PowerShell для режима управления Surface Enterprise (SEMM) или Surface Pro 3

Ограничение заряда батареи UEFI Surface также доступно для настройки с помощью следующих методов:

- Surface Pro 4 и более поздние 
    - [Microsoft Surface UEFI Configurator](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Сценарии Powershell диспетчера UEFI Surface (SEMM_Powershell.zip) в [средствах Surface для загрузки ИТ-отдела](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

###  <a name="using-microsoft-surface-uefi-configurator"></a>Использование Microsoft Surface UEFI Configurator

Чтобы настроить режим ограничения заряда батареи, установите **** параметр "Переопределения терминала" на странице "Дополнительные параметры" в SEMM (Surface Pro 4 и более поздних). ****

![Снимок экрана с расширенными настройками](images/semm-bl.png)

###  <a name="using-surface-uefi-manager-powershell-scripts"></a>Использование сценариев PowerShell диспетчера UEFI Surface

Управление ограничением заряда батареи осуществляется с помощью следующего параметра:  

`407 = Battery Profile`

**Описание:** схема активного управления для шаблона использования батареи

**По умолчанию:**  `0` 

Установите этот `1` режим, чтобы включить ограничение заряда батареи.

###  <a name="using-surface-pro-3-firmware-tools"></a>Использование средств микропрограмм Surface Pro 3

Управление ограничением заряда батареи осуществляется с помощью следующего параметра:  

**Name**: BatteryLimitEnable

**Описание:** BatteryLimit

**Текущее значение:**  `0` 

**Значение по умолчанию:** `0`

**Предложенное значение:** `0` 

Установите этот `1` режим, чтобы включить ограничение заряда батареи.

>[!NOTE]
>Чтобы настроить этот параметр, необходимо [ использовать ](https://www.microsoft.com/download/details.aspx?id=46703)SP3_Firmware_Powershell_Scripts.zip. 

