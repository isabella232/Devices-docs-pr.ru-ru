---
title: Новые возможности обновления Windows 10 для совместной работы 2020
description: Ознакомьтесь с новыми обновлениями операционной системы Surface Hub 2020 Windows 10 для совместной работы обновления.
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
ms.openlocfilehash: 753f0b64eb05e6d18d0ec2e32af8e0566a8c50b5
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676643"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Новые возможности обновления Windows 10 для совместной работы 2020

Windows 10 для совместной работы обновления 2020 года существенно улучшило развертывание и управляемость устройств наряду с последними Windows 10 функциями.

##  <a name="deployment-and-manageability"></a>Развертывание и управляемость

- **Современная проверка подлинности для учетных записей облачных устройств.** Surface Hub поддерживает проверку подлинности Exchange веб-служб (EWS) и Библиотеки проверки подлинности Active Directory (ADAL), чтобы подключиться к Exchange, что позволяет клиентам не применять базовую проверку подлинности. Дополнительные дополнительные информации см. в [сайте Modern authentication on Surface Hub.](surface-hub-modern-auth.md)
- Более 20 новых и обновленных параметров политики управления мобильными **устройствами (MDM).**  Эти параметры политики дают ИТ-администраторам улучшенный контроль над несколькими настройками устройств, включая: обновления приложений из Microsoft Store, параметры беспроводной проекции, такие как Miracast над инфраструктурой, сетевые параметры, такие как Quality-Of-Service и 802.1x проводной проверки подлинности, а также новые параметры конфиденциальности и GDPR. Новые поставщики служб конфигурации (CSP) включают: 

  - [Поставщик служб конфигурации учетных записей](/windows/client-management/mdm/accounts-csp) 
  - [Брандмауэр-CSP](/windows/client-management/mdm/firewall-csp) 
  - [Поставщик служб конфигурации RemoteWipe](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp) 

Дополнительные дополнительные информации см. в. 
- [CSPs, поддерживаемые в Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Управление Surface Hub с помощью поставщика MDM](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory Соединяемые устройства

- **Единый вход (SSO) для устройств, присоединив Azure AD.** При входе Microsoft 365 учетных данных в "Мои собрания и файлы" учетные данные пользователей плавно перетекают из приложения в приложение, включая Microsoft 365 в браузере.
- **Условный доступ (CA) для присоединенных устройств Azure AD.** ИТ-администраторы могут управлять доступом пользователей к организационным ресурсам из azure AD, присоединенных к Surface Hubs, назначив политики устройств в соответствии с требованиями корпоративной безопасности и соответствия требованиям.
- **Поддержка не глобальных администраторов для устройств,** присоединив Azure AD. Клиенты могут выбрать более детализированный набор администраторов в иерархии администраторов для управления Surface Hub. Дополнительные дополнительные новости см. в [врезке Configure non Global admin accounts on Surface Hub.](surface-hub-2s-nonglobal-admin.md)


## <a name="browser-and-pen"></a>Браузер и перо

- **Поддержка нового Microsoft Edge**. Microsoft Edge была восстановлена для оптимальной производительности, безопасности и конфиденциальности совместимости. Дополнительные дополнительные возможности см. в [сайте Install and configure the new Microsoft Edge на Surface Hub.](surface-hub-install-chromium-edge.md)
- **Двухъядерный inking на Surface Hub 2S**.   Пользователи могут отбелить доску и работать бок о бок на Surface Hub 2S с помощью двух Surface Hub 2 ручки. Обновления прошивки, необходимые для внося двойной пера, будут выпущены с последующим обновлением.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams установлен по умолчанию.**        Microsoft Teams включено в качестве приложения для собраний, вызовов и совместной работы на новых устройствах Surface Hub, которые можно изменить или настроить с помощью MDM или непосредственно Surface Hub с помощью Параметры приложения. Подробнее [см.](/MicrosoftTeams/teams-surface-hub)в Microsoft Teams.
- **Поддержка близости Присоединиться к Microsoft Teams**.  Proximity Join позволяет пользователям принимать запланированные Microsoft Teams вызовы в соседнем Surface Hub с помощью ноутбука или телефона или плавно перебирать в ходе выполнения собрания в соседний Surface Hub. Windows 10 для совместной работы 2020 обновление добавляет поддержку управления мобильными устройствами (MDM) для настройки proximity Join. Дополнительные дополнительные информации см. в. 

  - [Microsoft Teams блог](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Управление настройками Microsoft Teams на Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Поддержка согласованных собраний с Microsoft Teams**. В комнатах собраний с Surface Hub и устройством Microsoft Teams Room или пространствах с двумя устройствами Surface Hub, координированные собрания позволяют пользователям легко использовать оба устройства во время Microsoft Teams собрания. С помощью одного касания пользователи могут присоединяться к собранию с любого устройства и максимизировать экранную недвижимость, показывая видео-каналы на одном устройстве, а цифровую доску или контент на другом. Windows 10 для совместной работы 2020 г. Обновление добавляет поддержку управления мобильными устройствами (MDM) для настройки скоординированных собраний, и эта функция будет впоследствии выпущена в качестве обновления Microsoft Teams через Microsoft Store. Дополнительные дополнительные новости см. в ссылке Настройка согласованных собраний с Комнаты Microsoft Teams [и Surface Hub.](/MicrosoftTeams/rooms/coordinated-meetings)

## <a name="security"></a>Security

- **Вход без паролей с помощью ключей безопасности FIDO2**     С помощью ключей безопасности FIDO2 клиенты могут быстро и легко войти в Surface Hub без необходимости вводить имена пользователей и пароли. В сочетании с Sign-On (SSO) эта функция обеспечивает быструю и бесшовную проверку подлинности файлов, приложений и веб-сайтов во время собрания. Дополнительные дополнительные информации см. в [документе Настройка](surface-hub-2s-phone-authenticate.md)без паролей в Surface Hub.
- **Улучшения без паролей**при входе с Microsoft Authenticator .  Для организаций, которые используют Azure AD, пользователи могут использовать приложение Microsoft Authenticator для регистрации без необходимости вводить имена пользователей и пароли. Кроме того, пользователи могут войти с помощью предпочитаемых псевдонимов электронной почты в Azure AD в дополнение к основному имени пользователя (UPN). Дополнительные дополнительные ссылки см. в Surface Hub [с Microsoft Authenticator](surface-hub-authenticator-app.md).


## <a name="learn-more"></a>Подробнее

- [Обновление до выпуска Windows 10 для совместной работы](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Установка обновления Windows 10 для совместной работы 2020](surface-hub-2020-update.md)  
 
