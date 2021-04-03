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
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474736"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="c26a0-105">Применение политик ActiveSync к учетным записям устройств (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="c26a0-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="c26a0-106">Surface Hubs, использующие учетные записи устройств Active Directory (в формате Hub **в домене\имя** пользователя) и локальной службы Exchange, используют ActiveSync для синхронизации почты и календаря.</span><span class="sxs-lookup"><span data-stu-id="c26a0-106">Surface Hubs using Active Directory device accounts (provisioned on the Hub in **domain\username** format) and on-premises Exchange services make use of ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="c26a0-107">Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.</span><span class="sxs-lookup"><span data-stu-id="c26a0-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="c26a0-108">Чтобы эти компоненты можно было использовать, политики ActiveSync вашей организации необходимо настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c26a0-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="c26a0-109">Не должно быть глобальных политик, которые блокируют синхронизацию почтового ящика ресурса, используемого учетной записью устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c26a0-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="c26a0-110">Если существует такая политика блокировки, необходимо добавить Surface Hub в качестве разрешенного устройства.</span><span class="sxs-lookup"><span data-stu-id="c26a0-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="c26a0-111">Необходимо настроить политику почтового ящика мобильного устройства, параметру **PasswordEnabled** которой присвоено значение False.</span><span class="sxs-lookup"><span data-stu-id="c26a0-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="c26a0-112">Другие параметры политики почтового ящика мобильного устройства не совместимы с Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c26a0-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="c26a0-113">Разрешение deviceID</span><span class="sxs-lookup"><span data-stu-id="c26a0-113">Allowing the DeviceID</span></span>

<span data-ttu-id="c26a0-114">В организации может использоваться глобальная политика, которая блокирует синхронизацию учетных записей, подготовленных на устройствах Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c26a0-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="c26a0-115">Сведения о настройке этого свойства см. в разделе [Разрешение идентификаторов устройств для ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="c26a0-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="c26a0-116">Настройка параметра PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="c26a0-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="c26a0-117">Учетная запись устройства должна использовать политику ActiveSync, атрибут **PasswordEnabled** которое имеет значение False или 0.</span><span class="sxs-lookup"><span data-stu-id="c26a0-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="c26a0-118">Сведения о настройке свойства см. в разделе [Создание политики Microsoft Exchange ActiveSync, совместимой с Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="c26a0-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





