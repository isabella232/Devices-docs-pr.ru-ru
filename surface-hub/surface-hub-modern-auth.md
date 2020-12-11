---
title: Современная проверка подлинности на Surface Hub
description: На этой странице описывается использование современной проверки подлинности на Surface Hub в отличие от устаревшей базовой проверки подлинности.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206283"
---
# Современная проверка подлинности на Surface Hub

Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в [Обновление Windows 10 для группы 2020.](surface-hub-2020-update.md) После установки обновления 2020 можно перейти с базовой проверки подлинности прежних версий и использовать последние улучшения безопасности из Microsoft Azure и Exchange Online. С обновлением 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности на основе библиотеки проверки подлинности Active Directory (ADAL), что позволяет exchange Online синхронизировать учетные записи устройств.

Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online без дополнительной настройки, кроме простого создания учетных записей устройств в формате [alias@contoso.com.](mailto:alias@contoso.com) Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности. Дополнительные сведения см. в записи создания [устройства Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

> [!NOTE]
> Surface Hub не поддерживает современную проверку подлинности для локальной учетной записи. Учетные записи должны быть созданы в облаке.

