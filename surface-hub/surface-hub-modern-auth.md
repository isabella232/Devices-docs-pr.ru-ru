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
# <span data-ttu-id="32050-104">Современная проверка подлинности на Surface Hub</span><span class="sxs-lookup"><span data-stu-id="32050-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="32050-105">Поддержка современной проверки подлинности облачных учетных записей полностью интегрирована в предстоящее обновление Windows 10 Team 2020 с помощью предварительных сборок, доступных в [программе предварительной оценки Windows](https://insider.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="32050-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="32050-106">После [установки предварительной сборки](surface-hub-install-2020preview.md)вы можете перейти от устаревшей базовой проверки подлинности и использовать новейшие улучшенные средства безопасности из Microsoft Azure и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="32050-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="32050-107">С помощью обновления 2020 Surface Hub поддерживает протоколы веб-служб Exchange (EWS) и проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL), включая Exchange Online для синхронизации учетных записей устройств.</span><span class="sxs-lookup"><span data-stu-id="32050-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="32050-108">Для новых облачных учетных записей Surface Hub автоматически использует современной проверки подлинности для подключения к Exchange Online, не требуя дополнительной настройки, чем просто создание учетных записей устройств с помощью формата [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="32050-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="32050-109">Не используйте устаревший формат — Contoso\alias, который не поддерживается для современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="32050-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="32050-110">Дополнительные сведения можно найти в разделе [Создание Surface Hub 2S учетная запись устройства](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="32050-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="32050-111">Surface Hub не поддерживает современной проверки подлинности для локальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="32050-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="32050-112">Учетные записи должны быть созданы в облаке.</span><span class="sxs-lookup"><span data-stu-id="32050-112">The accounts must be created in the cloud.</span></span>

