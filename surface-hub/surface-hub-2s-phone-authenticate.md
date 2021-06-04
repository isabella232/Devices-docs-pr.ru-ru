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
# Настройка входа без пароля на Surface HUB

 
Вход без пароля упрощает доступ к приложениям, собраниям и файлам. Surface Hub поддерживает вход в систему с помощью приложения Microsoft Authenticator и ключей безопасности FIDO2, предоставленных вашей организацией.

**Внимание!** Это содержимое предназначено для пользователей. Чтобы использовать учетную запись без пароля, ИТ-администратор должен включить для вашей организации проверку подлинности, не защищенную паролем. Дополнительные сведения см. в следующих разделах:

- [Включить вход на мобильный телефон с паролем](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Включить вход в ключ безопасности без пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


##  <a name="configure-sign-in-using-microsoft-authenticator-app"></a>Настройка входа с помощью приложения Microsoft Authenticator

**Примечание.** Начиная с Windows 10 Team 2020, пользователи могут использовать свои предпочтительные псевдонимы электронной почты в Azure AD, а также их имя участника-пользователя (UPN) для входа в систему с помощью средства проверки подлинности Microsoft. Например, пользователь может использовать либо предпочтительный псевдоним (John.Doe@contoso.com), либо его UPN (jdoe@contoso.com) для входа.
 
Приложение Microsoft Authenticator поможет вам войти на Surface Hub с помощью мобильного устройства. Чтобы настроить вход с помощью средства проверки подлинности Microsoft:


1. На мобильном устройстве Скачайте приложение Microsoft Authenticator.
    - Google Android: на устройстве с Android перейдите в Google Play, чтобы [скачать и установить приложение Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: на устройстве Apple iOS перейдите в магазин приложений, чтобы [скачать и установить приложение Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. На компьютере [Настройте приложение Microsoft Authenticator на странице "сведения о безопасности"](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) для своей рабочей или учебной учетной записи.
3. В приложении Microsoft Authenticator на мобильном устройстве [включите и воспользуйтесь входом на телефоне](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) для своей рабочей или учебной учетной записи.

 
##  <a name="configure-sign-in-using-fido2-security-keys"></a>Настройка входа с помощью ключей безопасности FIDO2

> [!NOTE]
>  Для входа без пароля на Surface Hub с помощью ключей безопасности FIDO2 требуется обновление Windows 10 Team 2020.

> [!IMPORTANT]
> Surface Hub поддерживает только ключи контроля доступа USB.
 
Вы также можете войти на Surface Hub, используя ключ безопасности FIDO2, предоставленный вашей организацией. 

###  <a name="to-configure-sign-in-using-a-security-key"></a>Чтобы настроить вход с помощью ключа безопасности, выполните указанные ниже действия.


1. На компьютере перейдите на свою [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) страницу и войдите в свою рабочую или учебную учетную запись.
2. В области навигации слева выберите пункт **сведения о безопасности** или щелкните ссылку в блоке **сведений** о безопасности, а затем нажмите кнопку **Добавить метод** на странице **сведения о безопасности** .
3. На странице **Добавление метода** в раскрывающемся списке выберите **ключ безопасности** , а затем нажмите кнопку **добавить**.
4. На странице **ключа контроля доступа** выберите **USB-устройство**.
5. Обновите свой ключ безопасности и нажмите кнопку **Далее**.
6. В появившемся диалоговом окне следуйте инструкциям по добавлению ключа безопасности, созданию или вводу ПИН-кода и выполнению требуемого жеста (биометрического или сенсорного ввода).
7. На странице **ключа контроля доступа** введите имя ключа безопасности и нажмите кнопку **Далее**.
8. Нажмите кнопку **Готово** , чтобы завершить процесс.

##  <a name="sign-in-to-surface-hub"></a>Вход на Surface HUB

После того как вы настроили вход без пароля, вы можете использовать его для более удобного доступа к приложениям, собраниям и файлам на Surface Hub.

- Вы можете быстро присоединиться к собраниям и открыть последние файлы Microsoft 365. Дополнительные сведения можно найти в разделе [**Вход, чтобы просмотреть свои собрания и файлы**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Быстрый вход в приложения Microsoft, например доска, PowerPoint, Word, Excel, OneDrive и Power BI.
- Вы можете быстро войти в новый Microsoft EDGE, чтобы получить доступ к избранным и вашим настройкам просмотра. Дополнительные сведения можно найти [в разделе Установка и настройка нового приложения Microsoft Edge](surface-hub-install-chromium-edge.md).
- Войдя в Surface Hub, вы можете использовать другие приложения, не входя в нее, пока не будет выбрано значение **завершить сеанс**. Нажмите кнопку **завершить сеанс** , чтобы удалить с устройства учетные данные, файлы и личные данные. Дополнительные сведения можно найти в разделе [Завершение сеанса](finishing-your-surface-hub-meeting.md).


##  <a name="learn-more"></a>Подробнее

- [Параметры проверки подлинности с учетом пароля для Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Вход без пароля с помощью приложения Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Вход без пароля с помощью ключей безопасности FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

