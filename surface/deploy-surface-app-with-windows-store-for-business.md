---
title: Развертывание приложения Surface с помощью Microsoft Store для бизнеса или Microsoft Store для образования (Surface)
description: Узнайте, как добавить и скачать приложение Surface с помощью Microsoft Store для бизнеса или Microsoft Store для образовательных учреждений, а также установить приложение Surface с помощью PowerShell и MDT.
keywords: приложение Surface, приложение, развертывание, Настройка
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114717"
---
# <span data-ttu-id="d3a1f-104">Развертывание приложения Surface с помощью Microsoft Store для бизнеса и образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="d3a1f-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="d3a1f-105">Относится к:</span><span class="sxs-lookup"><span data-stu-id="d3a1f-105">Applies to</span></span>**

- <span data-ttu-id="d3a1f-106">Ноутбук Surface Go</span><span class="sxs-lookup"><span data-stu-id="d3a1f-106">Surface Laptop Go</span></span>
- <span data-ttu-id="d3a1f-107">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d3a1f-107">Surface Pro 7</span></span>
- <span data-ttu-id="d3a1f-108">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="d3a1f-108">Surface Laptop 3</span></span>
- <span data-ttu-id="d3a1f-109">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="d3a1f-109">Surface Pro 6</span></span>
- <span data-ttu-id="d3a1f-110">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="d3a1f-110">Surface Laptop 2</span></span>
- <span data-ttu-id="d3a1f-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="d3a1f-111">Surface Go</span></span>
- <span data-ttu-id="d3a1f-112">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="d3a1f-112">Surface Go with LTE</span></span>
- <span data-ttu-id="d3a1f-113">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="d3a1f-113">Surface Book 2</span></span>
- <span data-ttu-id="d3a1f-114">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="d3a1f-114">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="d3a1f-115">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="d3a1f-115">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="d3a1f-116">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="d3a1f-116">Surface Laptop</span></span>
- <span data-ttu-id="d3a1f-117">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="d3a1f-117">Surface Studio</span></span>
- <span data-ttu-id="d3a1f-118">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d3a1f-118">Surface Studio 2</span></span>
- <span data-ttu-id="d3a1f-119">Surface Book</span><span class="sxs-lookup"><span data-stu-id="d3a1f-119">Surface Book</span></span>
- <span data-ttu-id="d3a1f-120">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="d3a1f-120">Surface Pro 4</span></span>
- <span data-ttu-id="d3a1f-121">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="d3a1f-121">Surface 3 LTE</span></span>
- <span data-ttu-id="d3a1f-122">Surface 3</span><span class="sxs-lookup"><span data-stu-id="d3a1f-122">Surface 3</span></span>
- <span data-ttu-id="d3a1f-123">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d3a1f-123">Surface Pro 3</span></span>


