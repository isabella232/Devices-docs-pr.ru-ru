---
title: Обновление Surface Devices до Windows 10 с помощью набора средств развертывания Microsoft (Surface)
description: Узнайте, как выполнить развертывание Windows 10 на вашем устройстве Surface.
keywords: поверхность Windows 10, обновление, Настройка, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835536"
---
# <span data-ttu-id="dc28d-104">Обновление Surface Devices до Windows 10 с помощью набора средств развертывания Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc28d-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="dc28d-105">Относится к:</span><span class="sxs-lookup"><span data-stu-id="dc28d-105">Applies to</span></span>
- <span data-ttu-id="dc28d-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="dc28d-106">Surface Pro 6</span></span>
- <span data-ttu-id="dc28d-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="dc28d-107">Surface Laptop 2</span></span>
- <span data-ttu-id="dc28d-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="dc28d-108">Surface Go</span></span>
- <span data-ttu-id="dc28d-109">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="dc28d-109">Surface Go with LTE</span></span>
- <span data-ttu-id="dc28d-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="dc28d-110">Surface Book 2</span></span>
- <span data-ttu-id="dc28d-111">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="dc28d-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="dc28d-112">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="dc28d-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="dc28d-113">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="dc28d-113">Surface Laptop</span></span>
- <span data-ttu-id="dc28d-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="dc28d-114">Surface Studio</span></span>
- <span data-ttu-id="dc28d-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="dc28d-115">Surface Studio 2</span></span>
- <span data-ttu-id="dc28d-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="dc28d-116">Surface Book</span></span>
- <span data-ttu-id="dc28d-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="dc28d-117">Surface Pro 4</span></span>
- <span data-ttu-id="dc28d-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="dc28d-118">Surface 3 LTE</span></span>
- <span data-ttu-id="dc28d-119">Surface 3</span><span class="sxs-lookup"><span data-stu-id="dc28d-119">Surface 3</span></span>
- <span data-ttu-id="dc28d-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="dc28d-120">Surface Pro 3</span></span>
- <span data-ttu-id="dc28d-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="dc28d-121">Surface Pro 2</span></span>
- <span data-ttu-id="dc28d-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="dc28d-122">Surface Pro</span></span>
- <span data-ttu-id="dc28d-123">Windows 10;</span><span class="sxs-lookup"><span data-stu-id="dc28d-123">Windows 10</span></span>

<span data-ttu-id="dc28d-124">В дополнение к традиционным методам развертывания reimaging устройств, администраторы, которые хотят обновить Surface Devices под управлением Windows 8,1 или Windows 10, имеют возможность развертывания обновлений.</span><span class="sxs-lookup"><span data-stu-id="dc28d-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="dc28d-125">Выполнив развертывание обновления, можно применить к устройствам Windows 10, не удаляя пользователей, приложения или конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="dc28d-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="dc28d-126">Пользователи развернутых устройств могут просто продолжать использовать устройства с теми же приложениями и параметрами, которые использовались перед обновлением.</span><span class="sxs-lookup"><span data-stu-id="dc28d-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="dc28d-127">Последние сведения об обновлении устройств Surface с помощью MDT можно найти в статье [выполнение обновления на месте до Windows 10 с помощью MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="dc28d-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

