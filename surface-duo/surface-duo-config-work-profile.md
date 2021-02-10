---
title: Настройка корпоративного профиля Android для Surface Duo
description: В этой статье объясняется, как настроить рабочий профиль на Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326247"
---
# <span data-ttu-id="f0ae7-103">Настройка корпоративного профиля Android для Surface Duo</span><span class="sxs-lookup"><span data-stu-id="f0ae7-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="f0ae7-104">В развертываниях BYOD профили предоставляют отдельное пространство в приложениях и данных Для работы в Компании Duo, предоставляя организациям полный контроль над своими данными, приложениями и политиками безопасности, не мешая сотрудникам использовать свое устройство для личных приложений и данных.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="f0ae7-105">Настройка корпоративного профиля Android</span><span class="sxs-lookup"><span data-stu-id="f0ae7-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="f0ae7-106">Используйте профили работы для управления корпоративными данными и приложениями на пользовательских устройствах с Android.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="f0ae7-107">По умолчанию регистрация личных устройств с личными профилями работы включена и не требует дополнительной настройки администратора.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="f0ae7-108">Чтобы включить корпоративный рабочий профиль:</span><span class="sxs-lookup"><span data-stu-id="f0ae7-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="f0ae7-109">В Endpoint Manager выберите **устройства**для регистрации Android, а затем выберите  >  \*\*\*\*  >  \*\*\*\* **личные устройства с профилем работы.**</span><span class="sxs-lookup"><span data-stu-id="f0ae7-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![Включить корпоративный рабочий профиль](images/enroll-start.png)

 
**<span data-ttu-id="f0ae7-111">Вход в Surface Duo с помощью корпоративного профиля Android</span><span class="sxs-lookup"><span data-stu-id="f0ae7-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="f0ae7-112">Установите приложение "Портал компании" из Магазина Google Play и во sign in with your Microsoft work or school account.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![Вход в Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="f0ae7-114">На странице "Настройка Access" выберите **"Пуск"**.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="f0ae7-116">Просмотрите сведения на странице конфиденциальности и выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="f0ae7-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![Продолжить](images/duo-wp-3.png)
<br><br>
 ![Выберите "Продолжить"](images/duo-wp-4.png)
 
4. <span data-ttu-id="f0ae7-119">После завершения настройки профиля работы выберите **"Продолжить** активацию и регистрация устройства".</span><span class="sxs-lookup"><span data-stu-id="f0ae7-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![Выберите "Продолжить активацию и регистрация устройства"](images/duo-wp-5.png)

5. <span data-ttu-id="f0ae7-121">Выберите пункт **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-121">Select **Continue**.</span></span><br><br>
 ![Снова выберите "Продолжить"](images/duo-wp-6.png)

6. <span data-ttu-id="f0ae7-123">После активации профиля работы выберите **"Продолжить** обновление параметров устройства".</span><span class="sxs-lookup"><span data-stu-id="f0ae7-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="f0ae7-124">В этом примере рабочий профиль применяет параметр MDM, чтобы требовать более надежный 6-значный букво-цифровой пароль.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![Пример букв и цифр пароля](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="f0ae7-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span><span class="sxs-lookup"><span data-stu-id="f0ae7-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![Выберите "Продолжить настройку"](images/duo-wp-8.png)<br><br>
     ![полная настройка](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="f0ae7-129">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f0ae7-129">Learn more</span></span>

- [<span data-ttu-id="f0ae7-130">Настройка регистрации устройств с профилями работы Android Корпоративная</span><span class="sxs-lookup"><span data-stu-id="f0ae7-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

