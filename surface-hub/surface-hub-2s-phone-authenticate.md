---
title: Настройка входа без пароля на Surface HUB
description: В этой статье объясняется, как упростить вход на Surface Hub.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893051"
---
# <span data-ttu-id="3aafb-104">Настройка входа без пароля на Surface HUB</span><span class="sxs-lookup"><span data-stu-id="3aafb-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="3aafb-105">Вход без пароля упрощает доступ к приложениям, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="3aafb-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="3aafb-106">Surface Hub поддерживает вход в систему с помощью приложения Microsoft Authenticator и ключей безопасности FIDO2, предоставленных вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="3aafb-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="3aafb-107">**Внимание!** Это содержимое предназначено для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3aafb-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="3aafb-108">Чтобы использовать учетную запись без пароля, ИТ-администратор должен включить для вашей организации проверку подлинности, не защищенную паролем.</span><span class="sxs-lookup"><span data-stu-id="3aafb-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="3aafb-109">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3aafb-109">For more information, see:</span></span>

- [<span data-ttu-id="3aafb-110">Включить вход на мобильный телефон с паролем</span><span class="sxs-lookup"><span data-stu-id="3aafb-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="3aafb-111">Включить вход в ключ безопасности без пароля</span><span class="sxs-lookup"><span data-stu-id="3aafb-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="3aafb-112">Настройка входа с помощью приложения Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3aafb-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="3aafb-113">**Примечание.** Начиная с Windows 10 Team 2020, пользователи могут использовать свои предпочтительные псевдонимы электронной почты в Azure AD, а также их имя участника-пользователя (UPN) для входа в систему с помощью средства проверки подлинности Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3aafb-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="3aafb-114">Например, пользователь может использовать либо предпочтительный псевдоним (John.Doe@contoso.com), либо его UPN (jdoe@contoso.com) для входа.</span><span class="sxs-lookup"><span data-stu-id="3aafb-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="3aafb-115">Приложение Microsoft Authenticator поможет вам войти на Surface Hub с помощью мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="3aafb-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="3aafb-116">Чтобы настроить вход с помощью средства проверки подлинности Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3aafb-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="3aafb-117">На мобильном устройстве Скачайте приложение Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3aafb-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="3aafb-118">Google Android: на устройстве с Android перейдите в Google Play, чтобы [скачать и установить приложение Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span><span class="sxs-lookup"><span data-stu-id="3aafb-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="3aafb-119">Apple iOS: на устройстве Apple iOS перейдите в магазин приложений, чтобы [скачать и установить приложение Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span><span class="sxs-lookup"><span data-stu-id="3aafb-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="3aafb-120">На компьютере [Настройте приложение Microsoft Authenticator на странице "сведения о безопасности"](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) для своей рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3aafb-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="3aafb-121">В приложении Microsoft Authenticator на мобильном устройстве [включите и воспользуйтесь входом на телефоне](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) для своей рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3aafb-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="3aafb-122">Настройка входа с помощью ключей безопасности FIDO2</span><span class="sxs-lookup"><span data-stu-id="3aafb-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="3aafb-123">Для входа без пароля на Surface Hub с помощью ключей безопасности FIDO2 требуется обновление Windows 10 Team 2020.</span><span class="sxs-lookup"><span data-stu-id="3aafb-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aafb-124">Surface Hub поддерживает только ключи контроля доступа USB.</span><span class="sxs-lookup"><span data-stu-id="3aafb-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="3aafb-125">Вы также можете войти на Surface Hub, используя ключ безопасности FIDO2, предоставленный вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="3aafb-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="3aafb-126">Чтобы настроить вход с помощью ключа безопасности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3aafb-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="3aafb-127">На компьютере перейдите на свою [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) страницу и войдите в свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="3aafb-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="3aafb-128">В области навигации слева выберите пункт **сведения о безопасности** или щелкните ссылку в блоке **сведений** о безопасности, а затем нажмите кнопку **Добавить метод** на странице **сведения о безопасности** .</span><span class="sxs-lookup"><span data-stu-id="3aafb-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="3aafb-129">На странице **Добавление метода** в раскрывающемся списке выберите **ключ безопасности** , а затем нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3aafb-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="3aafb-130">На странице **ключа контроля доступа** выберите **USB-устройство**.</span><span class="sxs-lookup"><span data-stu-id="3aafb-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="3aafb-131">Обновите свой ключ безопасности и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3aafb-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="3aafb-132">В появившемся диалоговом окне следуйте инструкциям по добавлению ключа безопасности, созданию или вводу ПИН-кода и выполнению требуемого жеста (биометрического или сенсорного ввода).</span><span class="sxs-lookup"><span data-stu-id="3aafb-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="3aafb-133">На странице **ключа контроля доступа** введите имя ключа безопасности и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3aafb-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="3aafb-134">Нажмите кнопку **Готово** , чтобы завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="3aafb-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="3aafb-135">Вход на Surface HUB</span><span class="sxs-lookup"><span data-stu-id="3aafb-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="3aafb-136">После того как вы настроили вход без пароля, вы можете использовать его для более удобного доступа к приложениям, собраниям и файлам на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="3aafb-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="3aafb-137">Вы можете быстро присоединиться к собраниям и открыть последние файлы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3aafb-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="3aafb-138">Дополнительные сведения можно найти в разделе [**Вход, чтобы просмотреть свои собрания и файлы**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span><span class="sxs-lookup"><span data-stu-id="3aafb-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="3aafb-139">Быстрый вход в приложения Microsoft, например доска, PowerPoint, Word, Excel, OneDrive и Power BI.</span><span class="sxs-lookup"><span data-stu-id="3aafb-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="3aafb-140">Вы можете быстро войти в новый Microsoft EDGE, чтобы получить доступ к избранным и вашим настройкам просмотра.</span><span class="sxs-lookup"><span data-stu-id="3aafb-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="3aafb-141">Дополнительные сведения можно найти [в разделе Установка и настройка нового приложения Microsoft Edge](surface-hub-install-chromium-edge.md).</span><span class="sxs-lookup"><span data-stu-id="3aafb-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="3aafb-142">Войдя в Surface Hub, вы можете использовать другие приложения, не входя в нее, пока не будет выбрано значение **завершить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="3aafb-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="3aafb-143">Нажмите кнопку **завершить сеанс** , чтобы удалить с устройства учетные данные, файлы и личные данные.</span><span class="sxs-lookup"><span data-stu-id="3aafb-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="3aafb-144">Дополнительные сведения можно найти в разделе [Завершение сеанса](finishing-your-surface-hub-meeting.md).</span><span class="sxs-lookup"><span data-stu-id="3aafb-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="3aafb-145">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3aafb-145">Learn more</span></span>

- [<span data-ttu-id="3aafb-146">Параметры проверки подлинности с учетом пароля для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3aafb-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="3aafb-147">Вход без пароля с помощью приложения Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3aafb-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="3aafb-148">Вход без пароля с помощью ключей безопасности FIDO2</span><span class="sxs-lookup"><span data-stu-id="3aafb-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

