---
title: Вход в Surface Hub с помощью проверки Microsoft Authenticator
description: Использование Microsoft Authenticator на мобильном устройстве для входа в Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835256"
---
# <span data-ttu-id="c788b-103">Вход в Surface Hub с помощью проверки Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c788b-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="c788b-104">Сотрудники вашей организации могут выполнить вход в систему на Surface Hub без ввода пароля с помощью приложения Microsoft Authenticator, доступного для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="c788b-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <span data-ttu-id="c788b-105">Необходимые условия для организации</span><span class="sxs-lookup"><span data-stu-id="c788b-105">Organization prerequisites</span></span>

<span data-ttu-id="c788b-106">Чтобы разрешить сотрудникам организации выполнять вход в Surface Hub с помощью телефонов и других устройствах вместо использования пароля, необходимо убедиться, что организация соответствует следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="c788b-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="c788b-107">Организация должна быть гибридной или облачной и использовать Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c788b-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c788b-108">Дополнительные сведения см. в разделе [Что такое Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="c788b-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="c788b-109">Убедитесь, что у вас имеется подписки на Office 365 по меньшей мере уровня E3.</span><span class="sxs-lookup"><span data-stu-id="c788b-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="c788b-110">[Настройте многофакторную идентификацию](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="c788b-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="c788b-111">Убедитесь, что выбран параметр **Уведомление в мобильном приложении**.</span><span class="sxs-lookup"><span data-stu-id="c788b-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![параметры многофакторной идентификации](images/mfa-options.png)

- <span data-ttu-id="c788b-113">Включение размещения контента в службах Azure AD, таких как Office, SharePoint и т. д.</span><span class="sxs-lookup"><span data-stu-id="c788b-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="c788b-114">Устройство Surface Hub должно работать под управлением Windows 10 версии 1703 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c788b-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="c788b-115">Устройство Surface Hub должно быть настроено с помощью локальной учетной записи или учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="c788b-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

<span data-ttu-id="c788b-116">В настоящее время Microsoft Authenticator нельзя использовать для входа на устройства Surface Hub, которые присоединены к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c788b-116">Currently, you cannot use Microsoft Authenticator to sign in to Surface Hubs that are joined to Azure AD.</span></span>

## <span data-ttu-id="c788b-117">Необходимые условия для отдельных устройств</span><span class="sxs-lookup"><span data-stu-id="c788b-117">Individual prerequisites</span></span>

- <span data-ttu-id="c788b-118">Телефона под управлением Android версии 6.0 или более поздней или iPhone либо iPad под управлением iOS 9 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="c788b-118">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="c788b-119">Самая последняя версия приложения Microsoft Authenticator из соответствующего магазина</span><span class="sxs-lookup"><span data-stu-id="c788b-119">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="c788b-120">Версия приложения в iOS должна быть не ниже 5.4.0.</span><span class="sxs-lookup"><span data-stu-id="c788b-120">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="c788b-121">Приложение Microsoft Authenticator на телефонах под управлением операционной системы Windows не может использоваться для входа в Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c788b-121">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="c788b-122">На устройстве включен секретный код или экран блокировки</span><span class="sxs-lookup"><span data-stu-id="c788b-122">Passcode or screen lock on your device is enabled</span></span>

- <span data-ttu-id="c788b-123">Стандартный адрес электронной почты SMTP (пример: joe@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c788b-123">A standard SMTP email address (example: joe@contoso.com).</span></span> <span data-ttu-id="c788b-124">Нестандартные адреса электронной почты SMTP (пример: firstname.lastname@contoso.com) в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c788b-124">Non-standard or vanity SMTP email addresses (example: firstname.lastname@contoso.com) currently don’t work.</span></span>

## <span data-ttu-id="c788b-125">Настройка приложения Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c788b-125">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="c788b-126">Если на устройстве Android установлен корпоративный портал, удалите его перед установкой Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c788b-126">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="c788b-127">После установки приложения вы сможете переустановить корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="c788b-127">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="c788b-128">Если вы уже настроили Microsoft Authenticator на телефоне и зарегистрировали устройство, перейдите к разделу инструкции по входу.</span><span class="sxs-lookup"><span data-stu-id="c788b-128">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="c788b-129">Добавьте свою рабочую или учебную учетную запись в Microsoft Authenticator для многофакторной идентификации.</span><span class="sxs-lookup"><span data-stu-id="c788b-129">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="c788b-130">Вам потребуется QR-код, предоставленный вашим ИТ-отделом.</span><span class="sxs-lookup"><span data-stu-id="c788b-130">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="c788b-131">Дополнительные сведения см. в разделе [Начало работы с приложением Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span><span class="sxs-lookup"><span data-stu-id="c788b-131">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="c788b-132">Перейдите в раздел **Параметры** и зарегистрируйте свое устройство.</span><span class="sxs-lookup"><span data-stu-id="c788b-132">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="c788b-133">Вернитесь на страницу учетных записей и выберите **Разрешение входа на телефоне** из раскрывающегося меню учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c788b-133">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <span data-ttu-id="c788b-134">Выполнение входа в Surface Hub во время собрания</span><span class="sxs-lookup"><span data-stu-id="c788b-134">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="c788b-135">После настройки собрания перейдите в Surface Hub и выберите пункт **Войдите, чтобы просмотреть свои собрания и файлы**.</span><span class="sxs-lookup"><span data-stu-id="c788b-135">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="c788b-136">Если вы не знаете, как запланировать собрание на Surface Hub, см. раздел [Планирование собраний на Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span><span class="sxs-lookup"><span data-stu-id="c788b-136">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![снимок экрана: параметр входа на Surface Hub](images/sign-in.png)

2. <span data-ttu-id="c788b-138">Вы увидите список людей, приглашенных на собрание.</span><span class="sxs-lookup"><span data-stu-id="c788b-138">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="c788b-139">Выберите себя (или того, кому необходимо выполнить вход, — убедитесь, что этот человек прошел все шаги для настройки своего устройства перед собранием), а затем выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="c788b-139">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![снимок экрана: список участников собрания](images/attendees.png)

    <span data-ttu-id="c788b-141">Вы увидите код на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c788b-141">You'll see a code on the Surface Hub.</span></span>

    ![снимок экрана: код для подтверждения входа в систему](images/approve-signin.png)

3. <span data-ttu-id="c788b-143">Для подтверждения входа откройте приложение Microsoft Authenticator, введите код из четырех цифр, отображаемый на Surface Hub, и выберите **Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="c788b-143">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="c788b-144">Затем потребуется ввести ПИН-код или использовать отпечаток пальца, чтобы завершить вход.</span><span class="sxs-lookup"><span data-stu-id="c788b-144">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![снимок экрана подтверждения входа в приложении Microsoft Authenticator](images/approve-signin2.png)

<span data-ttu-id="c788b-146">Теперь можно получить доступ ко всем файлам с помощью приложения OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c788b-146">You can now access all files through the OneDrive app.</span></span>