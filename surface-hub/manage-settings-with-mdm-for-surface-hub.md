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
ms.openlocfilehash: 4308ce1ea8ff382dc15706e68d2d706d0fd33f5f
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576759"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Управление Surface Hub с помощью поставщика MDM

Surface Hub позволяет ИТ-администраторам управлять настройками и политиками с помощью поставщика управления мобильными устройствами (MDM), например Microsoft Intune. Surface Hub имеет встроенный компонент управления для связи с сервером управления. Нет необходимости устанавливать дополнительные клиенты на устройстве.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Регистрация Surface Hub в управление MDM 

Вы можете записать Surface в Microsoft Intune или другого поставщика MDM с помощью ручной или автоматической регистрации.

### <a name="manual-enrollment"></a>Регистрация вручную

1. Откройте приложение **Параметры** и вопишитесь в качестве локального администратора. Выберите **Surface Hub**  >  **управления устройствами,** а затем выберите управление **устройствами**.
2. Вам будет предложено войти в учетную запись для использования для поставщика MDM. После проверки подлинности устройство автоматически регистрируется у поставщика MDM.

> [!TIP]
> Если вы используете Intune и адрес сервера не обнаружен, введите **manage.microsoft.com.**
   
> [!NOTE]
> Регистрация MDM использует сведения учетной записи, предоставленные для проверки подлинности. Учетная запись должна иметь разрешения на регистрацию устройства Windows, а также лицензию Intune (или эквивалентные промиссии регистрации, настроенные в стороном поставщике MDM).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Автозачисление — филиал Azure AD

Во время начального процесса установки при Surface Hub с клиентом Azure Active Directory (AD) с включенной автоматической регистрацией Intune устройство автоматически зарегистрируется в Intune. Чтобы узнать больше, обратитесь к методам регистрации [Intune для Windows устройств.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods) Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Управление Surface Hub Windows 10 для совместной работы с помощью Intune

Основой управления настройками политик в Intune и других поставщиков MDM является протокол open Mobile Alliance-Device (OMA-DM) на основе XML. Windows 10 реализует XML OMA-DM с помощью одного из многих доступных поставщиков служб конфигурации (CSPs) с именами, как AccountManagement CSP, DeviceStatus CSP, WiFi-CSP и так далее. Для полного списка обратитесь к [CSP, поддерживаемые в Microsoft Surface Hub.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)

