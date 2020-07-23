---
title: Современная проверка подлинности на Surface HUB
description: На этой странице описывается использование современной проверки подлинности на Surface Hub в отличие от устаревшей базовой проверки подлинности.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893156"
---
# Современная проверка подлинности на Surface HUB

Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в обновление Windows 10 Team 2020, что позволяет вам перейти с устаревшей базовой проверки подлинности и использовать новейшие улучшенные возможности безопасности из Microsoft Azure и Exchange Online. С помощью обновления 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL), включая Exchange Online для синхронизации учетных записей устройств.

Для новых облачных учетных записей Surface Hub автоматически использует современной проверки подлинности для подключения к Exchange Online, не требуя дополнительной настройки, чем просто создание учетных записей устройств с помощью формата [alias@contoso.com](mailto:alias@contoso.com). Не используйте устаревший формат — Contoso\alias, который не поддерживается для современной проверки подлинности. Дополнительные сведения можно найти в разделе [Создание Surface Hub 2S учетная запись устройства](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub не поддерживает современной проверки подлинности для локальных учетных записей. Учетные записи должны быть созданы в облаке.

