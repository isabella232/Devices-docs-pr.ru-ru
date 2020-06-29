---
title: Создание пакетов подготовки для Surface Hub 2S
description: На этой странице описывается, как развернуть Surface Hub 2S с помощью пакетов подготовки и других средств.
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836940"
---
# <span data-ttu-id="bdce8-104">Создание пакетов подготовки для Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="bdce8-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="bdce8-105">Вы можете использовать конструктор конфигураций Windows (WCD) для создания пакетов подготовки для автоматизации процесса развертывания Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="bdce8-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="bdce8-106">Используйте пакеты подготовки для добавления сертификатов, настройте прокси-серверы, настройте администраторов устройств и учетные записи устройств.</span><span class="sxs-lookup"><span data-stu-id="bdce8-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="bdce8-107">Кроме того, вы можете использовать пакеты подготовки вместе с файлом конфигурации для развертывания нескольких Surface Hub с помощью одного USB-накопителя.</span><span class="sxs-lookup"><span data-stu-id="bdce8-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="bdce8-108">Установка конструктора конфигураций Windows</span><span class="sxs-lookup"><span data-stu-id="bdce8-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="bdce8-109">Установите конструктор конфигураций Windows из комплекта средств для развертывания и оценки Windows (ADK) для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bdce8-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="bdce8-110">Скачайте и установите приложение [ADK для Windows 10 версии 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="bdce8-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="bdce8-111">Дополнительные сведения можно найти [в разделе Загрузка и установка Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="bdce8-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="bdce8-112">Добавление сертификатов</span><span class="sxs-lookup"><span data-stu-id="bdce8-112">Add certificates</span></span>

<span data-ttu-id="bdce8-113">Вы можете импортировать сертификаты центра сертификации в Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="bdce8-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="bdce8-114">Чтобы добавить сертификаты в Surface Hub 2S, необходимо скопировать каждый из этих сертификатов в формате X. 509 в. cer.</span><span class="sxs-lookup"><span data-stu-id="bdce8-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="bdce8-115">Импортировать. CRT,. pfx и другие форматы контейнеров нельзя.</span><span class="sxs-lookup"><span data-stu-id="bdce8-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="bdce8-116">Сертификаты нужно импортировать в конструктор конфигураций Windows и упорядочить по иерархии:</span><span class="sxs-lookup"><span data-stu-id="bdce8-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![Добавление сертификатов](images/sh2-wcd.png)

### <span data-ttu-id="bdce8-118">Настройка прокси-сервера во время OOBE</span><span class="sxs-lookup"><span data-stu-id="bdce8-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="bdce8-119">В конструкторе конфигураций Windows перейдите на вкладку Настройка прокси-сервера и введите необходимые параметры, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bdce8-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![настроить параметры прокси-сервера;](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="bdce8-121">При настройке параметров прокси-сервера отключите **Автоматическое определение параметров** , если вы планируете использовать сценарий установки или прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="bdce8-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="bdce8-122">Вы можете использовать сценарий настройки *или* прокси-сервер, но не оба.</span><span class="sxs-lookup"><span data-stu-id="bdce8-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="bdce8-123">Дочерний центр Surface Hub 2S с Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bdce8-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="bdce8-124">Вы можете прикрепить Surface Hub 2 с Azure Active Directory с помощью пакета подготовки: в качестве глобального администратора Azure Active Directory вы можете присоединиться к большому числу новых устройств с Windows в Azure Active Directory и Intune с помощью массового маркера.</span><span class="sxs-lookup"><span data-stu-id="bdce8-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="bdce8-125">Чтобы создать массовый маркер, присвойте ему понятное имя, настройте дату окончания срока действия (не более 30 дней) и используйте учетные данные администратора для получения маркера, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="bdce8-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![Настройка администраторов устройств](images/sh2-token.png) <br><br>
 ![Настройка администраторов устройств](images/sh2-token2.png) <br><br>
 ![Настройка администраторов устройств](images/sh2-token3.png) <br><br>

### <span data-ttu-id="bdce8-129">Подготовка нескольких устройств (CSV-файла)</span><span class="sxs-lookup"><span data-stu-id="bdce8-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="bdce8-130">В дополнение к пакету подготовки, вы можете использовать файл конфигурации Surface Hub для упрощения настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="bdce8-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="bdce8-131">Файл конфигурации Surface Hub состоит из списка учетных записей устройств и понятных имен для беспроводных проекций.</span><span class="sxs-lookup"><span data-stu-id="bdce8-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="bdce8-132">Во время первого запуска вы получаете возможность выбрать учетную запись устройства и понятное имя из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bdce8-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="bdce8-133">Создание файла конфигурации Surface HUB</span><span class="sxs-lookup"><span data-stu-id="bdce8-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="bdce8-134">С помощью Microsoft Excel или другого редактора CSV создайте CSV-файл с именем: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="bdce8-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="bdce8-135">Введите список учетных записей устройств и понятные имена в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="bdce8-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="bdce8-136">Сохраните файл в корневой папке USB-накопителя, в который вы скопировали файл PPKG.</span><span class="sxs-lookup"><span data-stu-id="bdce8-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![Пример файла конфигурации](images/sh2-config-file.png)
