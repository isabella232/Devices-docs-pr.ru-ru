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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="3c3b5-104">Современная проверка подлинности на Surface Hub</span><span class="sxs-lookup"><span data-stu-id="3c3b5-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="3c3b5-105">Обновление Windows 10 Team 2020 добавляет поддержку современной проверки подлинности учетной записи устройства Hub в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="3c3b5-106">После установки обновления 2020 можно перейти из устаревшей базовой проверки подлинности, чтобы использовать последние улучшения безопасности, если учетная запись устройства проходит проверку подлинности через Azure Active Directory и почтовый ящик учетной записи находится в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="3c3b5-107">С обновлением 2020 года Surface Hub поддерживает протоколы Exchange Web Services (EWS) и библиотеку проверки подлинности Active Directory (ADAL) при синхронизации учетной записи устройства с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="3c3b5-108">Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online, не требуя дополнительной конфигурации, кроме простого добавления учетной записи устройства в Surface Hub с помощью [формата alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3c3b5-108">For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="3c3b5-109">Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="3c3b5-110">Дополнительные сведения см. в [записи создания и тестирования учетной записи устройства.](create-and-test-a-device-account-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="3c3b5-110">For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3c3b5-111">Современная проверка подлинности не поддерживается для локальной учетной записи Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-111">Modern authentication is not supported for on-premises Surface Hub accounts.</span></span> <span data-ttu-id="3c3b5-112">Для проверки подлинности учетные записи должны использовать только Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3c3b5-112">The accounts must use only Azure AD for authentication.</span></span>
