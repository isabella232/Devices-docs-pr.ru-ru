---
title: Реализация качества обслуживания на Surface HUB
ms.reviewer: ''
manager: laurawi
description: Узнайте, как настроить QoS на Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470487"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="5a53d-103">Реализация качества обслуживания (QoS) на Surface Hub</span><span class="sxs-lookup"><span data-stu-id="5a53d-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="5a53d-104">Качество службы (QoS) — это сочетание сетевых технологий, которое позволяет администраторам оптимизировать взаимодействие аудио- и видео- и приложений в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5a53d-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="5a53d-105">Настройка [QoS для Skype для](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) бизнеса на Surface Hub может быть сделана с помощью поставщика управления мобильными устройствами [(MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью пакета [обеспечения.](provisioning-packages-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="5a53d-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="5a53d-106">Эта процедура объясняет, как настроить QoS для Surface Hub с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5a53d-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="5a53d-107">В Intune [создайте настраиваемую политику.](https://docs.microsoft.com/intune/custom-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="5a53d-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана диалогового номера создания настраиваемой политики в Intune](images/qos-create.png)

2. <span data-ttu-id="5a53d-109">В **настраиваемом параметре OMA-URI**выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5a53d-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="5a53d-110">Для каждого добавленного параметра введите имя, описание (необязательно), тип данных, OMA-URI и значение.</span><span class="sxs-lookup"><span data-stu-id="5a53d-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана пустого диалоговое окно параметра OMA-URI](images/qos-setting.png)

3. <span data-ttu-id="5a53d-112">Добавьте следующие настраиваемые параметры OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="5a53d-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="5a53d-113">Имя</span><span class="sxs-lookup"><span data-stu-id="5a53d-113">Name</span></span> | <span data-ttu-id="5a53d-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5a53d-114">Data type</span></span> | <span data-ttu-id="5a53d-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="5a53d-115">OMA-URI</span></span><br><span data-ttu-id="5a53d-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="5a53d-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="5a53d-117">Значение</span><span class="sxs-lookup"><span data-stu-id="5a53d-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="5a53d-118">Порт источника аудио</span><span class="sxs-lookup"><span data-stu-id="5a53d-118">Audio Source Port</span></span> | <span data-ttu-id="5a53d-119">Строка</span><span class="sxs-lookup"><span data-stu-id="5a53d-119">String</span></span> |  <span data-ttu-id="5a53d-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="5a53d-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="5a53d-121">Получите значения от администратора Skype</span><span class="sxs-lookup"><span data-stu-id="5a53d-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="5a53d-122">DSCP звука</span><span class="sxs-lookup"><span data-stu-id="5a53d-122">Audio DSCP</span></span> | <span data-ttu-id="5a53d-123">целое число</span><span class="sxs-lookup"><span data-stu-id="5a53d-123">Integer</span></span> |  <span data-ttu-id="5a53d-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="5a53d-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="5a53d-125">46</span><span class="sxs-lookup"><span data-stu-id="5a53d-125">46</span></span>
    <span data-ttu-id="5a53d-126">Порт источника видео</span><span class="sxs-lookup"><span data-stu-id="5a53d-126">Video Source Port</span></span> | <span data-ttu-id="5a53d-127">Строка</span><span class="sxs-lookup"><span data-stu-id="5a53d-127">String</span></span> |  <span data-ttu-id="5a53d-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="5a53d-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="5a53d-129">Получите значения от администратора Skype</span><span class="sxs-lookup"><span data-stu-id="5a53d-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="5a53d-130">DSCP видео</span><span class="sxs-lookup"><span data-stu-id="5a53d-130">Video DSCP</span></span> | <span data-ttu-id="5a53d-131">целое число</span><span class="sxs-lookup"><span data-stu-id="5a53d-131">Integer</span></span> |  <span data-ttu-id="5a53d-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="5a53d-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="5a53d-133">34</span><span class="sxs-lookup"><span data-stu-id="5a53d-133">34</span></span>
    <span data-ttu-id="5a53d-134">Имя процесса аудио</span><span class="sxs-lookup"><span data-stu-id="5a53d-134">Audio Process Name</span></span> | <span data-ttu-id="5a53d-135">Строка</span><span class="sxs-lookup"><span data-stu-id="5a53d-135">String</span></span> |  <span data-ttu-id="5a53d-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="5a53d-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="5a53d-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="5a53d-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="5a53d-138">Имя процесса видео</span><span class="sxs-lookup"><span data-stu-id="5a53d-138">Video Process Name</span></span> | <span data-ttu-id="5a53d-139">Строка</span><span class="sxs-lookup"><span data-stu-id="5a53d-139">String</span></span> |  <span data-ttu-id="5a53d-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="5a53d-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="5a53d-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="5a53d-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="5a53d-142">Каждый **путь OMA-URI** начинается с `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="5a53d-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="5a53d-143">Полный путь для параметра порта источника звука, например, будет `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="5a53d-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="5a53d-144">После создания политики разверни ее в Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5a53d-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="5a53d-145">В настоящее время невозможно настроить параметр **IPProtocolMatchCondition** в [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)</span><span class="sxs-lookup"><span data-stu-id="5a53d-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="5a53d-146">Если этот параметр настроен, политика не будет применяться.</span><span class="sxs-lookup"><span data-stu-id="5a53d-146">If this setting is configured, the policy will fail to apply.</span></span>
 
