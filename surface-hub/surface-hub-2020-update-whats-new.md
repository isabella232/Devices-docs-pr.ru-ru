---
title: Новые возможности обновления 2020 Windows 10 для совместной работы 2020 г.
description: Ознакомьтесь с новыми обновлениями операционной системы Surface Hub 2020 Windows 10 для совместной работы обновления.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448272"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Новые возможности обновления 2020 Windows 10 для совместной работы 2020 г.

Surface Hub от периодических обновлений, которые обеспечивают новые функции и функции. Обновление 2020 (20H2) для Windows 10 для совместной работы и последующее обновление 1 & Update 2 обеспечивают значительные улучшения развертывания и управляемости устройств наряду с последними Windows 10 функциями.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 для совместной работы 2020 Обновление 2 

### <a name="gcc-high-support"></a>GCC высокая поддержка

После установки этого обновления ([KB5010415](https://support.microsoft.com/help/5010415) или последующего Windows cu) surface Hubs поддерживаются в GCC среде. В настоящее [время для ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) успешного подключения Комнаты Teams клиента к GCC клиенты High необходимы дополнительные действия.

### <a name="ease-of-access-updates"></a>Простота обновлений доступа

Пользователи могут настраивать параметры простоты доступа во время сеанса Surface Hub и закрывать приложения так же, как и в других версиях Windows 10. 

- **Простота доступа**. Пользователи могут настроить следующие параметры без входов: Display, Text cursor, Magnifier, High Contrast, Narrator, Closed captions и Keyboard. 
- **Знакомый пользовательский интерфейс для приложений**. Пользователи могут закрыть приложения Surface Hub, выбрав кнопку Закрыть в правом верхнем углу приложения. Это устраняет необходимость закрытия приложений, перетаскивание их в нижней части Surface Hub экрана. (Примечание. Эта функция будет доступна в браузере Edge в рамках следующего обновления Edge, запланированного на март 2022 г.). 

Дополнительные дополнительные возможности см[. в дополнительных параметрах Adjust Ease of Access в Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Обновления администратора

- **Просмотр событий**. Администраторы могут получить доступ к Windows просмотра событий непосредственно из Параметры приложения. 
- **Новые параметры политики управления мобильными устройствами (MDM**). Новые поставщики служб конфигурации (CSP) включают:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Дополнительные дополнительные новости см. в [рубрезе Настройка](surface-hub-2s-nonglobal-admin.md) учетных записей администратора не глобального масштаба на Surface Hub.


## <a name="windows-10-team-2020-update-1"></a>Windows 10 для совместной работы 2020 Обновление 1

### <a name="support-for-new-teams-rooms-application"></a>Поддержка нового Комнаты Teams приложения

После установки этого обновления ([KB5005101](https://support.microsoft.com/help/5005101) или последующего Windows cu) Surface Hubs поддерживает автоматическое обновление до нового клиента Комнаты Teams через Windows Update[](surface-hub-teams-rooms.md).

### <a name="support-for-new-whiteboard-application"></a>Поддержка нового приложения доски

После установки этого обновления Surface Hubs поддерживает автоматическое обновление (при наличии) для нового приложения [доски](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) Microsoft Store обновлений.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Новый Microsoft Edge браузер, установленный по умолчанию

После установки этого обновления surface Hubs автоматически заменит устаревшая версия Microsoft Edge браузера на новый Chromium браузер Edge.  Дополнительные дополнительные дополнительные [Microsoft Edge в Surface Hub](surface-hub-install-chromium-edge.md). Edge Legacy больше не доступен Windows 10 для совместной работы после установки этого обновления или последующего Windows cu.


## <a name="windows-10-team-2020-update-20h2"></a>Обновление Windows 10 для совместной работы 2020 (20H2)

### <a name="deployment-and-manageability"></a>Развертывание и управляемость

- **Современная проверка подлинности для учетных записей облачных устройств**. Surface Hub поддерживает проверку подлинности Exchange веб-служб (EWS) и библиотеки проверки подлинности Active Directory (ADAL), чтобы подключиться к Exchange, что позволяет клиентам не применять базовую проверку подлинности. Дополнительные дополнительные информации см[. в сайте Modern authentication on Surface Hub](surface-hub-modern-auth.md).
- **Более 20 новых и обновленных параметров политики MDM**.  Эти параметры политики дают ИТ-администраторам улучшенный контроль над несколькими настройками устройств, включая обновления приложений из Microsoft Store, параметры беспроводной проекции, такие как Miracast над инфраструктурой, сетевые параметры, такие как Quality-Of-Service и 802.1x проводной проверки подлинности, а также новые параметры конфиденциальности и GDPR. Новые CSP включают в себя:

  - [Поставщик служб конфигурации учетных записей](/windows/client-management/mdm/accounts-csp)
  - [Брандмауэр-CSP](/windows/client-management/mdm/firewall-csp)
  - [Поставщик служб конфигурации RemoteWipe](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Дополнительные дополнительные информации см. в.

- [CSPs, поддерживаемые в Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Управление Surface Hub с помощью поставщика MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory подключились устройства

- **Единый вход (SSO) для устройств Azure AD**. При входе в Microsoft 365 учетных данных в мои собрания и **** файлы их учетные данные плавно перетекают из приложения в приложение, в том числе Microsoft 365 в браузере.
- **Условный доступ (CA) для присоединенных устройств Azure AD**. ИТ-администраторы могут управлять доступом пользователей к организационным ресурсам из присоединенных к Surface Hubs Azure AD, назначая политики устройств в соответствии с требованиями корпоративной безопасности и соответствия требованиям.
- **Поддержка не глобальных администраторов для устройств Azure AD.** Клиенты могут выбрать более детализированный набор администраторов в иерархии администраторов для управления Surface Hub. Дополнительные дополнительные новости см. в [рубрезе Настройка](surface-hub-2s-nonglobal-admin.md) учетных записей администратора не глобального масштаба на Surface Hub.

### <a name="inking-improvements"></a>Inking improvements

- **Поддержка двух перьев в Surface Hub 2S**.  Используйте доску и совместное взаимодействие на Surface Hub 2S с двумя Surface Hub 2 ручками. Любое обновление системного оборудования, установленное после обновления Windows 10 для совместной работы 2020 г., добавит поддержку прошивки для этого сценария.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams по умолчанию**. Microsoft Teams включено в качестве приложения по умолчанию для собраний, вызовов и совместной работы на новых устройствах Surface Hub, которые можно изменить или настроить с помощью MDM или непосредственно Surface Hub с помощью Параметры приложения. Дополнительные дополнительные информации см. [в Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Поддержка близости Присоединиться к Microsoft Teams**.  Proximity Join позволяет пользователям принимать запланированные Microsoft Teams вызовы по Surface Hub с помощью ноутбука или телефона.  Кроме того, он позволяет пользователям перейти на собрание, на которое находится Surface Hub. Windows 10 для совместной работы обновления 2020 добавляет поддержку управления мобильными устройствами (MDM) для настройки proximity Join. Дополнительные дополнительные информации см. в.

  - [Microsoft Teams блог](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Управление настройками Microsoft Teams на Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Поддержка согласованных собраний с Microsoft Teams**. В комнатах собраний с Surface Hub и устройством Microsoft Teams Room или пространствах с двумя устройствами Surface Hub, координированные собрания позволяет пользователям быстро использовать оба устройства во время Microsoft Teams собрания. Пользователи могут присоединяться к собранию с любого устройства одним касанием и максимизировать экранную недвижимость, показывая видео-каналы на одном устройстве и цифровую доску или контент на другом. Windows 10 для совместной работы 2020 г. Обновление добавляет поддержку управления мобильными устройствами (MDM) для настройки скоординированных собраний, и эта функция будет впоследствии выпущена в качестве обновления Microsoft Teams через Microsoft Store. Дополнительные новости см. в [ссылке Настройка согласованных собраний с Комнаты Microsoft Teams и Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>Безопасность

- **Вход без паролей с помощью ключей безопасности FIDO2** С помощью ключей безопасности FIDO2 пользователи могут быстро войти в Surface Hub без ввода имен пользователей и паролей. В сочетании с single Sign-On (SSO) эта функция обеспечивает быструю и бесшовную проверку подлинности файлов, приложений и веб-сайтов во время собрания. Дополнительные дополнительные информации см. [в документе Настройка](surface-hub-2s-phone-authenticate.md) входных записей без паролей на Surface Hub.
- **Улучшения без паролей при входе с Microsoft Authenticator**.  Для организаций, которые используют Azure AD, пользователи могут войти в Microsoft Authenticator приложение. Кроме того, пользователи могут войти со своими предпочтительными псевдонимами электронной почты в Azure AD, а также их главным именем пользователя (UPN). Дополнительные дополнительные ссылки см. в Surface Hub [с Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Подробнее

- [Windows 10 для совместной работы 2020 обновление 1 выпущено для всех концентраторов Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 для совместной работы 2020 Обновление доступно 27 октября](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Установка обновления Windows 10 для совместной работы 2020](surface-hub-2020-update.md)
