---
title: Surface Slim Pen 2 haptics dev notes
description: На этой странице содержится заметки о реализации для разработчиков приложений, которые хотят расширить Windows 11 ink возможностей Surface Slim Pen 2 для бизнеса.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: 8a3dbbdde85cfdceaf5674750a68fc21d3fcd877
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338707"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>Surface Slim Pen 2 haptics dev notes

На этой странице содержится заметки о реализации для разработчиков приложений, которые хотят расширить Windows 11 ink возможностей [Surface Slim Pen 2 для бизнеса](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). Настраиваемые функции haptics включают в себя следующие функции:

- **Inking feedback** that simulates the feel of pens, pencils, and other writing or drawing tools.
- **Обратная** связь взаимодействия, которая реагирует непосредственно на действия пользователя, такие как наведении на кнопку, нажатие кнопки или выполнение задачи с помощью пера.

Если вы настраиваете приложение для Surface Slim Pen 2, обратитесь к рекомендациям Windows Ink, описанным в взаимодействиях [Pen](/windows/apps/design/input/pen-haptics) и тактической обратной связи, а затем проконсультируйтесь с примечаниями ниже.

## <a name="implementation-notes"></a>Заметки по реализации

Surface Slim Pen 2 соответствует Windows 11 Ink с следующими исключениями:

- **Формы волн взаимодействия.** Как описано в разделе [Отправка](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback) и остановка обратной связи взаимодействия", отправка формы волн взаимодействия при окинговом виостановлении временно прервет висят волновую форму. Однако при текущей реализации Slim Pen 2 при остановке формы волны взаимодействия может не возобновиться. Поэтому, если требуется, включаемая волноваяформа должна быть включена повторно после обратной связи взаимодействия. Нет необходимости ждать завершения обратной связи взаимодействия.
- **Неподтверченные функции.** Как описано в разделе Параметры настройки обратной связи [haptic](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations), следующие необязательные функции не поддерживаются в Surface Slim Pen 2: Play Count and Replay Pause Interval. Хотя эти использования отображаются в дескрипторе, в настоящее время они не поддерживаются. Поэтому следующие функции возвращают неправильное значение: IsPlayCountSupported, IsPlayDurationSupported, IsReplayPauseIntervalSupported.

## <a name="learn-more"></a>Подробнее

- [Взаимодействие и Windows Ink в Windows приложениях](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 для бизнеса](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Функции пера Surface и совместимость](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)

