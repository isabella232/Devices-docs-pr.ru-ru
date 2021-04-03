---
title: Создание и тестирование учетной записи устройства (Surface Hub)
description: В этом разделе описано создание и тестирование учетной записи устройства, которую Microsoft Surface Hub использует для связи с Microsoft Exchange и Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: создание и тестирование учетной записи устройства, учетная запись устройства, Surface Hub и Microsoft Exchange, Surface Hub и Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 685359f1371a1bef8bd216223a98b934c997a1d8
ms.sourcegitcommit: 879e80200aea26f6705c887fa392db5db35b99ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2021
ms.locfileid: "11475093"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Создание и тестирование учетной записи устройства (Surface Hub)

Создание учетной записи устройства Surface Hub (также известной как учетная запись ресурса или почтовый ящик комнаты) позволяет Surface Hub получать, утверждать или отклонять запросы на собрания и присоединяться к собраниям.

После того как учетная запись устройства будет добавлена в Surface Hub, люди смогут добавить эту учетную запись в приглашение на собрание так же, как они будут приглашать конференц-зал. 

Вы можете настроить учетную запись устройства во время установки [Out-of-Box Experience (OOBE).](first-run-program-surface-hub.md) При необходимости вы также можете изменить его позже в **настройках**  >  **учетных записей Surface Hub.**  >  ****

## <a name="configuration-overview"></a>Обзор конфигурации

В этой таблице описаны основные шаги и решения по конфигурации при создании учетной записи устройства.
 
| Этап | Описание                     |  Назначение                             |
|------|---------------------------------|--------------------------------------|
| 1    | Создание почтового ящика с поддержкой логотипа (Exchange Online или Exchange Server 2016 г. и более поздней 2016 г.) | Этот тип почтового ящика позволяет устройству поддерживать календарь собраний, получать запросы на собрания и отправлять почту. Она должна быть включена с помощью логотипа, чтобы использовать ее в Surface Hub. |
| 2    | Настройка свойств почтового ящика | Необходимо правильно настроить свойства почтового ящика, чтобы обеспечить максимально эффективное использование Surface Hub на собраниях. Дополнительные сведения о свойствах почтового ящика см. в разделе [Свойства почтового ящика](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Убедитесь, что веб-службы Exchange (EWS) включены, а многофакторная проверка подлинности (MFA) отключена | Surface Hub использует EWS для синхронизации календаря. Если по умолчанию не разрешается использовать EWS в среде, почтовый ящик Hub должен быть включен явно. Поскольку Surface Hub входит в Exchange в фоновом режиме без взаимодействия с пользователем, он не может отвечать на любые интерактивные запросы, такие как MFA. Создаемая учетная запись устройства должна быть исключена из любых таких требований к проверке подлинности. В противном случае Surface Hub не удастся синхронизировать сведения почты и календаря. |
| 4    | Включить учетную запись Teams или Skype для бизнеса (Skype для бизнеса Server 2015 и более поздний) | Skype для бизнеса или teams должен быть включен для использования функций телефонных разговоров, таких как видеозвонков, обмена мгновенными данными и обмена экранами. Дополнительные сведения о лицензиях, которые позволяют Teams, см. в описании [лицензирования и](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) [службы Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)Teams. |
| 5    | (Необязательно) Отключение срока действия пароля | Чтобы упростить управление, можно отключить истечение срока действия пароля для учетной записи устройства и разрешить Surface Hub автоматически менять пароль учетной записи устройства. Дополнительные сведения об управлении паролями см. в разделе [Управление паролями](password-management-for-surface-hub-device-accounts.md).  |
| 6    | (Необязательный) Настройка политик Exchange, чтобы разрешить ActiveSync | При определенных локальном развертывании Exchange Server & Active Directory activeSync будет использоваться для синхронизации данных учетных записей устройств и календаря. Дополнительные сведения о политиках, которые необходимо настроить, см. в записях [ActiveSync для учетных записей Surface Hub.](apply-activesync-policies-for-surface-hub-device-accounts.md) |

> [!NOTE]  
> Учетная запись устройства Surface Hub не поддерживает сторонних поставщиков идентификаторов (идентификаторов) и должна пройти проверку подлинности с помощью Active Directory или Azure Active Directory.

## <a name="detailed-configuration-steps"></a>Подробное пошаговое описание конфигурации 

Рекомендуется настраивать учетные записи устройств Surface Hub с помощью удаленных Windows PowerShell. Microsoft предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)скрипт, который поможет создать новые учетные записи ресурсов или проверить существующие учетные записи ресурсов, которые у вас есть, чтобы помочь вам превратить их в совместимые учетные записи устройств Surface Hub. Если вы хотите, вы можете выбрать вариант из приведенной ниже таблицы и следовать подробным шагам PowerShell, основанным на развертывании организации.

| Развертывание в организации             |  Описание                  |        Формат, который можно использовать во время установки Surface Hub
|---------------------------------|--------------------------------------|
| [Развертывание в Интернете (Microsoft 365 или Office 365)](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |Среда организации полностью развернута в Microsoft 365 или Office 365. | имя_пользователя@domain.com |
| [Гибридное развертывание (локальное развертывание Exchange)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | В организации имеется сочетание служб, в Exchange Server в помещениях и Microsoft Teams в Интернете. | username@domain.com [если гибридная современная](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) проверка подлинности включена в Exchange, ДОМЕН\имя пользователя в противном случае |
| [Гибридное развертывание (Exchange Online)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | В вашей организации имеется сочетание служб, в том что Skype для бизнеса Server имеется в помещениях и Exchange Online. | username@domain.com если [гибридная современная](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) проверка подлинности включена в SfB, ДОМЕН\имя пользователя в противном случае |
| [Локальное развертывание (с одним лесом)](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | В организации есть серверы, которые она контролирует, где Active Directory, Exchange и Skype для бизнеса Server находятся в среде с одним лесом.  | ДОМЕН\имя_пользователя |
| [Локальное развертывание (с несколькими лесами)](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | В организации есть серверы, которые она контролирует, где Active Directory, Exchange и Skype для бизнеса Server находятся в многолесной среде. | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>Проверка и тестирование учетной записи

Существует два метода, которые можно использовать для проверки и тестирования учетной записи устройства Surface Hub: [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) и аппаратного диагностического [приложения Surface Hub.](https://www.microsoft.com/store/apps/9nblggh51f2g) Сценарий создания учетной записи может проверить ранее созданную учетную запись устройства с помощью PowerShell с компьютера. Приложение диагностики оборудования Surface Hub устанавливается на устройстве Surface Hub и предоставляет подробные отзывы о сбоях входа и связи. Оба способа эффективным решением для проверки новых учетных записей устройств, и их следует использовать для оптимизации доступности учетной записи.
