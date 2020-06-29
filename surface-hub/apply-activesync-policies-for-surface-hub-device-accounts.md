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
ms.openlocfilehash: 6e93069c2d90bdc4c2f505bc28ba0ec1a4f08076
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835800"
---
# <span data-ttu-id="a342b-105">Применение политик ActiveSync к учетным записям устройств (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="a342b-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="a342b-106">Для синхронизации почты и календаря в учетной записи устройства Microsoft Surface Hub используется протокол ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="a342b-106">The Microsoft Surface Hub's device account uses ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="a342b-107">Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.</span><span class="sxs-lookup"><span data-stu-id="a342b-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="a342b-108">Чтобы эти компоненты можно было использовать, политики ActiveSync вашей организации необходимо настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a342b-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="a342b-109">Не должно быть глобальных политик, которые блокируют синхронизацию почтового ящика ресурса, используемого учетной записью устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a342b-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="a342b-110">Если такая политика заблокирована, необходимо добавить Surface Hub в качестве разрешенного устройства.</span><span class="sxs-lookup"><span data-stu-id="a342b-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="a342b-111">Необходимо настроить политику почтового ящика мобильного устройства, параметру **PasswordEnabled** которой присвоено значение False.</span><span class="sxs-lookup"><span data-stu-id="a342b-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="a342b-112">Другие параметры политики почтового ящика мобильного устройства не совместимы с Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a342b-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <span data-ttu-id="a342b-113">Разрешение DeviceID</span><span class="sxs-lookup"><span data-stu-id="a342b-113">Allowing the DeviceID</span></span>


<span data-ttu-id="a342b-114">В организации может использоваться глобальная политика, которая блокирует синхронизацию учетных записей, подготовленных на устройствах Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a342b-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="a342b-115">Сведения о настройке этого свойства см. в разделе [Разрешение идентификаторов устройств для ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="a342b-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).</span></span>

## <span data-ttu-id="a342b-116">Настройка параметра PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="a342b-116">Setting PasswordEnabled</span></span>


<span data-ttu-id="a342b-117">Учетная запись устройства должна использовать политику ActiveSync, атрибут **PasswordEnabled** которое имеет значение False или 0.</span><span class="sxs-lookup"><span data-stu-id="a342b-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="a342b-118">Сведения о настройке свойства см. в разделе [Создание политики Microsoft Exchange ActiveSync, совместимой с Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="a342b-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





