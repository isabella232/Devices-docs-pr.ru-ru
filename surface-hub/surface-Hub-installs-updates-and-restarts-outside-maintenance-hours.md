---
title: Surface Hub может устанавливать обновления и перезапускаться за пределами времени обслуживания
description: устранение неполадок для Surface Hub автоматических обновлений
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: концентратор поверхности, окно обслуживания, обновление
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577029"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="bdf07-104">Surface Hub может устанавливать обновления и перезапускаться за пределами времени обслуживания</span><span class="sxs-lookup"><span data-stu-id="bdf07-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="bdf07-105">В определенных условиях Surface Hub устанавливает обновления в часы работы, а не во время регулярного окна обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="bdf07-106">Затем устройство перезапускается, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="bdf07-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="bdf07-107">Вы не можете использовать устройство до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="bdf07-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="bdf07-108">Это не ожидаемое поведение для пропуска окна обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="bdf07-109">Это происходит только в том случае, если устройство давно устарело.</span><span class="sxs-lookup"><span data-stu-id="bdf07-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="bdf07-110">Причина</span><span class="sxs-lookup"><span data-stu-id="bdf07-110">Cause</span></span>

<span data-ttu-id="bdf07-111">Чтобы Surface Hub остается доступным для использования в часы работы, концентратор настроен для выполнения административных функций во время окна обслуживания, определенного в Параметры (см. "Ссылки", ниже).</span><span class="sxs-lookup"><span data-stu-id="bdf07-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="bdf07-112">В этот период обслуживания концентратор автоматически устанавливает все доступные обновления через Windows или Windows обновления для бизнеса (WUFB).</span><span class="sxs-lookup"><span data-stu-id="bdf07-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="bdf07-113">После завершения обновлений концентратор может перезапуститься.</span><span class="sxs-lookup"><span data-stu-id="bdf07-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="bdf07-114">Обновления можно установить в окне обслуживания, только если Surface Hub включена, но не используется или зарезервирована.</span><span class="sxs-lookup"><span data-stu-id="bdf07-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="bdf07-115">Например, если Surface Hub собрания, которое длится 24 часа, все обновления, которые планируется установить, будут отложены до тех пор, пока концентратор не будет доступен в течение следующего окна обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="bdf07-116">Если концентратор по-прежнему занят и не хватает нескольких окон обслуживания, концентратор в конечном итоге начнет устанавливать и загружать обновления.</span><span class="sxs-lookup"><span data-stu-id="bdf07-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="bdf07-117">Это может произойти во время или за пределами окна обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="bdf07-118">После загрузки и установки устройство может перезапуститься.</span><span class="sxs-lookup"><span data-stu-id="bdf07-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="bdf07-119">Чтобы избежать этой проблемы</span><span class="sxs-lookup"><span data-stu-id="bdf07-119">To avoid this issue</span></span>

<span data-ttu-id="bdf07-120">Важно, чтобы вы отложили время на Surface Hub для выполнения административных функций.</span><span class="sxs-lookup"><span data-stu-id="bdf07-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="bdf07-121">Сохранение Surface Hub в течение 24 часов или использование устройства во время задержки установки обновлений в окне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="bdf07-122">Рекомендуется не использовать концентратор и не зарезервировать его во время запланированного периода обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bdf07-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="bdf07-123">Для обновления необходимо зарезервировать двухчасовое окно.</span><span class="sxs-lookup"><span data-stu-id="bdf07-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="bdf07-124">Один из вариантов, который можно использовать для управления доступностью обновлений, Windows для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bdf07-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="bdf07-125">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bdf07-125">Learn more</span></span>
 
- [<span data-ttu-id="bdf07-126">Обновление Surface Hub</span><span class="sxs-lookup"><span data-stu-id="bdf07-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="bdf07-127">Период обслуживания</span><span class="sxs-lookup"><span data-stu-id="bdf07-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 
