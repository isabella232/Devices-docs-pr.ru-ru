---
title: Развертывание приложения Surface с помощью Microsoft Store для бизнеса или Microsoft Store для образования (Surface)
description: Узнайте, как добавить и скачать приложение Surface в Microsoft Store для бизнеса или Microsoft Store для образования, а также установить приложение Surface с помощью PowerShell и MDT.
keywords: surface app, app, deployment, customize
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271076"
---
# <span data-ttu-id="e4903-104">Развертывание приложения Surface с помощью Microsoft Store для бизнеса и образования</span><span class="sxs-lookup"><span data-stu-id="e4903-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="e4903-105">Относится к:</span><span class="sxs-lookup"><span data-stu-id="e4903-105">Applies to</span></span>**

- <span data-ttu-id="e4903-106">Surface Pro 7 и более</span><span class="sxs-lookup"><span data-stu-id="e4903-106">Surface Pro 7+</span></span>
- <span data-ttu-id="e4903-107">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="e4903-107">Surface Laptop Go</span></span>
- <span data-ttu-id="e4903-108">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="e4903-108">Surface Pro 7</span></span>
- <span data-ttu-id="e4903-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="e4903-109">Surface Laptop 3</span></span>
- <span data-ttu-id="e4903-110">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="e4903-110">Surface Pro 6</span></span>
- <span data-ttu-id="e4903-111">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="e4903-111">Surface Laptop 2</span></span>
- <span data-ttu-id="e4903-112">Surface Go</span><span class="sxs-lookup"><span data-stu-id="e4903-112">Surface Go</span></span>
- <span data-ttu-id="e4903-113">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="e4903-113">Surface Go with LTE</span></span>
- <span data-ttu-id="e4903-114">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="e4903-114">Surface Book 2</span></span>
- <span data-ttu-id="e4903-115">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="e4903-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="e4903-116">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="e4903-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="e4903-117">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="e4903-117">Surface Laptop</span></span>
- <span data-ttu-id="e4903-118">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="e4903-118">Surface Studio</span></span>
- <span data-ttu-id="e4903-119">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="e4903-119">Surface Studio 2</span></span>
- <span data-ttu-id="e4903-120">Surface Book</span><span class="sxs-lookup"><span data-stu-id="e4903-120">Surface Book</span></span>
- <span data-ttu-id="e4903-121">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="e4903-121">Surface Pro 4</span></span>
- <span data-ttu-id="e4903-122">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="e4903-122">Surface 3 LTE</span></span>
- <span data-ttu-id="e4903-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="e4903-123">Surface 3</span></span>
- <span data-ttu-id="e4903-124">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="e4903-124">Surface Pro 3</span></span>


