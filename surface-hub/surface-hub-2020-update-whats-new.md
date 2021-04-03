---
title: Новые возможности обновления Windows 10 для совместной работы 2020
description: Узнайте, что нового нового в последнем обновлении операционной системы Surface Hub Windows 10 Team 2020 Update.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 14e08cf099ac441f7b2b3b76366406868ac6c056
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470427"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Новые возможности обновления Windows 10 для совместной работы 2020

Обновление Windows 10 Team 2020 позволяет существенно улучшить развертывание и управляемость устройств наряду с последними функциями Windows 10.

##  <a name="deployment-and-manageability"></a>Развертывание и управляемость

- **Современная проверка подлинности для учетных записей облачных устройств.** Surface Hub поддерживает проверку подлинности на основе Exchange Web Services (EWS) и Active Directory Authentication Library (ADAL), чтобы подключиться к Exchange, что позволяет клиентам ухудшить использование базовой проверки подлинности. Дополнительные дополнительные информации см. в [сайте Modern authentication on Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- Более 20 новых и обновленных параметров политики управления мобильными **устройствами (MDM).**  Эти параметры политики дают ИТ-администраторам улучшенный контроль над несколькими настройками устройств, включая обновления приложений из Microsoft Store, параметры беспроводной проекции, такие как Miracast над инфраструктурой, сетевые параметры, такие как Quality-Of-Service и 802.1x проводной проверки подлинности, а также новые параметры конфиденциальности и GDPR. Новые поставщики служб конфигурации (CSP) включают: 

  - [Поставщик служб конфигурации учетных записей](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) 
  - [Брандмауэр-CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) 
  - [Поставщик служб конфигурации RemoteWipe](https://docs.microsoft.com/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 

Дополнительные дополнительные информации см. в. 
- [CSPs, поддерживаемые в Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Управление surface Hub с поставщиком MDM](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Устройства Azure Active Directory

- **Единый вход (SSO) для устройств, присоединив Azure AD.** Когда пользователи включались с учетными данными Microsoft 365 в "Мои собрания и файлы", их учетные данные пользователей плавно перетекают из приложения в приложение, включая интерфейсы Microsoft 365 в браузере.
- **Условный доступ (CA) для присоединенных устройств Azure AD.**       ИТ-администраторы могут развертывать политики безопасности на уровне устройств в своих azure AD, присоединенных к Surface Hub, чтобы контролировать доступ к организационным ресурсам в соответствии с требованиями корпоративной безопасности и соответствия требованиям.
- **Поддержка не глобальных администраторов для устройств,** присоединив Azure AD. Клиенты могут выбрать более детализированный набор администраторов в иерархии администрирования для управления Surface Hub. Дополнительные дополнительные новости см. в [перенастройке учетных](surface-hub-2s-nonglobal-admin.md)записей не глобального администратора в Surface Hub.


## <a name="browser-and-pen"></a>Браузер и перо

- **Поддержка нового Microsoft Edge**. Microsoft Edge был перестроен для обеспечения оптимальной производительности, безопасности и конфиденциальности совместимости. Дополнительные дополнительные возможности см. в [веб-сайте Install and configure the new Microsoft Edge on Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- **Двумя перьями в Surface Hub 2S**.   Пользователи могут отбелить и совместно работать на Surface Hub 2S с помощью двух перьев Surface Hub 2. Обновления прошивки, необходимые для внося двойной пера, будут выпущены с последующим обновлением.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams, установленные по умолчанию.**        Microsoft Teams включена в качестве приложения для собраний, вызовов и совместной работы по умолчанию на новых устройствах Surface Hub, которые можно изменить или настроить с помощью MDM или непосредственно на Surface Hub с помощью приложения Параметры. Дополнительные дополнительные информации см. в [сайте Deploy Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Поддержка близости Присоединяйтесь к Microsoft Teams.**  Proximity Join позволяет пользователям принимать запланированные вызовы Microsoft Teams на соседнем Surface Hub с помощью ноутбука или телефона или плавно перенабирать в ходе выполнения собрания в расположенный неподалеку Surface Hub. Обновление Windows 10 Team 2020 добавляет поддержку управления мобильными устройствами (MDM) для настройки proximity Join. Дополнительные дополнительные информации см. в. 

  - [Блог Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Управление настройками Microsoft Teams на Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Поддержка согласованных собраний с Microsoft Teams.** В залах собраний с устройством Surface Hub и устройством Microsoft Teams Room или пространствами с двумя устройствами Surface Hub скоординированные собрания позволяют пользователям легко использовать оба устройства во время собрания Microsoft Teams. С помощью одного касания пользователи могут присоединяться к собранию с любого устройства и максимизировать экранную недвижимость, показывая видео-каналы на одном устройстве, а цифровую доску или контент на другом. Windows 10 Team 2020 Update добавляет поддержку управления мобильными устройствами (MDM) для настройки скоординированных собраний, и эта функция будет впоследствии выпущена в качестве обновления Microsoft Teams через Microsoft Store.To подробнее см. в статью Настройка скоординированных собраний с [Microsoft Teams Rooms и Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings).

## <a name="security"></a>Безопасность

- **Вход без паролей с помощью ключей безопасности FIDO2**     С помощью ключей безопасности FIDO2 клиенты могут быстро и легко войти в Surface Hub без необходимости вводить имена пользователей и пароли. В сочетании с Sign-On (SSO) эта функция обеспечивает быструю и бесшовную проверку подлинности файлов, приложений и веб-сайтов во время собрания. Дополнительные дополнительные информации см. в [документе Configure Passwordless sign-in on Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)
- **Улучшения для входов без паролей с помощью Microsoft Authenticator**.  Для организаций, которые используют Azure AD, пользователи могут использовать приложение Microsoft Authenticator для регистрации без необходимости вводить имена пользователей и пароли. Кроме того, пользователи могут войти с помощью предпочитаемых псевдонимов электронной почты в Azure AD в дополнение к основному имени пользователя (UPN). Дополнительные дополнительные ссылки см. [в документе Вход в Surface Hub с Помощью Microsoft Authenticator.](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## <a name="learn-more"></a>Подробнее

- [Обновление до выпуска Windows 10 для совместной работы](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Установка обновления Windows 10 для совместной работы 2020](surface-hub-2020-update.md)  
 