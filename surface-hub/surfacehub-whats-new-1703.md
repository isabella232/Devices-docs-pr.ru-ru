---
title: Что нового в Windows 10 (версия 1703 для Surface Hub)
description: Windows 10 версии 1703 (Creators Update) предоставляет ряд новых возможностей в Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924945"
---
# <span data-ttu-id="dbd25-103">Новые возможности Windows 10 (версия 1703 для Microsoft Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="dbd25-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="dbd25-104">Инженер Surface Hub Джордан Маркезе рассказывает об обновлениях для Microsoft Surface Hub в Windows 10 версии 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="dbd25-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="dbd25-105">Windows 10 версии 1703 (также называемая Creators Update) представляет следующие изменения для Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="dbd25-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="dbd25-106">Новые параметры</span><span class="sxs-lookup"><span data-stu-id="dbd25-106">New settings</span></span>

<span data-ttu-id="dbd25-107">Добавлены параметры для управления мобильными устройствами (MDM) и поставщиками служб настройки (CSP), чтобы расширить возможности управления Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="dbd25-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="dbd25-108">[Новые параметры включают](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="dbd25-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="dbd25-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="dbd25-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="dbd25-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="dbd25-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="dbd25-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="dbd25-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="dbd25-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="dbd25-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="dbd25-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="dbd25-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="dbd25-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="dbd25-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="dbd25-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="dbd25-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="dbd25-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="dbd25-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="dbd25-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="dbd25-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="dbd25-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="dbd25-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="dbd25-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="dbd25-119">System/AllowStorageCard</span></span>

<span data-ttu-id="dbd25-120">А также параметры на базе [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) и [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span><span class="sxs-lookup"><span data-stu-id="dbd25-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="dbd25-121">Мастер подготовки</span><span class="sxs-lookup"><span data-stu-id="dbd25-121">Provisioning wizard</span></span>

<span data-ttu-id="dbd25-122">Простой в использовании мастер поможет вам быстро создавать пакеты подготовки, которые можно применить к нескольким устройствам Surface Hub. Он также включает массовое присоединение к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbd25-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="dbd25-123">Узнайте, как создать пакет подготовки для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="dbd25-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![действия мастера подготовки устройств Surface Hub](images/wcd-wizard.png)
    
## <span data-ttu-id="dbd25-125">Использование Miracast в существующей беспроводной или локальной сети</span><span class="sxs-lookup"><span data-stu-id="dbd25-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="dbd25-126">Корпорация Майкрософт добавила возможность [отправки потока Miracast по локальной сети](miracast-over-infrastructure.md) вместо прямого беспроводного соединения.</span><span class="sxs-lookup"><span data-stu-id="dbd25-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="dbd25-127">Восстановление в облаке</span><span class="sxs-lookup"><span data-stu-id="dbd25-127">Cloud recovery</span></span>

<span data-ttu-id="dbd25-128">После сброса устройства Surface Hub вы сможете скачать и установить заводскую сборку операционной системы из облака.</span><span class="sxs-lookup"><span data-stu-id="dbd25-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="dbd25-129">Дополнительные сведения о восстановлении в облаке.</span><span class="sxs-lookup"><span data-stu-id="dbd25-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="dbd25-130">Восстановление в облаке не работает, если вы используете прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="dbd25-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![Переустановка](images/reinstall.png)
    
## <span data-ttu-id="dbd25-132">Завершить сеанс</span><span class="sxs-lookup"><span data-stu-id="dbd25-132">End session</span></span>

<span data-ttu-id="dbd25-133">**Готово** теперь заменено на **Завершить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="dbd25-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="dbd25-134">Узнайте, как использовать функцию "Завершить сеанс".</span><span class="sxs-lookup"><span data-stu-id="dbd25-134">Learn how to use End session.</span></span>](finishing-your-surface-hub-meeting.md) 

![завершить сеанс](images/end-session.png)



 

 
