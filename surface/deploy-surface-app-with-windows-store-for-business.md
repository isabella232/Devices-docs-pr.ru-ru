---
title: Развертывание приложения Surface с Microsoft Store для бизнеса или Microsoft Store для образования (Surface)
description: Узнайте, как добавить и скачать приложение Surface с Microsoft Store для бизнеса или Microsoft Store для образования, а также установить приложение Surface с PowerShell и MDT.
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
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576529"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a><span data-ttu-id="eb6d4-104">Развертывание приложения Surface с Microsoft Store для бизнеса и образованием</span><span class="sxs-lookup"><span data-stu-id="eb6d4-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="eb6d4-105">Относится к:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-105">Applies to</span></span>**

- <span data-ttu-id="eb6d4-106">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="eb6d4-106">Surface Laptop 4</span></span>
- <span data-ttu-id="eb6d4-107">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="eb6d4-107">Surface Pro 7+</span></span>
- <span data-ttu-id="eb6d4-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="eb6d4-108">Surface Laptop Go</span></span>
- <span data-ttu-id="eb6d4-109">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="eb6d4-109">Surface Pro 7</span></span>
- <span data-ttu-id="eb6d4-110">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="eb6d4-110">Surface Laptop 3</span></span>
- <span data-ttu-id="eb6d4-111">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="eb6d4-111">Surface Pro 6</span></span>
- <span data-ttu-id="eb6d4-112">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="eb6d4-112">Surface Laptop 2</span></span>
- <span data-ttu-id="eb6d4-113">Surface Go</span><span class="sxs-lookup"><span data-stu-id="eb6d4-113">Surface Go</span></span>
- <span data-ttu-id="eb6d4-114">Surface Go с LTE</span><span class="sxs-lookup"><span data-stu-id="eb6d4-114">Surface Go with LTE</span></span>
- <span data-ttu-id="eb6d4-115">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="eb6d4-115">Surface Book 2</span></span>
- <span data-ttu-id="eb6d4-116">Surface Pro с функцией LTE Advanced (модель 1807)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-116">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="eb6d4-117">Surface Pro (модель 1796)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-117">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="eb6d4-118">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="eb6d4-118">Surface Laptop</span></span>
- <span data-ttu-id="eb6d4-119">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="eb6d4-119">Surface Studio</span></span>
- <span data-ttu-id="eb6d4-120">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="eb6d4-120">Surface Studio 2</span></span>
- <span data-ttu-id="eb6d4-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="eb6d4-121">Surface Book</span></span>
- <span data-ttu-id="eb6d4-122">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="eb6d4-122">Surface Pro 4</span></span>
- <span data-ttu-id="eb6d4-123">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="eb6d4-123">Surface 3 LTE</span></span>
- <span data-ttu-id="eb6d4-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="eb6d4-124">Surface 3</span></span>
- <span data-ttu-id="eb6d4-125">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="eb6d4-125">Surface Pro 3</span></span>


<span data-ttu-id="eb6d4-126">Приложение Surface — это легкое Microsoft Store, которое обеспечивает управление многими настройками и опциями, в том числе:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-126">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="eb6d4-127">Включение и отключение кнопки Windows на устройстве Surface 
</span><span class="sxs-lookup"><span data-stu-id="eb6d4-127">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="eb6d4-128">Регулировка чувствительности ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="eb6d4-128">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="eb6d4-129">Настройка действий кнопки ручки Surface 
</span><span class="sxs-lookup"><span data-stu-id="eb6d4-129">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="eb6d4-130">Включение и отключение расширенных аудиофункций Surface 
</span><span class="sxs-lookup"><span data-stu-id="eb6d4-130">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="eb6d4-131">Быстрый доступ к документации и информации для поддержки устройства</span><span class="sxs-lookup"><span data-stu-id="eb6d4-131">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="eb6d4-132">Пользователи, использующие Windows Update, обычно получают приложение Surface в рамках автоматических обновлений.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-132">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="eb6d4-133">Но если ваша организация готовит изображения для развертывания на устройствах Surface, вы можете включить приложение Surface (ранее называемое Surface Hub) в процесс визуализации и развертывания, а не требовать от пользователей каждого отдельного устройства скачивать и устанавливать приложение из Microsoft Store или Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-133">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="eb6d4-134">Эта статья не применяется к Surface Pro X. Дополнительные сведения можно получить в [области развертывания, управления](surface-pro-arm-app-management.md) и обслуживания Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="eb6d4-134">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <a name="surface-app-overview"></a><span data-ttu-id="eb6d4-135">Обзор приложения Surface</span><span class="sxs-lookup"><span data-stu-id="eb6d4-135">Surface app overview</span></span>

