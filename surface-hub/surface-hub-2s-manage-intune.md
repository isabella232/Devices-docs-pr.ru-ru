---
title: Управление Surface Hub 2S с помощью Intune
description: Узнайте, как обновить Surface Hub 2S и управлять им с помощью Intune.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 3b3b5ed47e3a34369c6890aac051436db1f42347
ms.sourcegitcommit: f8f32455b1230742c58ee74004cbaaad037069b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328213"
---
# Управление Surface Hub 2S с помощью Intune

## Регистрация Surface Hub 2S в Intune

Surface Hub 2S позволяет ИТ-администраторам управлять параметрами и политиками с помощью службы управления мобильными устройствами (MDM). Surface Hub 2S содержит встроенный компонент управления для взаимодействия с сервером управления, поэтому нет необходимости устанавливать на устройстве дополнительные клиенты.

### Регистрация вручную

1. Откройте приложение **"Параметры"** на Surface Hub 2S и во sign in as a local administrator. Откройте **Surface Hub** > **Управление устройством** и выберите **+** для добавления.
2. Вам будет предложено войти с использованием учетной записи для Intune. После проверки подлинности устройство будет автоматически зарегистрировано в Intune.

   ![Регистрация Surface Hub 2S в Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> Учетная запись, используемая для проверки подлинности, будет учетной записью регистрации Intune и должна быть лицензирована для Intune.

### Автоматическая регистрация — связь с Azure Active Directory

В процессе начальной настройки, когда выполняется связывание Surface Hub с клиентом Azure AD с включенной автоматической регистрацией в Intune, устройство автоматически регистрируется в Intune. Дополнительные сведения см. в статье [Способы регистрации в Intune для устройств Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## Управление настройками Windows 10 Team с помощью Intune

1. Во sign into **Microsoft Endpoint Manager**, select **Devices**  >  **Configuration profiles**  >  **Create profile**. 
2. В **группе "Платформа"** выберите **ограничения для Windows 10**и более поздних устройств  >  **(Windows 10 Team)** и выберите команду **"Создать".** 
3. Теперь вы можете просматривать и выбирать предустановленные параметры ограничений устройств для Surface Hub и Surface Hub 2S.

 ![Настройка ограничений устройства для Surface Hub 2.](images/sh2-set-intune3.png) <br>

Эти параметры охватывают следующие категории: приложения и возможности, операционные данные Azure, обслуживание, сеанс и беспроводная проекция.  

## Поддерживаемые поставщики служб конфигурации (CPS)

Помимо политик, доступных непосредственно через консоль Intune, существует множество поставщиков служб конфигурации (CPS), которые соединуют с ключами реестра или файлами. 

Корпорация Майкрософт обычно предоставляет новые CSP с каждой новой версией операционной системы Windows 10. Обновление [Windows 10 для группы 2020](surface-hub-2020-update.md) включает более 20 новых и обновленных политик управления устройствами для Surface Hub и Surface Hub 2S. Эти политики MDM дают ИТ-администраторам улучшенный контроль над обновлениями приложений из Microsoft Store, параметры беспроводной проекции, такие как Miracast по инфраструктуре, сетевые параметры, такие как качество обслуживания и проводная проверка подлинности 802.1x, а также новые параметры конфиденциальности и GDPR.

Для получения дополнительных сведений см. следующие ресурсы. 

- [Справочник по поставщикам служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [Поставщик служб конфигурации SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Политика поставщиков служб конфигурации (CSP), поддерживаемая Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Новые возможности обновления Surface Hub Team 2020](surface-hub-2020-update-whats-new.md)

## Параметры качества обслуживания (QoS)

Чтобы обеспечить оптимальное качество видео и звука на Surface Hub 2, добавьте следующие параметры качества обслуживания в устройстве. 

### Параметры качества обслуживания Microsoft Teams 

| Имя | Описание | OMA-URI | Тип | Значение |
|:------ |:------------- |:--------- |:------ |:------- |
|**Звуковые порты**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Строка  | 3478-3479 |
|**DSCP звука**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | целое число | 46 |
|**Видеопорт**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Строка  | 3480 |
|**DSCP видео**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | целое число | 34 |
|**Общий порт**| Диапазон портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Строка  | 3481 |
|**Общий доступ к DSCP**| Маркировка общего доступа к портам | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | целое число | 18 |
|**Звуковые порты P2P**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Строка  | 50000-50019 |
|**DSCP звука P2P**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | целое число | 46 |
|**Видеопорты P2P**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Строка  | 50020-50039 |
|**DSCP видео P2P**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | целое число | 34 |
|**Порты общего доступа P2P**| Диапазон портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | Строка  | 50040-50059 |
|**P2P Sharing DSCP**| Маркировка общего доступа к портам | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | целое число | 18 |


### Параметры качества обслуживания Skype для бизнеса

| Имя                 | Описание           | OMA-URI                                                                    | Тип    | Значение                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Звуковые порты          | Диапазон звуковых портов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | Строка  | 50000-50019                    |
| DSCP звука           | Маркировка звуковых портов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | целое число | 46                             |
| Источник звука   | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | Строка  | Microsoft.PPISkype.Windows.exe |
| Видеопорты          | Диапазон видеопортов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | Строка  | 50020-50039                    |
| DSCP видео           | Маркировка видеопортов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | целое число | 34                             |
| Источник видео   | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | Строка  | Microsoft.PPISkype.Windows.exe |
| Общий доступ к портам        | Диапазон портов общего доступа    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Строка  | 50040-50059                    |
| Общий доступ к DSCP         | Маркировка общего доступа к портам | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | целое число | 18                             |
| Общий доступ к источнику мультимедиа | Имя приложения Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | Строка  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Обе таблицы содержат диапазоны портов, используемые по умолчанию. Администраторы могут изменить диапазоны портов в панели управления Skype для бизнеса и Teams.

## Параметры Microsoft Teams

Вы можете настроить различные параметры Microsoft Teams с помощью Intune.

### Режимы

Surface Hub 2 поставляется с установленным Microsoft Teams в режиме 0, поддерживающем Microsoft Teams и Skype для бизнеса. Режимы работают, как описано ниже:

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — Microsoft Teams с функциональностью Skype для бизнеса для запланированных собраний.
- Режим 2 — только Microsoft Teams.

Чтобы настроить режим, добавьте следующие параметры в [пользовательский профиль конфигурации устройства.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Имя | Описание | OMA-URI | Тип | Значение |
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0 или 1 или 2|

### Координированные собрания и бесконтактное участие

Функции координации собраний и близкого join в Teams можно настроить с помощью [XML-файла,](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) развернутых с помощью профиля Intune.
