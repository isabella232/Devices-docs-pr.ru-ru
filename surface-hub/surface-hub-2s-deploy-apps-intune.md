---
title: Развертывание приложений на Surface Hub 2S с помощью Intune
description: Сведения о том, как развертывать приложения на Surface Hub 2S с помощью Intune.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835688"
---
# <span data-ttu-id="7f913-104">Развертывание приложений на Surface Hub 2S с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="7f913-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="7f913-105">Вы можете установить дополнительные приложения в соответствии с потребностями группы или организации.</span><span class="sxs-lookup"><span data-stu-id="7f913-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="7f913-106">Рекомендации для разработчиков</span><span class="sxs-lookup"><span data-stu-id="7f913-106">Developer guidelines</span></span>

- <span data-ttu-id="7f913-107">Surface Hub выполняет только [приложения универсальной платформы Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span><span class="sxs-lookup"><span data-stu-id="7f913-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="7f913-108">Приложения, созданные с помощью [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter), не будут запускаться в Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7f913-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="7f913-109">Приложения должны быть предназначены для [универсального семейства устройств](https://msdn.microsoft.com/library/windows/apps/dn894631) или семейства устройств команды разработчиков Windows.</span><span class="sxs-lookup"><span data-stu-id="7f913-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="7f913-110">Surface Hub поддерживает только [автономно лицензированные приложения](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) из [Microsoft Store для бизнеса](https://businessstore.microsoft.com/store).</span><span class="sxs-lookup"><span data-stu-id="7f913-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="7f913-111">По умолчанию приложения для установки должны иметь подпись Магазина.</span><span class="sxs-lookup"><span data-stu-id="7f913-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="7f913-112">Во время тестирования и разработки можно выбрать для запуска приложения UWP с подписью разработчика, переведя устройство в режим разработчика.</span><span class="sxs-lookup"><span data-stu-id="7f913-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="7f913-113">При разработке и отправке приложений в Microsoft Store настройте доступность семейства устройств и параметры корпоративного лицензирования, чтобы обеспечить доступность приложений для работы на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7f913-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="7f913-114">Для установки приложений на Surface Hub вам понадобятся учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="7f913-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="7f913-115">Surface Hub, предназначенный для использования в помещениях для собраний и других общих сферах, не позволяет обычным пользователям получать доступ к Microsoft Store для загрузки и установки приложений.</span><span class="sxs-lookup"><span data-stu-id="7f913-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="7f913-116">Рекомендации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="7f913-116">Deployment guidelines</span></span>

<span data-ttu-id="7f913-117">Приложения для универсальной платформы Windows (UWP) можно развертывать на Surface Hub 2S с помощью Intune, что позволяет замедлению развертывания приложений на устройства.</span><span class="sxs-lookup"><span data-stu-id="7f913-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="7f913-118">Чтобы развернуть приложение, включите MDM для своей организации.</span><span class="sxs-lookup"><span data-stu-id="7f913-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="7f913-119">На портале Intune выберите **Intune** в качестве администратора MDM (рекомендуемый вариант).</span><span class="sxs-lookup"><span data-stu-id="7f913-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![Выбор центра MDM](images/sh2-set-intune5.png)

2. <span data-ttu-id="7f913-121">Включите Microsoft Store для бизнеса в Intune.</span><span class="sxs-lookup"><span data-stu-id="7f913-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="7f913-122">Откройте Intune, выберите **клиентские приложения**  >  **Microsoft Store для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="7f913-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![Включить магазин для бизнеса](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="7f913-124">В Intune откройте **Microsoft Store для бизнеса** и выберите **Параметры**  >  **распространения**  >  **средств управления**.</span><span class="sxs-lookup"><span data-stu-id="7f913-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="7f913-125">Выберите **Microsoft Intune** в качестве средства управления.</span><span class="sxs-lookup"><span data-stu-id="7f913-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![Добавление Intune в качестве средства управления](images/sh2-set-intune8.png)

4. <span data-ttu-id="7f913-127">В Microsoft Store для бизнеса выберите **Параметры**для покупок в  >  **магазине**  >  **Shopping Experience**и установите флажок **Показать автономные приложения**.</span><span class="sxs-lookup"><span data-stu-id="7f913-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="7f913-128">Автономные приложения ссылаются на приложения, которые можно синхронизировать с Intune и централизованно развернутые на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7f913-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="7f913-129">После включения автономных покупок вы можете получать лицензии на автономные приложения для приложений, которые можно синхронизировать с Intune и развернуть в качестве лицензирования устройств.</span><span class="sxs-lookup"><span data-stu-id="7f913-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="7f913-130">В **Intune**  >  **приложениях клиента**Intune  >  **Microsoft Store для бизнеса**нажмите кнопку " **синхронизировать**".</span><span class="sxs-lookup"><span data-stu-id="7f913-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="7f913-131">На странице клиентские приложения выполните поиск приложения в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="7f913-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="7f913-132">Назначьте приложения для нужной группы или групп устройств.</span><span class="sxs-lookup"><span data-stu-id="7f913-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="7f913-133">Выберите **назначение**  >  **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="7f913-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* Назначение приложений группам \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="7f913-135">В разделе Тип задания выберите значение **обязательно**.</span><span class="sxs-lookup"><span data-stu-id="7f913-135">Under assignment type, choose **Required**.</span></span> <br>

![\* Назначение приложений группам \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="7f913-137">Для выбранных групп выберите **Лицензирование устройств** , а затем нажмите кнопку **ОК** и сохраните задание.</span><span class="sxs-lookup"><span data-stu-id="7f913-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* Назначение приложений группам \*](images/sh2-apps-assign.png)
