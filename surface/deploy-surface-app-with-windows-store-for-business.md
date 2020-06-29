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
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835123"
---
# <span data-ttu-id="7297a-104">Развертывание приложения Surface с помощью Microsoft Store для бизнеса и образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="7297a-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="7297a-105">Относится к:</span><span class="sxs-lookup"><span data-stu-id="7297a-105">Applies to</span></span>**

- <span data-ttu-id="7297a-106">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="7297a-106">Surface Pro 7</span></span>
- <span data-ttu-id="7297a-107">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="7297a-107">Surface Laptop 3</span></span>
- <span data-ttu-id="7297a-108">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="7297a-108">Surface Pro 6</span></span>
- <span data-ttu-id="7297a-109">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="7297a-109">Surface Laptop 2</span></span>
- <span data-ttu-id="7297a-110">Surface Go</span><span class="sxs-lookup"><span data-stu-id="7297a-110">Surface Go</span></span>
- <span data-ttu-id="7297a-111">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="7297a-111">Surface Go with LTE</span></span>
- <span data-ttu-id="7297a-112">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="7297a-112">Surface Book 2</span></span>
- <span data-ttu-id="7297a-113">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="7297a-113">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="7297a-114">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="7297a-114">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="7297a-115">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="7297a-115">Surface Laptop</span></span>
- <span data-ttu-id="7297a-116">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="7297a-116">Surface Studio</span></span>
- <span data-ttu-id="7297a-117">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="7297a-117">Surface Studio 2</span></span>
- <span data-ttu-id="7297a-118">Surface Book</span><span class="sxs-lookup"><span data-stu-id="7297a-118">Surface Book</span></span>
- <span data-ttu-id="7297a-119">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="7297a-119">Surface Pro 4</span></span>
- <span data-ttu-id="7297a-120">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="7297a-120">Surface 3 LTE</span></span>
- <span data-ttu-id="7297a-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="7297a-121">Surface 3</span></span>
- <span data-ttu-id="7297a-122">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="7297a-122">Surface Pro 3</span></span>


<span data-ttu-id="7297a-123">Приложение Surface — это упрощенное приложение Microsoft Store, которое обеспечивает управление многими параметрами и параметрами, связанными с определенной поверхностью, в том числе:</span><span class="sxs-lookup"><span data-stu-id="7297a-123">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="7297a-124">Включение и отключение кнопки Windows на устройстве Surface 
</span><span class="sxs-lookup"><span data-stu-id="7297a-124">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="7297a-125">Регулировка чувствительности ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="7297a-125">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="7297a-126">Настройка действий кнопки ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="7297a-126">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="7297a-127">Включение и отключение расширенных аудиофункций Surface 
</span><span class="sxs-lookup"><span data-stu-id="7297a-127">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="7297a-128">Быстрый доступ к документации и сведениям об устройстве</span><span class="sxs-lookup"><span data-stu-id="7297a-128">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="7297a-129">Пользователи, использующие Windows Update, обычно получают приложение Surface в составе автоматических обновлений.</span><span class="sxs-lookup"><span data-stu-id="7297a-129">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="7297a-130">Но если ваша организация готовит изображения для развертывания на Surface Devices, вы можете добавить приложение Surface (прежнее название Surface HUB) в процесс создания образа и развертывания, а не требовать от пользователей каждого отдельного устройства загрузить и установить приложение из магазина Microsoft Store или из Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7297a-130">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="7297a-131">Эта статья не относится к Surface Pro X. Дополнительные сведения можно найти в разделе [развертывание, управление и обслуживание Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="7297a-131">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="7297a-132">Общие сведения о приложении Surface</span><span class="sxs-lookup"><span data-stu-id="7297a-132">Surface app overview</span></span>

