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
# <span data-ttu-id="42659-104">Современная проверка подлинности на Surface HUB</span><span class="sxs-lookup"><span data-stu-id="42659-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="42659-105">Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в обновление Windows 10 Team 2020, что позволяет вам перейти с устаревшей базовой проверки подлинности и использовать новейшие улучшенные возможности безопасности из Microsoft Azure и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="42659-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="42659-106">С помощью обновления 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL), включая Exchange Online для синхронизации учетных записей устройств.</span><span class="sxs-lookup"><span data-stu-id="42659-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="42659-107">Для новых облачных учетных записей Surface Hub автоматически использует современной проверки подлинности для подключения к Exchange Online, не требуя дополнительной настройки, чем просто создание учетных записей устройств с помощью формата [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="42659-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="42659-108">Не используйте устаревший формат — Contoso\alias, который не поддерживается для современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="42659-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="42659-109">Дополнительные сведения можно найти в разделе [Создание Surface Hub 2S учетная запись устройства](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="42659-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="42659-110">Surface Hub не поддерживает современной проверки подлинности для локальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="42659-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="42659-111">Учетные записи должны быть созданы в облаке.</span><span class="sxs-lookup"><span data-stu-id="42659-111">The accounts must be created in the cloud.</span></span>

