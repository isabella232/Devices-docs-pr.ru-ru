---
title: Управление обновлениями драйвера Surface в Configuration Manager
description: В этой статье описаны доступные параметры для управления и развертывания микропрограмм и обновлений драйверов для устройств Surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, встроенное ПО, обновление, устройство, управление, развертывание, драйвер, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835867"
---
# <span data-ttu-id="87c51-104">Управление обновлениями драйвера Surface в Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87c51-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="87c51-105">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="87c51-105">Summary</span></span>

<span data-ttu-id="87c51-106">Начиная с [Microsoft System Center Configuration Manager версии 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), вы можете выполнять синхронизацию и развертывание встроенного по и обновлений для Surface (Майкрософт) прямо через клиент Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="87c51-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="87c51-107">Процесс напоминает развертывание регулярных обновлений.</span><span class="sxs-lookup"><span data-stu-id="87c51-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="87c51-108">Однако некоторые дополнительные конфигурации необходимы для получения обновлений драйвера Surface в каталог.</span><span class="sxs-lookup"><span data-stu-id="87c51-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="87c51-109">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="87c51-109">Prerequisites</span></span>

<span data-ttu-id="87c51-110">Для управления обновлениями драйверов Surface должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="87c51-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="87c51-111">Необходимо использовать Configuration Manager версии 1710 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="87c51-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="87c51-112">Все точки обновления программного обеспечения (SUPs) должны работать под управлением Windows Server 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="87c51-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="87c51-113">В противном случае Configuration Manager не пропустит этот параметр и драйверы Surface не будут синхронизироваться.</span><span class="sxs-lookup"><span data-stu-id="87c51-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="87c51-114">Если ваша среда не отвечает требованиям, ознакомьтесь с [альтернативными методами](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) для развертывания драйверов Surface и обновлений микропрограмм в разделе " [вопросы и ответы](#frequently-asked-questions-faq) ".</span><span class="sxs-lookup"><span data-stu-id="87c51-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="87c51-115">Полезные файлы журнала</span><span class="sxs-lookup"><span data-stu-id="87c51-115">Useful log files</span></span>

