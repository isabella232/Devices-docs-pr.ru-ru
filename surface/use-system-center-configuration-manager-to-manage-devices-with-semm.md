---
title: Использование диспетчера конфигураций конечных точек Microsoft для управления устройствами с помощью SEMM (Surface)
description: Сведения об управлении корпоративным режимом Microsoft Surface Management (SEMM) с диспетчером конфигурации конечной точки.
keywords: регистрация, обновление, сценарии, параметры
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: bba99d202d5d0dc5085c454202ae9a95df56109c
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835523"
---
# <span data-ttu-id="0b42c-104">Использование диспетчера конфигураций конечных точек Microsoft для управления устройствами с помощью SEMM</span><span class="sxs-lookup"><span data-stu-id="0b42c-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="0b42c-105">Функция режима корпоративного управления Surface (SEMM) для устройств UEFI Surface позволяет администраторам управлять конфигурацией параметров UEFI Surface и помогать им в защите.</span><span class="sxs-lookup"><span data-stu-id="0b42c-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="0b42c-106">Для большинства организаций этот процесс выполняется путем создания пакетов установщика Windows (MSI) с помощью средства конфигуратора UEFI Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="0b42c-107">Эти пакеты затем выполняются или развертываются на клиентских устройствах Surface для регистрации устройств в SEMM и обновления конфигурации параметров UEFI Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="0b42c-108">Для организаций, использующих диспетчер конфигураций конечных точек Microsoft, вы можете использовать процесс конфигуратора UEFI Microsoft Surface. msi для развертывания и администрирования SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="0b42c-109">Microsoft Surface UEFI Manager — это упрощенная программа установки, которая делает необходимые сборки для управления SEMM доступными на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0b42c-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="0b42c-110">Установив эти сборки с помощью Microsoft Surface UEFI Manager на управляемом клиенте, SEMM можно администрировать в Configuration Manager с помощью сценариев PowerShell, развернутых в качестве приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="0b42c-111">Благодаря этому процессу управление SEMM выполняется в Configuration Manager, что устраняет необходимость в использовании внешней программы конфигуратора UEFI Surface (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="0b42c-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="0b42c-112">Несмотря на то, что описанный в этой статье процесс может работать с более ранними версиями диспетчера конфигураций конечных точек или с другими решениями для управления сторонними компаниями, управление SEMM с помощью Microsoft Surface UEFI Manager и PowerShell поддерживается только в текущей ветви диспетчера конфигураций конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0b42c-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="0b42c-113">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="0b42c-113">Prerequisites</span></span>

