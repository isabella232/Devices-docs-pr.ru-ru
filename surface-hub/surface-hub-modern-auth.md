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
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474766"
---
# <a name="modern-authentication-on-surface-hub"></a>Современная проверка подлинности на Surface Hub

Обновление Windows 10 Team 2020 добавляет поддержку современной проверки подлинности учетной записи устройства Hub в некоторых сценариях. После установки обновления 2020 можно перейти из устаревшей базовой проверки подлинности, чтобы использовать последние улучшения безопасности, если учетная запись устройства проходит проверку подлинности через Azure Active Directory и почтовый ящик учетной записи находится в Exchange Online. С обновлением 2020 года Surface Hub поддерживает протоколы Exchange Web Services (EWS) и библиотеку проверки подлинности Active Directory (ADAL) при синхронизации учетной записи устройства с Exchange Online.

Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online, не требуя дополнительной конфигурации, кроме простого добавления учетной записи устройства в Surface Hub с помощью [формата alias@contoso.com](mailto:alias@contoso.com). Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности. Дополнительные сведения см. в [записи создания и тестирования учетной записи устройства.](create-and-test-a-device-account-surface-hub.md)

> [!NOTE]
> Современная проверка подлинности не поддерживается для локальной учетной записи Surface Hub. Для проверки подлинности учетные записи должны использовать только Azure AD.
