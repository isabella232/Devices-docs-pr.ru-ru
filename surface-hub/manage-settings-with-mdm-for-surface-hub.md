---
title: Управление параметрами с помощью поставщика MDM (Surface Hub)
description: ИТ-администраторы могут управлять политиками и бизнес-приложениями на устройствах Microsoft Surface Hub с помощью решения для управления мобильными устройствами (MDM).
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: управление мобильными устройствами, MDM, политики управления
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497792"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Управление Surface Hub с помощью поставщика MDM

Surface Hub позволяет ИТ-администраторам управлять параметрами и политиками с помощью поставщика управления мобильными устройствами (MDM), например Microsoft Intune. Surface Hub имеет встроенный компонент управления для взаимодействия с сервером управления. Нет необходимости устанавливать дополнительные клиенты на устройстве.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Регистрация Surface Hub в управлении MDM 

Вы можете зарегистрировать Surface в Microsoft Intune или другом поставщике MDM с помощью ручной или автоматической регистрации.

### <a name="manual-enrollment"></a>Регистрация вручную

1. Откройте приложение **Параметры** и войдите в систему с правами локального администратора. Выберите **Surface Hub** >  **Device,** а затем **выберите +Управление устройствами**.
2. Вам будет предложено войти с помощью учетной записи, которая будет использоваться для поставщика MDM. После проверки подлинности устройство автоматически регистрируется у поставщика MDM.

> [!TIP]
> Если вы используете Intune адрес сервера не обнаружен, введите **manage.microsoft.com**.
   
> [!NOTE]
> При регистрации MDM используются сведения об учетной записи, предоставленные для проверки подлинности. Учетная запись должна иметь разрешения на регистрацию устройства Windows, а также лицензию Intune (или эквивалентные разрешения на регистрацию, настроенные в стороннем поставщике MDM).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Автоматическая регистрация — Azure AD связанных

Во время начальной настройки при установке Surface Hub с клиентом Azure Active Directory (AD), в котором включена автоматическая регистрация Intune, устройство автоматически регистрируется в Intune. Дополнительные сведения см. [в Intune регистрации для Windows устройств](/intune/enrollment/windows-enrollment-methods). Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Управление Surface Hub Windows 10 для совместной работы с помощью Intune

