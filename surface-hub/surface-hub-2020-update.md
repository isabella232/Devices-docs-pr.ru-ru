---
title: Установка обновления Windows 10 для совместной работы 2020
description: Получите последнее обновление операционной системы Surface Hub версии Windows 10 для совместной работы 2020.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 7474787351a9371fb09fa10348ac9f6591b81f6b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497832"
---
# <a name="install-windows-10-team-2020-update"></a>Установка обновления Windows 10 для совместной работы 2020 

Новая операционная система Surface Hub **, обновление Windows 10 для совместной работы 2020** на основе версии Windows 10 20H2, теперь доступна для Surface Hub 2S и исходного Surface Hub (версия 1). 

- См. также: [Известные проблемы: Windows 10 для совместной работы 2020 г](surface-hub-2020-team-update-known-issues.md).

## <a name="distribution"></a>Распространения

Обновление за Windows 2020 г. можно получить одним из следующих способов:

- **клиентский компонент Центра обновления Windows для бизнеса**.
- **Образ восстановления без операционной системы (BMR**). Рекомендуемый вариант для клиентов, которые присоединяются к своим устройствам Azure Active Directory или не разрешают устройствам получать обновления из Интернета. Чтобы приступить к работе, см [. статью "Скачивание образа восстановления для Surface"](https://support.microsoft.com/surfacerecoveryimage).
- **Центр обновления Windows.** Доступность зависит от региона или страны, как указано в следующей таблице:

| Этап | Страна или регион                         | Начиная          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Австралия, Канада, Бельгия, Мексика | Октябрь 2020 г.  |
| 2     | Соединенное Королевство, Япония, Швейцария, Испания          | Ноябрь 2020 г. |
| 3     | Германия, Нидерланды                   | В конце февраля 2021 г. |
| 4     | Глобальная                                 | Ранний март 2021 г. |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Обслуживание Устройств Surface Hub с Windows 10 для совместной работы Edition версии 1703 

Полная поддержка обслуживания [Windows 10 для совместной работы Edition версии 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) будет продолжена до 16 марта 2021 г.

### <a name="2s-devices"></a>Устройства 2S 

Клиенты во всех регионах могут обновить свои устройства Surface Hub 2S до обновления 2020 с помощью клиентский компонент Центра обновления Windows, клиентский компонент Центра обновления Windows для бизнеса или с помощью образа восстановления без операционной системы (BMR), как описано в разделе "Сброс и восстановление для [ Surface Hub 2S](surface-hub-2s-recover-reset.md).

### <a name="v1-devices"></a>Устройства версии 1 

Клиенты во всех регионах могут обновить свои устройства Surface Hub версии 1 до обновления 2020 через клиентский компонент Центра обновления Windows, клиентский компонент Центра обновления Windows для бизнеса или с помощью [Surface Hub Recovery Средство](surface-hub-recovery-tool.md). Чтобы получить обновление по беспроводной сети, необходимо установить KB5000749. Дополнительные сведения см. в блоге [Pro Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Новые возможности

Windows 10 для совместной работы 2020 г. обеспечивает значительные улучшения развертывания устройств и управляемости, а также новейшие Windows устройств. Дополнительные сведения см. в статье "Новые возможности Windows 10 для совместной работы [2020 г."](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Перед началом работы

Перед установкой Windows 10 для совместной работы обновления 2020 убедитесь, что вы сохраните ключ BitLocker, связанный с устройством. 

**Сохранение ключа BitLocker вручную**

1. Вставьте USB-накопитель в Surface Hub.
2. На **Surface Hub откройте Параметры** и при появлении запроса введите учетные данные администратора.
3. Перейдите **к разделу &** **SecurityRecovery** > .
4. В **разделе BitLocker выберите** " **Сохранить"**. Ключ BitLocker сохраняется в текстовом файле на USB-накопителе.

Дополнительные сведения см [. в разделе "Сохранение ключа BitLocker"](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Подробнее

- [Новые возможности обновления Windows 10 для совместной работы 2020](surface-hub-2020-update-whats-new.md)
- [Обновление до выпуска Windows 10 для совместной работы](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
