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
# <span data-ttu-id="8dcf4-104">Современная проверка подлинности на Surface Hub</span><span class="sxs-lookup"><span data-stu-id="8dcf4-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="8dcf4-105">Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в [Обновление Windows 10 для группы 2020.](surface-hub-2020-update.md)</span><span class="sxs-lookup"><span data-stu-id="8dcf4-105">Support for modern authentication of cloud-based accounts is fully integrated in [Windows 10 Team 2020 Update](surface-hub-2020-update.md).</span></span> <span data-ttu-id="8dcf4-106">После установки обновления 2020 можно перейти с базовой проверки подлинности прежних версий и использовать последние улучшения безопасности из Microsoft Azure и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8dcf4-106">Once you install the 2020 update, you can migrate from legacy basic authentication and use the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="8dcf4-107">С обновлением 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности на основе библиотеки проверки подлинности Active Directory (ADAL), что позволяет exchange Online синхронизировать учетные записи устройств.</span><span class="sxs-lookup"><span data-stu-id="8dcf4-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="8dcf4-108">Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online без дополнительной настройки, кроме простого создания учетных записей устройств в формате [alias@contoso.com.](mailto:alias@contoso.com)</span><span class="sxs-lookup"><span data-stu-id="8dcf4-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="8dcf4-109">Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8dcf4-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="8dcf4-110">Дополнительные сведения см. в записи создания [устройства Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)</span><span class="sxs-lookup"><span data-stu-id="8dcf4-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="8dcf4-111">Surface Hub не поддерживает современную проверку подлинности для локальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="8dcf4-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="8dcf4-112">Учетные записи должны быть созданы в облаке.</span><span class="sxs-lookup"><span data-stu-id="8dcf4-112">The accounts must be created in the cloud.</span></span>

