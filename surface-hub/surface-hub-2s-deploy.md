---
title: Создание пакетов подготовки для Surface Hub 2S
description: На этой странице описывается развертывание Surface Hub 2S с помощью пакетов предварительного обеспечения и других средств.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576869"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="025fa-104">Создание пакетов подготовки для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="025fa-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="025fa-105">Вы можете использовать Windows (WCD) для создания пакетов подготовка для автоматизации развертывания Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="025fa-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="025fa-106">Используйте пакеты подготовка для добавления сертификатов, настройки прокси, настройки администраторов устройств и учетных записей устройств.</span><span class="sxs-lookup"><span data-stu-id="025fa-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="025fa-107">Вы также можете использовать пакеты подготовка вместе с файлом конфигурации для развертывания нескольких концентраторов Surface с одним usb-накопителем.</span><span class="sxs-lookup"><span data-stu-id="025fa-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="025fa-108">Установка конструктора конфигураций Windows</span><span class="sxs-lookup"><span data-stu-id="025fa-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="025fa-109">Установите Windows конструктор конфигурации из набора Windows и развертывания (ADK) для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="025fa-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="025fa-110">Скачайте и установите [ADK для Windows 10 версии 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="025fa-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="025fa-111">Дополнительные сведения см. в разделе [Скачивание и установка Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="025fa-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="025fa-112">Добавление сертификатов</span><span class="sxs-lookup"><span data-stu-id="025fa-112">Add certificates</span></span>

<span data-ttu-id="025fa-113">Вы можете импортировать сертификаты Authority в Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="025fa-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="025fa-114">Чтобы добавить сертификаты Surface Hub 2S, вам потребуется копия каждого сертификата в формате X.509 в формате .cer.</span><span class="sxs-lookup"><span data-stu-id="025fa-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="025fa-115">Невозможно импортировать .crt, .pfx или другие форматы контейнера.</span><span class="sxs-lookup"><span data-stu-id="025fa-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="025fa-116">Сертификаты должны импортироваться в Windows configuration Designer и организовываться по иерархии:</span><span class="sxs-lookup"><span data-stu-id="025fa-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![Добавление сертификатов](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="025fa-118">Настройка прокси во время OOBE</span><span class="sxs-lookup"><span data-stu-id="025fa-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="025fa-119">В Windows Конструктор конфигурации перейдите на вкладку Настройка параметров прокси и введите соответствующие параметры, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="025fa-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![настроить параметры прокси-сервера;](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="025fa-121">При настройке параметров прокси-сервера автоматически отключите параметры, если вы собираетесь использовать сценарий установки или прокси-сервер. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="025fa-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="025fa-122">Вы можете использовать сценарий установки *или* прокси-сервер, а не оба.</span><span class="sxs-lookup"><span data-stu-id="025fa-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="025fa-123">Партнерская Surface Hub 2S с Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="025fa-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="025fa-124">Вы можете аффилировать Surface Hub 2S с Azure Active Directory с помощью пакета подготовка: в качестве глобального администратора Azure Active Directory вы можете присоединиться к большому числу новых устройств Windows для Azure Active Directory и Intune с помощью маркера массы.</span><span class="sxs-lookup"><span data-stu-id="025fa-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="025fa-125">Чтобы создать основной маркер, назовите ему дружеское имя, настройте дату истечения срока действия (максимум 30 дней) и используйте учетные данные администратора для приобретения маркера, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="025fa-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="025fa-129">Подготовка нескольких устройств (.csv файла)</span><span class="sxs-lookup"><span data-stu-id="025fa-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="025fa-130">В дополнение к пакету подготовка можно использовать файл Surface Hub конфигурации, чтобы упростить настройку устройств.</span><span class="sxs-lookup"><span data-stu-id="025fa-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="025fa-131">Файл Surface Hub конфигурации содержит список учетных записей устройств и дружественные имена для беспроводной проекции.</span><span class="sxs-lookup"><span data-stu-id="025fa-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="025fa-132">Во время первого запуска вы получаете возможность выбрать учетную запись устройства и удобное имя из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="025fa-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="025fa-133">Создание файла Surface Hub конфигурации</span><span class="sxs-lookup"><span data-stu-id="025fa-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="025fa-134">С Microsoft Excel или другого редактора CSV создайте CSV-файл с именем: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="025fa-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="025fa-135">Введите список учетных записей устройств и дружественных имен в этом формате:</span><span class="sxs-lookup"><span data-stu-id="025fa-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="025fa-136">Сохраните файл в корневом диске USB, где вы скопировали файл PPKG.</span><span class="sxs-lookup"><span data-stu-id="025fa-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Пример файла конфигурации](images/sh2-config-file.png)