<span data-ttu-id="d3a1f-124">Приложение Surface — это упрощенное приложение Microsoft Store, которое обеспечивает управление многими параметрами и параметрами, связанными с определенной поверхностью, в том числе:</span><span class="sxs-lookup"><span data-stu-id="d3a1f-124">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="d3a1f-125">Включение и отключение кнопки Windows на устройстве Surface 
</span><span class="sxs-lookup"><span data-stu-id="d3a1f-125">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="d3a1f-126">Регулировка чувствительности ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="d3a1f-126">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="d3a1f-127">Настройка действий кнопки ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="d3a1f-127">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="d3a1f-128">Включение и отключение расширенных аудиофункций Surface 
</span><span class="sxs-lookup"><span data-stu-id="d3a1f-128">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="d3a1f-129">Быстрый доступ к документации и сведениям об устройстве</span><span class="sxs-lookup"><span data-stu-id="d3a1f-129">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="d3a1f-130">Пользователи, использующие Windows Update, обычно получают приложение Surface в составе автоматических обновлений.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-130">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="d3a1f-131">Но если ваша организация готовит изображения для развертывания на Surface Devices, вы можете добавить приложение Surface (прежнее название Surface HUB) в процесс создания образа и развертывания, а не требовать от пользователей каждого отдельного устройства загрузить и установить приложение из магазина Microsoft Store или из Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-131">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="d3a1f-132">Эта статья не относится к Surface Pro X. Дополнительные сведения можно найти в разделе [развертывание, управление и обслуживание Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="d3a1f-132">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="d3a1f-133">Общие сведения о приложении Surface</span><span class="sxs-lookup"><span data-stu-id="d3a1f-133">Surface app overview</span></span>

<span data-ttu-id="d3a1f-134">Приложение Surface доступно для бесплатной загрузки из [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="d3a1f-134">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="d3a1f-135">Пользователи могут скачать и установить его из Microsoft Store, но если ваша организация использует Microsoft Store для бизнеса, вам нужно будет добавить ее в запасы магазина и, возможно, включить это приложение в рамках процесса развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-135">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="d3a1f-136">Эти процессы описаны в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-136">These processes are discussed throughout this article.</span></span> <span data-ttu-id="d3a1f-137">Дополнительные сведения о Microsoft Store для бизнеса можно найти в [Microsoft Store для бизнеса](https://docs.microsoft.com/microsoft-store/) в центре Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-137">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="d3a1f-138">Добавление приложения Surface в учетную запись Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d3a1f-138">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="d3a1f-139">Прежде чем пользователи смогут установить или развернуть приложение из учетной записи Майкрософт магазина компании Microsoft Store для бизнеса, нужные приложения должны быть предоставлены и лицензированы для пользователей компании.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-139">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="d3a1f-140">Создайте [учетную запись Microsoft Store для бизнеса](https://www.microsoft.com/business-store), если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-140">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="d3a1f-141">Войдите на портал.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-141">Log on to the portal.</span></span> 

3. <span data-ttu-id="d3a1f-142">Включить автономное лицензирование: выберите **управление >параметры магазина**, а затем установите флажок **Показывать лицензируемые приложения для покупок в магазине** , как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-142">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="d3a1f-143">Дополнительные сведения о моделях лицензирования приложений Microsoft Store для бизнеса можно найти в статьях [приложения в Microsoft Store для бизнеса и образовательных учреждений](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="d3a1f-143">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Флажок "показывать автономные приложения лицензий"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="d3a1f-145">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-145">Figure 1.</span></span> <span data-ttu-id="d3a1f-146">Включение приложений для автономного использования</span><span class="sxs-lookup"><span data-stu-id="d3a1f-146">Enable apps for offline use</span></span>*

4. <span data-ttu-id="d3a1f-147">Добавьте приложение Surface в учетную запись Microsoft Store для бизнеса, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-147">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="d3a1f-148">Откройте меню " **произ** .</span><span class="sxs-lookup"><span data-stu-id="d3a1f-148">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="d3a1f-149">В поле поиска введите **Surface приложение**и щелкните значок Поиск.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-149">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="d3a1f-150">После того как приложение Surface появится в результатах поиска, щелкните значок приложения.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-150">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="d3a1f-151">Вы увидите вариант выбора (выберите в **Интернете** или в **автономном режиме**), как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-151">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="d3a1f-153">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-153">Figure 2.</span></span> <span data-ttu-id="d3a1f-154">Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел</span><span class="sxs-lookup"><span data-stu-id="d3a1f-154">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="d3a1f-155">Щелкните **автономно** , чтобы выбрать режим лицензирования в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-155">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="d3a1f-156">Нажмите кнопку **получить приложение** , чтобы добавить приложение в инвентаризацию Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-156">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="d3a1f-157">Как показано на рис. 3, появится диалоговое окно с запросом о том, что автономные приложения можно развертывать с помощью средства управления или загрузить с инвентарной страницы компании в частном магазине.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-157">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="d3a1f-158">Окно подтверждения приложения, лицензированное в автономном режиме ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *, рисунок 3. Подтверждение приложения, лицензированное в автономном режиме*</span><span class="sxs-lookup"><span data-stu-id="d3a1f-158">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="d3a1f-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-159">Click **OK**.</span></span>

## <span data-ttu-id="d3a1f-160">Скачать приложение Surface из учетной записи Майкрософт магазина для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d3a1f-160">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="d3a1f-161">После того как вы добавите приложение в учетную запись Microsoft Store для бизнеса в автономном режиме, вы можете скачать и добавить приложение в качестве AppxBundle в общий доступ к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-161">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="d3a1f-162">Войдите в учетную запись Microsoft Store для бизнеса по адресу https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="d3a1f-162">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="d3a1f-163">Выберите **>приложения & программное обеспечение**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-163">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="d3a1f-164">Откроется список всех приложений вашей компании, включая приложение Surface, которое вы добавили в [приложение добавить Surface в раздел учетной записи Microsoft Store для бизнеса](#add-surface-app-to-a-microsoft-store-for-business-account) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-164">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="d3a1f-165">В разделе **действия**нажмите кнопку с многоточием (**...**), а затем выберите команду **скачать для автономного использования** для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-165">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="d3a1f-166">Выберите нужные параметры **платформы** и **архитектуры** из доступных вариантов выбора для выбранного приложения, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-166">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Пример пакета AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="d3a1f-168">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-168">Figure 4.</span></span> <span data-ttu-id="d3a1f-169">Загрузка пакета AppxBundle для приложения</span><span class="sxs-lookup"><span data-stu-id="d3a1f-169">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="d3a1f-170">Нажмите кнопку **загрузить**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-170">Click **Download**.</span></span> <span data-ttu-id="d3a1f-171">Будет загружен пакет AppxBundle.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-171">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="d3a1f-172">Убедитесь, что путь к скачанному файлу указан, так как это потребуется позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-172">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="d3a1f-173">Выберите " **зашифрованная лицензия** " или " **нешифрованная лицензия** ".</span><span class="sxs-lookup"><span data-stu-id="d3a1f-173">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="d3a1f-174">Используйте закодированную лицензию с помощью средств управления, таких как диспетчер конфигурации конечных точек Майкрософт, или с помощью конструктора конфигураций Windows для создания пакета подготовки.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-174">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="d3a1f-175">Выберите параметр нешифрованная лицензия при использовании системы обслуживания образов развертывания и управления ими (DISM) и решений для развертывания на основе обработки изображений, включая Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="d3a1f-175">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="d3a1f-176">Нажмите кнопку " **создать** ", чтобы создать и скачать лицензию для приложения.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-176">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="d3a1f-177">Убедитесь, что вы запомните путь к файлу лицензии, так как это потребуется позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-177">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="d3a1f-178">Когда вы загружаете приложение для автономного использования, например приложение Surface, вы можете заметить раздел в нижней части страницы, помеченной **необходимыми платформами**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-178">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="d3a1f-179">Для запуска приложения на конечных компьютерах должны быть установлены платформы, поэтому вам может потребоваться повторить процесс загрузки для каждой из необходимых платформ (x86 или x64), а также включить их в развертывание Windows, описанное ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-179">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="d3a1f-180">На рисунке 5 показаны необходимые платформы для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-180">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Необходимые платформы для приложения Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="d3a1f-182">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-182">Figure 5.</span></span> <span data-ttu-id="d3a1f-183">Необходимые платформы для приложения Surface</span><span class="sxs-lookup"><span data-stu-id="d3a1f-183">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="d3a1f-184">Номера версий приложения Surface и требуемой платформы будут изменяться по мере обновления приложений.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-184">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="d3a1f-185">Проверьте наличие последней версии приложения Surface и каждой платформы в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-185">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="d3a1f-186">Всегда используйте приложение Surface и рекомендуемые версии платформы, предоставленные Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-186">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="d3a1f-187">Использование устаревших платформ или неправильных версий может привести к ошибкам или сбою приложения.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-187">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="d3a1f-188">Чтобы скачать необходимые платформы для приложения Surface, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-188">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="d3a1f-189">Нажмите кнопку **загрузить** в разделе **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-189">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="d3a1f-190">Загрузи Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe. Appx-файл в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-190">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="d3a1f-191">Нажмите кнопку **загрузить** в разделе **Microsoft. NET. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-191">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="d3a1f-192">Это загрузит файл Microsoft. NET. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe. appx в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-192">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="d3a1f-193">Для устройств Surface требуется только 64-разрядная (x64) версия каждой платформы.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-193">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="d3a1f-194">Устройства Surface — это машинные 64-битовые устройства UEFI, несовместимые с 32-разрядной (x86) версиями Windows, для которых требуется 32-разрядные платформы.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-194">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="d3a1f-195">Установка Surface App на компьютере с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3a1f-195">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="d3a1f-196">Описанная ниже процедура позволяет получить приложение Surface на компьютере и сделать ее доступной для всех учетных записей пользователей, созданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-196">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="d3a1f-197">С помощью процедуры, описанной в разделе [Загрузка приложения Surface из раздела учетной записи Microsoft Store для бизнеса](#download-surface-app-from-a-microsoft-store-for-business-account) в этой статье, скачайте файл AppxBundle приложения Surface и License File.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-197">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="d3a1f-198">Запустите сеанс Windows PowerShell с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-198">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="d3a1f-199">Если вы не запускаете PowerShell в качестве администратора, сеанс не будет обладать необходимыми разрешениями для установки приложения.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-199">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="d3a1f-200">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="d3a1f-200">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="d3a1f-201">Где `<DownloadPath>` находится папка, в которой загружен файл AppxBundle и License, из учетной записи Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-201">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="d3a1f-202">Например, если вы загрузили файлы в c:\Temp, вы можете использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d3a1f-202">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="d3a1f-203">Приложение Surface теперь доступно на этом компьютере под управлением Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-203">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="d3a1f-204">Перед тем как приложение Surface будет работать на компьютере, на котором оно было подготовлено, необходимо также подготовить платформы, описанные выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-204">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="d3a1f-205">Чтобы подготовить эти платформы, выполните описанные ниже действия в сеансе PowerShell с повышенными привилегиями, который вы использовали для подготовки приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-205">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="d3a1f-206">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="d3a1f-206">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="d3a1f-207">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="d3a1f-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="d3a1f-208">Установка Surface App с MDT</span><span class="sxs-lookup"><span data-stu-id="d3a1f-208">Install Surface app with MDT</span></span>
<span data-ttu-id="d3a1f-209">В описанной ниже процедуре используется MDT для автоматизации установки приложения Surface во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-209">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="d3a1f-210">MDT автоматически предоставляет приложение во время развертывания и, таким образом, этот процесс можно применять к существующим образам.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-210">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="d3a1f-211">Это рекомендуемый процесс развертывания приложения Surface в рамках развертывания Windows для устройств Surface, так как он не уменьшает межплатформенную совместимость образа Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-211">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="d3a1f-212">В описанной [ниже](#download-surface-app-from-a-microsoft-store-for-business-account)процедуре Скачайте файл AppxBundle приложения Surface и License File.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-212">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="d3a1f-213">С помощью мастера создания приложений в средстве развертывания MDT импортируйте Скачанные файлы в новое **приложение с исходными файлами**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-213">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="d3a1f-214">На странице **сведения о команде** мастера создания приложений укажите **Рабочий каталог** по умолчанию, а для **команды** укажите имя файла AppxBundle, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-214">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="d3a1f-215">Команда</span><span class="sxs-lookup"><span data-stu-id="d3a1f-215">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="d3a1f-216">Рабочий каталог:%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="d3a1f-216">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="d3a1f-217">Для использования приложения Surface на целевом компьютере необходимы также платформы, описанные ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-217">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="d3a1f-218">Выполните описанные ниже действия, чтобы импортировать платформы, необходимые для приложения Surface, на MDT и настроить их в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-218">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="d3a1f-219">В описанной выше процедуре загрузите файлы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-219">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="d3a1f-220">Храните каждую платформу в отдельной папке.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-220">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="d3a1f-221">С помощью мастера создания приложений в средстве развертывания MDT импортируйте Скачанные файлы в новое **приложение с исходными файлами**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-221">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="d3a1f-222">На странице **сведения о команде** введите имя каждого приложения, которое вы загрузили, в поле **команда** и рабочий каталог по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-222">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="d3a1f-223">Чтобы настроить платформы в качестве зависимостей приложения Surface, используйте следующий процесс:</span><span class="sxs-lookup"><span data-stu-id="d3a1f-223">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="d3a1f-224">Откройте свойства приложения Surface в Workbench для развертывания MDT.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-224">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="d3a1f-225">Откройте вкладку **зависимости** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-225">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="d3a1f-226">Установите флажок для каждой платформы, используя имя, указанное в мастере создания приложений.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-226">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="d3a1f-227">После импорта приложение Surface будет доступно для выбора на этапе **приложений** мастера развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-227">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="d3a1f-228">Можно также устанавливать приложение автоматически путем добавления его в последовательность задач развертывания следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-228">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="d3a1f-229">Откройте свою последовательность задач развертывания в MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-229">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="d3a1f-230">Добавьте новую задачу **Установить приложение** в разделе развертывания **Восстановление состояния**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-230">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="d3a1f-231">Выберите **установить одно приложение** и укажите **приложение Surface** в качестве приложения, **которое необходимо установить**.</span><span class="sxs-lookup"><span data-stu-id="d3a1f-231">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="d3a1f-232">Дополнительные сведения о том, как включить приложения в развертывание Windows, приведены в разделе [развертывание Windows 10 с помощью набора средств развертывания Microsoft](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="d3a1f-232">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
