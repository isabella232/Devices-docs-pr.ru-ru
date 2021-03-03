---
title: Современная проверка подлинности на Surface Hub
description: На этой странице описывается использование современной проверки подлинности в Surface Hub в отличие от устаревшей базовой проверки подлинности.
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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385167"
---
# <a name="modern-authentication-on-surface-hub"></a>Современная проверка подлинности на Surface Hub

Обновление Windows 10 Team 2020 добавляет поддержку современной проверки подлинности учетной записи устройства Hub в некоторых сценариях. После установки обновления 2020 можно перейти из устаревшей базовой проверки подлинности, чтобы использовать последние улучшения безопасности, если учетная запись устройства проходит проверку подлинности через Azure Active Directory и почтовый ящик учетной записи находится в Exchange Online. С обновлением 2020 года Surface Hub поддерживает протоколы Exchange Web Services (EWS) и библиотеку проверки подлинности Active Directory (ADAL) при синхронизации учетной записи устройства с Exchange Online.

Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online, не требуя дополнительной конфигурации, кроме простого создания учетных записей устройств [с помощью формата alias@contoso.com.](mailto:alias@contoso.com) Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности. Дополнительные сведения см. в [записи устройства Create Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

> [!NOTE]
> Surface Hub не поддерживает современную проверку подлинности для учетных записей на локальной основе. Учетные записи должны создаваться в облаке.