Microsoft Intune и другие поставщики MDM используют CSPs для доставки пользовательского интерфейса, который позволяет настраивать параметры политики в профилях конфигурации. Intune использует Surface Hub CSP для встроенного в профиль — ограничения устройства **(Windows 10 для совместной работы)** — позволяя настраивать основные параметры, такие как предотвращение Surface Hub "пробуждения" всякий раз, когда кто-либо перемещается поблизости в пределах его близости. Чтобы управлять настройками и функциями концентратора вне встроенного профиля Intune, необходимо использовать настраиваемый профиль, как показано [ниже.](#create-custom-configuration-profile) 

Чтобы резюмировать, параметры настройки и управления настройками политики в Intune включают следующие: 
 
- **Создайте профиль ограничений устройства.** Используйте встроенный intune в профиле и настраивать параметры непосредственно в пользовательском интерфейсе Intune. См. [в странице Создание профиля ограничения устройств.](#create-device-restriction-profile)
- **Создание профиля конфигурации устройства.**  Выберите шаблон, ориентированный на определенные функции или технологии, такие как Microsoft Defender или сертификаты безопасности. См. [профиль конфигурации устройства](#create-device-configuration-profile).
- **Создание настраиваемой конфигурации профиля.**  Расширяйте область управления с помощью единого идентификатора ресурсов OMA (OMA URI) из любого из [CSPs,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)поддерживаемых Microsoft Surface Hub. См. [создание настраиваемой конфигурации](#create-custom-configuration-profile)профиля .

> [!NOTE]
> Профили должны быть назначены группам устройств, содержащим зарегистрированные Surface Hub устройства.

## <a name="create-device-restriction-profile"></a>Создание профиля ограничения устройств

1. Во входе [**в Microsoft Endpoint Manager центра администрирования**](https://endpoint.microsoft.com/)выберите профили **конфигурации устройств**Создать  >  ****  >  **+** **профиль**.
2. В **платформе**выберите **Windows 10 и более поздней** >
3. В типе ****Профиль**выберите** **Шаблоны,** а затем выберите ограничения устройства **(Windows 10 для совместной работы)**
4. Выберите **Создание,** добавьте имя и выберите **Далее.**
6. Теперь вы можете просматривать и выбирать из предустановленных параметров ограничения устройств для Surface Hub следующих категорий: Приложения и опыт, оперативные сведения Azure, обслуживание, сеанс и беспроводная проекция. В примере, показанном на следующем рисунке, указывается 4-часовое окно обслуживания и 15-минутное время для возобновления работы экрана, сна и сеанса.

     ![Настройка параметров Surface Hub с помощью профиля ограничения устройств Intune](images/sh-device-restrictions.png)

Дополнительные сведения о создании и управлении профилями см. в странице Ограничение возможностей устройств [с использованием политики в Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)
 
Дополнительные сведения об управлении Surface Hub функциями и настройками см. в Surface Hub Windows 10 для совместной работы ограничения устройства [в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Создание профиля конфигурации устройства

1. Во входе [**в Microsoft Endpoint Manager центра администрирования**](https://endpoint.microsoft.com/)выберите ****  >  **профили**конфигурации устройств  >  **+ Создайте профиль**.
2. В **платформе**выберите **Windows 10 и более поздней** >
3. В **типе Profile**выберите **Шаблоны** и выберите из следующих шаблонов, поддерживаемых Surface Hub:

    - Ограничения устройства (Windows 10 для совместной работы), как описано в предыдущем [разделе](#create-device-restriction-profile).
    - Защитник Microsoft для конечной точки (Windows 10 Desktop)
    - Сертификат PKCS
    - Импортируемый сертификат PKCS
    - Сертификат SCEP
    - Доверенный сертификат

## <a name="create-custom-configuration-profile"></a>Создание настраиваемой конфигурации профиля

Можно расширить область управления, [](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) создав настраиваемый профиль с помощью URI OMA из любого из [CSP,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)поддерживаемых Microsoft Surface Hub. Каждый параметр в CSP имеет соответствующий OMA-URI, который можно установить с помощью пользовательских профилей конфигурации в Intune. Дополнительные сведения о CSP, поддерживаемых Surface Hub, можно ссылаться на следующие ресурсы: 

- [Справочник по поставщикам служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Политика поставщиков служб конфигурации (CSP), поддерживаемая Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Поставщик служб конфигурации SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Управление учетной записью устройства с помощью параметров [службы CSP SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) в настоящее время невозможно с помощью Intune и требует использования стороннего поставщика MDM.

Чтобы реализовать параметры политики на основе CSP, начните с создания URI OMA, а затем добавьте его в настраиваемый профиль конфигурации в Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Создание URI OMA для целевого параметра
 
Для создания URI OMA для любого параметра:

1. В [документации CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)определите корневой узел CSP. Как правило, это выглядит **как ./Vendor/MSFT/ <name of CSP> **. 
    - **Пример:** Корневой узел [CSP SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) **— ./Vendor/MSFT/SurfaceHub.**
2. Определите путь к узлу для нужного параметра. 
    - **Пример:** Путь узла для параметра для включения беспроводной проекции **— InBoxApps/WirelessProjection/Enabled.**
3. Добавьте путь к узлу в корневой узел, чтобы создать универсальный код ресурса OMA. 
    - **Пример:** URI OMA для параметра для включения беспроводной проекции **является ./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. Этот тип данных также указан в документации поставщика служб конфигурации. Самые распространенные типы данных:
    - char (строка)
    - int (целое)
    - bool (логическое)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Добавление URI OMA в настраиваемый профиль конфигурации

1. В Endpoint Manager выберите **профили конфигурации устройств**Создание  >  ****  >  **профиля**.
2. В платформе **выберите Windows 10 и более поздней стадии.** В профиле выберите **Настраиваемый,** а затем выберите **Создать.**
3. Добавьте имя и необязательное описание, а затем выберите **Далее.**
4. В **параметрах**  >  **Конфигурация OMA-URI Параметры**выберите **Добавить**.

  
## <a name="manage-specific-surface-hub-features"></a>Управление определенными Surface Hub функциями

В этом разделе освещаются сведения о функциях, которые можно управлять с помощью Intune или другого поставщика MDM. К ним относятся:

- [Качество обслуживания (QoS)](#quality-of-service-settings)
- [Microsoft Teams и Skype для бизнеса](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>Качество параметров службы

Чтобы обеспечить оптимальное качество видео и Surface Hub, добавьте на устройство следующие параметры QoS. 

| Имя | Описание | OMA-URI | Тип | Значение |
|:------ |:------------- |:--------- |:------ |:------- |
|**Звуковые порты**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Строка  | 3478-3479 |
|**DSCP звука**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | целое число | 46 |
|**Видеопорт**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Строка  | 3480 |
|**DSCP видео**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | целое число | 34 |
|**Общий порт**| Диапазон общего доступа к порту | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Строка  | 3481 |
|**Совместное использование DSCP**| Разметка портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | целое число | 18 |
|**Звуковые порты P2P**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Строка  | 50000-50019 |
|**DSCP звука P2P**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | целое число | 46 |
|**Видеопорты P2P**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Строка  | 50020-50039 |
|**DSCP видео P2P**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | целое число | 34 |
|**P2P Sharing Ports**| Диапазон общего доступа к порту | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | Строка  | 50040-50059 |
|**P2P Sharing DSCP**| Разметка портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | целое число | 18 |


#### <a name="skype-for-business-qos-settings"></a>Параметры качества обслуживания Skype для бизнеса

| Имя                 | Описание           | OMA-URI                                                                    | Тип    | Значение                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Звуковые порты          | Диапазон звуковых портов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | Строка  | 50000-50019                    |
| DSCP звука           | Маркировка звуковых портов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | целое число | 46                             |
| Источник звука   | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | Строка  | Microsoft.PPISkype.Windows.exe |
| Видеопорты          | Диапазон видеопортов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | Строка  | 50020-50039                    |
| DSCP видео           | Маркировка видеопортов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | целое число | 34                             |
| Источник видео   | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | Строка  | Microsoft.PPISkype.Windows.exe |
| Общий доступ к портам        | Диапазон общего доступа к порту    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Строка  | 50040-50059                    |
| Совместное использование DSCP         | Разметка портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | целое число | 18                             |
| Общий доступ к источнику мультимедиа | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | Строка  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Обе таблицы содержат диапазоны портов, используемые по умолчанию. Администраторы могут изменить диапазоны портов в панели управления Skype для бизнеса и Teams.

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams и Skype для бизнеса параметров

Вы можете создать настраиваемый профиль конфигурации для управления Teams согласованными собраниями, близостью и другими функциями. Подробнее см. в Microsoft Teams [конфигурации Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

#### <a name="changing-default-business-communications-platform"></a>Изменение платформы бизнес-коммуникаций по умолчанию

Платформа бизнес-коммуникаций по умолчанию Surface Hub зависит от того, как Windows 10 для совместной работы обновления 2020 (он же Windows 10 20H2). При повторном Surface Hub Windows 10 20H2 Microsoft Teams по умолчанию будет Skype для бизнеса функциональность (режим 1). Если вы обновите концентратор из более ранней версии ОС, Skype для бизнеса останется по умолчанию, Teams функциональные возможности (Mode 0), если по умолчанию Teams не настроены. 

Чтобы изменить установку по умолчанию, используйте [настраиваемый](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) профиль, Teams Режим приложения следующим образом:  

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — Microsoft Teams с функциональностью Skype для бизнеса для запланированных собраний.
- Режим 2 — только Microsoft Teams.

| Имя | Описание | OMA-URI | Тип | Значение |
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0 или 1 или 2|