Базовым стандартным блоком управления параметрами политики в Intune и других поставщиках MDM является протокол Open Mobile Alliance-Device Management (OMA-DM) на основе XML. Windows реализует OMA-DM XML через один из многих доступных поставщиков служб конфигурации (CSP) с такими именами, как AccountManagement CSP, DeviceStatus CSP, WiFi-CSP и т. д. Полный список см. на [веб-сайте CSP, поддерживаемом Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune и другие поставщики MDM используют поставщики служб конфигурации для предоставления пользовательского интерфейса, который позволяет настраивать параметры политики в профилях конфигурации. Intune использует поставщик служб конфигурации Surface Hub для встроенного профиля ( ограничения устройств **(Windows 10 для совместной работы)** — позволяет настраивать основные параметры, такие как предотвращение Surface Hub "поднимаясь" каждый раз, когда кто-либо перемещается рядом в пределах его диапазона близкого взаимодействия. Чтобы управлять параметрами и функциями концентратора вне Intune встроенного профиля, необходимо использовать пользовательский профиль, как [показано ниже](#create-custom-configuration-profile). 

Подводя итоги, можно настроить параметры политики и управлять ими в Intune следующие параметры: 
 
- **Создайте профиль ограничений устройств.** Используйте Intune встроенного профиля и настройте параметры непосредственно в Intune пользовательском интерфейсе. См [. раздел "Создание профиля ограничения устройства"](#create-device-restriction-profile).
- **Создайте профиль конфигурации устройства.**  Выберите шаблон, ориентированный на определенную функцию или технологию, например Microsoft Defender или сертификаты безопасности. См [. раздел "Создание профиля конфигурации устройства"](#create-device-configuration-profile).
- **Создайте пользовательский профиль конфигурации.**  Расширите область управления с помощью универсального кода ресурса OMA (OMA URI) из любого поставщика служб конфигурации, поддерживаемого [в Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). См [. раздел "Создание настраиваемого профиля конфигурации"](#create-custom-configuration-profile).

> [!NOTE]
> Профили должны назначаться группам устройств, содержащим зарегистрированные Surface Hub устройствах.

## <a name="create-device-restriction-profile"></a>Создание профиля ограничения устройств

1. Войдите в [**Microsoft Endpoint Manager центра администрирования**](https://endpoint.microsoft.com/) и выберите **профиль Создания** профилей  > **+****DevicesConfiguration** > .****
2. В **разделе "Платформа****" выберите Windows 10 и более поздних версий.** >
3. В разделе ****Тип профиля выберите **"Шаблоны**"**,** а затем выберите "**Ограничения устройства" (Windows 10 для совместной работы)**
4. Нажмите **кнопку "** Создать", добавьте имя и нажмите кнопку **"Далее".**
6. Теперь вы можете просматривать и выбирать из предустановки параметров ограничения устройств для Surface Hub в следующих категориях: приложения и интерфейс, операционная аналитика Azure, обслуживание, сеанс и беспроводная проекция. В примере, показанном на следующем рисунке, указывается 4-часовой период обслуживания и 15-минутное время ожидания для экрана, спящего режима и возобновления сеанса.

     ![Настройте Surface Hub с помощью профиля Intune устройств.](images/sh-device-restrictions.png)

Дополнительные сведения о создании профилей и управлении ими см. в статье "Ограничение возможностей устройств с помощью [политики в Microsoft Intune"](/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
Дополнительные сведения об управлении Surface Hub и параметрами см. в Windows 10 для совместной работы параметров, чтобы разрешить или ограничить функции Surface Hub [с помощью Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Создание профиля конфигурации устройства

1. Войдите в [**Microsoft Endpoint Manager центра администрирования**](https://endpoint.microsoft.com/), выберите **"Профили** **DevicesConfiguration** >  > **+ Создать профиль"**.
2. В **разделе "Платформа****" выберите Windows 10 и более поздних версий.** >
3. В **разделе "Тип профиля**" выберите **"Шаблоны**" и выберите один из следующих шаблонов, поддерживаемых Surface Hub:

    - Ограничения устройств (Windows 10 для совместной работы), как описано в [предыдущем разделе](#create-device-restriction-profile).
    - Microsoft Defender для конечной точки (Windows 10 Desktop)
    - Сертификат PKCS
    - Импортированный сертификат PKCS
    - Сертификат SCEP
    - Доверенный сертификат

## <a name="create-custom-configuration-profile"></a>Создание настраиваемого профиля конфигурации

Вы можете расширить область управления, создав [](/mem/intune/configuration/custom-settings-configure) пользовательский профиль с помощью OMA URI из любого из поставщиков служб конфигурации, [поддерживаемых в Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Каждый параметр в CSP имеет соответствующий OMA-URI, который можно задать с помощью настраиваемых профилей конфигурации в Intune. Дополнительные сведения о CSP, поддерживаемых Surface Hub, см. в следующих ресурсах: 

- [Справочник по поставщикам служб конфигурации](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Политика поставщиков служб конфигурации (CSP), поддерживаемая Microsoft Surface Hub](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Поставщик служб конфигурации SurfaceHub](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Управление учетной записью устройства с помощью параметров из поставщика служб конфигурации [SurfaceHub](/windows/client-management/mdm/surfacehub-csp) в настоящее время невозможно с Intune и требует использования стороннего поставщика MDM.

Чтобы реализовать параметры политики на основе CSP, начните с создания URI OMA, а затем добавьте его в пользовательский профиль конфигурации в Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Создание OMA URI для целевого параметра
 
Чтобы создать OMA URI для любого параметра:

1. В [документации CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) определите корневой узел CSP. Как правило, это выглядит так: **./Vendor/MSFT/NameOfCSP**. 
    - **Примере:** Корневым узлом [CSP SurfaceHub](/windows/client-management/mdm/surfacehub-csp) является **./Vendor/MSFT/SurfaceHub**.
2. Определите путь к узлу для нужного параметра. 
    - **Примере:** Путь к узлу для параметра для включения беспроводной проекции — **InBoxApps/WirelessProjection/Enabled**.
3. Добавьте путь к узлу в корневой узел, чтобы создать универсальный код ресурса OMA. 
    - **Примере:** Универсальный код ресурса (URI) OMA для параметра для включения беспроводной проекции — **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. Этот тип данных также указан в документации поставщика служб конфигурации. Самые распространенные типы данных:
    - char (строка)
    - int (целое)
    - bool (логическое)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Добавление OMA URI в пользовательский профиль конфигурации

1. В Endpoint Manager выберите **профиль** **DevicesConfiguration** >  **profilesCreate** > .
2. В разделе "Платформа **" Windows 10 и более поздних версий.** В разделе "Профиль" **выберите "Пользовательский**", а затем нажмите кнопку **"Создать".**
3. Добавьте имя и необязательное описание, а затем нажмите кнопку **"Далее".**
4. В **разделе configuration settingsOMA-URI** >  **Параметры** нажмите кнопку **"Добавить"**.

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams и Skype для бизнеса параметров

В этом разделе Teams и Skype для бизнеса, которые можно управлять с помощью Intune или другого поставщика MDM. К ним относятся:

- [Качество обслуживания (QoS)](#quality-of-service-settings)
- [Управление Teams для конкретных функций](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>Параметры качества обслуживания

Чтобы обеспечить оптимальное качество видео и звука на Surface Hub, добавьте на устройство следующие параметры качества обслуживания. 

| Имя                 | Описание           | OMA-URI                                                                 | Тип    | Значение                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| Звуковые порты          | Диапазон звуковых портов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | Строка  | 50000-50019                    |
| DSCP звука           | Маркировка звуковых портов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | целое число | 46                             |
| Видеопорты          | Диапазон видеопортов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | Строка  | 50020-50039                    |
| DSCP видео           | Маркировка видеопортов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | целое число | 34                             |
| Совместное использование портов        | Диапазон портов общего доступа    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | Строка  | 50040-50059                    |
| Общий доступ к DSCP         | Маркировка портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | целое число | 18                             |

> [!NOTE]
> В таблице показаны диапазоны портов по умолчанию. Администраторы могут изменить диапазоны портов в панели управления Skype для бизнеса и Teams.

### <a name="manage-teams-specific-features"></a>Управление Teams для конкретных функций

Вы можете создать пользовательский профиль конфигурации для управления Teams, присоединением к близкому соединению и другими функциями. Дополнительные сведения см. в [Microsoft Teams конфигурации Surface Hub](/microsoftteams/rooms/surface-hub-manage-config).

### <a name="changing-default-app-for-meetings--calls"></a>Изменение приложения по умолчанию для собраний & вызовов

Приложение по умолчанию для собраний & на Surface Hub зависит от способа установки обновления Windows 10 для совместной работы 2020 (также как Windows 10 20H2 Team Edition). При повторном создании образа Surface Hub на Windows 10 20H2 Microsoft Teams будет установлено значение по умолчанию, Skype для бизнеса недоступно (режим 1). Если вы обновите центр с более ранней версии ОС, Skype для бизнеса останется в качестве используемого по умолчанию с Teams функциональными возможностями (режим 0), если вы еще не настроили Teams в качестве используемого по умолчанию. 

Чтобы изменить установку по умолчанию, используйте [пользовательский](/mem/intune/configuration/custom-settings-configure) профиль, чтобы задать режим Teams собрания следующим образом:  

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — только Microsoft Teams.

| Имя | Описание | OMA-URI | Тип | Значение |
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0или1|


