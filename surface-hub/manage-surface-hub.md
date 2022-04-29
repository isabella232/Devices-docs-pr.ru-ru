---
title: Управление Microsoft Surface Hub
description: Узнайте, как управлять устройством Surface Hub после завершения программы первого запуска.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: управление Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 0230f5abbb33e1a447bc662741d241042f4d278b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497933"
---
# <a name="manage-microsoft-surface-hub"></a>Управление Microsoft Surface Hub

После начальной настройки Microsoft Surface Hub параметры и конфигурацию устройства можно изменить несколькими способами:

- **Локальное управление**— каждое устройство Surface Hub можно настроить локально с помощью приложения **Параметры** на устройстве. Во избежание несанкционированного изменения параметров для открытия приложения «Параметры» требуются учетные данные администратора. Дополнительные сведения см. в разделе [Локальное управление параметрами Surface Hub](local-management-surface-hub-settings.md).
- **** Удаленное управление Surface Hub позволяет ИТ-администраторам управлять параметрами и политиками с помощью поставщика управления мобильными устройствами (MDM), например Microsoft Intune, Microsoft Endpoint Configuration Manager и других сторонних поставщиков. Кроме того, администраторы могут отслеживать Surface Hub с помощью Azure Monitor.  Дополнительные сведения см. в статье "Управление параметрами с помощью поставщика [MDM](manage-settings-with-mdm-for-surface-hub.md)" и мониторинг [Устройств Surface Hub с помощью Azure Monitor для отслеживания их работоспособности](/azure/azure-monitor/insights/surface-hubs).

> [!NOTE]
> Эти методы управления не являются взаимоисключающими. Устройствами можно управлять локально и удаленно по вашему выбору. Однако политики и параметры MDM будут перезаписывать локальные изменения при Surface Hub синхронизации с сервером управления.

## <a name="in-this-section"></a>В этом разделе

Узнайте об управлении и обновлении Surface Hub.

| Раздел | Описание |
| ----- | ----------- |
| [Удаленное управление Surface Hub](remote-surface-hub-management.md) |Разделы, связанные с удаленным управлением Surface Hub. Включены материалы об установке приложений, управлении параметрами с помощью MDM и отслеживании с использованием Operations Management Suite. |
| [Управление параметрами Surface Hub](manage-surface-hub-settings.md) |Разделы, посвященные управлению параметрами Surface Hub: специальные возможности, учетная запись устройства, сброс устройства, полное доменное имя устройства, параметры центра обновления Windows и беспроводная сеть |
| [Установка приложений на устройстве Surface Hub](install-apps-on-surface-hub.md) | Администраторы могут устанавливать приложения из Microsoft Store и Microsoft Store для бизнеса.|
[Настройка меню "Пуск" Surface Hub](surface-hub-start-menu.md) | Используйте MDM для настройки меню "Пуск" устройства Surface Hub.
| [Настройка и использование Доски (Майкрософт)](whiteboard-collaboration.md)  | Последнее обновление приложения Доска (Майкрософт) включает возможность совместной работы двух устройств Surface Hub в режиме реального времени на одной доске.   |
| [Завершение собрания с помощью кнопки "Завершить сеанс"](finishing-your-surface-hub-meeting.md) | В конце собрания пользователи могут коснуться кнопки **Завершить сеанс**, чтобы удалить конфиденциальные данные и подготовить устройство к следующему собранию.|
| [Вход в Surface Hub с помощью проверки Microsoft Authenticator](surface-hub-authenticator-app.md) | Выполнить вход в систему на Surface Hub без ввода пароля можно с помощью приложения Microsoft Authenticator, доступного для iOS и Android.   |
| [Сохранение ключа BitLocker](save-bitlocker-key-surface-hub.md) | На каждом устройстве Surface Hub автоматически устанавливается программное обеспечение для шифрования дисков BitLocker. Корпорация Майкрософт настоятельно рекомендует создавать резервные копии ключей восстановления BitLocker.|
| [Подключение других устройств и отображение их содержимого с помощью Surface Hub](connect-and-display-with-surface-hub.md) | Вы можете подключить к Surface Hub другое устройство и отобразить его содержимое.|
| [Использование Miracast в существующей беспроводной или локальной сети](miracast-over-infrastructure.md) | Вы можете использовать Miracast в беспроводной или локальной сети для подключения к Surface Hub. |
 [Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети](enable-8021x-wired-authentication.md) | Политики MDM для проверки подлинности по стандарту безопасности 802.1X в проводной сети были включены на устройствах Surface Hub.
| [Использование системы управления помещением](use-room-control-system-with-surface-hub.md) | Вы можете использовать системы управления помещением вместе с устройством Microsoft Surface Hub.|
[Использование средства восстановления Surface Hub](surface-hub-recovery-tool.md) | Используйте средство Surface Hub восстановления для повторного создания образа Surface Hub SSD.
[Замена SSD-диска Surface Hub](surface-hub-ssd-replacement.md) | Узнайте, как удалить и заменить твердотельный накопитель в Surface Hub.

## <a name="related-topics"></a>Статьи по теме

- [Просмотр отчетов и панелей мониторинга в режиме презентации на Surface Hub и Windows 10 устройствах](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
