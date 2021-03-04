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
ms.date: 03/03/2021
ms.localizationpriority: medium
ms.openlocfilehash: d09a95d25b4f4ae86d64acd7d7f16f004f991ce3
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387494"
---
# <a name="manage-settings-with-an-mdm-provider-surface-hub"></a>Управление параметрами с помощью поставщика MDM (Surface Hub)

Surface Hub и другие устройства с Windows 10 позволяют ИТ-администраторам управлять параметрами и политиками с помощью службы управления мобильными устройствами (MDM). Встроенный компонент управления взаимодействует с сервером управления, поэтому нет необходимости устанавливать на устройстве дополнительные клиенты. Дополнительные сведения см. в разделе [Управление мобильными устройствами с Windows 10](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

Surface Hub была проверена у поставщиков MDM майкрософт:
- Исключительно Microsoft Intune
- Локальное управление MDM с Microsoft Endpoint Configuration Manager

Также можно управлять устройствами Surface Hub с помощью сторонних служб MDM, которые могут взаимодействовать с Windows 10 по протоколу MDM.

## <a name="enroll-a-surface-hub-into-mdm"></a><a href="" id="enroll-into-mdm"></a>Регистрация Surface Hub в MDM
Вы можете записать свои концентраторы Surface с помощью массовой, ручной или автоматической регистрации.

### <a name="bulk-enrollment"></a>Массовая регистрация
**Настройка массовой регистрации**
- Surface Hub поддерживает [поставщик служб конфигурации подготовки](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) для массовой регистрации в службе MDM. Дополнительные сведения см. в разделе [Массовая регистрация Windows 10](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--ИЛИ--
- Если у вас есть локальной инфраструктуры Microsoft [Endpoint Configuration Manager,](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm)см. в примере Как массово зарегистрировать устройства с помощью локального управления мобильными устройствами в Microsoft Endpoint Configuration Manager.

### <a name="manual-enrollment"></a>Регистрация вручную
**Настройка регистрации вручную**
1. На Surface Hub откройте приложение **Параметры**.
2. Введите учетные данные администратора устройства.
3. Выберите **Это устройство** и перейдите в раздел **Управление устройствами**.
4. В разделе **Управление устройствами** выберите **+ Управление устройствами**.
5. Выполните инструкции в диалоговом окне, чтобы подключиться к службе MDM.

### <a name="automatic-enrollment-via-azure-active-directory-join"></a>Автоматическая регистрация с помощью присоединиться к Azure Active Directory

Surface Hub теперь поддерживает возможность автоматической регистрации в Intune, присоединив устройство к Azure Active Directory. 

Первым шагом является настройка автоматической регистрации MDM. См. [функцию Включить автоматическую регистрацию в Windows 10.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)

Затем, когда устройства настроены во время первого запуска, выберите параметр присоединиться к Azure Active Directory, см. в странице Настройка администраторов [для этой страницы устройства.](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## <a name="manage-surface-hub-settings-with-mdm"></a>Управление параметрами Surface Hub с помощью MDM

Можно использовать MDM для управления некоторыми [параметрами поставщика служб конфигурации Surface Hub](#supported-surface-hub-csp-settings) и некоторыми [параметрами Windows 10](#supported-windows-10-settings). В зависимости от используемой службы MDM можно настроить эти параметры с использованием встроенного пользовательского интерфейса или развернув пользовательский SyncML. Microsoft Intune и Microsoft Endpoint Configuration Manager предоставляют встроенные возможности для создания шаблонов политики для Surface Hub. Обратитесь к документации поставщика MDM, чтобы узнать, как создавать и развертывать SyncML.

### <a name="supported-surface-hub-csp-settings"></a>Поддерживаемые параметры поставщика служб конфигурации Surface Hub

С помощью MDM можно настроить параметры Surface Hub в следующей таблице. В таблице определяется, поддерживается ли параметр с помощью Microsoft Intune, Microsoft Endpoint Configuration Manager или SyncML.

Дополнительные сведения см. в разделе [Поставщик служб конфигурации SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Параметр                                      |                                                    Узел в поставщике служб конфигурации SurfaceHub                                                    |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Часы обслуживания                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Да                        |                       Да                       |             Да             |
|              Автоматическое включение экрана с помощью датчиков движения               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Да                        |                       Да                       |             Да             |
|                      Требовать PIN-код для беспроводной проекции                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Да                        |                       Да                       |             Да             |
|                            Включение беспроводной проекции                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                 Канал Miracast для использования беспроводной проекции                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|              Подключение к рабочей области Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                         Фоновое изображение экрана приветствия                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Сведения о собрании, отображаемые на приветственном экране                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Да                        | Да.<br> [Используйте настраиваемый параметр.] (#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             Да             |
|                      Понятное имя для беспроводной проекции                       |                                                     Properties/FriendlyName                                                      | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                   Учетная запись устройства                                                 | DeviceAccount/*`<name_of_policy>`* <br> См. раздел [Поставщик служб конфигурации SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Нет                        |                       Нет                        |             Да             |
|                               Укажите домен Skype                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Автоматический запуск приложения Connect при инициировании проекции               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                                Задайте громкость по умолчанию                                |                                                     Properties/DefaultVolume                                                     |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                                Задайте время ожидания для экрана                                |                                                     Properties/ScreenTimeout                                                     |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                               Установите время ожидания для сеанса                                |                                                    Properties/SessionTimeout                                                     |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                                Время ожидания перехода в режим сна                                 |                                                     Properties/SleepTimeout                                                      |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                   Разрешите возобновление сеанса после перехода экрана в неактивное состояние                   |                                                  Properties/AllowSessionResume                                                   |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|             Разрешите использование учетной записи устройства для проверки подлинности прокси-сервера             |                                                  Properties/AllowAutoProxyAuth                                                   |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Отключите автоматическое заполнение данных о приглашенных из запланированных собраний в диалоговом окне входа |                                               Properties/DisableSignInSuggestions                                                |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|              Отключите функцию "Мои собрания и файлы" в меню "Пуск"               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    Да </br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                     Установка LanProfile для проверки подлинности по стандарту безопасности 802.1x в проводной сети                     |                                                         Dot3/LanProfile                                                          | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                    Установка EapUserData для проверки подлинности по стандарту безопасности 802.1x в проводной сети                     |                                                         Dot3/EapUserData                                                         | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

### <a name="supported-windows-10-settings"></a>Поддерживаемые параметры Windows 10

Помимо характерных для Surface Hub параметров существует множество параметров, характерных для всех устройств Windows10. Эти параметры определены в [Справочнике по поставщикам служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

В следующих таблицах представлены сведения о параметрах Windows 10, которые были проверены для Surface Hub. Составлена таблица с параметрами для следующих областей: безопасность, браузер, обновления Windows, Защитник Windows, удаленная перезагрузка, сертификаты и журналы. Каждая таблица определяет, поддерживается ли параметр с помощью Microsoft Intune, Microsoft Endpoint Configuration Manager или SyncML.

#### <a name="security-settings"></a>Параметры безопасности

|      Параметр       |                                            Подробности                                             |                                                                          Справочник по CSP                                                                           |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Разрешить Bluetooth   |                      Оставьте этот параметр включенным для поддержки периферийных устройств Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Политики Bluetooth | Используйте, чтобы задать имя устройства Bluetooth и заблокировать рекламу, обнаружение и автоматическое связывание. |                     Bluetooth/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|    Разрешите использование камеры    |                           Оставьте этот параметр включенным для Skype для бизнеса.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|   Разрешить расположение   |                        Оставьте этот параметр включенным для поддержки приложений, таких как "Карты".                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Да. <br> .                    | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Разрешить телеметрию   |                    Оставьте этот параметр включенным, чтобы помочь Майкрософт в совершенствовании Surface Hub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Разрешите USB-устройства  |                     Оставьте этот параметр включенным, чтобы поддерживать USB-устройства на Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows. 

#### <a name="browser-settings"></a>Параметры обозревателя

|                          Параметр                          |                                                                        Подробности                                                                        |                                                                             Справочник по CSP                                                                              |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Домашние страницы                         |                                               Используется для настройки домашних страниц по умолчанию в Microsoft Edge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                       Разрешить файлы cookie                       |                    Surface Hub автоматически удаляет файлы cookie в конце сеанса. Используйте это для блокирования cookie во время сеанса.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                   Разрешить средства разработчика                   |                                                   Используйте, чтобы заблокировать использование средств разработчика F12 пользователями.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                    Allow Do Not Track                     |                                                          Используйте для включения функции неотслеживания заголовков.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                       Разрешить всплывающие окна                       |                                                         Используйте для блокирования всплывающих окон в браузере.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                 Разрешить варианты поиска                  |                                                  Используйте для блокирования вариантов поиска в адресной строке.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                     Разрешить Защитник Windows SmartScreen                     |                                                       Чтобы включить эту возможность, Защитник Windows SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Предотвращение игнорирования Защитник Windows SmartScreen для веб-сайтов |     Чтобы получить дополнительную безопасность, используйте для того, чтобы пользователи не Защитник Windows smartScreen и не получили доступ к потенциально вредоносным веб-сайтам.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Предотвращение игнорирования Защитник Windows SmartScreen для файлов   | Для дополнительной безопасности используйте для того, чтобы пользователи не Защитник Windows smartScreen и не загружали непроверенные файлы из Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="windows-update-settings"></a>Параметры Центра обновления Windows

|                      Параметр                      |                                                                                                           Подробности                                                                                                            |                                                                    Справочник по CSP                                                                    |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Использование Current Branch и Current Branch for Business |                                                       Используйте для настройки Центра обновления Windows для бизнеса— см. раздел [Обновления Windows](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Отсрочка обновлений компонентов               |                                                                                                          См. выше.                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Отсрочка исправлений               |                                                                                                          См. выше.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Приостановка обновлений компонентов               |                                                                                                          См. выше.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Приостановка исправлений               |                                                                                                          См. выше.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|           Настройка устройства для использования служб WSUS            |                                            Используйте для подключения устройства Surface Hub к WSUS вместо Центра обновления Windows— см. раздел [Обновления Windows](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Оптимизация доставки               | Используйте одноранговый обмен содержимым, чтобы свести к минимуму проблемы с пропускной способностью во время обновлений. См. подробные сведения в разделе [Настройка оптимизации доставки для Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization). |         DeliveryOptimization/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="windows-defender-settings"></a>Параметры Защитника Windows

|      Параметр      |                                              Подробности                                               |                                                     Справочник по CSP                                                      |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Политики Защитника |            Используйте для настройки различных параметров Защитника, включая время запланированного сканирования.            | Defender/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Состояние Защитника  | Используйте для инициалов проверки Defender, принудительного обновления сведении безопасности, запроса любых обнаруженных угроз. |                   [Поставщик служб конфигурации Defender](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Да                        |                       Да                       |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="remote-reboot"></a>Удаленная перезагрузка

|                       Параметр                        |                                                          Подробности                                                          |                                                             Справочник по CSP                                                             |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Перезагрузите устройство немедленно.             | Используйте совместно с Azure Monitor, чтобы свести к минимуму затраты на поддержку — см. в видеоролике [Monitor your Microsoft Surface Hub.](monitor-surface-hub.md) |        ./Vendor/MSFT/Reboot/RebootNow <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Да                        |                       Нет                        |             Да             |
|    Перезагрузите устройство в запланированную дату и время    |                                                        См. выше.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Перезагружайте устройство ежедневно в запланированную дату и время |                                                        См. выше.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="install-certificates"></a>Установка сертификатов

|             Параметр             |                           Подробности                            |                                           Справочник по CSP                                            |                                                         Поддержка<br>Intune?                                                          |                                                                  Поддержка<br>Configuration Manager?                                                                  | Поддержка<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Установка сертификатов доверенного ЦС | Используйте для развертывания сертификатов доверенных корневых и промежуточных ЦС. | [Поставщик служб конфигурации RootCATrustedCertificates](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Да. <br> См. раздел [Настройка профилей сертификата Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Да. <br> Узнайте, [как создать профили сертификатов в Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles) |             Да             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="collect-logs"></a>Собирать журналы

|     Параметр      |                      Подробности                       |                                     Справочник по CSP                                      | Поддержка<br>Intune? | Поддержка<br>Configuration Manager? | Поддержка<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Сбор журналов трассировки событий Windows | Используйте для удаленного сбора журналов трассировки событий Windows из Surface Hub. | [Поставщик служб конфигурации DiagnosticLog](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Нет             |                    Нет                    |             Да             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="set-network-quality-of-service-qos-policy"></a>Настройка политики качества обслуживания сети (QoS)

|        Параметр         |                                                            Подробности                                                             |                                                    Справочник по CSP                                                     |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Настройка политики качества обслуживания сети | Используйте этот параметр, чтобы настроить политику качества обслуживания сети для выполнения набора действий с сетевым трафиком. Это полезно для определения приоритета сетевых пакетов Skype. | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="set-network-proxy"></a>Установка прокси-сервера сети

|      Параметр      |                               Подробности                               |                                                Справочник по CSP                                                 |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Установка прокси-сервера сети | NetworkProxy CSP позволяет настраивать прокси-сервер для соединений Wi-Fi и Ethernet. | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### <a name="configure-start-menu"></a>Настройка меню "Пуск"

|       Параметр        |                                                                       Подробности                                                                        |                                                        Справочник по CSP                                                         |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Настройка меню "Пуск" | Используется для настройки приложений, отображаемых в меню "Пуск". Дополнительные сведения см. в разделе [Настройка меню "Пуск" Surface Hub](surface-hub-start-menu.md) | [CSP политики: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

### <a name="generate-oma-uris-for-settings"></a>Создание универсальных кодов ресурса OMA для параметров 
Для создания настраиваемой политики в Intune или настраиваемого параметра в Microsoft Endpoint Configuration Manager необходимо использовать OMA URI параметра параметра.

**Создание универсального кода ресурса OMA для любого параметра в документации поставщика служб конфигурации**
1. В документации поставщика служб конфигурации идентифицируйте корневой узел CSP. Как правило, он выглядит следующим образом: `./Vendor/MSFT/<name of CSP>` <br>
*Например, корневой узел [поставщика служб конфигурации SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) — `./Vendor/MSFT/SurfaceHub`.*
2. Определите путь к узлу для нужного параметра. <br>
*Например, путь к узлу для параметра, позволяющего включить беспроводную проекцию, — `InBoxApps/WirelessProjection/Enabled`.*
3. Добавьте путь к узлу в корневой узел, чтобы создать универсальный код ресурса OMA. <br>
*Например, универсальный код ресурса OMA для параметра, включающего беспроводную проекцию,— это `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`.*

Этот тип данных также указан в документации поставщика служб конфигурации. Самые распространенные типы данных:
- char (строка)
- int (целое)
- bool (логическое)


## <a name="example-manage-surface-hub-settings-with-microsoft-intune"></a>Пример: управление параметрами Surface Hub с использованием Microsoft Intune

Microsoft Intune можно использовать для управления параметрами Surface Hub. Для пользовательских параметров следуйте инструкциям в разделе [Настройка пользовательских параметров устройства в Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure). В поле **Платформа** выберите **Windows 10 и более поздние версии**, а в поле **Тип профиля** выберите **Ограничения устройств (Windows 10 для совместной работы)**.



## <a name="example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager"></a>Пример: управление настройками Surface Hub с помощью Microsoft Endpoint Configuration Manager
Configuration Manager поддерживает управление современными устройствами, для управления ими которых не требуется клиент Configuration Manager, в том числе Surface Hub. Если вы уже используете Диспетчер конфигурации для управления другими устройствами в организации, вы можете продолжать использовать консоль Configuration Manager в качестве единого расположения для управления концентраторами Surface.

> [!NOTE]
> Эти инструкции основаны на текущей ветви диспетчера конфигурации.

**Создание элемента конфигурации для параметров Surface Hub**

1. В рабочей области **Активы и соответствие** консоли Configuration Manager щелкните **Обзор** > **Параметры соответствия** > **Элементы конфигурации**.
2. На вкладке **Домашняя** в группе **Создание** щелкните **Создать элемент конфигурации**.
3. На странице **Общие** мастера создания элементов конфигурации укажите имя и необязательное описание элемента конфигурации.
4. В разделе **Параметры для устройств, управляемых без использования клиента Configuration Manager** выберите **Windows 8.1 и Windows 10**, а затем нажмите кнопку **Далее**.

    ![пример пользовательского интерфейса](images/configmgr-create.png)
5. На странице **Поддерживаемые платформы** разверните **Windows 10** и выберите **Все Windows 10 для совместной работы и выше**. Отмените выбор других платформ Windows и нажмите кнопку **Далее**.

    ![выбор платформы](images/configmgr-platform.png)
7. На странице **Параметры устройства** в разделе **Группы параметров устройств** выберите **Windows 10 для совместной работы**.


8. На странице **Windows 10 для совместной работы** настройте требуемые параметры.

    ![Windows 10 для совместной работы](images/configmgr-team.png)
9. Для управления параметрами, которые недоступны на странице Windows 10 для рабочих групп, потребуется создать пользовательские параметры. На странице **Параметры устройства** установите флажок **Настроить дополнительные параметры, которые не входят в группы параметров по умолчанию**.

    ![дополнительные параметры](images/configmgr-additional.png)
10. На странице **Дополнительные параметры** щелкните **Добавить**.
11. В диалоговом окне **Обзор параметров** щелкните **Создать параметр**.
12. В диалоговом окне **Создание параметра** на вкладке **Общие** укажите имя и необязательное описание пользовательского параметра.
13. В разделе **Тип параметра**выберите **Универсальный код ресурса OMA**.
14. Заполните форму, чтобы создать новый параметр, а затем нажмите кнопку **ОК**.

    ![параметр OMA URI](images/configmgr-oma-uri.png)
15. В диалоговом окне **Обзор параметров** в разделе **Доступные параметры** выберите новый созданный параметр и нажмите **Выбрать**.
16. В диалоговом окне **Создание правила** заполните форму, чтобы указать правил для параметра, а затем нажмите кнопку **ОК**.
17. Повторите шаги с 9 по 15 для каждого пользовательского параметра, который требуется добавить в элемент конфигурации.
18. Когда все будет готово, в диалоговом окне **Обзор параметров** щелкните **Закрыть**.
19. Завершите работу мастера. <br> Новый элемент конфигурации можно просмотреть в узле **Элементы конфигурации** рабочей области **Активы и соответствие**.

Дополнительные сведения см. в статьи Создание элементов конфигурации [для устройств Windows 8.1 и Windows 10,](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client)управляемых без клиента Microsoft Endpoint Configuration Manager.

## <a name="related-topics"></a>Статьи по теме

[Управление Microsoft Surface Hub](manage-surface-hub.md)











