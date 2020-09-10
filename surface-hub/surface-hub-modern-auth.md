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
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004471"
---
# Современная проверка подлинности на Surface Hub

Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в предстоящее обновление Windows 10 Team 2020 с помощью предварительных сборок, доступных в [программе предварительной оценки Windows](https://insider.windows.com/). После [установки предварительной сборки](surface-hub-install-2020preview.md)вы можете перейти от устаревшей базовой проверки подлинности и использовать новейшие улучшенные средства безопасности из Microsoft Azure и Exchange Online. С помощью обновления 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL), включая Exchange Online для синхронизации учетных записей устройств.

Для новых облачных учетных записей Surface Hub автоматически использует современной проверки подлинности для подключения к Exchange Online, не требуя дополнительной настройки, чем просто создание учетных записей устройств с помощью формата [alias@contoso.com](mailto:alias@contoso.com). Не используйте устаревший формат — Contoso\alias, который не поддерживается для современной проверки подлинности. Дополнительные сведения можно найти в разделе [Создание Surface Hub 2S учетная запись устройства](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub не поддерживает современной проверки подлинности для локальных учетных записей. Учетные записи должны быть созданы в облаке.