<span data-ttu-id="e4903-125">Приложение Surface — это облегченное приложение Microsoft Store, которое обеспечивает управление множеством параметров и параметров, в том числе:</span><span class="sxs-lookup"><span data-stu-id="e4903-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="e4903-126">Включение и отключение кнопки Windows на устройстве Surface 
</span><span class="sxs-lookup"><span data-stu-id="e4903-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="e4903-127">Регулировка чувствительности ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="e4903-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="e4903-128">Настройка действий кнопки ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="e4903-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="e4903-129">Включение и отключение расширенных аудиофункций Surface 
</span><span class="sxs-lookup"><span data-stu-id="e4903-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="e4903-130">Быстрый доступ к документации и информации о поддержке устройства</span><span class="sxs-lookup"><span data-stu-id="e4903-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="e4903-131">Пользователи, использующие Обновление Windows, обычно получают приложение Surface в рамках автоматических обновлений.</span><span class="sxs-lookup"><span data-stu-id="e4903-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="e4903-132">Но если ваша организация подготавливает образы для развертывания на устройства Surface, вы можете включить приложение Surface (прежнее название Surface Hub) в процесс создания образа и развертывания вместо того, чтобы требовать от пользователей каждого отдельного устройства скачивать и устанавливать приложение из Microsoft Store или Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4903-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4903-133">Эта статья не относится к Surface Pro X. Дополнительные сведения: [развертывание, управление и обслуживание Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="e4903-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="e4903-134">Обзор приложения Surface</span><span class="sxs-lookup"><span data-stu-id="e4903-134">Surface app overview</span></span>

<span data-ttu-id="e4903-135">Приложение Surface доступно для бесплатной загрузки из [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="e4903-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="e4903-136">Пользователи могут скачать и установить его из Microsoft Store, но если в вашей организации вместо этого используется Microsoft Store для бизнеса, вам потребуется добавить его в перечень вашего магазина и, возможно, включить приложение в процесс развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="e4903-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="e4903-137">Эти процессы обсуждаются в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="e4903-138">Дополнительные сведения о Microsoft Store для бизнеса см. в [Microsoft Store для бизнеса](https://docs.microsoft.com/microsoft-store/) в Техническом центре Windows.</span><span class="sxs-lookup"><span data-stu-id="e4903-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="e4903-139">Добавление приложения Surface в учетную запись Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4903-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="e4903-140">Прежде чем пользователи смогут установить или развернуть приложение из учетной записи Microsoft Store для бизнеса компании, необходимо сначала сделать нужные приложения доступными и лицензироваться для пользователей предприятия.</span><span class="sxs-lookup"><span data-stu-id="e4903-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="e4903-141">Если это еще не сделано, создайте учетную запись [Microsoft Store для бизнеса.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="e4903-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="e4903-142">Войдите на портал.</span><span class="sxs-lookup"><span data-stu-id="e4903-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="e4903-143">Включить автономное лицензирование: нажмите кнопку "Управление **>Store"** и выберите "Показать приложения с автономным лицензированием для людей, которые будут делать покупки в магазине", как показано на рисунке 1. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e4903-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="e4903-144">Дополнительные сведения о моделях лицензирования приложений Microsoft Store для бизнеса см. в приложении [в Microsoft Store для бизнеса и образования.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="e4903-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Show offline licenses apps checkbox](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="e4903-146">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="e4903-146">Figure 1.</span></span> <span data-ttu-id="e4903-147">Включить приложения для автономного использования</span><span class="sxs-lookup"><span data-stu-id="e4903-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="e4903-148">Чтобы добавить приложение Surface в свою учетную запись Microsoft Store для бизнеса, с помощью следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="e4903-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="e4903-149">Выберите меню **"Магазин".**</span><span class="sxs-lookup"><span data-stu-id="e4903-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="e4903-150">В поле поиска введите **приложение Surface**и щелкните значок поиска.</span><span class="sxs-lookup"><span data-stu-id="e4903-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="e4903-151">После того как приложение Surface будет представлено в результатах поиска, щелкните значок приложения.</span><span class="sxs-lookup"><span data-stu-id="e4903-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="e4903-152">Вы можете выбрать вариант (выберите "В сети" или "В автономном режиме"), как показано на рисунке 2. \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e4903-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Выберите режим автономного лицензирования и добавьте приложение в инвентарный список](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="e4903-154">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="e4903-154">Figure 2.</span></span> <span data-ttu-id="e4903-155">Выберите режим автономного лицензирования и добавьте приложение в инвентарный список</span><span class="sxs-lookup"><span data-stu-id="e4903-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="e4903-156">Щелкните **автономный** режим, чтобы выбрать режим автономного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e4903-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="e4903-157">Щелкните **"Получить приложение",** чтобы добавить его в ассортимент Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4903-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="e4903-158">Как показано на рисунке 3, вы увидите диалоговое окно с запросом подтверждения того, что автономные приложения можно развернуть с помощью средства управления или скачать со страницы инвентаризации компании в частном магазине.</span><span class="sxs-lookup"><span data-stu-id="e4903-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="e4903-159">Окно подтверждения приложения с автономной лицензией ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *на рис. 3. Подтверждение приложения с автономной лицензией*</span><span class="sxs-lookup"><span data-stu-id="e4903-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="e4903-160">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4903-160">Click **OK**.</span></span>

## <span data-ttu-id="e4903-161">Скачивание приложения Surface из учетной записи Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4903-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="e4903-162">После добавления приложения в учетную запись Microsoft Store для бизнеса в автономном режиме вы можете скачать и добавить приложение в качестве AppxBundle в обную долю развертывания.</span><span class="sxs-lookup"><span data-stu-id="e4903-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="e4903-163">Войдите в учетную запись Microsoft Store для бизнеса по этой же https://businessstore.microsoft.com учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e4903-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="e4903-164">Щелкните **"Управление >приложениями & программного обеспечения.**</span><span class="sxs-lookup"><span data-stu-id="e4903-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="e4903-165">Отобразить список всех приложений вашей компании, включая приложение Surface, добавленное в приложении ["Добавление Surface"](#add-surface-app-to-a-microsoft-store-for-business-account) в раздел учетной записи Microsoft Store для бизнеса в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="e4903-166">В **области "Действия"** щелкните многолипки (**...**) и нажмите кнопку "Скачать для автономного **использования"** для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="e4903-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="e4903-167">Выберите **нужные** параметры **платформы** и архитектуры из доступных вариантов для выбранного приложения, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="e4903-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Пример пакета AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="e4903-169">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="e4903-169">Figure 4.</span></span> <span data-ttu-id="e4903-170">Скачивание пакета AppxBundle для приложения</span><span class="sxs-lookup"><span data-stu-id="e4903-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="e4903-171">Нажмите **кнопку «Скачать».**</span><span class="sxs-lookup"><span data-stu-id="e4903-171">Click **Download**.</span></span> <span data-ttu-id="e4903-172">Будет загружен пакет AppxBundle.</span><span class="sxs-lookup"><span data-stu-id="e4903-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="e4903-173">Обратите внимание на путь к загруженным файлам, так как он понадобится вам далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="e4903-174">Щелкните либо **закодированную лицензию,** либо **некодированную** лицензию.</span><span class="sxs-lookup"><span data-stu-id="e4903-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="e4903-175">Используйте параметр закодированной лицензии с помощью таких средств управления, как Microsoft Endpoint Configuration Manager, или при создании пакета подготовка с помощью конструктора конфигураций Windows.</span><span class="sxs-lookup"><span data-stu-id="e4903-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="e4903-176">Выберите некодированную лицензию при использовании службы обслуживания образа развертывания и управления ими (DISM) или решений развертывания на основе изображений, в том числе Microsoft Deployment набор средств (MDT).</span><span class="sxs-lookup"><span data-stu-id="e4903-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="e4903-177">Нажмите **кнопку** "Создать", чтобы создать и скачать лицензию для приложения.</span><span class="sxs-lookup"><span data-stu-id="e4903-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="e4903-178">Заметьте путь к файлу лицензии, так как он понадобится вам далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="e4903-179">При загрузке приложения для автономного использования, например для приложения Surface, вы можете заметить раздел в нижней части страницы с меткой **"Необходимые структуры".**</span><span class="sxs-lookup"><span data-stu-id="e4903-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="e4903-180">На целевых компьютерах должны быть установлены структуры для запуска приложения, поэтому может потребоваться повторить процесс скачивания для каждой из необходимых для архитектуры (x86 или x64) структур, а также включить их в развертывание Windows, рассмотренного далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="e4903-181">На рисунке 5 показаны необходимые для приложения Surface структуры.</span><span class="sxs-lookup"><span data-stu-id="e4903-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Необходимые структуры для приложения Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="e4903-183">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="e4903-183">Figure 5.</span></span> <span data-ttu-id="e4903-184">Необходимые структуры для приложения Surface</span><span class="sxs-lookup"><span data-stu-id="e4903-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="e4903-185">Номера версий приложения Surface и необходимые структуры будут изменяться по мере обновления приложений.</span><span class="sxs-lookup"><span data-stu-id="e4903-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="e4903-186">Проверьте последнюю версию приложения Surface и каждой структуры в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4903-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="e4903-187">Всегда используйте приложение Surface и рекомендуемые версии структуры, предоставляемые Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4903-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="e4903-188">Использование устаревших или неправильных версий может привести к ошибкам или сбоям приложений.</span><span class="sxs-lookup"><span data-stu-id="e4903-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="e4903-189">Чтобы скачать необходимые для приложения Surface структуры, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e4903-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="e4903-190">Нажмите **кнопку** "Скачать" в **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="e4903-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="e4903-191">При этом загружается Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Appx-файл в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="e4903-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="e4903-192">Нажмите **кнопку** "Скачать" в **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.**</span><span class="sxs-lookup"><span data-stu-id="e4903-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="e4903-193">При этом Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="e4903-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="e4903-194">Для устройств Surface требуется только 64-битная (x64) версия каждой структуры.</span><span class="sxs-lookup"><span data-stu-id="e4903-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="e4903-195">Устройства Surface являются 64-битными устройствами UEFI и несовместимы с 32-битными (x86) версиями Windows, для чего требуются 32-битные структуры.</span><span class="sxs-lookup"><span data-stu-id="e4903-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="e4903-196">Установка приложения Surface на компьютере с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4903-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="e4903-197">Следующая процедура создает приложение Surface на компьютере и делает его доступным для всех учетных записей пользователей, созданных на компьютере после этого.</span><span class="sxs-lookup"><span data-stu-id="e4903-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="e4903-198">Используя процедуру, описанную в разделе этой статьи о загрузке приложения Surface из раздела учетной записи [Microsoft Store](#download-surface-app-from-a-microsoft-store-for-business-account) для бизнеса, скачайте приложение Surface AppxBundle и файл лицензии.</span><span class="sxs-lookup"><span data-stu-id="e4903-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="e4903-199">Запустите сеанс Windows PowerShell с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="e4903-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="e4903-200">Если вы не запустите PowerShell в качестве администратора, сеанс не будет иметь необходимых разрешений для установки приложения.</span><span class="sxs-lookup"><span data-stu-id="e4903-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="e4903-201">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="e4903-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="e4903-202">Где находится папка, в которой вы скачали AppxBundle и файл лицензии из учетной записи `<DownloadPath>` Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4903-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="e4903-203">Например, если вы скачали файлы в папку c:\Temp, вы запустите команду:</span><span class="sxs-lookup"><span data-stu-id="e4903-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="e4903-204">Приложение Surface теперь доступно на этом компьютере под управлением Windows.</span><span class="sxs-lookup"><span data-stu-id="e4903-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="e4903-205">Прежде чем приложение Surface будет работать на компьютере, на котором оно было установлено, необходимо также подготовку структур, описанных выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4903-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="e4903-206">Для предоставления этих структур используйте следующую процедуру в сеансе PowerShell с повышенными полномочиями, который использовался для предоставления приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="e4903-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="e4903-207">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="e4903-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="e4903-208">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="e4903-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="e4903-209">Установка приложения Surface с помощью MDT</span><span class="sxs-lookup"><span data-stu-id="e4903-209">Install Surface app with MDT</span></span>
<span data-ttu-id="e4903-210">Следующая процедура использует MDT для автоматизации установки приложения Surface во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="e4903-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="e4903-211">MDT автоматически предоставляет приложение во время развертывания и, таким образом, этот процесс можно применять к существующим образам.</span><span class="sxs-lookup"><span data-stu-id="e4903-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="e4903-212">Это рекомендуемый процесс развертывания приложения Surface в рамках развертывания Windows на устройствах Surface, так как он не снижает совместимость образа Windows на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="e4903-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="e4903-213">С помощью процедуры, описанной [выше в этой статье,](#download-surface-app-from-a-microsoft-store-for-business-account)скачайте приложение Surface AppxBundle и файл лицензии.</span><span class="sxs-lookup"><span data-stu-id="e4903-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="e4903-214">С помощью мастера нового приложения в MDT Deployment Workbench импортировать загруженные файлы в качестве нового приложения **с исходными файлами.**</span><span class="sxs-lookup"><span data-stu-id="e4903-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="e4903-215">На странице **"Сведения** о команде" мастера \*\*\*\* нового приложения укажите \*\*\*\* рабочий каталог по умолчанию, а для команды укажите имя файла AppxBundle следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4903-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="e4903-216">Команда:</span><span class="sxs-lookup"><span data-stu-id="e4903-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="e4903-217">Рабочий каталог: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="e4903-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="e4903-218">Для работы приложения Surface на целевом компьютере также потребуются описанные ранее в этой статье структуры.</span><span class="sxs-lookup"><span data-stu-id="e4903-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="e4903-219">Используйте следующую процедуру для импорта структур, необходимых для приложения Surface, в MDT и их настройки в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e4903-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="e4903-220">С помощью процедуры, описанной ранее в этой статье, скачайте файлы структуры.</span><span class="sxs-lookup"><span data-stu-id="e4903-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="e4903-221">Храните каждую структуру в отдельной папке.</span><span class="sxs-lookup"><span data-stu-id="e4903-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="e4903-222">С помощью мастера нового приложения в MDT Deployment Workbench импортировать загруженные файлы в качестве нового приложения **с исходными файлами.**</span><span class="sxs-lookup"><span data-stu-id="e4903-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="e4903-223">На странице **"Сведения о** команде" введите имя файла \*\*\*\* каждого приложения, загруженного в поле команд, и рабочий каталог по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e4903-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="e4903-224">Чтобы настроить структуры в качестве зависимостей приложения Surface, используйте этот процесс:</span><span class="sxs-lookup"><span data-stu-id="e4903-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="e4903-225">Откройте свойства приложения Surface в MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="e4903-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="e4903-226">Перейдите **на вкладку "Зависимости"** и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e4903-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="e4903-227">Поимяв имя, которое вы предоставили в мастере нового приложения, выберите для каждой из этих структур.</span><span class="sxs-lookup"><span data-stu-id="e4903-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="e4903-228">После импорта приложение Surface будет доступно для \*\*\*\* выбора на этапе приложений мастера развертывания Windows.</span><span class="sxs-lookup"><span data-stu-id="e4903-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="e4903-229">Можно также устанавливать приложение автоматически путем добавления его в последовательность задач развертывания следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4903-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="e4903-230">Откройте свою последовательность задач развертывания в MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="e4903-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="e4903-231">Добавьте новую задачу **Установить приложение** в разделе развертывания **Восстановление состояния**.</span><span class="sxs-lookup"><span data-stu-id="e4903-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="e4903-232">Выберите **"Установить одно приложение"** и укажите **Приложение Surface в** качестве **устанавливаемой программы.**</span><span class="sxs-lookup"><span data-stu-id="e4903-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="e4903-233">Дополнительные сведения о включании приложений в развертывания Windows см. в этой [набор средств.](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)</span><span class="sxs-lookup"><span data-stu-id="e4903-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
