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
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: 2bee8b58b7978923c6e60e43f9e10a85dc4bec06
ms.sourcegitcommit: 17170c03206d190851b5f8e794fcc83ebbed7b5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103905"
---
# Управление параметрами с помощью поставщика MDM (Surface Hub)

Surface Hub и другие устройства с Windows 10 позволяют ИТ-администраторам управлять параметрами и политиками с помощью службы управления мобильными устройствами (MDM). Встроенный компонент управления взаимодействует с сервером управления, поэтому нет необходимости устанавливать на устройстве дополнительные клиенты. For more information, see [Windows 10 mobile device management](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

Surface Hub has been validated with Microsoft's first-party MDM providers:
- Microsoft Intune standalone
- On-premises MDM with Microsoft Endpoint Configuration Manager

You can also manage Surface Hubs using any third-party MDM provider that can communicate with Windows 10 using the MDM protocol.

## <a href="" id="enroll-into-mdm"></a>Enroll a Surface Hub into MDM
You can enroll your Surface Hubs using bulk, manual, or automatic enrollment.

### Bulk enrollment
**Настройка массовой регистрации**
- Surface Hub поддерживает [поставщик служб конфигурации подготовки](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) для массовой регистрации в службе MDM. Дополнительные сведения см. в разделе [Массовая регистрация Windows 10](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--OR--
- If you have an on-premises Microsoft Endpoint Configuration Manager infrastructure, see [How to bulk enroll devices with On-premises Mobile Device Management in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Manual enrollment
**Настройка регистрации вручную**
1. На Surface Hub откройте приложение **Параметры**.
2. Введите учетные данные администратора устройства.
3. Выберите **Это устройство** и перейдите в раздел **Управление устройствами**.
4. В разделе **Управление устройствами** выберите **+ Управление устройствами**.
5. Follow the instructions in the dialog to connect to your MDM provider.

### Automatic enrollment via Azure Active Directory join

Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory. 

First step is to set up Automatic MDM enrollment. See [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Then, when devices are setup during First-run, pick the option to join to Azure Active Directory, see [Set up admins for this device page](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## Manage Surface Hub settings with MDM

Можно использовать MDM для управления некоторыми [параметрами поставщика служб конфигурации Surface Hub](#supported-surface-hub-csp-settings) и некоторыми [параметрами Windows 10](#supported-windows-10-settings). Depending on the MDM provider that you use, you may set these settings using a built-in user interface, or by deploying custom SyncML. Microsoft Intune and Microsoft Endpoint Configuration Manager provide built-in experiences to help create policy templates for Surface Hub. Refer to documentation from your MDM provider to learn how to create and deploy SyncML.

### Поддерживаемые параметры поставщика служб конфигурации Surface Hub

You can configure the Surface Hub settings in the following table using MDM. The table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

For more information, see [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Параметр                                      |                                                    Узел в поставщике служб конфигурации SurfaceHub                                                    |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Часы обслуживания                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Да                        |                       Да                       |             Да             |
|              Автоматическое включение экрана с помощью датчиков движения               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Да                        |                       Да                       |             Да             |
|                      Требовать PIN-код для беспроводной проекции                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Да                        |                       Да                       |             Да             |
|                            Включение беспроводной проекции                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                 Канал Miracast для использования беспроводной проекции                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|              Подключение к рабочей области Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                         Фоновое изображение экрана приветствия                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Да                        | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Сведения о собрании, отображаемые на приветственном экране                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Да                        | Yes.<br> [Use a custom setting.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             Yes             |
|                      Понятное имя для беспроводной проекции                       |                                                     Properties/FriendlyName                                                      | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                   Device account                                                 | DeviceAccount/*`<name_of_policy>`* <br> См. раздел [Поставщик служб конфигурации SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Нет                        |                       Нет                        |             Да             |
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

### Поддерживаемые параметры Windows 10

Помимо характерных для Surface Hub параметров существует множество параметров, характерных для всех устройств Windows10. Эти параметры определены в [Справочнике по поставщикам служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

В следующих таблицах представлены сведения о параметрах Windows 10, которые были проверены для Surface Hub. There is a table with settings for these areas: security, browser, Windows Updates, Windows Defender, remote reboot, certificates, and logs. Each table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

#### Security settings

|      Параметр       |                                            Подробности                                             |                                                                          Справочник по CSP                                                                           |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Разрешить Bluetooth   |                      Оставьте этот параметр включенным для поддержки периферийных устройств Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Политики Bluetooth | Используйте, чтобы задать имя устройства Bluetooth и заблокировать рекламу, обнаружение и автоматическое связывание. |                     Bluetooth/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|    Разрешите использование камеры    |                           Оставьте этот параметр включенным для Skype для бизнеса.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|   Разрешить расположение   |                        Оставьте этот параметр включенным для поддержки приложений, таких как "Карты".                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Да. <br> .                    | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Разрешить телеметрию   |                    Оставьте этот параметр включенным, чтобы помочь Майкрософт в совершенствовании Surface Hub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Да. <br>                     | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Разрешите USB-устройства  |                     Оставьте этот параметр включенным, чтобы поддерживать USB-устройства на Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows. 

#### Параметры обозревателя

|                          Параметр                          |                                                                        Подробности                                                                        |                                                                             Справочник по CSP                                                                              |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Домашние страницы                         |                                               Используется для настройки домашних страниц по умолчанию в Microsoft Edge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                       Разрешить файлы cookie                       |                    Surface Hub автоматически удаляет файлы cookie в конце сеанса. Используйте это для блокирования cookie во время сеанса.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                   Разрешить средства разработчика                   |                                                   Используйте, чтобы заблокировать использование средств разработчика F12 пользователями.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                    Allow Do Not Track                     |                                                          Используйте для включения функции неотслеживания заголовков.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                       Разрешить всплывающие окна                       |                                                         Используйте для блокирования всплывающих окон в браузере.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|                 Разрешить варианты поиска                  |                                                  Используйте для блокирования вариантов поиска в адресной строке.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                     Allow Windows Defender SmartScreen                     |                                                       Keep this enabled to turn on Windows Defender SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
| Prevent ignoring Windows Defender SmartScreen warnings for websites |     For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from accessing potentially malicious websites.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|  Prevent ignoring Windows Defender SmartScreen warnings for files   | For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from downloading unverified files from Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Параметры Центра обновления Windows

|                      Параметр                      |                                                                                                           Подробности                                                                                                            |                                                                    Справочник по CSP                                                                    |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Use Current Branch or Current Branch for Business |                                                       Используйте для настройки Центра обновления Windows для бизнеса— см. раздел [Обновления Windows](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Отсрочка обновлений компонентов               |                                                                                                          См. выше.                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Отсрочка исправлений               |                                                                                                          См. выше.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Приостановка обновлений компонентов               |                                                                                                          См. выше.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Приостановка исправлений               |                                                                                                          См. выше.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|           Настройка устройства для использования служб WSUS            |                                            Используйте для подключения устройства Surface Hub к WSUS вместо Центра обновления Windows— см. раздел [Обновления Windows](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|               Оптимизация доставки               | Используйте одноранговый обмен содержимым, чтобы свести к минимуму проблемы с пропускной способностью во время обновлений. См. подробные сведения в разделе [Настройка оптимизации доставки для Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization). |         DeliveryOptimization/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Параметры Защитника Windows

|      Параметр      |                                              Подробности                                               |                                                     Справочник по CSP                                                      |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Политики Защитника |            Используйте для настройки различных параметров Защитника, включая время запланированного сканирования.            | Defender/*`<name of policy>`* <br> См. раздел [Поставщик служб конфигурации политики](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
|  Defender status  | Use to initiate a Defender scan, force a Security intelligence update, query any threats detected. |                   [Defender CSP](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Yes                        |                       Да                       |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Удаленная перезагрузка

|                       Параметр                        |                                                          Подробности                                                          |                                                             Справочник по CSP                                                             |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Перезагрузите устройство немедленно.             | Используйте в сочетании с OMS, чтобы свести к минимуму затраты на поддержку— см. раздел [Отслеживание Microsoft Surface Hub](monitor-surface-hub.md). |        ./Vendor/MSFT/Reboot/RebootNow <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Да                        |                       Нет                        |             Да             |
|    Перезагрузите устройство в запланированную дату и время    |                                                        См. выше.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |
| Перезагружайте устройство ежедневно в запланированную дату и время |                                                        См. выше.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> См. раздел [Перезагрузка поставщика служб конфигурации](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Установка сертификатов

|             Параметр             |                           Подробности                            |                                           Справочник по CSP                                            |                                                         Поддержка<br>Intune?                                                          |                                                                  Поддержка<br>Configuration Manager?                                                                  | Поддержка<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Установка сертификатов доверенного ЦС | Используйте для развертывания сертификатов доверенных корневых и промежуточных ЦС. | [Поставщик служб конфигурации RootCATrustedCertificates](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Да. <br> См. раздел [Настройка профилей сертификата Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Yes. <br> See [How to create certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Yes             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Собирать журналы

|     Параметр      |                      Подробности                       |                                     Справочник по CSP                                      | Поддержка<br>Intune? | Поддержка<br>Configuration Manager? | Поддержка<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Collect ETW logs | Используйте для удаленного сбора журналов трассировки событий Windows из Surface Hub. | [Поставщик служб конфигурации DiagnosticLog](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Нет             |                    Нет                    |             Да             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Настройка политики качества обслуживания сети (QoS)

|        Параметр         |                                                            Подробности                                                             |                                                    Справочник по CSP                                                     |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network QoS Policy | Используйте этот параметр, чтобы настроить политику качества обслуживания сети для выполнения набора действий с сетевым трафиком. Это полезно для определения приоритета сетевых пакетов Skype. | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Установка прокси-сервера сети

|      Параметр      |                               Подробности                               |                                                Справочник по CSP                                                 |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network proxy | NetworkProxy CSP позволяет настраивать прокси-сервер для соединений Wi-Fi и Ethernet. | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

#### Настройка меню "Пуск"

|       Параметр        |                                                                       Подробности                                                                        |                                                        Справочник по CSP                                                         |            Поддержка<br>Intune?             |    Поддержка<br>Configuration Manager?     | Поддержка<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configure Start menu | Используется для настройки приложений, отображаемых в меню "Пуск". Дополнительные сведения см. в разделе [Настройка меню "Пуск" Surface Hub](surface-hub-start-menu.md) | [CSP политики: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Да <br> [Используйте пользовательскую политику.](#example-manage-surface-hub-settings-with-microsoft-intune) | Да.<br> [Используйте пользовательский параметр.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Да             |

\*Параметры, поддерживаемые SyncML, также можно настроить в пакете подготовки конструктора конфигураций Windows.

### Generate OMA URIs for settings 
You need to use a setting's OMA URI to create a custom policy in Intune, or a custom setting in Microsoft Endpoint Configuration Manager.

**To generate the OMA URI for any setting in the CSP documentation**
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


## Пример: управление параметрами Surface Hub с использованием Microsoft Intune

Microsoft Intune можно использовать для управления параметрами Surface Hub. Для пользовательских параметров следуйте инструкциям в разделе [Настройка пользовательских параметров устройства в Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure). For **Platform**, select **Windows 10 and later**, and in **Profile type**, select **Device restrictions (Windows 10 Team)**.



## Example: Manage Surface Hub settings with Microsoft Endpoint Configuration Manager
Configuration Manager supports managing modern devices that do not require the Configuration Manager client to manage them, including Surface Hub. If you already use Configuration Manager to manage other devices in your organization, you can continue to use the Configuration Manager console as your single location for managing Surface Hubs.

> [!NOTE]
> These instructions are based on the current branch of Configuration Manager.

**To create a configuration item for Surface Hub settings**

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
19. Завершите работу мастера. <br> You can view the new configuration item in the **Configuration Items** node of the **Assets and Compliance** workspace.

For more information, see [Create configuration items for Windows 8.1 and Windows 10 devices managed without the Microsoft Endpoint Configuration Manager client](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## Related topics

[Управление Microsoft Surface Hub](manage-surface-hub.md)











