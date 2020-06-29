---
title: Surface Hub может устанавливать обновления и перезапускаться за пределами времени обслуживания
description: сведения об устранении неполадок для Surface Hub в отношении автоматических обновлений
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub, окно обслуживания, обновление
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836403"
---
# <span data-ttu-id="541d9-104">Surface Hub может устанавливать обновления и перезапускаться за пределами времени обслуживания</span><span class="sxs-lookup"><span data-stu-id="541d9-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="541d9-105">В определенных обстоятельствах Surface Hub устанавливает обновления в рабочее время, а не в окне обычного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="541d9-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="541d9-106">При необходимости устройство будет перезапускаться.</span><span class="sxs-lookup"><span data-stu-id="541d9-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="541d9-107">Вы не можете использовать устройство, пока процесс не будет завершен.</span><span class="sxs-lookup"><span data-stu-id="541d9-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="541d9-108">Это не является ожидаемым поведением для отсутствующего окна обслуживания.</span><span class="sxs-lookup"><span data-stu-id="541d9-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="541d9-109">Это происходит только в том случае, если устройство устарело в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="541d9-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="541d9-110">Причина</span><span class="sxs-lookup"><span data-stu-id="541d9-110">Cause</span></span>
<span data-ttu-id="541d9-111">Чтобы гарантировать, что Surface Hub останется доступным для использования в рабочее время, он настраивается для выполнения административных функций во время периода обслуживания, определенного в параметрах (см. раздел "ссылки" ниже).</span><span class="sxs-lookup"><span data-stu-id="541d9-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="541d9-112">В течение этого периода обслуживания центр автоматически устанавливает любые доступные обновления с помощью центра обновления Windows или службы обновления Windows Server (WSUS).</span><span class="sxs-lookup"><span data-stu-id="541d9-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="541d9-113">После завершения обновления центр может перезапуститься.</span><span class="sxs-lookup"><span data-stu-id="541d9-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="541d9-114">Обновления можно устанавливать в окне обслуживания только в том случае, если Surface Hub включены, но не используются или не зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="541d9-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="541d9-115">Например, если Surface Hub запланирован на собрание, продолжительность которого составляет 24 часа, любые обновления, запланированные к установке, будут отложены до тех пор, пока он не будет доступен в окне следующего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="541d9-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="541d9-116">Если концентратор продолжает заняты и пропускают несколько окон обслуживания, концентратор в итоге начнет устанавливать и скачивать обновления.</span><span class="sxs-lookup"><span data-stu-id="541d9-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="541d9-117">Это может происходить во время или за пределами периода обслуживания.</span><span class="sxs-lookup"><span data-stu-id="541d9-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="541d9-118">После того как загрузка и установка началась, устройство может перезагрузиться.</span><span class="sxs-lookup"><span data-stu-id="541d9-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="541d9-119">Чтобы избежать этой ошибки</span><span class="sxs-lookup"><span data-stu-id="541d9-119">To avoid this issue</span></span>

<span data-ttu-id="541d9-120">Важно настроить время обслуживания Surface Hub для выполнения административных функций.</span><span class="sxs-lookup"><span data-stu-id="541d9-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="541d9-121">Резервирование Surface Hub в течение 24 часового пояса или использование устройства во время периода обслуживания задерживает установку обновлений.</span><span class="sxs-lookup"><span data-stu-id="541d9-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="541d9-122">Мы рекомендуем не использовать или зарезервировать центр в течение запланированного периода обслуживания.</span><span class="sxs-lookup"><span data-stu-id="541d9-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="541d9-123">В течение двух часов окно должно быть зарезервировано для обновления.</span><span class="sxs-lookup"><span data-stu-id="541d9-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="541d9-124">Один из вариантов, с помощью которых можно управлять доступом обновлений — служба обновления Windows Server (WSUS).</span><span class="sxs-lookup"><span data-stu-id="541d9-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="541d9-125">WSUS предоставляет контроль над тем, какие обновления установлены и когда.</span><span class="sxs-lookup"><span data-stu-id="541d9-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="541d9-126">Ссылки</span><span class="sxs-lookup"><span data-stu-id="541d9-126">References</span></span> 
 
[<span data-ttu-id="541d9-127">Обновление Surface Hub</span><span class="sxs-lookup"><span data-stu-id="541d9-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="541d9-128">Период обслуживания</span><span class="sxs-lookup"><span data-stu-id="541d9-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="541d9-129">Развертывание обновлений Windows 10 с помощью служб Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="541d9-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