<span data-ttu-id="0b42c-114">Перед началом процесса, описанным в этой статье, ознакомьтесь с приведенными ниже технологиями и инструментами.</span><span class="sxs-lookup"><span data-stu-id="0b42c-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="0b42c-115">UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="0b42c-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="0b42c-116">Surface Enterprise Management Mode (SEMM)</span><span class="sxs-lookup"><span data-stu-id="0b42c-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="0b42c-117">Сценарии PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b42c-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="0b42c-118">Развертывание приложения System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0b42c-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="0b42c-119">Управление сертификатами</span><span class="sxs-lookup"><span data-stu-id="0b42c-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="0b42c-120">Вам понадобится также доступ к сертификату, который вы хотите использовать для защиты SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="0b42c-121">Сведения о требованиях для этого сертификата можно найти в разделе [требования к сертификату режима управления предприятием в Surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="0b42c-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="0b42c-122">Очень важно, чтобы этот сертификат хранился в безопасном месте и был правильно сохранен в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="0b42c-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="0b42c-123">Если этот сертификат теряется или не годен для использования, невозможно сбросить UEFI Surface, изменить параметры UEFI управляемой поверхности или удалить SEMM с устройства, на котором зарегистрирована поверхность.</span><span class="sxs-lookup"><span data-stu-id="0b42c-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="0b42c-124">Скачать Диспетчер UEFI Surface (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0b42c-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="0b42c-125">Для управления SEMM с помощью Configuration Manager требуется установка Microsoft Surface UEFI Manager на каждом клиентском устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="0b42c-126">Вы можете скачать Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) со страницы [инструменты Surface для ИТ](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0b42c-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="0b42c-127">Скачайте сценарии SEMM для Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0b42c-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="0b42c-128">После установки Microsoft Surface UEFI Manager на клиентском устройстве Surface SEMM разворачивается и управляется с помощью сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b42c-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="0b42c-129">Вы можете скачать примеры [сценариев управления SEMM](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки.</span><span class="sxs-lookup"><span data-stu-id="0b42c-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="0b42c-130">Развертывание диспетчера UEFI Surface (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0b42c-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="0b42c-131">Развертывание диспетчера UEFI Surface (Майкрософт) — это типичное развертывание приложения.</span><span class="sxs-lookup"><span data-stu-id="0b42c-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="0b42c-132">Файл установщика Microsoft Surface UEFI Manager — это стандартный файл установщика Windows, который можно установить со [стандартным параметром quiet](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span><span class="sxs-lookup"><span data-stu-id="0b42c-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="0b42c-133">Для установки диспетчера Microsoft Surface UEFI Manager необходимо выполнить следующие команды.</span><span class="sxs-lookup"><span data-stu-id="0b42c-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="0b42c-134">Ниже приведена команда для удаления диспетчера UEFI Surface (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="0b42c-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="0b42c-135">Чтобы создать новое приложение и развернуть его в коллекции, содержащей устройства Surface, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0b42c-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="0b42c-136">Откройте консоль Configuration Manager на **начальном** экране или в меню " **Пуск** ".</span><span class="sxs-lookup"><span data-stu-id="0b42c-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="0b42c-137">В левом нижнем углу окна выберите **Библиотека программного обеспечения** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="0b42c-138">Разверните узел **Управление приложениями** библиотеки программного обеспечения, а затем выберите пункт **приложения**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="0b42c-139">Нажмите кнопку " **создать приложение** " под вкладкой " **Главная** " в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="0b42c-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="0b42c-140">Запустится мастер создания приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="0b42c-141">Мастер создания приложений предоставляет ряд шагов.</span><span class="sxs-lookup"><span data-stu-id="0b42c-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="0b42c-142">**Общие** : параметр **автоматически определяет сведения об этом приложении из файлов установки** по умолчанию установлен.</span><span class="sxs-lookup"><span data-stu-id="0b42c-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="0b42c-143">В поле **тип** **(файл. msi)** также выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b42c-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="0b42c-144">Нажмите кнопку **Обзор** , перейдите к пункту **SurfaceUEFIManagerSetup.msi**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="0b42c-145">Расположение SurfaceUEFIManagerSetup.msi должно находиться в сетевой папке и находиться в папке, которая не имеет других файлов.</span><span class="sxs-lookup"><span data-stu-id="0b42c-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="0b42c-146">Нельзя использовать локальное расположение файлов.</span><span class="sxs-lookup"><span data-stu-id="0b42c-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="0b42c-147">**Импорт данных** — мастер создания приложений проанализирует MSI-файл и прочтите **имя приложения** и **код продукта**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="0b42c-148">SurfaceUEFIManagerSetup.msi должны быть указаны в качестве единственного файла **содержимого**строки, как показано на рисунке 1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="0b42c-149">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-149">Select **Next** to proceed.</span></span>

      ![Данные из программы установки диспетчера UEFI Surface автоматически анализируются](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="0b42c-151">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-151">Figure 1.</span></span> <span data-ttu-id="0b42c-152">Сведения от программы установки Microsoft Surface UEFI Manager автоматически анализируются</span><span class="sxs-lookup"><span data-stu-id="0b42c-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="0b42c-153">**Общие сведения** — вы можете изменить имя приложения и сведения о его издателе и версии, а также добавить примечания на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0b42c-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="0b42c-154">Команда установки для Microsoft Surface UEFI Manager отображается в поле программы установки.</span><span class="sxs-lookup"><span data-stu-id="0b42c-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="0b42c-155">Поведение по умолчанию при установке для системы позволяет диспетчеру UEFI Microsoft Surface устанавливать необходимые сборки для SEMM, даже если пользователь не вошел на устройство Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="0b42c-156">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="0b42c-157">**Summary (сводка** ) — данные, которые были проанализированы на этапе **импорта данных** , и выбранные на странице " **Общие сведения** " отображаются на этой вкладке.</span><span class="sxs-lookup"><span data-stu-id="0b42c-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="0b42c-158">Нажмите кнопку **Далее** , чтобы подтвердить выборку и создать приложение.</span><span class="sxs-lookup"><span data-stu-id="0b42c-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="0b42c-159">**Ход выполнения** — отображает индикатор выполнения и состояние при импорте и добавлении приложения в библиотеку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="0b42c-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="0b42c-160">**Завершение** — подтверждение успешного создания приложения отображается по завершении процесса создания приложения.</span><span class="sxs-lookup"><span data-stu-id="0b42c-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="0b42c-161">Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="0b42c-162">После того как приложение создано в Configuration Manager, вы можете распространить его на точки распространения и развернуть в коллекции, в том числе на Surface Devices.</span><span class="sxs-lookup"><span data-stu-id="0b42c-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="0b42c-163">Это приложение не установит и не включит SEMM на устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="0b42c-164">Она предоставляет только сборки, необходимые для включения SEMM с помощью сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b42c-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="0b42c-165">Если вы не хотите устанавливать сборки Microsoft Surface UEFI Manager на устройствах, которые не будут управляться с помощью SEMM, можно настроить диспетчер Microsoft Surface UEFI в качестве зависимости от сценариев Configuration Manager SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="0b42c-166">Этот сценарий рассматривается в разделе [сценарии SEMM Configuration Manager для развертывания](#deploy-semm-configuration-manager-scripts) в этой статье ниже.</span><span class="sxs-lookup"><span data-stu-id="0b42c-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="0b42c-167">Создание и изменение сценариев Configuration Manager SEMM</span><span class="sxs-lookup"><span data-stu-id="0b42c-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="0b42c-168">После установки на устройствах необходимых сборок процесс регистрации устройств в SEMM и настройки UEFI Surface выполняется с помощью сценариев PowerShell и развернут как приложение сценария с помощью Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0b42c-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="0b42c-169">Эти сценарии можно изменить в соответствии с потребностями Организации и среды.</span><span class="sxs-lookup"><span data-stu-id="0b42c-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="0b42c-170">Например, вы можете создать несколько конфигураций для управляемых устройств Surface в разных подразделениях или ролях.</span><span class="sxs-lookup"><span data-stu-id="0b42c-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="0b42c-171">Вы можете скачать примеры сценариев для SEMM и Configuration Manager из ссылки в разделе [необходимые условия](#prerequisites) в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="0b42c-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="0b42c-172">Для выполнения развертывания SEMM с помощью Configuration Manager вам понадобятся два основных сценария.</span><span class="sxs-lookup"><span data-stu-id="0b42c-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="0b42c-173">**ConfigureSEMM.ps1** — используйте этот сценарий для создания пакетов конфигурации для устройств Surface с помощью параметров UEFI, необходимых для применения указанных параметров к устройству Surface, для регистрации устройства в SEMM и для настройки ключа реестра, используемого для определения регистрации устройства в SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="0b42c-174">**ResetSEMM.ps1** — используйте этот сценарий для сброса SEMM на устройстве Surface, который отменяет его из SEMM и удаляет элемент управления для параметров UEFI Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="0b42c-175">Примеры сценариев включают в себя примеры того, как задавать параметры UEFI Surface и управлять разрешениями для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="0b42c-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="0b42c-176">Эти параметры можно изменить на Secure UEFI Surface и установить параметры UEFI Surface в соответствии с потребностями вашей среды.</span><span class="sxs-lookup"><span data-stu-id="0b42c-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="0b42c-177">В следующих разделах этой статьи описаны сценарии ConfigureSEMM.ps1 и рассматриваются изменения, которые необходимо внести в сценарий в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="0b42c-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="0b42c-178">Сценарии Configuration Manager SEMM и экспортированный файл сертификата SEMM (PFX) следует размещать в той же папке, где нет других файлов, прежде чем они будут добавлены в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0b42c-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="0b42c-179">Указание имен сертификатов и пакетов</span><span class="sxs-lookup"><span data-stu-id="0b42c-179">Specify certificate and package names</span></span>

<span data-ttu-id="0b42c-180">Первый регион сценария, который необходимо изменить, — это часть, которая определяет и загружает сертификат SEMM, а также указывает SurfaceUEFIManager версию и имена пакета конфигурации SEMM и SEMM сброса пакета.</span><span class="sxs-lookup"><span data-stu-id="0b42c-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="0b42c-181">Имя сертификата и SurfaceUEFIManager версия указываются в строках 56 – 73 в сценарии ConfigureSEMM.ps1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="0b42c-182">Замените значение **FabrikamSEMMSample. pfx** для переменной **$certName** именем вашего файла сертификата SEMM в строке 58.</span><span class="sxs-lookup"><span data-stu-id="0b42c-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="0b42c-183">Сценарий создаст рабочую папку (с именем config) в папке, в которой находятся ваши сценарии, а затем скопирует файл сертификата в этот рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="0b42c-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="0b42c-184">Пакет владельца и пакет сброса будут также созданы в каталоге конфигурации и содержат конфигурацию для параметров UEFI Surface и разрешений, создаваемых сценарием.</span><span class="sxs-lookup"><span data-stu-id="0b42c-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="0b42c-185">В строке 73 замените значение переменной **$Password** из **1234** на пароль для файла сертификата.</span><span class="sxs-lookup"><span data-stu-id="0b42c-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="0b42c-186">Если пароль не требуется, удалите текст **1234** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="0b42c-187">Последние два символа отпечатка сертификата необходимы для регистрации устройства в SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="0b42c-188">Этот сценарий отобразит эти цифры для пользователя, который позволит пользователю или специалисту записать эти цифры перед перезагрузкой системы, чтобы зарегистрировать устройство в SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="0b42c-189">Для этого в сценарии используется следующий код, найденный в строках 150-155.</span><span class="sxs-lookup"><span data-stu-id="0b42c-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Администраторы, у которых есть доступ к файлу сертификата (PFX), могут в любое время прочитать отпечаток, открыв PFX-файл в CertMgr. <span data-ttu-id="0b42c-191">Чтобы просмотреть отпечаток с помощью CertMgr, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0b42c-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="0b42c-192">Щелкните PFX-файл правой кнопкой мыши и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="0b42c-193">Разверните папку в области навигации.</span><span class="sxs-lookup"><span data-stu-id="0b42c-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="0b42c-194">Выберите **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="0b42c-195">Щелкните правой кнопкой мыши свой сертификат в основной области и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="0b42c-196">Откройте вкладку **сведения** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="0b42c-197">В раскрывающемся меню **Показать** должны быть выбраны только **все** или **свойства** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="0b42c-198">Выберите **отпечаток**поля.</span><span class="sxs-lookup"><span data-stu-id="0b42c-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="0b42c-199">Имя сертификата SEMM и пароль также должны быть введены в этом разделе сценария ResetSEMM.ps1, чтобы настроить Configuration Manager для удаления SEMM с устройства с помощью действия удаления.</span><span class="sxs-lookup"><span data-stu-id="0b42c-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="0b42c-200">Настройка разрешений</span><span class="sxs-lookup"><span data-stu-id="0b42c-200">Configure permissions</span></span>

<span data-ttu-id="0b42c-201">Первый регион сценария, в котором вы укажете конфигурацию UEFI Surface, — это область " **Настройка разрешений** ".</span><span class="sxs-lookup"><span data-stu-id="0b42c-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="0b42c-202">Этот регион начинается со строки 210 в сценарии Sample с примечанием **# Настройка разрешений** и переход к строке 247.</span><span class="sxs-lookup"><span data-stu-id="0b42c-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="0b42c-203">В следующем фрагменте кода сначала устанавливаются разрешения для всех параметров UEFI Surface, так что они могут быть изменены только в SEMM, а затем добавлены явные разрешения, позволяющие локальному пользователю изменять пароль UEFI Surface, TPM и передние и задние камеры.</span><span class="sxs-lookup"><span data-stu-id="0b42c-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="0b42c-204">Каждая переменная **$uefiV 2** определяет параметр UEFI Surface, задавая имя или идентификатор, а затем настраивает разрешения для одного из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0b42c-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="0b42c-205">**$ownerOnly** — разрешение на изменение этого параметра предоставляется только в SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="0b42c-206">**$ownerAndLocalUser** — разрешение на изменение этого параметра предоставлено локальному пользователю, загружается в UEFI Surface и SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="0b42c-207">Сведения о доступных именах параметров и идентификаторах для UEFI Surface можно найти в разделе [Параметры и идентификаторы](#settings-names-and-ids) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="0b42c-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="0b42c-208">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="0b42c-208">Configure settings</span></span>

<span data-ttu-id="0b42c-209">Вторая область сценария, в которой вы укажете конфигурацию UEFI Surface, — это область " **Настройка параметров** " сценария ConfigureSEMM.ps1, который позволяет настроить включение или отключение каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="0b42c-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="0b42c-210">В примере сценария содержатся инструкции по заданию значений по умолчанию для всех параметров.</span><span class="sxs-lookup"><span data-stu-id="0b42c-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="0b42c-211">Затем сценарий предоставляет явные инструкции по отключению IPv6 для загрузки PXE и оставлению пароля администратора UEFI Surface без изменений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="0b42c-212">Этот регион можно найти, начиная с комментария " **# Настройка параметров** " в строке 291 – 335 в примере сценария.</span><span class="sxs-lookup"><span data-stu-id="0b42c-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="0b42c-213">Область выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0b42c-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="0b42c-214">Так же, как и разрешения, заданные в разделе " **Настройка разрешений** " сценария, настройка каждого из параметров UEFI Surface выполняется путем определения переменной **$uefiV 2** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="0b42c-215">Для каждой строки, определяющей переменную **$uefiV 2** , параметр UEFI Surface определяется с помощью параметра Name (имя) или ID, для которого задано значение **Enabled (включено** ) или **Disabled (отключить**).</span><span class="sxs-lookup"><span data-stu-id="0b42c-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="0b42c-216">Если вы не хотите изменять конфигурацию UEFI Surface, например, чтобы не пропустить пароль администратора UEFI Surface при сбросе параметров UEFI Surface по умолчанию, можно использовать **ClearConfiguredValue ()** для принудительного изменения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="0b42c-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="0b42c-217">В примере сценарий используется в строке 323 для предотвращения очистки пароля администратора UEFI Surface, определенного в образце сценария с помощью идентификатора параметра, **501**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="0b42c-218">Сведения о доступных именах параметров и идентификаторах для UEFI Surface можно найти в разделе [Параметры и идентификаторы](#settings-names-and-ids) ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b42c-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="0b42c-219">Раздел "Параметры" в реестре</span><span class="sxs-lookup"><span data-stu-id="0b42c-219">Settings registry key</span></span>

<span data-ttu-id="0b42c-220">Чтобы определить зарегистрированные системы для Configuration Manager, в сценарии ConfigureSEMM.ps1 записываются разделы реестра, которые можно использовать для определения зарегистрированных систем в том виде, в котором они были установлены с помощью сценария конфигурации SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="0b42c-221">Эти разделы можно найти в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="0b42c-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="0b42c-222">Следующий фрагмент кода, который находится в строках 380-477, используется для записи этих разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="0b42c-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="0b42c-223">Имена и идентификаторы параметров</span><span class="sxs-lookup"><span data-stu-id="0b42c-223">Settings names and IDs</span></span>

<span data-ttu-id="0b42c-224">Чтобы настроить параметры UEFI Surface или разрешения для параметров UEFI Surface, необходимо обратиться к каждому параметру, указав его имя параметра или идентификатор параметра.</span><span class="sxs-lookup"><span data-stu-id="0b42c-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="0b42c-225">После каждого нового обновления для UEFI Surface можно добавить новые параметры.</span><span class="sxs-lookup"><span data-stu-id="0b42c-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="0b42c-226">Лучший способ получить полный список параметров, доступных на устройстве Surface (вместе с именем и идентификатором параметров), — использовать сценарий ShowSettingsOptions.ps1 из SEMM_Powershell.zip [для загрузок средства Surface для IT downloads](https://www.microsoft.com/download/details.aspx?id=46703) .</span><span class="sxs-lookup"><span data-stu-id="0b42c-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="0b42c-227">На компьютере, на котором запущен ShowSettingsOptions.ps1, должен быть установлен диспетчер Microsoft Surface UEFI Manager, но для этого сценария не требуется устройство Surface.</span><span class="sxs-lookup"><span data-stu-id="0b42c-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>

<span data-ttu-id="0b42c-228">Лучший способ просмотреть наиболее актуальные имена параметров и идентификаторов для устройств — использовать сценарий ConfigureSEMM.ps1 или ConfigureSEMM- <device name> . ps1 из SEMM_Powershell.zip в разделе [средства для загрузки для загрузок](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="0b42c-228">The best way to view the most current Setting names and IDs for devices is to use the ConfigureSEMM.ps1 script or the ConfigureSEMM - <device name>.ps1 from the SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>

<span data-ttu-id="0b42c-229">Имена параметров и идентификаторы для всех устройств можно просмотреть в сценарии ConfigureSEMM.ps1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-229">Setting names and IDs for all devices can be seen in the ConfigureSEMM.ps1 script.</span></span>

<span data-ttu-id="0b42c-230">В сценариях ConfigureSEMM-. ps1 можно просматривать имена параметров и идентификаторов для определенных устройств <device name> .</span><span class="sxs-lookup"><span data-stu-id="0b42c-230">Setting names and IDs for specific devices can be seen in the ConfigureSEMM - <device name>.ps1 scripts.</span></span> <span data-ttu-id="0b42c-231">Например, параметры names и ID для Surface Pro X можно найти в сценарии ConfigureSEMM – ProX.ps1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-231">For example, setting names and IDs for Surface Pro X can be found in the ConfigureSEMM – ProX.ps1 script.</span></span>

## <span data-ttu-id="0b42c-232">Развертывание сценариев Configuration Manager SEMM</span><span class="sxs-lookup"><span data-stu-id="0b42c-232">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="0b42c-233">После того как сценарии будут подготовлены для настройки и включения SEMM на клиентском устройстве, следующий шаг — добавить эти сценарии как приложение в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0b42c-233">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="0b42c-234">Прежде чем открыть Configuration Manager, убедитесь в том, что указанные ниже файлы находятся в общей папке, не включающей другие файлы.</span><span class="sxs-lookup"><span data-stu-id="0b42c-234">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="0b42c-235">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="0b42c-235">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="0b42c-236">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="0b42c-236">ResetSEMM.ps1</span></span>
* <span data-ttu-id="0b42c-237">Сертификат SEMM (например, SEMMCertificate. pfx)</span><span class="sxs-lookup"><span data-stu-id="0b42c-237">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="0b42c-238">Сценарии Configuration Manager SEMM будут добавлены в Configuration Manager как приложение сценария.</span><span class="sxs-lookup"><span data-stu-id="0b42c-238">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="0b42c-239">Команда для установки SEMM с ConfigureSEMM.ps1 описана ниже.</span><span class="sxs-lookup"><span data-stu-id="0b42c-239">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="0b42c-240">Команда для удаления SEMM с ResetSEMM.ps1 описана ниже.</span><span class="sxs-lookup"><span data-stu-id="0b42c-240">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="0b42c-241">Чтобы добавить в приложение Configuration Manager сценарии Configuration Manager SEMM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0b42c-241">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="0b42c-242">Запустите мастер создания приложений, выполнив действия 1 – 5 из раздела [развертывание ДИСПЕТЧЕРА UEFI Surface (Майкрософт](#deploy-microsoft-surface-uefi-manager) ), описанного выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b42c-242">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="0b42c-243">Выполните описанные ниже действия с помощью мастера создания приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-243">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="0b42c-244">**General (общие** ) — **Укажите сведения о приложении вручную**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-244">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="0b42c-245">**Общие сведения** : введите имя приложения (например, SEMM) и любые другие сведения, такие как издатель, версия или комментарии на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0b42c-245">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="0b42c-246">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-246">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="0b42c-247">**Каталог приложений** — поля на этой странице можно оставить, указав значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b42c-247">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="0b42c-248">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b42c-248">Select **Next**.</span></span>

   - <span data-ttu-id="0b42c-249">**Типы развертывания** : нажмите кнопку **Добавить** , чтобы запустить мастер создания типа развертывания.</span><span class="sxs-lookup"><span data-stu-id="0b42c-249">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="0b42c-250">Следуйте указаниям мастера создания типа развертывания, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0b42c-250">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="0b42c-251">**Общие** — выберите **Установщик сценариев** в раскрывающемся меню **Type (тип** ).</span><span class="sxs-lookup"><span data-stu-id="0b42c-251">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="0b42c-252">Параметр " **сведения о типе развертывания** " будет выбран автоматически.</span><span class="sxs-lookup"><span data-stu-id="0b42c-252">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="0b42c-253">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-253">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="0b42c-254">**Общие сведения** : введите имя для типа развертывания (например, SEMM), а затем нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-254">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="0b42c-255">**Содержимое** : нажмите кнопку **Обзор** рядом с полем **расположение содержимого** , а затем выберите папку, в которой находятся ваши сценарии Configuration Manager SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-255">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="0b42c-256">В поле **программа установки** введите [команду установки](#deploy-semm-configuration-manager-scripts) , описанную ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b42c-256">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="0b42c-257">В поле **Удаление программы** введите [команду](#deploy-semm-configuration-manager-scripts) удаления, описанную ранее в этой статье (на рис. 2).</span><span class="sxs-lookup"><span data-stu-id="0b42c-257">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="0b42c-258">Нажмите кнопку **Далее** , чтобы перейти на следующую страницу.</span><span class="sxs-lookup"><span data-stu-id="0b42c-258">Select **Next** to move to the next page.</span></span>
    
     ![Настройка сценариев Configuration Manager SEMM в качестве команд установки и удаления](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="0b42c-260">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="0b42c-260">Figure 2.</span></span> <span data-ttu-id="0b42c-261">Настройка сценариев Configuration Manager SEMM в качестве команд установки и удаления</span><span class="sxs-lookup"><span data-stu-id="0b42c-261">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="0b42c-262">**Метод обнаружения** — выберите **Add (добавить** ), чтобы добавить правило обнаружения разделов реестра для сценария диспетчера конфигураций SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-262">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="0b42c-263">Откроется окно " **правило обнаружения** ", как показано на рисунке 3.</span><span class="sxs-lookup"><span data-stu-id="0b42c-263">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="0b42c-264">Используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0b42c-264">Use the following settings:</span></span>

       - <span data-ttu-id="0b42c-265">Выберите **раздел реестра** в раскрывающемся меню **тип параметра** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-265">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="0b42c-266">В раскрывающемся меню **куст** выберите пункт **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-266">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="0b42c-267">Введите **SOFTWARE\Microsoft\Surface\SEMM** в поле " **ключ** ".</span><span class="sxs-lookup"><span data-stu-id="0b42c-267">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="0b42c-268">Введите **CertName** в поле **value (значение** ).</span><span class="sxs-lookup"><span data-stu-id="0b42c-268">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="0b42c-269">В раскрывающемся меню **тип данных** выберите пункт **строка** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-269">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="0b42c-270">Выберите **этот параметр реестра должен соответствовать следующему правилу, которое указывает на наличие кнопки приложения** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-270">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="0b42c-271">Введите имя сертификата, введенного в строке 58 сценария, в поле **value (значение** ).</span><span class="sxs-lookup"><span data-stu-id="0b42c-271">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="0b42c-272">Нажмите кнопку **ОК** , чтобы закрыть окно **правила обнаружения** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-272">Select **OK** to close the **Detection Rule** window.</span></span>

     ![Использование раздела реестра для определения устройств, зарегистрированных в SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="0b42c-274">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="0b42c-274">Figure 3.</span></span> <span data-ttu-id="0b42c-275">Использование раздела реестра для определения устройств, зарегистрированных в SEMM</span><span class="sxs-lookup"><span data-stu-id="0b42c-275">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="0b42c-276">Нажмите кнопку **Далее** , чтобы перейти к следующей странице.</span><span class="sxs-lookup"><span data-stu-id="0b42c-276">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="0b42c-277">**Взаимодействие с пользователем** : выберите пункт **установить для системы** в раскрывающемся меню **поведение при установке** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-277">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="0b42c-278">Если вы хотите, чтобы ваши пользователи записали и ввели отпечаток сертификата, оставьте требование для входа в систему **только в том случае, если у пользователя есть учетные**данные.</span><span class="sxs-lookup"><span data-stu-id="0b42c-278">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="0b42c-279">Если вы хотите, чтобы ваши администраторы **выписали** отпечаток для пользователей и не должны видеть отпечаток, укажите, входит ли пользователь в раскрывающемся меню " **необходимость входа** в систему".</span><span class="sxs-lookup"><span data-stu-id="0b42c-279">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="0b42c-280">**Требования** : сценарий ConfigureSEMM.ps1 автоматически проверяет, является ли устройство Surface устройством, прежде чем попытаться включить SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-280">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="0b42c-281">Тем не менее, если вы планируете развертывать это приложение этого сценария в коллекции с использованием SEMM, вы можете добавить требования для обеспечения того, что это приложение будет выполняться только на устройствах Surface или устройствах, которыми вы планируете управлять с помощью SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-281">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="0b42c-282">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-282">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="0b42c-283">**Зависимости** : нажмите кнопку **Добавить** , чтобы открыть окно **Добавление зависимости** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-283">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="0b42c-284">Нажмите кнопку **Добавить** , чтобы открыть окно **укажите требуемое приложение** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-284">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="0b42c-285">Введите имя для зависимостей SEMM в поле **имя группы зависимостей** (например, *SEMM сборки*).</span><span class="sxs-lookup"><span data-stu-id="0b42c-285">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="0b42c-286">В списке **доступных приложений** и типа развертывания MSI выберите **Microsoft Surface UEFI Manager** , а затем нажмите кнопку **ОК** , чтобы закрыть окно **Указание требуемого приложения** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-286">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="0b42c-287">Если вы хотите, чтобы диспетчер Microsoft Surface UEFI автоматически устанавливался на устройствах при попытке включить SEMM с помощью сценариев Configuration Manager, не устанавливайте флажок " **Автоматическая установка** ".</span><span class="sxs-lookup"><span data-stu-id="0b42c-287">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="0b42c-288">Нажмите кнопку **ОК** , чтобы закрыть окно **Добавление зависимости** .</span><span class="sxs-lookup"><span data-stu-id="0b42c-288">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="0b42c-289">Нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="0b42c-289">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="0b42c-290">**Summary (сводка** ): сведения, введенные в мастере создания типа развертывания, отображаются на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0b42c-290">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="0b42c-291">Нажмите кнопку **Далее** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="0b42c-291">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="0b42c-292">**Ход выполнения** — индикатор выполнения и состояние, так как тип развертывания добавляется для приложения сценария SEMM, отображается на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0b42c-292">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="0b42c-293">**Завершение** — подтверждение создания типа развертывания отображается по завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="0b42c-293">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="0b42c-294">Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания типа развертывания.</span><span class="sxs-lookup"><span data-stu-id="0b42c-294">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="0b42c-295">**Сводка** : на экране будут показаны данные, введенные в мастере создания приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-295">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="0b42c-296">Нажмите кнопку **Далее** , чтобы создать приложение.</span><span class="sxs-lookup"><span data-stu-id="0b42c-296">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="0b42c-297">**Ход выполнения** : на этой странице отображается индикатор выполнения и состояние, которое приложение добавляет в библиотеку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="0b42c-297">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="0b42c-298">**Завершение** — подтверждение успешного создания приложения отображается по завершении процесса создания приложения.</span><span class="sxs-lookup"><span data-stu-id="0b42c-298">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="0b42c-299">Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания приложений.</span><span class="sxs-lookup"><span data-stu-id="0b42c-299">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="0b42c-300">После того как приложение сценария будет доступно в библиотеке программного обеспечения Configuration Manager, вы можете распространять и развертывать SEMM с помощью сценариев, подготовленных к устройствам или коллекциям.</span><span class="sxs-lookup"><span data-stu-id="0b42c-300">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="0b42c-301">Если вы настроили сборки Microsoft Surface UEFI Manager как зависимость, которая будет автоматически установлена, вы можете развернуть SEMM за один шаг.</span><span class="sxs-lookup"><span data-stu-id="0b42c-301">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="0b42c-302">Если вы не настроили сборки в качестве зависимости, они должны быть установлены на устройствах, которыми вы планируете управлять, прежде чем включать SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-302">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="0b42c-303">При развертывании SEMM с помощью этого приложения сценария и конфигурации, видимой для конечного пользователя, сценарий PowerShell запускается и отпечаток сертификата будет отображаться в окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b42c-303">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="0b42c-304">Пользователи могут записать этот отпечаток и ввести его в ответ на запрос UEFI Surface после перезагрузки устройства.</span><span class="sxs-lookup"><span data-stu-id="0b42c-304">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="0b42c-305">Кроме того, можно настроить автоматическую перезагрузку приложения и установить невидимый для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b42c-305">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="0b42c-306">В этом случае специалисту потребуется ввести отпечаток на каждом устройстве при перезагрузке.</span><span class="sxs-lookup"><span data-stu-id="0b42c-306">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="0b42c-307">Любой специалист, у которого есть доступ к файлу сертификата, может прочитать отпечаток, просматривая сертификат с помощью CertMgr.</span><span class="sxs-lookup"><span data-stu-id="0b42c-307">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="0b42c-308">Инструкции по просмотру отпечатка с помощью CertMgr находятся в разделе [Создание или изменение сценариев Configuration Manager SEMM](#create-or-modify-the-semm-configuration-manager-scripts) , описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b42c-308">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="0b42c-309">Удаление SEMM с устройства, развернутого в Configuration Manager, с помощью этих сценариев так же просто, как и удаление приложения в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0b42c-309">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="0b42c-310">Это действие запускает сценарий ResetSEMM.ps1 и соответствующим образом отменяет регистрацию устройства с помощью того же файла сертификата, который использовался при развертывании SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-310">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="0b42c-311">Microsoft Surface рекомендует создавать сбрасывать пакеты только в том случае, если нужно отменить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="0b42c-311">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="0b42c-312">Эти пакеты обычно действительны только для одного устройства, определяемого их порядковым номером.</span><span class="sxs-lookup"><span data-stu-id="0b42c-312">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="0b42c-313">Тем не менее, вы можете создать универсальный пакет сброса, который будет работать для любого устройства, зарегистрированного в SEMM с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="0b42c-313">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="0b42c-314">Настоятельно рекомендуем защитить универсальный пакет сброса так же, как и сертификат, который вы использовали для регистрации устройств в SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-314">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="0b42c-315">Помните, что, точно так же, как и сам сертификат, этот универсальный пакет сброса можно использовать, чтобы отдать заявку на доступ к устройствам Surface из компании SEMM.</span><span class="sxs-lookup"><span data-stu-id="0b42c-315">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="0b42c-316">При установке пакета сброса значение, равное минимальному значению (LSV), сбрасывается до значения 1.</span><span class="sxs-lookup"><span data-stu-id="0b42c-316">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="0b42c-317">Вы можете повторно зарегистрировать устройство, используя существующий пакет конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b42c-317">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="0b42c-318">Устройство будет запрашивать отпечаток сертификата перед тем, как будет сделан владелец.</span><span class="sxs-lookup"><span data-stu-id="0b42c-318">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="0b42c-319">По этой причине для повторной регистрации устройства в SEMM потребуется создать и установить на нем новый пакет.</span><span class="sxs-lookup"><span data-stu-id="0b42c-319">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="0b42c-320">Так как это действие является новой регистрацией, а не изменением в конфигурации устройства, уже зарегистрированного в SEMM, устройство будет запрашивать отпечаток сертификата, прежде чем будет сделан владелец.</span><span class="sxs-lookup"><span data-stu-id="0b42c-320">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
