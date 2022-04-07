---
title: Новые возможности обновлений Windows 10 для совместной работы 2020 г.
description: Узнайте, что нового в последнем обновлении операционной системы Surface Hub версии Windows 10 для совместной работы 2020.
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
ms.openlocfilehash: 6a35783c08fdc4da3b3c7aabcd99da385c292d24
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472538"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Новые возможности обновлений Windows 10 для совместной работы 2020 г.

Surface Hub преимущества периодических обновлений, которые предоставляют новые функции и функции. Обновление 2020 (20H2) для Windows 10 для совместной работы, а затем обновление 1 & с обновлением 2, обеспечивает значительные улучшения развертывания устройств и управляемости вместе с последними Windows 10.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 для совместной работы 2020 с обновлением 2 

### <a name="gcc-high-support"></a>GCC высокий уровень поддержки

После установки этого обновления ([KB5010415](https://support.microsoft.com/help/5010415) или последующего Windows CU) Surface Hub поддерживается в GCC средах с высоким уровнем доступности. В данный [момент для ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) успешного подключения клиента Комнаты Teams клиента GCC клиента с высоким уровнем доступности.

### <a name="support-for-surface-hub-2-smart-camera"></a>Поддержка интеллектуальной камеры Surface Hub 2

Смарт-камера на основе ИИ Surface Hub 2 оптимизирована для гибридных команд, позволяя удаленным участникам видеть, как пользователи взаимодействуют с содержимым на Surface Hub, а также просматривать других пользователей в комнате.  Дополнительные сведения см. в статье об установке [Surface Hub 2 Smart Camera](surface-hub-2-smart-camera.md) и управлении ими. 

### <a name="support-for-progressive-web-apps-pwas"></a>Поддержка прогрессивных веб-приложения (PWA)

Администраторы могут удаленно устанавливать PWA на Устройствах Surface Hub с помощью поставщика управления мобильными устройствами (MDM), применяя пакет подготовки. Дополнительные сведения см. в [статье "Установка веб-приложения на Surface Hub](install-pwa-surface-hub.md)". 

### <a name="ease-of-access-updates"></a>Обновления для специальных функций

Пользователи могут настраивать параметры специальных Surface Hub во время сеанса и закрывать приложения так же, как и в других версиях Windows 10. 

- **Специальные возможности**. Пользователи могут настраивать следующие параметры без входа: display, Text cursor, Magnifier, High contrast, Narrator, Closed captions и Keyboard. 
- **Знакомый пользовательский интерфейс для приложений**. Пользователи могут закрыть приложения в Surface Hub, нажатием кнопки "Закрыть" в правом верхнем углу приложения. Это устраняет необходимость закрытия приложений, перетаскивая их в нижнюю часть Surface Hub экрана. (Примечание. Эта функция будет доступна в браузере Edge в рамках следующего обновления Edge, запланированного на март 2022 г.). 

Дополнительные сведения см. в разделе "Настройка параметров простоты доступа[" Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Обновления администратора

- **Просмотр событий**. Администраторы могут получить доступ к Windows Просмотр событий непосредственно из Параметры приложения. 
- **Новые параметры политики управления мобильными устройствами (MDM**). Новые поставщики служб конфигурации (CSP) включают в себя:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Дополнительные сведения см. в статье "Настройка учетных записей администраторов, [не включаемого](surface-hub-2s-nonglobal-admin.md) в глобальный Surface Hub".


## <a name="windows-10-team-2020-update-1"></a>Windows 10 для совместной работы 2020 с обновлением 1

### <a name="support-for-new-teams-rooms-application"></a>Поддержка нового Комнаты Teams приложения

После установки этого обновления ([KB5005101](https://support.microsoft.com/help/5005101) или последующего Windows CU) Surface Hub поддерживает автоматическое обновление до нового клиента Комнаты Teams через клиентский компонент Центра обновления Windows.[](surface-hub-teams-rooms.md)

### <a name="support-for-new-whiteboard-application"></a>Поддержка нового приложения доски

После установки этого обновления Surface Hub поддерживает автоматическое обновление (если доступно) для нового приложения доски с [](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) помощью Microsoft Store обновлений.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Новый Microsoft Edge, установленный по умолчанию

После установки этого обновления Surface Hub автоматически заменит устаревшая версия Microsoft Edge браузера новым браузером Chromium Edge.  Дополнительные сведения см. в [Microsoft Edge на Surface Hub](surface-hub-install-chromium-edge.md). Устаревшая версия Edge больше недоступна Windows 10 для совместной работы после установки этого обновления или последующего Windows накопительного пакета обновления.


## <a name="windows-10-team-2020-update-20h2"></a>Обновление Windows 10 для совместной работы 2020 (20H2)

### <a name="deployment-and-manageability"></a>Развертывание и управляемость

- **Современная проверка подлинности для учетных записей облачных устройств**. Surface Hub поддерживает проверку подлинности на основе Exchange веб-служб (EWS) и библиотеки проверки подлинности Active Directory (ADAL) для подключения к Exchange, что позволяет клиентам не рекомендуется использовать обычную проверку подлинности. Дополнительные сведения см. в [разделе "Современная проверка подлинности" Surface Hub](surface-hub-modern-auth.md).
- **Более 20 новых и обновленных параметров политики MDM**.  Эти параметры политики предоставляют ИТ-администраторам улучшенный контроль над несколькими параметрами устройства, включая обновления приложений из Microsoft Store, параметры беспроводной проекции, такие как Miracast через инфраструктуру, сетевые параметры, такие как качество обслуживания и проводная проверка подлинности 802.1x, а также новые параметры конфиденциальности и GDPR. К новым CSP относятся:

  - [Поставщик служб конфигурации учетных записей](/windows/client-management/mdm/accounts-csp)
  - [Брандмауэр-CSP](/windows/client-management/mdm/firewall-csp)
  - [Поставщик служб конфигурации RemoteWipe](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Дополнительные сведения см. в следующих статьях:

- [CSP, поддерживаемые в Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Управление Surface Hub с помощью поставщика MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory присоединенных устройств

- **Единый вход (SSO) для устройств, присоединенных к Azure AD**. При входе пользователей с Microsoft 365 учетными данными на мои **** собрания и файлы их учетные данные легко перенабесят из приложения в приложение, включая Microsoft 365 в браузере.
- **Условный доступ (ЦС) для устройств, присоединенных к Azure AD**. ИТ-администраторы могут управлять доступом пользователей к ресурсам организации из устройств Surface Hub, присоединенных к Azure AD, назначая политики устройств в соответствии с корпоративными требованиями к безопасности и соответствию.
- **Поддержка не глобальных администраторов для устройств, присоединенных к Azure AD**. Клиенты могут выбрать более детализированный набор администраторов в иерархии администраторов для управления Surface Hub. Дополнительные сведения см. в статье "Настройка учетных записей администраторов, [не включаемого](surface-hub-2s-nonglobal-admin.md) в глобальный Surface Hub".

### <a name="inking-improvements"></a>Улучшения рукописного ввода

- **Поддержка рукописного ввода с двумя перьев в Surface Hub 2S**.  Используйте доску и работайте параллельно на Surface Hub 2S с двумя Surface Hub 2 перьев. Любое обновление системного оборудования, установленное после обновления до Windows 10 для совместной работы 2020 г., добавит поддержку встроенного ПО для этого сценария.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams устанавливается по умолчанию**. Microsoft Teams является приложением по умолчанию для собраний, звонков и совместной работы на новых устройствах Surface Hub, которые можно изменить или настроить с помощью MDM или непосредственно Surface Hub с помощью Параметры приложения. Дополнительные сведения см. в статье [Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Поддержка соединения близкого взаимодействия с Microsoft Teams**.  Присоединение к близкому подключению позволяет пользователям выполнять запланированные Microsoft Teams вызовы на Surface Hub с помощью ноутбука или телефона.  Он также позволяет пользователям переназначить существующее собрание в ближайший Surface Hub. Windows 10 для совместной работы обновления 2020 добавляет поддержку мобильных Управление устройствами (MDM) для настройки присоединения к близкому соединению. Дополнительные сведения см. в следующих статьях:

  - [Microsoft Teams блог](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Управление настройками Microsoft Teams на Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Поддержка координированного собрания с Microsoft Teams**. В комнатах для собраний с Surface Hub и устройством комнаты Microsoft Teams или пробелами с двумя устройствами Surface Hub, координированное собрание позволяет пользователям быстро использовать оба устройства во время Microsoft Teams собрания. Пользователи могут присоединяться к собранию с любого устройства одним касанием и разворачивать экранные пространства, отображая видеопотоки на одном устройстве и цифровую доску или содержимое на другом. Windows 10 для совместной работы 2020 г. добавлена поддержка мобильных Управление устройствами (MDM) для настройки координированных собраний, и эта функция будет впоследствии выпущена как обновление Microsoft Teams через Microsoft Store. Дополнительные сведения см. в статье ["Настройка скоординированных собраний с помощью Комнаты Microsoft Teams и Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings)".

### <a name="security"></a>Безопасность

- **Вход без пароля с помощью ключей безопасности FIDO2** С помощью ключей безопасности FIDO2 пользователи могут быстро войти в Surface Hub, не введя имена пользователей и пароли. В сочетании с единым Sign-On (SSO) эта функция обеспечивает быструю и удобную проверку подлинности для файлов, приложений и веб-сайтов во время собрания. Дополнительные сведения см. в статье ["Настройка входа без пароля на](surface-hub-2s-phone-authenticate.md) Surface Hub".
- **Улучшения входа без пароля с помощью Microsoft Authenticator**.  Для организаций, использующих Azure AD, пользователи могут выполнять вход с помощью Microsoft Authenticator приложения. Кроме того, пользователи могут выполнять вход с помощью предпочитаемых псевдонимов электронной почты в Azure AD или имени участника-пользователя (UPN). Дополнительные сведения см. в статье о входе [Surface Hub с помощью Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Подробнее

- [Windows 10 для совместной работы 2020 с обновлением 1, выпущенное для всех устройств Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 для совместной работы 2020 г., доступное 27 октября](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Установка обновления Windows 10 для совместной работы 2020](surface-hub-2020-update.md)
