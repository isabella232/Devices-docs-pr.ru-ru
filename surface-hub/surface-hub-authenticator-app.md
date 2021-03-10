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
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400740"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a>Вход в Surface Hub с помощью проверки Microsoft Authenticator

Сотрудники вашей организации могут выполнить вход в систему на Surface Hub без ввода пароля с помощью приложения Microsoft Authenticator, доступного для iOS и Android.

## <a name="organization-prerequisites"></a>Необходимые условия для организации

Чтобы разрешить сотрудникам организации выполнять вход в Surface Hub с помощью телефонов и других устройствах вместо использования пароля, необходимо убедиться, что организация соответствует следующим требованиям. 

- Организация должна быть гибридной или облачной и использовать Azure Active Directory (Azure AD). Дополнительные сведения см. в разделе [Что такое Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)

- Убедитесь, что у вас имеется подписки на Office 365 по меньшей мере уровня E3. 

- [Настройте многофакторную идентификацию](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings). Убедитесь, что выбран параметр **Уведомление в мобильном приложении**. 

    ![параметры многофакторной идентификации](images/mfa-options.png)

- Включить размещение контента в службах Azure AD, таких как Office, SharePoint и т.д. 

- Устройство Surface Hub должно работать под управлением Windows 10 версии 1703 или более поздней версии.

- Устройство Surface Hub должно быть настроено с помощью локальной учетной записи или учетной записи домена.

## <a name="individual-prerequisites"></a>Необходимые условия для отдельных устройств

- Телефона под управлением Android версии 6.0 или более поздней или iPhone либо iPad под управлением iOS 9 или более поздней версии 

- Самая последняя версия приложения Microsoft Authenticator из соответствующего магазина

    >[!NOTE]
    >Версия приложения в iOS должна быть не ниже 5.4.0.
    >
    >Приложение Microsoft Authenticator на телефонах под управлением операционной системы Windows не может использоваться для входа в Surface Hub.

- На устройстве включен секретный код или экран блокировки

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a>Настройка приложения Microsoft Authenticator

>[!NOTE]
>Если на устройстве Android установлен корпоративный портал, удалите его перед установкой Microsoft Authenticator. После установки приложения вы сможете переустановить корпоративный портал.
>
>Если вы уже настроили Microsoft Authenticator на телефоне и зарегистрировали устройство, перейдите к разделу инструкции по входу.

1. Добавьте свою рабочую или учебную учетную запись в Microsoft Authenticator для многофакторной идентификации. Вам потребуется QR-код, предоставленный вашим ИТ-отделом. Дополнительные сведения см. в разделе [Начало работы с приложением Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).
2. Перейдите в раздел **Параметры** и зарегистрируйте свое устройство.
3. Вернитесь на страницу учетных записей и выберите **Разрешение входа на телефоне** из раскрывающегося меню учетной записи.

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a>Выполнение входа в Surface Hub во время собрания

1. После настройки собрания перейдите в Surface Hub и выберите пункт **Войдите, чтобы просмотреть свои собрания и файлы**.

    >[!NOTE]
    >Если вы не знаете, как запланировать собрание на Surface Hub, см. раздел [Планирование собраний на Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).

    ![снимок экрана: параметр входа на Surface Hub](images/sign-in.png)

2. Вы увидите список людей, приглашенных на собрание. Выберите себя (или того, кому необходимо выполнить вход, — убедитесь, что этот человек прошел все шаги для настройки своего устройства перед собранием), а затем выберите **Продолжить**.

    ![снимок экрана: список участников собрания](images/attendees.png)

    Вы увидите код на устройстве Surface Hub.

    ![снимок экрана: код для подтверждения входа в систему](images/approve-signin.png)

3. Для подтверждения входа откройте приложение Microsoft Authenticator, введите код из четырех цифр, отображаемый на Surface Hub, и выберите **Подтвердить**. Затем потребуется ввести ПИН-код или использовать отпечаток пальца, чтобы завершить вход. 

    ![снимок экрана подтверждения входа в приложении Microsoft Authenticator](images/approve-signin2.png)

Теперь можно получить доступ ко всем файлам с помощью приложения OneDrive.
