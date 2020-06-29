---
title: Настройка запуска при первом включении в случае развертывания Surface
description: В этой статье описана процедура настройки параметров Surface, которые будут действовать при первом запуске устройства конечными пользователями в вашей организации.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: развертывание, настройка, автоматизация, сеть, ручка, связывание, загрузка
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835667"
---
# <span data-ttu-id="9c84b-104">Настройка запуска при первом включении в случае развертывания Surface</span><span class="sxs-lookup"><span data-stu-id="9c84b-104">Customize the OOBE for Surface deployments</span></span>

<span data-ttu-id="9c84b-105">В этой статье описана настройка функции "поверхность" для конечных пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="9c84b-105">This article describes customizing the Surface out-of-box experience for end users in your organization.</span></span>

<span data-ttu-id="9c84b-106">При развертывании Windows распространенной практикой является настройка параметров первого запуска компьютеров, на которых выполняется развертывание. Эту процедуру также называют OOBE.</span><span class="sxs-lookup"><span data-stu-id="9c84b-106">It is common practice in a Windows deployment to customize the user experience for the first startup of deployed computers — the out-of-box experience, or OOBE.</span></span>

>[!NOTE]
><span data-ttu-id="9c84b-107">Термин OOBE также часто используется для обозначения стадии или этапа настройки Windows, в ходе которого происходит взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="9c84b-107">OOBE is also often used to describe the phase, or configuration pass, of Windows setup during which the user experience is displayed.</span></span> <span data-ttu-id="9c84b-108">Дополнительные сведения об этапе OOBE в процедуре настройки см. в разделе [Как работают этапы настройки](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c84b-108">For more information about the OOBE phase of setup, see [How Configuration Passes Work](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).</span></span>

<span data-ttu-id="9c84b-109">В некоторых случаях может потребоваться обеспечение полной автоматизации, чтобы добиться готовности компьютеров к использованию после развертывания без какого-либо взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="9c84b-109">In some scenarios, you may want to provide complete automation to ensure that at the end of a deployment, computers are ready for use without any interaction from the user.</span></span> <span data-ttu-id="9c84b-110">В других случаях будет удобнее, если пользователи сами предпримут необходимые действия или выберут важные параметры для настройки основных пользовательских функций.</span><span class="sxs-lookup"><span data-stu-id="9c84b-110">In other scenarios, you may want to leave key elements of the experience for users to perform necessary actions or select between important choices.</span></span> <span data-ttu-id="9c84b-111">Для администраторов, занимающихся развертыванием устройств Surface, все эти случаи представляют собой уникальную задачу, требующую решения.</span><span class="sxs-lookup"><span data-stu-id="9c84b-111">For administrators deploying to Surface devices, each of these scenarios presents a unique challenge to overcome.</span></span>

> [!NOTE]
> <span data-ttu-id="9c84b-112">Эта статья не относится к Surface Pro X. Дополнительные сведения можно найти в разделе [развертывание, управление и обслуживание Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="9c84b-112">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

<span data-ttu-id="9c84b-113">В этой статье приводится обзор сценариев, в которых развертывание может потребовать дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="9c84b-113">This article provides a summary of the scenarios where a deployment might require additional steps.</span></span> <span data-ttu-id="9c84b-114">Здесь также приводится информация, необходимая для обеспечения того, чтобы на каждом разворачиваемом устройстве Surface пользователь проходил необходимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9c84b-114">It also provides the required information to ensure that the desired experience is achieved on any newly deployed Surface device.</span></span> <span data-ttu-id="9c84b-115">Эта статья предназначена для администраторов, знакомых с процессом развертывания, а также с такими понятиями, как файлы ответов и [эталонные образы](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).</span><span class="sxs-lookup"><span data-stu-id="9c84b-115">This article is intended for administrators who are familiar with the deployment process, as well as concepts such as answer files and [reference images](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).</span></span>

>[!NOTE]
><span data-ttu-id="9c84b-116">Несмотря на то что этап настройки OOBE по-прежнему запускается во время развертывания с помощью решения для автоматического развертывания, такого как [Microsoft Deployment Toolkit (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) или Microsoft Endpoint Configuration Manager (OSD), оно автоматически обновляется параметрами, заданными в мастере развертывания и последовательности задач.</span><span class="sxs-lookup"><span data-stu-id="9c84b-116">Although the OOBE phase of setup is still run during a deployment with an automated deployment solution such as the [Microsoft Deployment Toolkit (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) or Microsoft Endpoint Configuration Manager Operating System Deployment (OSD), it is automated by the settings supplied in the Deployment Wizard and task sequence.</span></span> <span data-ttu-id="9c84b-117">Подробную информацию см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9c84b-117">For more information see:</span></span><br/>
>- [<span data-ttu-id="9c84b-118">Развертывание Windows 10 с помощью Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="9c84b-118">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [<span data-ttu-id="9c84b-119">Развертывание Windows 10 с помощью System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9c84b-119">Deploy Windows 10 with System Center 2012 R2 Configuration Manager</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

## <span data-ttu-id="9c84b-120">Сценарий 1: доступ к беспроводной сети во время запуска при первом включении с помощью MDT 2013</span><span class="sxs-lookup"><span data-stu-id="9c84b-120">Scenario 1: Wireless networking in OOBE with MDT 2013</span></span>


<span data-ttu-id="9c84b-121">Если во время запуска при первом включении доступен адаптер беспроводной сети, отобразится страница **Присоединиться к беспроводной сети**, которая предлагает пользователю подключиться к беспроводной сети.</span><span class="sxs-lookup"><span data-stu-id="9c84b-121">When a wireless network adapter is present during OOBE, the **Join a wireless network** page is displayed, which prompts a user to connect to a wireless network.</span></span> <span data-ttu-id="9c84b-122">Эта страница не скрывается автоматически технологиями развертывания, включая MDT 2013, и, соответственно, будет отображаться, даже если развертывание настроено на полную автоматизацию.</span><span class="sxs-lookup"><span data-stu-id="9c84b-122">This page is not automatically hidden by deployment technologies, including MDT 2013, and therefore will be displayed even when a deployment is configured for complete automation.</span></span>

<span data-ttu-id="9c84b-123">Для предотвращения остановки автоматического развертывания этой страницей необходимо скрыть эту страницу, настроив дополнительный параметр в файле ответов — **HideWirelessSetupInOOBE**.</span><span class="sxs-lookup"><span data-stu-id="9c84b-123">To ensure that an automated deployment is not stopped by this page, the page must be hidden by configuring an additional setting in the answer file, **HideWirelessSetupInOOBE**.</span></span> <span data-ttu-id="9c84b-124">Дополнительные сведения о параметре **HideWirelessSetupInOOBE** можно найти в [справочнике по автоматической установке Windows](https://technet.microsoft.com/library/ff716213.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c84b-124">You can find additional information about the **HideWirelessSetupInOOBE** setting in [Unattended Windows Setup Reference](https://technet.microsoft.com/library/ff716213.aspx).</span></span>

## <span data-ttu-id="9c84b-125">Сценарий 2: связывание ручки Surface во время запуска при первом включении</span><span class="sxs-lookup"><span data-stu-id="9c84b-125">Scenario 2: Surface Pen pairing in OOBE</span></span>


<span data-ttu-id="9c84b-126">При первом знакомстве с устройством Surface Pro 3, Surface Pro 4, Surface Book или Surface Studio после его распаковки во время запуска заводской образ предлагает пользователю связать входящую в комплект ручку Surface с устройством.</span><span class="sxs-lookup"><span data-stu-id="9c84b-126">When you first take a Surface Pro 3, Surface Pro 4, Surface Book, or Surface Studio out of the package and start it up, the first-run experience of the factory image includes a prompt that asks you to pair the included Surface Pen to the device.</span></span> <span data-ttu-id="9c84b-127">Этот запрос содержится только в заводском образе, поставляемом вместе с устройством, и не включен в другие образы, используемые для развертывания, например в установочный комплект Windows Корпоративная, который можно скачать с сайта Volume Licensing Service Center.</span><span class="sxs-lookup"><span data-stu-id="9c84b-127">This prompt is only provided by the factory image that ships with the device and is not included in other images used for deployment, such as the Windows Enterprise installation media downloaded from the Volume Licensing Service Center.</span></span> <span data-ttu-id="9c84b-128">Так как для связывания ручки Surface через Bluetooth при последующих запусках требуется открыть панель управления или параметры компьютера и вручную связать устройство Bluetooth, возможно, вам будет удобно, если пользователи или обслуживающий персонал смогут использовать данную процедуру для связывания.</span><span class="sxs-lookup"><span data-stu-id="9c84b-128">Because pairing the Bluetooth Surface Pen outside of this experience requires that you enter the Control Panel or PC Settings and manually pair a Bluetooth device, you may want to have users or a technician use this prompt to perform the pairing operation.</span></span>

<span data-ttu-id="9c84b-129">Для применения заводской процедуры подключения ручки Surface в ходе запуска при первом включении необходимо скопировать 4 файла из заводского образа Surface в эталонный образ.</span><span class="sxs-lookup"><span data-stu-id="9c84b-129">To provide the factory Surface Pen pairing experience in OOBE, you must copy four files from the factory Surface image into the reference image.</span></span> <span data-ttu-id="9c84b-130">Чтобы подключить образ, вы можете скопировать эти файлы в эталонную среду перед записью эталонного образа либо добавить позже с помощью системы обслуживания образов развертывания и управления ими (DISM).</span><span class="sxs-lookup"><span data-stu-id="9c84b-130">You can copy these files into the reference environment before you capture the reference image, or you can add them later by using Deployment Image Servicing and Management (DISM) to mount the image.</span></span> <span data-ttu-id="9c84b-131">Необходимы вот эти четыре файла:</span><span class="sxs-lookup"><span data-stu-id="9c84b-131">The four required files are:</span></span>

-   <span data-ttu-id="9c84b-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span><span class="sxs-lookup"><span data-stu-id="9c84b-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span></span>
-   <span data-ttu-id="9c84b-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="9c84b-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span></span>
-   <span data-ttu-id="9c84b-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="9c84b-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span></span>
-   <span data-ttu-id="9c84b-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="9c84b-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span></span>

>[!NOTE]
><span data-ttu-id="9c84b-136">Скопируйте файлы из заводского образа для той же модели устройства Surface, на которой планируется провести развертывание.</span><span class="sxs-lookup"><span data-stu-id="9c84b-136">You should copy the files from a factory image for the same model Surface device that you intend to deploy to.</span></span> <span data-ttu-id="9c84b-137">Например, вы должны использовать файлы из Surface Pro 7 для развертывания на Surface Pro 7, а файлы из Surface Book 2 — для развертывания Surface Book 2, но не следует использовать файлы из Surface Pro 7 для развертывания Surface Book или Surface Pro 6.</span><span class="sxs-lookup"><span data-stu-id="9c84b-137">For example, you should use the files from a Surface Pro 7 to deploy to Surface Pro 7, and the files from Surface Book 2 to deploy Surface Book 2, but you should not use the files from a Surface Pro 7 to deploy Surface Book or Surface Pro 6.</span></span>

 

<span data-ttu-id="9c84b-138">Пошаговые инструкции по добавлению этих файлов в образ приведены в статье [Советы по развертыванию Surface Pro 3, касающиеся ручки Surface и OneNote](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/).</span><span class="sxs-lookup"><span data-stu-id="9c84b-138">The step-by-step process for adding these required files to an image is described in [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/).</span></span> <span data-ttu-id="9c84b-139">Эта запись в блоге также включает советы по обеспечению установки необходимых обновлений для функции составления быстрых заметок с помощью ручки Surface, которая позволяет пользователям одним нажатием отправлять заметки в OneNote.</span><span class="sxs-lookup"><span data-stu-id="9c84b-139">This blog post also includes tips to ensure that the necessary updates for the Surface Pen Quick Note-Taking Experience are installed, which allows users to send notes to OneNote with a single click.</span></span>

 

 





