---
title: Настройка входа без пароля на Surface Hub
description: Узнайте, как упростить вход в Surface Hub.
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
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101184"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>Настройка входа без пароля на Surface Hub

 
Вход без паролей упрощает доступ к приложениям, собраниям и файлам. Surface Hub поддерживает вход с помощью Microsoft Authenticator приложения и ключей безопасности FIDO2, предоставляемых вашей организацией.

**Важно:** Этот контент предназначен для пользователей. Чтобы использовать вход без паролей, ИТ-администратор должен включить проверку подлинности без паролей для вашей организации. Дополнительные сведения см. в следующих разделах:

- [Включить вход в телефон без паролей](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Включить вход ключа безопасности без паролей](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>Настройка входных ок с помощью Microsoft Authenticator приложения

**Примечание:** Начиная с обновления Windows 10 для совместной работы 2020 г. пользователи могут использовать свои предпочтительные псевдонимы электронной почты в Azure AD, а также свое имя пользователя (UPN), чтобы войти в Microsoft Authenticator. Например, пользователь может использовать для регистрации либо предпочтительный псевдоним (John.Doe@contoso.com), либо jdoe@contoso.com.
 
Приложение Microsoft Authenticator помогает вам войти в Surface Hub с помощью мобильного устройства. Настройка входных ок. с помощью Microsoft Authenticator:


1. На мобильном устройстве скачайте Microsoft Authenticator приложение.
    - Google Android. На устройстве Android перейдите в Google Play, чтобы скачать и установить [приложение Microsoft Authenticator.](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)
    - Apple iOS. На устройстве Apple iOS перейдите в Магазин Приложений, чтобы скачать и установить [Microsoft Authenticator.](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)
2. На компьютере настройка [приложения Microsoft Authenticator на странице Сведения](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) о безопасности для вашей работы или учебной учетной записи.
3. Из приложения Microsoft Authenticator на мобильном устройстве [включите](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) и используйте вход телефона для работы или учетной записи школы.

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>Настройка входных данных с помощью ключей безопасности FIDO2

> [!NOTE]
>  Для регистрации без паролей на Surface Hub с помощью ключей безопасности FIDO2 требуется обновление Windows 10 для совместной работы 2020 года.

> [!IMPORTANT]
> Surface Hub поддерживает только клавиши безопасности USB.
 
Вы также можете войти в Surface Hub с помощью ключа безопасности FIDO2, предоставленного вашей организацией. 

### <a name="to-configure-sign-in-using-a-security-key"></a>Настройка входных данных с помощью ключа безопасности:


1. На компьютере перейдите на [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) страницу и войдите в свою работу или учетную запись школы.
2. Выберите **сведения о безопасности** на левой области навигации или по ссылке в блоке Сведения о безопасности, а затем выберите метод **Добавить** на странице **Сведения о безопасности.** ****
3. На странице **Добавление метода** выберите клавишу **Безопасности** из отпадаемого списка и выберите **Добавить**.
4. На странице **Ключ безопасности** выберите **USB-устройство.**
5. Подготовь ключ безопасности и выберите **Далее.**
6. В диалоговом окне, который появляется, следуйте инструкциям, чтобы вставить ключ безопасности, создать или ввести ПИН-код, и выполнить необходимый жест (биометрический или сенсорный).
7. На странице **Ключ безопасности** дайте ключу безопасности имя, а затем выберите **Далее**.
8. Выберите **Сделано** для завершения процесса.

## <a name="sign-in-to-surface-hub"></a>Вход в Surface Hub

После настройки входной записи без паролей вы можете использовать его, чтобы упростить доступ к приложениям, собраниям и файлам в Surface Hub:

- Быстро присоединяйся к собраниям и открывай последние Microsoft 365 файлы. Дополнительные сведения см. в [**документе Вход, чтобы увидеть собрания и файлы.**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)
- Быстро вопишитесь в приложения Майкрософт, такие как Доска, PowerPoint, Word, Excel, OneDrive и Power BI.
- Быстро впишитесь в новый Microsoft Edge, чтобы получить доступ к вашим предпочтениям и предпочтениям просмотра. Дополнительные сведения см. в [перенастройке](surface-hub-install-chromium-edge.md)и настройке нового Microsoft Edge.
- После того как вы зарегистрировались в Surface Hub, вы можете использовать другие приложения без необходимости снова входить, пока не выберите **конечный сеанс**. Выбор **сеанса End удаляет** учетные данные, файлы и личные данные с устройства. Дополнительные сведения см. в конце [сеанса](finishing-your-surface-hub-meeting.md).


## <a name="learn-more"></a>Подробнее

- [Параметры проверки подлинности без паролей для Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [Вход без паролей с приложением Microsoft Authenticator](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Вход без паролей с помощью ключей безопасности FIDO2](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

