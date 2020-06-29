---
title: Реализация качества обслуживания на Surface HUB
ms.reviewer: ''
manager: laurawi
description: Сведения о том, как настроить качество обслуживания на Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835192"
---
# <span data-ttu-id="d74f1-103">Реализация качества обслуживания (QoS) на Surface HUB</span><span class="sxs-lookup"><span data-stu-id="d74f1-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="d74f1-104">Качество обслуживания (QoS) — это сочетание сетевых технологий, позволяющее администраторам оптимизировать взаимодействие голосовых и видеофайлов и обмена приложениями в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="d74f1-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="d74f1-105">Настройка [QoS для Skype для бизнеса](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) на Surface HUB может быть выполнена с помощью [поставщика управления мобильными устройствами (MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью [пакета подготовки](provisioning-packages-for-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d74f1-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="d74f1-106">В этой статье объясняется, как настроить качество обслуживания Surface Hub с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d74f1-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="d74f1-107">В Intune [Создайте настраиваемую политику](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="d74f1-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Снимок экрана: диалоговое окно создания настраиваемой политики в Intune](images/qos-create.png)

2. <span data-ttu-id="d74f1-109">В окне **особые параметры OMA-URI**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d74f1-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="d74f1-110">Для каждого параметра, который вы хотите добавить, введите имя, описание (необязательно), тип данных, OMA-URI и значение.</span><span class="sxs-lookup"><span data-stu-id="d74f1-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![Снимок экрана: диалоговое окно "пустой параметр OMA-URI"](images/qos-setting.png)

3. <span data-ttu-id="d74f1-112">Добавьте следующие особые параметры OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="d74f1-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="d74f1-113">Имя</span><span class="sxs-lookup"><span data-stu-id="d74f1-113">Name</span></span> | <span data-ttu-id="d74f1-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d74f1-114">Data type</span></span> | <span data-ttu-id="d74f1-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="d74f1-115">OMA-URI</span></span><br><span data-ttu-id="d74f1-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="d74f1-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="d74f1-117">Значение</span><span class="sxs-lookup"><span data-stu-id="d74f1-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="d74f1-118">Порт источника звуковых данных</span><span class="sxs-lookup"><span data-stu-id="d74f1-118">Audio Source Port</span></span> | <span data-ttu-id="d74f1-119">Строка</span><span class="sxs-lookup"><span data-stu-id="d74f1-119">String</span></span> |  <span data-ttu-id="d74f1-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="d74f1-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="d74f1-121">Получение значений от администратора Skype</span><span class="sxs-lookup"><span data-stu-id="d74f1-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="d74f1-122">DSCP звука</span><span class="sxs-lookup"><span data-stu-id="d74f1-122">Audio DSCP</span></span> | <span data-ttu-id="d74f1-123">целое число</span><span class="sxs-lookup"><span data-stu-id="d74f1-123">Integer</span></span> |  <span data-ttu-id="d74f1-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="d74f1-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="d74f1-125">46</span><span class="sxs-lookup"><span data-stu-id="d74f1-125">46</span></span>
    <span data-ttu-id="d74f1-126">Порт источника видео</span><span class="sxs-lookup"><span data-stu-id="d74f1-126">Video Source Port</span></span> | <span data-ttu-id="d74f1-127">Строка</span><span class="sxs-lookup"><span data-stu-id="d74f1-127">String</span></span> |  <span data-ttu-id="d74f1-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="d74f1-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="d74f1-129">Получение значений от администратора Skype</span><span class="sxs-lookup"><span data-stu-id="d74f1-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="d74f1-130">DSCP видео</span><span class="sxs-lookup"><span data-stu-id="d74f1-130">Video DSCP</span></span> | <span data-ttu-id="d74f1-131">целое число</span><span class="sxs-lookup"><span data-stu-id="d74f1-131">Integer</span></span> |  <span data-ttu-id="d74f1-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="d74f1-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="d74f1-133">34</span><span class="sxs-lookup"><span data-stu-id="d74f1-133">34</span></span>
    <span data-ttu-id="d74f1-134">Имя звукового процесса</span><span class="sxs-lookup"><span data-stu-id="d74f1-134">Audio Process Name</span></span> | <span data-ttu-id="d74f1-135">Строка</span><span class="sxs-lookup"><span data-stu-id="d74f1-135">String</span></span> |  <span data-ttu-id="d74f1-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="d74f1-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="d74f1-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="d74f1-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="d74f1-138">Имя видеопроцесса</span><span class="sxs-lookup"><span data-stu-id="d74f1-138">Video Process Name</span></span> | <span data-ttu-id="d74f1-139">Строка</span><span class="sxs-lookup"><span data-stu-id="d74f1-139">String</span></span> |  <span data-ttu-id="d74f1-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="d74f1-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="d74f1-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="d74f1-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="d74f1-142">Каждый путь к **OMA-URI** начинается с `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="d74f1-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="d74f1-143">Например, можно задать полный путь к порту источника звука `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="d74f1-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="d74f1-144">После создания политики [разверните ее на Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="d74f1-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="d74f1-145">В настоящее время вы не можете настроить **IPProtocolMatchCondition** параметров в [поставщике служб шифрования NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="d74f1-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="d74f1-146">Если этот параметр настроен, политика не будет применена.</span><span class="sxs-lookup"><span data-stu-id="d74f1-146">If this setting is configured, the policy will fail to apply.</span></span>
 
