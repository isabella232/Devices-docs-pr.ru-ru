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
ms.openlocfilehash: 1afa4d63dde793e61e30d1c4dd54f552b5581a81
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470465"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Управление surface Hub с поставщиком MDM

Surface Hub позволяет ИТ-администраторам управлять настройками и политиками с помощью поставщика управления мобильными устройствами (MDM), например Microsoft Intune. Surface Hub имеет встроенный компонент управления для связи с сервером управления. Нет необходимости устанавливать дополнительные клиенты на устройстве.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Регистрация Surface Hub в управлении MDM 

Вы можете зарегистрироваться Surface в Microsoft Intune или другом поставщике MDM с помощью ручной или автоматической регистрации.

### <a name="manual-enrollment"></a>Регистрация вручную

1. Откройте приложение **Параметры** и вопишитесь в качестве локального администратора. Выберите **управление устройствами Surface**  >  **Hub,** а затем **выберите управление устройствами**.
2. Вам будет предложено войти в учетную запись для использования для поставщика MDM. После проверки подлинности устройство автоматически регистрируется у поставщика MDM.

> [!TIP]
> Если вы используете Intune и адрес сервера не обнаружен, введите **manage.microsoft.com.**
   
> [!NOTE]
>  Регистрация MDM использует сведения учетной записи, предоставленные для проверки подлинности. Учетная запись должна иметь разрешения на регистрацию устройства Windows, а также лицензии Intune (или эквивалентные промиссии регистрации, настроенные в стороном поставщике MDM).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Автозачисление — филиал Azure AD

Во время начального процесса настройки при подстройке Surface Hub с клиентом Azure Active Directory (AD) с включенной автоматической регистрацией Intune устройство автоматически зарегистрируется в Intune. Чтобы узнать больше, обратитесь к методам регистрации [Intune для устройств Windows.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods) Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Управление настройками команды Surface Hub Windows 10 с помощью Intune

Основой управления настройками политик в Intune и других поставщиков MDM является протокол open Mobile Alliance-Device (OMA-DM) на основе XML. Windows 10 реализует XML OMA-DM с помощью одного из многих доступных поставщиков служб конфигурации (CSPs) с именами, как AccountManagement CSP, DeviceStatus CSP, Wirednetwork-CSP и так далее. Для полного списка обратитесь к [CSP, поддерживаемые в Microsoft Surface Hub.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)


