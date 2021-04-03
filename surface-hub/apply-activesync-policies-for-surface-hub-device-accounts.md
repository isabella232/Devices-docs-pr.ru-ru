---
title: Применение политик ActiveSync к учетным записям устройств (Surface Hub)
description: Для синхронизации почты и календаря в учетной записи устройства Microsoft Surface Hub используется протокол ActiveSync. Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, политики ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: e8181ec499364c48586f5218983f667331788fc3
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470447"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="79b0d-105">Применение политик ActiveSync к учетным записям устройств (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="79b0d-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="79b0d-106">Концентраторы Surface, использующие операционную систему Windows 10 Team 1703, используют ActiveSync для синхронизации почты и календаря учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="79b0d-106">Surface Hubs using the Windows 10 Team 1703 operating system make use of ActiveSync to sync mail and calendar of the device account.</span></span> <span data-ttu-id="79b0d-107">Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.</span><span class="sxs-lookup"><span data-stu-id="79b0d-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="79b0d-108">Чтобы эти компоненты можно было использовать, политики ActiveSync вашей организации необходимо настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="79b0d-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="79b0d-109">Не должно быть глобальных политик, которые блокируют синхронизацию почтового ящика ресурса, используемого учетной записью устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="79b0d-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="79b0d-110">Если существует такая политика блокировки, необходимо добавить Surface Hub в качестве разрешенного устройства.</span><span class="sxs-lookup"><span data-stu-id="79b0d-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="79b0d-111">Необходимо настроить политику почтового ящика мобильного устройства, параметру **PasswordEnabled** которой присвоено значение False.</span><span class="sxs-lookup"><span data-stu-id="79b0d-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="79b0d-112">Другие параметры политики почтового ящика мобильного устройства не совместимы с Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="79b0d-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="79b0d-113">Разрешение deviceID</span><span class="sxs-lookup"><span data-stu-id="79b0d-113">Allowing the DeviceID</span></span>

<span data-ttu-id="79b0d-114">В организации может использоваться глобальная политика, которая блокирует синхронизацию учетных записей, подготовленных на устройствах Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="79b0d-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="79b0d-115">Сведения о настройке этого свойства см. в разделе [Разрешение идентификаторов устройств для ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="79b0d-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="79b0d-116">Настройка параметра PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="79b0d-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="79b0d-117">Учетная запись устройства должна использовать политику ActiveSync, атрибут **PasswordEnabled** которое имеет значение False или 0.</span><span class="sxs-lookup"><span data-stu-id="79b0d-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="79b0d-118">Сведения о настройке свойства см. в разделе [Создание политики Microsoft Exchange ActiveSync, совместимой с Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="79b0d-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