<span data-ttu-id="87c51-116">Следующие журналы особенно полезны при управлении обновлениями драйверов Surface.</span><span class="sxs-lookup"><span data-stu-id="87c51-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="87c51-117">Имя журнала</span><span class="sxs-lookup"><span data-stu-id="87c51-117">Log name</span></span>|<span data-ttu-id="87c51-118">Описание</span><span class="sxs-lookup"><span data-stu-id="87c51-118">Description</span></span>|
|---|---|
|<span data-ttu-id="87c51-119">WCM. log</span><span class="sxs-lookup"><span data-stu-id="87c51-119">WCM.log</span></span>|<span data-ttu-id="87c51-120">Записывает сведения о настройке точки обновления программного обеспечения и подключения к серверу WSUS для подписок на обновления, классификаций и языков.</span><span class="sxs-lookup"><span data-stu-id="87c51-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="87c51-121">WsyncMgr. log</span><span class="sxs-lookup"><span data-stu-id="87c51-121">WsyncMgr.log</span></span>|<span data-ttu-id="87c51-122">Записываются сведения о процессе синхронизации обновлений программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="87c51-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="87c51-123">Эти журналы находятся на сервере сайта, который управляет SUPм, или на самом SUP, если он установлен непосредственно на сервере сайта.</span><span class="sxs-lookup"><span data-stu-id="87c51-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="87c51-124">Полный список журналов Configuration Manager можно найти [в разделе файлы журнала в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="87c51-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="87c51-125">Включение управления обновлениями драйверов Surface</span><span class="sxs-lookup"><span data-stu-id="87c51-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="87c51-126">Чтобы включить управление обновлениями драйверов Surface в диспетчере конфигураций, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="87c51-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="87c51-127">На консоли Configuration Manager перейдите на сайт " **Administration**  >  **Общие сведения об**администрировании сайтов"  >  **Site Configuration**  >  **Sites**.</span><span class="sxs-lookup"><span data-stu-id="87c51-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="87c51-128">Выберите сайт, содержащий сервер SUP верхнего уровня для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="87c51-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="87c51-129">На ленте выберите пункт **Настройка компонентов сайта**, а затем — **пункт Обновление программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="87c51-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="87c51-130">Либо щелкните сайт правой кнопкой мыши и выберите пункт **Настройка**  >  **точки обновления программного обеспечения**для компонентов сайта.</span><span class="sxs-lookup"><span data-stu-id="87c51-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="87c51-131">На вкладке **классификации** установите флажок **включить драйверы Microsoft Surface Driver и обновления встроенного по** .</span><span class="sxs-lookup"><span data-stu-id="87c51-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![Свойства компонента точки обновления программного обеспечения](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="87c51-133">При появлении следующего сообщения с предупреждением нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="87c51-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Configuration Manager;](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="87c51-135">На вкладке продукты выберите продукты, которые вы хотите обновить, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="87c51-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="87c51-136">Большинство факторов относятся к следующим группам продуктов:</span><span class="sxs-lookup"><span data-stu-id="87c51-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="87c51-137">Драйверы Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="87c51-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="87c51-138">Драйверы обслуживания & обновления для Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="87c51-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-139">Годовщина Windows 10 и более поздние версии драйверов обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-140">Обновления и более поздние версии драйверов для Windows 10 & обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-141">Windows 10 — создатели обновлений и более поздних версий драйверов обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-142">Обновления Windows 10 для дизайнеров и более поздних версий & драйверов обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-143">Обновления Windows 10 и более поздние версии драйверов обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-144">Обновление и более поздние версии драйверов для Windows 10 & обслуживания</span><span class="sxs-lookup"><span data-stu-id="87c51-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-145">Драйверы обслуживания Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="87c51-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="87c51-146">Драйверы Windows 10 S версии 1709 и более поздних версий для тестирования</span><span class="sxs-lookup"><span data-stu-id="87c51-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="87c51-147">Windows 10 S версии 1709 и более поздних версий & обслуживание драйверов для тестирования</span><span class="sxs-lookup"><span data-stu-id="87c51-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="87c51-148">Большинство драйверов Surface относятся к нескольким группам продуктов Windows 10.</span><span class="sxs-lookup"><span data-stu-id="87c51-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="87c51-149">Возможно, вам не придется выделять все продукты, которые перечислены здесь.</span><span class="sxs-lookup"><span data-stu-id="87c51-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="87c51-150">Чтобы уменьшить количество продуктов, которые заполняют каталог обновлений, мы рекомендуем выбирать только те продукты, которые необходимы вашей среде для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="87c51-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="87c51-151">Проверка конфигурации</span><span class="sxs-lookup"><span data-stu-id="87c51-151">Verifying the configuration</span></span>

<span data-ttu-id="87c51-152">Чтобы убедиться в правильности настройки SUP, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="87c51-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="87c51-153">Откройте WsyncMgr. log и найдите следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="87c51-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="87c51-154">Если в WsyncMgr. log записано какое – либо из указанных ниже записей, повторно проверьте шаг 4 в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="87c51-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="87c51-155">Откройте средство WCM. log и найдите запись, похожую на приведенную ниже.</span><span class="sxs-lookup"><span data-stu-id="87c51-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![Параметры WCM. log](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="87c51-157">Этот элемент является элементом XML, в котором перечислены все группы продуктов и классификация, синхронизированные в настоящее время с помощью сервера SUP.</span><span class="sxs-lookup"><span data-stu-id="87c51-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="87c51-158">Например, вы можете увидеть запись, которая похожа на приведенную ниже.</span><span class="sxs-lookup"><span data-stu-id="87c51-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="87c51-159">Если вы не можете найти продукты, которые вы выбрали на шаге 6 в предыдущем разделе, проверьте, не сохраняются ли параметры SUP.</span><span class="sxs-lookup"><span data-stu-id="87c51-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="87c51-160">Вы также можете подождать, пока завершится следующая синхронизация, а затем проверить, указаны ли обновления для драйвера Surface и микропрограмм в разделе обновления программного обеспечения на консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="87c51-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="87c51-161">Например, консоль может отобразить следующие данные:</span><span class="sxs-lookup"><span data-stu-id="87c51-161">For example, the console might display the following information:</span></span>

   ![Все результаты поиска обновлений программного обеспечения](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="87c51-163">Синхронизация вручную</span><span class="sxs-lookup"><span data-stu-id="87c51-163">Manual synchronization</span></span>

<span data-ttu-id="87c51-164">Если вы не хотите ждать следующей синхронизации, выполните указанные ниже действия, чтобы начать синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="87c51-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="87c51-165">На консоли Configuration Manager перейдите в раздел Обзор **библиотеки программного**обеспечения, в котором выводятся  >  **Overview**  >  **обновленные**  >  **обновления программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="87c51-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="87c51-166">На ленте выберите **синхронизировать обновления программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="87c51-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="87c51-167">Или щелкните правой кнопкой мыши **Обновление программного обеспечения**, а затем выберите команду **синхронизировать обновление программного обеспечения**.</span><span class="sxs-lookup"><span data-stu-id="87c51-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="87c51-168">Отслеживайте ход выполнения синхронизации, выполнив поиск по следующим записям в WsyncMgr. log:</span><span class="sxs-lookup"><span data-stu-id="87c51-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <span data-ttu-id="87c51-169">Развертывание микропрограммы и обновлений драйверов Surface</span><span class="sxs-lookup"><span data-stu-id="87c51-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="87c51-170">Встроенное по и обновления драйверов можно развертывать так же, как и при развертывании других обновлений.</span><span class="sxs-lookup"><span data-stu-id="87c51-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="87c51-171">Дополнительные сведения о развертывании можно найти в статье [System Center 2012 Configuration Manager – part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span><span class="sxs-lookup"><span data-stu-id="87c51-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="87c51-172">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="87c51-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="87c51-173">После выполнения действий, описанных в этой статье, видеодрайверы Surfaces по-прежнему не синхронизируются.</span><span class="sxs-lookup"><span data-stu-id="87c51-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="87c51-174">Почему?</span><span class="sxs-lookup"><span data-stu-id="87c51-174">Why?</span></span>**

<span data-ttu-id="87c51-175">Если вы синхронизируются с вышестоящим сервером Windows Server Update Services (WSUS) вместо центра обновления Майкрософт, убедитесь в том, что вышестоящий WSUS-сервер настроен таким, чтобы он поддерживал и синхронизировались обновления драйверов Surface.</span><span class="sxs-lookup"><span data-stu-id="87c51-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="87c51-176">Все подчиненные серверы ограничены обновлениями, которые присутствуют в базе данных вышестоящего сервера WSUS.</span><span class="sxs-lookup"><span data-stu-id="87c51-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="87c51-177">В WSUS более 68 000 обновлений, которые классифицируются как драйверы.</span><span class="sxs-lookup"><span data-stu-id="87c51-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="87c51-178">Чтобы предотвратить синхронизацию драйверов, не связанных с Surface, с помощью Configuration Manager, Microsoft фильтрует синхронизацию драйверов с разрешающим списком.</span><span class="sxs-lookup"><span data-stu-id="87c51-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="87c51-179">После публикации и включения нового списка разрешенных в Configuration Manager новые драйверы добавляются на консоль после следующей синхронизации.</span><span class="sxs-lookup"><span data-stu-id="87c51-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="87c51-180">Корпорация Майкрософт стремится получить драйверы Surface, добавленные в список разрешений ежемесячно с помощью обновления, чтобы сделать их доступными для синхронизации с Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="87c51-180">Microsoft aims to get the Surface drivers added to the allow list each month in line with Patch Tuesday to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="87c51-181">Если ваша среда Configuration Manager находится в автономном режиме, каждый раз при импорте обновлений для [обслуживания](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) в Configuration Manager будет импортироваться новый список разрешений.</span><span class="sxs-lookup"><span data-stu-id="87c51-181">If your Configuration Manager environment is offline, a new allow list is imported every time you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="87c51-182">Кроме того, вы должны импортировать [новый каталог WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) , содержащий драйверы, прежде чем они будут отображаться в консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="87c51-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="87c51-183">Так как в автономной среде WSUS есть больше драйверов, чем SUP Configuration Manager, мы рекомендуем установить среду Configuration Manager, в которой есть возможности Online, и настроить ее для синхронизации драйверов Surface.</span><span class="sxs-lookup"><span data-stu-id="87c51-183">Because a stand-alone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="87c51-184">Это обеспечивает меньший экспорт WSUS, похожий на автономную среду.</span><span class="sxs-lookup"><span data-stu-id="87c51-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="87c51-185">Если ваша среда Configuration Manager находится в сети и может определять новые обновления, вы будете получать обновления списка автоматически.</span><span class="sxs-lookup"><span data-stu-id="87c51-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="87c51-186">Если вы не видите ожидаемых драйверов, ознакомьтесь с разработкой WCM. log и WsyncMgr. log на предмет ошибок синхронизации.</span><span class="sxs-lookup"><span data-stu-id="87c51-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log for any synchronization failures.</span></span>

**<span data-ttu-id="87c51-187">Моя среда Configuration Manager находится в автономном режиме, можно ли вручную импортировать драйверы Surfaces в WSUS?</span><span class="sxs-lookup"><span data-stu-id="87c51-187">My Configuration Manager environment is offline, can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="87c51-188">Нет.</span><span class="sxs-lookup"><span data-stu-id="87c51-188">No.</span></span> <span data-ttu-id="87c51-189">Несмотря на то, что обновление будет импортировано в WSUS, оно не будет импортировано на консоль Configuration Manager для развертывания, если оно не указано в списке разрешений.</span><span class="sxs-lookup"><span data-stu-id="87c51-189">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="87c51-190">Для импорта обновлений для обслуживания в Configuration Manager необходимо использовать [средство подключения служб](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) , чтобы обновить список разрешений.</span><span class="sxs-lookup"><span data-stu-id="87c51-190">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="87c51-191">Какие альтернативные методы необходимо для развертывания драйверов Surface и обновлений микропрограмм?</span><span class="sxs-lookup"><span data-stu-id="87c51-191">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="87c51-192">Сведения о том, как развертывать драйверы Surface и обновления встроенного по с помощью альтернативных каналов, можно найти в разделе [Управление обновлениями Surface Driver и микропрограмм](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="87c51-192">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span></span> <span data-ttu-id="87c51-193">Если вы хотите скачать MSI-или exe-файл, а затем развернуть его через традиционные каналы развертывания программного обеспечения, ознакомьтесь со сведениями о том, как [обновить встроенное по в Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="87c51-193">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="87c51-194">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="87c51-194">Additional Information</span></span>

<span data-ttu-id="87c51-195">Дополнительные сведения об обновлениях драйверов и микропрограмм Surface можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="87c51-195">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="87c51-196">Скачивание последних версий встроенного ПО и драйверов для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="87c51-196">Download the latest firmware and drivers for Surface devices</span></span>](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [<span data-ttu-id="87c51-197">Управление обновлениями драйверов и встроенного ПО Surface</span><span class="sxs-lookup"><span data-stu-id="87c51-197">Manage Surface driver and firmware updates</span></span>](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [<span data-ttu-id="87c51-198">Рекомендации для Surface и System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87c51-198">Considerations for Surface and System Center Configuration Manager</span></span>](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)
