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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="73b54-104">Современная проверка подлинности на Surface Hub</span><span class="sxs-lookup"><span data-stu-id="73b54-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="73b54-105">Обновление Windows 10 Team 2020 добавляет поддержку современной проверки подлинности учетной записи устройства Hub в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="73b54-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="73b54-106">После установки обновления 2020 можно перейти из устаревшей базовой проверки подлинности, чтобы использовать последние улучшения безопасности, если учетная запись устройства проходит проверку подлинности через Azure Active Directory и почтовый ящик учетной записи находится в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73b54-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="73b54-107">С обновлением 2020 года Surface Hub поддерживает протоколы Exchange Web Services (EWS) и библиотеку проверки подлинности Active Directory (ADAL) при синхронизации учетной записи устройства с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73b54-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="73b54-108">Для новых облачных учетных записей Surface Hub автоматически использует современную проверку подлинности для подключения к Exchange Online, не требуя дополнительной конфигурации, кроме простого создания учетных записей устройств [с помощью формата alias@contoso.com.](mailto:alias@contoso.com)</span><span class="sxs-lookup"><span data-stu-id="73b54-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="73b54-109">Не используйте устаревший формат Contoso\alias, который не поддерживается для современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73b54-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="73b54-110">Дополнительные сведения см. в [записи устройства Create Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)</span><span class="sxs-lookup"><span data-stu-id="73b54-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="73b54-111">Surface Hub не поддерживает современную проверку подлинности для учетных записей на локальной основе.</span><span class="sxs-lookup"><span data-stu-id="73b54-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="73b54-112">Учетные записи должны создаваться в облаке.</span><span class="sxs-lookup"><span data-stu-id="73b54-112">The accounts must be created in the cloud.</span></span>