<span data-ttu-id="eb6d4-136">Приложение Surface доступно в качестве бесплатной загрузки из [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-136">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="eb6d4-137">Пользователи могут скачать и установить его из Microsoft Store, но если ваша организация использует Microsoft Store для бизнеса вместо этого, вам потребуется добавить его в инвентарь вашего магазина и, возможно, включить приложение в Windows процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-137">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="eb6d4-138">Эти процессы обсуждаются в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-138">These processes are discussed throughout this article.</span></span> <span data-ttu-id="eb6d4-139">Дополнительные сведения о Microsoft Store для бизнеса см. [Microsoft Store для бизнеса](https://docs.microsoft.com/microsoft-store/) в Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-139">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a><span data-ttu-id="eb6d4-140">Добавление приложения Surface в Microsoft Store для бизнеса учетную запись</span><span class="sxs-lookup"><span data-stu-id="eb6d4-140">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="eb6d4-141">Прежде чем пользователи смогут установить или развернуть приложение из Microsoft Store для бизнеса учетной записи компании, необходимо сначала сделать желаемое приложение доступным и лицензироваться для пользователей бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-141">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="eb6d4-142">Если вы еще этого не сделали, создайте Microsoft Store для бизнеса [учетную запись.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-142">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="eb6d4-143">Войдите на портал.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-143">Log on to the portal.</span></span> 

3. <span data-ttu-id="eb6d4-144">Включить автономное лицензирование: **щелкните параметры Manage->Store,** а затем выберите приложение **Show offline licensed** для людей, которые будут делать покупки в почтовом ящике магазина, как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-144">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="eb6d4-145">Дополнительные сведения о Microsoft Store для бизнеса моделей лицензирования приложений см. в Microsoft Store для бизнеса [Apps in Microsoft Store для бизнеса education.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-145">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Показать автономные лицензии приложений-контрольных ящиков](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="eb6d4-147">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-147">Figure 1.</span></span> <span data-ttu-id="eb6d4-148">Включить приложения для автономного использования</span><span class="sxs-lookup"><span data-stu-id="eb6d4-148">Enable apps for offline use</span></span>*

4. <span data-ttu-id="eb6d4-149">Добавьте приложение Surface в свою Microsoft Store для бизнеса учетную запись, следуя этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-149">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="eb6d4-150">Щелкните **меню Магазин.**</span><span class="sxs-lookup"><span data-stu-id="eb6d4-150">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="eb6d4-151">В поле поиска введите **приложение Surface**и нажмите значок поиска.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-151">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="eb6d4-152">После того как приложение Surface будет представлено в результатах поиска, щелкните значок приложения.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-152">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="eb6d4-153">Вам будет представлен выбор (выберите **Online** или **Offline),** как показано на рисунке 2.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-153">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Выберите режим автономного лицензирования и добавьте приложение в инвентарь](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="eb6d4-155">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-155">Figure 2.</span></span> <span data-ttu-id="eb6d4-156">Выберите режим автономного лицензирования и добавьте приложение в инвентарь</span><span class="sxs-lookup"><span data-stu-id="eb6d4-156">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="eb6d4-157">Щелкните **автономный** режим, чтобы выбрать режим автономного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-157">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="eb6d4-158">Нажмите **кнопку Получить приложение,** чтобы добавить приложение в Microsoft Store для бизнеса инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-158">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="eb6d4-159">Как показано на рисунке 3, вы увидите диалоговое окно, которое подсказивает вам, что автономные приложения можно развернуть с помощью средства управления или загрузить со страницы инвентаризации компании в их частном магазине.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-159">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="eb6d4-160">Окно подтверждения приложения с автономной лицензией ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *На рисунке 3. Подтверждение приложения с автономной лицензией*</span><span class="sxs-lookup"><span data-stu-id="eb6d4-160">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="eb6d4-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-161">Click **OK**.</span></span>

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a><span data-ttu-id="eb6d4-162">Скачайте приложение Surface из Microsoft Store для бизнеса учетной записи</span><span class="sxs-lookup"><span data-stu-id="eb6d4-162">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="eb6d4-163">После добавления приложения в учетную запись Microsoft Store для бизнеса в автономном режиме вы можете скачать и добавить приложение в качестве AppxBundle в долю развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-163">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="eb6d4-164">Войдите в Microsoft Store для бизнеса учетную https://businessstore.microsoft.com запись.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-164">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="eb6d4-165">Нажмите **кнопку Управление >приложениями & программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-165">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="eb6d4-166">Отображается список всех приложений вашей компании, включая приложение Surface, добавленное в приложении [Add Surface](#add-surface-app-to-a-microsoft-store-for-business-account) в раздел Microsoft Store для бизнеса учетной записи этой статьи.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-166">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="eb6d4-167">В **статье Действия**нажмите ellipsis **(...),** а затем нажмите кнопку **Скачать** для автономного использования для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-167">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="eb6d4-168">Выберите нужные **параметры платформы** и **архитектуры** из доступных выборов для выбранного приложения, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-168">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Пример пакета AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="eb6d4-170">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-170">Figure 4.</span></span> <span data-ttu-id="eb6d4-171">Скачайте пакет AppxBundle для приложения</span><span class="sxs-lookup"><span data-stu-id="eb6d4-171">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="eb6d4-172">Нажмите **кнопку Скачать**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-172">Click **Download**.</span></span> <span data-ttu-id="eb6d4-173">Пакет AppxBundle будет загружен.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-173">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="eb6d4-174">Убедитесь, что вы обратите внимание на путь скачаного файла, так как это потребуется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-174">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="eb6d4-175">Щелкните либо **закодированную лицензию,** либо параметр **Unencoded license.**</span><span class="sxs-lookup"><span data-stu-id="eb6d4-175">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="eb6d4-176">Используйте параметр закодированной лицензии с помощью средств управления, таких как Microsoft Endpoint Configuration Manager или при Windows конструктора конфигурации для создания пакета подготовка.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-176">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="eb6d4-177">Выберите некодированную лицензию при использовании решений по обслуживанию и управлению изображениями развертывания (DISM) или развертывания на основе изображений, в том числе microsoft Deployment набор средств (MDT).</span><span class="sxs-lookup"><span data-stu-id="eb6d4-177">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="eb6d4-178">Щелкните **Создать,** чтобы создать и скачать лицензию для приложения.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-178">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="eb6d4-179">Убедитесь, что вы обратите внимание на путь файла лицензии, так как вам потребуется это позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-179">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="eb6d4-180">При загрузке приложения для автономного использования, например приложения Surface, вы можете заметить раздел в нижней части страницы с меткой **Required frameworks.**</span><span class="sxs-lookup"><span data-stu-id="eb6d4-180">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="eb6d4-181">На ваших целевых компьютерах должны быть установлены фреймворки, установленные для запуска приложения, поэтому может потребоваться повторить процесс загрузки для каждой из необходимых для вашей архитектуры рамок (x86 или x64), а также включить их в развертывание Windows, рассмотренного далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-181">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="eb6d4-182">На рисунке 5 показаны необходимые рамки для приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-182">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Необходимые рамки для приложения Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="eb6d4-184">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-184">Figure 5.</span></span> <span data-ttu-id="eb6d4-185">Необходимые рамки для приложения Surface</span><span class="sxs-lookup"><span data-stu-id="eb6d4-185">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="eb6d4-186">Номера версий приложения Surface и необходимые рамки будут изменяться по мере обновления приложений.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-186">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="eb6d4-187">Проверьте последнюю версию приложения Surface и каждую фреймворк в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-187">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="eb6d4-188">Всегда используйте приложение Surface и рекомендуемые версии фреймворка, как это предусмотрено Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-188">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="eb6d4-189">Использование устаревших фреймворков или неправильных версий может привести к ошибкам или сбоям приложения.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-189">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="eb6d4-190">Чтобы скачать необходимые рамки для приложения Surface, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-190">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="eb6d4-191">Нажмите кнопку **Скачать** **в Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-191">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="eb6d4-192">При этом загружается Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Файл Appx в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-192">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="eb6d4-193">Нажмите **кнопку Скачать** **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-193">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="eb6d4-194">При этом файл Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-194">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="eb6d4-195">Для устройств Surface требуется только 64-битная (x64) версия каждой фреймворка.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-195">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="eb6d4-196">Устройства Surface являются родными 64-битными устройствами UEFI и не совместимы с 32-битными (x86) версиями Windows, для чего потребуются 32-битные фреймворки.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-196">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <a name="install-surface-app-on-your-computer-with-powershell"></a><span data-ttu-id="eb6d4-197">Установка приложения Surface на компьютере с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb6d4-197">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="eb6d4-198">Следующая процедура содержит приложение Surface на компьютере и делает его доступным для любых учетных записей пользователей, созданных на компьютере после этого.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-198">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="eb6d4-199">Используя процедуру, описанную в разделе Как скачать приложение [Surface](#download-surface-app-from-a-microsoft-store-for-business-account) из раздела Microsoft Store для бизнеса учетной записи этой статьи, скачайте приложение Surface AppxBundle и файл лицензии.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="eb6d4-200">Запустите сеанс Windows PowerShell с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-200">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="eb6d4-201">Если вы не запустите PowerShell в качестве администратора, сеанс не будет иметь необходимых разрешений для установки приложения.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-201">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="eb6d4-202">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="eb6d4-202">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="eb6d4-203">Где находится папка, в которой вы скачали файл AppxBundle и лицензию из `<DownloadPath>` Microsoft Store для бизнеса учетной записи.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-203">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="eb6d4-204">Например, если вы скачали файлы в c:\Temp, вы запустите команду:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-204">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="eb6d4-205">Приложение Surface теперь доступно на этом компьютере под управлением Windows.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-205">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="eb6d4-206">Прежде чем приложение Surface будет работать на компьютере, на котором оно было предварительно, необходимо также укачить рамки, описанные ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-206">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="eb6d4-207">Для обеспечения этих рамок используйте следующую процедуру в сеансе PowerShell, который использовался для обеспечения приложения Surface.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-207">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="eb6d4-208">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="eb6d4-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="eb6d4-209">В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: </span><span class="sxs-lookup"><span data-stu-id="eb6d4-209">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a><span data-ttu-id="eb6d4-210">Установка приложения Surface с помощью MDT</span><span class="sxs-lookup"><span data-stu-id="eb6d4-210">Install Surface app with MDT</span></span>
<span data-ttu-id="eb6d4-211">Следующая процедура использует MDT для автоматизации установки приложения Surface во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-211">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="eb6d4-212">MDT автоматически предоставляет приложение во время развертывания и, таким образом, этот процесс можно применять к существующим образам.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-212">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="eb6d4-213">Это рекомендуемый процесс развертывания приложения Surface в рамках развертывания Windows на устройствах Surface, так как это не снижает совместимость Windows платформы.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-213">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="eb6d4-214">С помощью процедуры, описанной [ранее в этой статье,](#download-surface-app-from-a-microsoft-store-for-business-account)скачайте приложение Surface AppxBundle и файл лицензии.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-214">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="eb6d4-215">Используя мастер нового приложения в workbench развертывания MDT, импортировать загруженные файлы в качестве нового приложения **с исходными файлами**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-215">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="eb6d4-216">На странице **Командные** сведения мастера нового приложения \*\*\*\* укажите рабочий \*\*\*\* каталог по умолчанию, а для команды укажите имя файла AppxBundle следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-216">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="eb6d4-217">Команда:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-217">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="eb6d4-218">Рабочий каталог: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="eb6d4-218">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="eb6d4-219">Чтобы приложение Surface функционировал на целевом компьютере, ему также потребуются рамки, описанные ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-219">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="eb6d4-220">Используйте следующую процедуру для импорта структур, необходимых для приложения Surface, в MDT и настройки их в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-220">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="eb6d4-221">С помощью процедуры, описанной ранее в этой статье, скачайте файлы фреймворка.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-221">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="eb6d4-222">Храните каждую фреймворк в отдельной папке.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-222">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="eb6d4-223">Используя мастер нового приложения в workbench развертывания MDT, импортировать загруженные файлы в качестве нового приложения **с исходными файлами**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-223">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="eb6d4-224">На странице **Командные сведения** введите имя файла каждого приложения, скачаного в поле **Команд,** и рабочий каталог по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-224">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="eb6d4-225">Чтобы настроить фреймворки как зависимости приложения Surface, используйте этот процесс:</span><span class="sxs-lookup"><span data-stu-id="eb6d4-225">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="eb6d4-226">Откройте свойства приложения Surface в workbench развертывания MDT.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-226">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="eb6d4-227">Щелкните **вкладку Зависимостей** и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-227">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="eb6d4-228">Выберите контрольный ящик для каждой структуры с помощью имени, которое вы предоставили в мастере нового приложения.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-228">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="eb6d4-229">После импорта приложение Surface будет доступно для выбора в шаге **Приложения** мастера Windows развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-229">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="eb6d4-230">Можно также устанавливать приложение автоматически путем добавления его в последовательность задач развертывания следующим образом.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-230">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="eb6d4-231">Откройте свою последовательность задач развертывания в MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-231">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="eb6d4-232">Добавьте новую задачу **Установить приложение** в разделе развертывания **Восстановление состояния**.</span><span class="sxs-lookup"><span data-stu-id="eb6d4-232">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="eb6d4-233">Выберите **Установите одно приложение и** укажите Surface **App** в **качестве установленного приложения.**</span><span class="sxs-lookup"><span data-stu-id="eb6d4-233">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="eb6d4-234">Дополнительные сведения о в том числе приложениях в Windows развертывания см. в Windows 10 с microsoft [Deployment набор средств.](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)</span><span class="sxs-lookup"><span data-stu-id="eb6d4-234">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