Microsoft Intune и другие поставщики MDM используют CSPs для доставки пользовательского интерфейса, который позволяет настраивать параметры политики в профилях конфигурации. Intune использует CSP Surface Hub для встроенного в профиль — ограничения устройств  **(Windows 10 Team)** — позволяя настраивать основные параметры, такие как предотвращение "пробуждения" Surface Hub всякий раз, когда кто-либо перемещается поблизости в пределах его близости. Чтобы управлять настройками и функциями концентратора вне встроенного профиля Intune, необходимо использовать настраиваемый профиль, как показано [ниже.](#create-custom-configuration-profile) 

Чтобы резюмировать, параметры настройки и управления настройками политики в Intune включают следующие: 
 
- **Создайте профиль ограничений устройства.** Используйте встроенный intune в профиле и настраивать параметры непосредственно в пользовательском интерфейсе Intune. См. [в странице Создание профиля ограничения устройств.](#create-device-restriction-profile)
- **Создание профиля конфигурации устройства.**  Выберите шаблон, ориентированный на определенные функции или технологии, такие как Microsoft Defender или сертификаты безопасности. См. [профиль конфигурации устройства](#create-device-configuration-profile).
- **Создание настраиваемой конфигурации профиля.**  Расширяйте область управления с помощью единого идентификатора ресурсов OMA (OMA URI) из любого центра [CSP,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)поддерживаемого в Microsoft Surface Hub. См. [создание настраиваемой конфигурации](#create-custom-configuration-profile)профиля .


## <a name="create-device-restriction-profile"></a>Создание профиля ограничения устройств

1. Во входе [**в центр администрирования Microsoft Endpoint Manager**](https://endpoint.microsoft.com/)выберите профили **конфигурации**устройств  >  ****  >  **+** **Создать профиль**.
2. В **платформе**выберите **Windows 10 и более поздние версии** >
3. В соответствии с типом *****Profile**выберите** **Шаблоны,** а затем выберите ограничения устройства **(Windows 10 Team)**
4. Выберите **Создание,** добавьте имя и выберите **Далее.**
6. Теперь вы можете просматривать и выбирать из заранее заданной параметров ограничения устройств для Surface Hub в следующих категориях: Приложения и опыт, оперативные сведения Azure, обслуживание, сеанс и беспроводная проекция. В примере, показанном на следующем рисунке, указывается 4-часовое окно обслуживания и 15-минутное время для возобновления работы экрана, сна и сеанса.

     ![Настройка параметров Surface Hub с профилем ограничения устройств Intune](images/sh-device-restrictions.png)

Дополнительные сведения о создании и управлении профилями см. в странице Ограничение возможностей устройств [с помощью политики в Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)
 
Дополнительные сведения об управлении функциями и настройками Surface Hub см. в сведениях об ограничениях устройств [Surface Hub Windows 10 Team в Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Создание профиля конфигурации устройства

1. Во входе [**в центр администрирования Microsoft Endpoint Manager**](https://endpoint.microsoft.com/)выберите профили конфигурации устройств + ****  >  ****  >  **Создайте профиль**.
2. В **платформе**выберите **Windows 10 и более поздние версии** >
3. В **типе Profile**выберите **Шаблоны** и выберите следующие шаблоны, поддерживаемые в Surface Hub:

    - Ограничения устройств (Windows 10 Team), как описано в предыдущем [разделе.](#create-device-restriction-profile)
    - Защитник Microsoft для конечной точки (Windows 10 Desktop)
    - Сертификат PKCS
    - Импортируемый сертификат PKCS
    - Сертификат SCEP
    - Доверенный сертификат

## <a name="create-custom-configuration-profile"></a>Создание настраиваемой конфигурации профиля

Можно расширить область управления, [](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) создав настраиваемый профиль с помощью URI OMA из любого из [CSP,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)поддерживаемых в Microsoft Surface Hub. Каждый параметр в CSP имеет соответствующий OMA-URI, который можно установить с помощью пользовательских профилей конфигурации в Intune. Дополнительные сведения о CSP, поддерживаемых Surface Hub, можно ссылаться на следующие ресурсы: 

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

1. В Endpoint Manager выберите **профили**  >  **конфигурации устройств**  >  **Создание профиля**.
2. Под платформой выберите **Windows 10 и более поздний.** В профиле выберите **Настраиваемый,** а затем выберите **Создать.**
3. Добавьте имя и необязательное описание, а затем выберите **Далее.**
4. В **параметрах Конфигурация**  >  **OMA-URI Параметры**выберите **Добавить**.

  
## <a name="manage-specific-surface-hub-features"></a>Управление определенными функциями Surface Hub

В этом разделе освещаются сведения о функциях, которые можно управлять с помощью Intune или другого поставщика MDM. К ним относятся:

- [Качество обслуживания (QoS)](#quality-of-service-settings)
- [Microsoft Teams и Skype для бизнеса](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>Качество параметров службы

Чтобы обеспечить оптимальное качество видео и звука на Surface Hub, добавьте на устройство следующие параметры QoS. 

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

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Параметры Microsoft Teams и Skype для бизнеса

Вы можете создать настраиваемый профиль конфигурации для управления согласованными собраниями teams, proximity Join и другими функциями. Дополнительные дополнительные информации см. в [веб-сайте Управление конфигурацией Microsoft Teams в Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

#### <a name="changing-default-business-communications-platform"></a>Изменение платформы бизнес-коммуникаций по умолчанию

Платформа бизнес-коммуникаций по умолчанию в Surface Hub варьируется в зависимости от установки обновления Windows 10 Team 2020 (она же Windows 10 20H2). При повторном изображении Surface Hub в Windows 10 20H2 Microsoft Teams будет назначена по умолчанию, а функциональные возможности Skype для бизнеса доступны (режим 1). Если вы обновите концентратор из более ранней версии ОС, Skype для бизнеса останется по умолчанию, а функции Teams доступны (Режим 0), если только вы не настроили Teams в качестве по умолчанию. 

Чтобы изменить установку по умолчанию, используйте [настраиваемый профиль,](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) установив режим командного приложения следующим образом:  

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — Microsoft Teams с функциональностью Skype для бизнеса для запланированных собраний.
- Режим 2 — только Microsoft Teams.

| Имя | Описание | OMA-URI | Тип | Значение |
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0 или 1 или 2|