<span data-ttu-id="7297a-133">Приложение Surface доступно для бесплатной загрузки из [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="7297a-133">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="7297a-134">Пользователи могут скачать и установить его из Microsoft Store, но если ваша организация использует Microsoft Store для бизнеса, вам нужно будет добавить ее в запасы магазина и, возможно, включить это приложение в рамках процесса развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="7297a-134">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="7297a-135">Эти процессы описаны в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7297a-135">These processes are discussed throughout this article.</span></span> <span data-ttu-id="7297a-136">Дополнительные сведения о Microsoft Store для бизнеса можно найти в [Microsoft Store для бизнеса](https://docs.microsoft.com/microsoft-store/) в центре Windows.</span><span class="sxs-lookup"><span data-stu-id="7297a-136">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="7297a-137">Добавление приложения Surface в учетную запись Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7297a-137">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="7297a-138">Прежде чем пользователи смогут установить или развернуть приложение из учетной записи Майкрософт магазина компании Microsoft Store для бизнеса, нужные приложения должны быть предоставлены и лицензированы для пользователей компании.</span><span class="sxs-lookup"><span data-stu-id="7297a-138">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="7297a-139">Создайте [учетную запись Microsoft Store для бизнеса](https://www.microsoft.com/business-store), если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="7297a-139">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="7297a-140">Войдите на портал.</span><span class="sxs-lookup"><span data-stu-id="7297a-140">Log on to the portal.</span></span> 

3. <span data-ttu-id="7297a-141">Включить автономное лицензирование: выберите **управление >параметры магазина**, а затем установите флажок **Показывать лицензируемые приложения для покупок в магазине** , как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="7297a-141">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="7297a-142">Дополнительные сведения о моделях лицензирования приложений Microsoft Store для бизнеса можно найти в статьях [приложения в Microsoft Store для бизнеса и образовательных учреждений](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="7297a-142">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span><br/> <br/>
   ![Флажок "показывать автономные приложения лицензий"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="7297a-144">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="7297a-144">Figure 1.</span></span> <span data-ttu-id="7297a-145">Включение приложений для автономного использования</span><span class="sxs-lookup"><span data-stu-id="7297a-145">Enable apps for offline use</span></span>*

4. <span data-ttu-id="7297a-146">Добавьте приложение Surface в учетную запись Microsoft Store для бизнеса, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7297a-146">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>
    * <span data-ttu-id="7297a-147">Откройте меню " **произ** .</span><span class="sxs-lookup"><span data-stu-id="7297a-147">Click the **Shop** menu.</span></span>
    * <span data-ttu-id="7297a-148">В поле поиска введите **Surface приложение**и щелкните значок Поиск.</span><span class="sxs-lookup"><span data-stu-id="7297a-148">In the search box, type **Surface app**, and then click the search icon.</span></span>
    * <span data-ttu-id="7297a-149">После того как приложение Surface появится в результатах поиска, щелкните значок приложения.</span><span class="sxs-lookup"><span data-stu-id="7297a-149">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    * <span data-ttu-id="7297a-150">Вы увидите вариант выбора (выберите в **Интернете** или в **автономном режиме**), как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="7297a-150">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span><br/><br/>
    
    ![Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *<span data-ttu-id="7297a-152">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="7297a-152">Figure 2.</span></span> <span data-ttu-id="7297a-153">Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел</span><span class="sxs-lookup"><span data-stu-id="7297a-153">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="7297a-154">Щелкните **автономно** , чтобы выбрать режим лицензирования в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="7297a-154">Click **Offline** to select the Offline licensing mode.</span></span>
    * <span data-ttu-id="7297a-155">Нажмите кнопку **получить приложение** , чтобы добавить приложение в инвентаризацию Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7297a-155">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="7297a-156">Как показано на рис. 3, появится диалоговое окно с запросом о том, что автономные приложения можно развертывать с помощью средства управления или загрузить с инвентарной страницы компании в частном магазине.</span><span class="sxs-lookup"><span data-stu-id="7297a-156">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
    ![Окно подтверждения приложения, лицензированное в автономном режиме](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *<span data-ttu-id="7297a-158">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="7297a-158">Figure 3.</span></span> <span data-ttu-id="7297a-159">Подтверждение приложения, лицензированное в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="7297a-159">Offline-licensed app acknowledgement</span></span>*
    * <span data-ttu-id="7297a-160">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7297a-160">Click **OK**.</span></span>

## <span data-ttu-id="7297a-161">Скачать приложение Surface из учетной записи Майкрософт магазина для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7297a-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="7297a-162">После того как вы добавите приложение в учетную запись Microsoft Store для бизнеса в автономном режиме, вы можете скачать и добавить приложение в качестве AppxBundle в общий доступ к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7297a-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>
1. <span data-ttu-id="7297a-163">Войдите в учетную запись Microsoft Store для бизнеса по адресу https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="7297a-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>
2. <span data-ttu-id="7297a-164">Выберите **>приложения & программное обеспечение**.</span><span class="sxs-lookup"><span data-stu-id="7297a-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="7297a-165">Откроется список всех приложений вашей компании, включая приложение Surface, которое вы добавили в [приложение добавить Surface в раздел учетной записи Microsoft Store для бизнеса](#add-surface-app-to-a-microsoft-store-for-business-account) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7297a-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>
3. <span data-ttu-id="7297a-166">В разделе **действия**нажмите кнопку с многоточием (**...**), а затем выберите команду **скачать для автономного использования** для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="7297a-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>
4. <span data-ttu-id="7297a-167">Выберите нужные параметры **платформы** и **архитектуры** из доступных вариантов выбора для выбранного приложения, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="7297a-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    ![Пример пакета AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *<span data-ttu-id="7297a-169">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="7297a-169">Figure 4.</span></span> <span data-ttu-id="7297a-170">Загрузка пакета AppxBundle для приложения</span><span class="sxs-lookup"><span data-stu-id="7297a-170">Download the AppxBundle package for an app</span></span>*
5. <span data-ttu-id="7297a-171">Нажмите кнопку **загрузить**.</span><span class="sxs-lookup"><span data-stu-id="7297a-171">Click **Download**.</span></span> <span data-ttu-id="7297a-172">Будет загружен пакет AppxBundle.</span><span class="sxs-lookup"><span data-stu-id="7297a-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="7297a-173">Убедитесь, что путь к скачанному файлу указан, так как это потребуется позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7297a-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>
6. <span data-ttu-id="7297a-174">Выберите " **зашифрованная лицензия** " или " **нешифрованная лицензия** ".</span><span class="sxs-lookup"><span data-stu-id="7297a-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="7297a-175">Используйте закодированную лицензию с помощью средств управления, таких как диспетчер конфигурации конечных точек Майкрософт, или с помощью конструктора конфигураций Windows для создания пакета подготовки.</span><span class="sxs-lookup"><span data-stu-id="7297a-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="7297a-176">Выберите параметр нешифрованная лицензия при использовании системы обслуживания образов развертывания и управления ими (DISM) и решений для развертывания на основе обработки изображений, включая Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="7297a-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>
7. <span data-ttu-id="7297a-177">Нажмите кнопку " **создать** ", чтобы создать и скачать лицензию для приложения.</span><span class="sxs-lookup"><span data-stu-id="7297a-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="7297a-178">Убедитесь, что вы запомните путь к файлу лицензии, так как это потребуется позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7297a-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="7297a-179">Когда вы загружаете приложение для автономного использования, например приложение Surface, вы можете заметить раздел в нижней части страницы, помеченной **необходимыми платформами**.</span><span class="sxs-lookup"><span data-stu-id="7297a-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="7297a-180">Для запуска приложения на конечных компьютерах должны быть установлены платформы, поэтому вам может потребоваться повторить процесс загрузки для каждой из необходимых платформ (x86 или x64), а также включить их в развертывание Windows, описанное ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7297a-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="7297a-181">На рисунке 5 показаны необходимые платформы для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="7297a-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

![Необходимые платформы для приложения Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*<span data-ttu-id="7297a-183">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="7297a-183">Figure 5.</span></span> <span data-ttu-id="7297a-184">Необходимые платформы для приложения Surface</span><span class="sxs-lookup"><span data-stu-id="7297a-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="7297a-185">Номера версий приложения Surface и требуемой платформы будут изменяться по мере обновления приложений.</span><span class="sxs-lookup"><span data-stu-id="7297a-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="7297a-186">Проверьте наличие последней версии приложения Surface и каждой платформы в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7297a-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="7297a-187">Всегда используйте приложение Surface и рекомендуемые версии платформы, предоставленные Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7297a-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="7297a-188">Использование устаревших платформ или неправильных версий может привести к ошибкам или сбою приложения.</span><span class="sxs-lookup"><span data-stu-id="7297a-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="7297a-189">Чтобы скачать необходимые платформы для приложения Surface, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7297a-189">To download the required frameworks for the Surface app, follow these steps:</span></span>
1. <span data-ttu-id="7297a-190">Нажмите кнопку **загрузить** в разделе **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="7297a-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="7297a-191">Загрузи Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe. Appx-файл в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="7297a-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>
2. <span data-ttu-id="7297a-192">Нажмите кнопку **загрузить** в разделе **Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="7297a-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="7297a-193">В указанную папку будет загружен файл Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. appx.</span><span class="sxs-lookup"><span data-stu-id="7297a-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="7297a-194">Для устройств Surface требуется только 64-разрядная (x64) версия каждой платформы.</span><span class="sxs-lookup"><span data-stu-id="7297a-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="7297a-195">Устройства Surface — это машинные 64-битовые устройства UEFI, несовместимые с 32-разрядной (x86) версиями Windows, для которых требуется 32-разрядные платформы.</span><span class="sxs-lookup"><span data-stu-id="7297a-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="7297a-196">Установка Surface App на компьютере с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="7297a-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="7297a-197">Описанная ниже процедура позволяет получить приложение Surface на компьютере и сделать ее доступной для всех учетных записей пользователей, созданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7297a-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>
1. <span data-ttu-id="7297a-198">С помощью процедуры, описанной в разделе [Загрузка приложения Surface из раздела учетной записи Microsoft Store для бизнеса](#download-surface-app-from-a-microsoft-store-for-business-account) в этой статье, скачайте файл AppxBundle приложения Surface и License File.</span><span class="sxs-lookup"><span data-stu-id="7297a-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 
2. <span data-ttu-id="7297a-199">Запустите сеанс Windows PowerShell с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="7297a-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7297a-200">Если вы не запускаете PowerShell в качестве администратора, сеанс не будет обладать необходимыми разрешениями для установки приложения.</span><span class="sxs-lookup"><span data-stu-id="7297a-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="7297a-201">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="7297a-201">In the elevated PowerShell session, copy and paste the following command:</span></span>
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="7297a-202">Где `<DownloadPath>` находится папка, в которой загружен файл AppxBundle и License, из учетной записи Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7297a-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="7297a-203">Например, если вы загрузили файлы в c:\Temp, вы можете использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7297a-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
