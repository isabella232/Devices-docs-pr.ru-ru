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
ms.openlocfilehash: 406fcc58bdb09d7fd47966cd17123d55faec2b65
ms.sourcegitcommit: ea853f2dba67e63e6df33538670fd581e17facab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "11408794"
---
# <a name="manage-surface-hub-2s-with-intune"></a>Управление Surface Hub 2S с помощью Intune

## <a name="register-surface-hub-2s-with-intune"></a>Регистрация Surface Hub 2S в Intune

Surface Hub 2S позволяет ИТ-администраторам управлять параметрами и политиками с помощью службы управления мобильными устройствами (MDM). Surface Hub 2S содержит встроенный компонент управления для взаимодействия с сервером управления, поэтому нет необходимости устанавливать на устройстве дополнительные клиенты.

### <a name="manual-registration"></a>Регистрация вручную

1. Откройте приложение **Параметры** на Surface Hub 2S и вопишитесь в качестве локального администратора. Откройте **Surface Hub** > **Управление устройством** и выберите **+** для добавления.
2. Вам будет предложено войти в учетную запись, чтобы использовать для Intune. После проверки подлинности устройство будет автоматически зарегистрировано в Intune.

   ![Регистрация Surface Hub 2S в Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> Учетная запись, используемая для проверки подлинности, будет учетной записью регистрации Intune и должна быть лицензирована для Intune.

### <a name="auto-registration--azure-active-directory-affiliated"></a>Автоматическая регистрация — связь с Azure Active Directory

В процессе начальной настройки, когда выполняется связывание Surface Hub с клиентом Azure AD с включенной автоматической регистрацией в Intune, устройство автоматически регистрируется в Intune. Дополнительные сведения см. в статье [Способы регистрации в Intune для устройств Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## <a name="managing-windows-10-team-settings-with-intune"></a>Управление настройками команды Windows 10 с помощью Intune

1. Впишитесь **в Microsoft Endpoint Manager**, выберите **профили конфигурации устройств**Создать  >  ****  >  **профиль**. 
2. В **платформе**выберите **ограничения устройств Windows 10**и более поздних шаблонов  >  ****  >  **(Windows 10 Team),** а затем выберите **Create**. 
3. Теперь можно просмотреть и выбрать параметры предустановленного ограничения устройств для Surface Hub и Surface Hub 2S.

 ![Настройка ограничений устройства для Surface Hub 2.](images/sh2-set-intune3.png) <br>

Эти параметры охватывают следующие категории: приложения и опыт, оперативные сведения Azure, обслуживание, сеанс и беспроводная проекция.  

## <a name="supported-configuration-service-providers-csps"></a>Поддерживаемые поставщики служб конфигурации (CSPs)

Помимо политик, доступных непосредственно через консоль Intune, существуют многочисленные поставщики служб конфигурации (CSPs), которые соеди- 

Microsoft обычно предоставляет новые CSP с каждой новой версией операционной системы Windows 10. Обновление [Windows 10 Team 2020](surface-hub-2020-update.md) включает более 20 новых и обновленных политик управления устройствами для Surface Hub и Surface Hub 2S. Эти политики MDM дают ИТ-администраторам улучшенный контроль над обновлениями приложений из Microsoft Store, настройками беспроводных проекций, такими как Miracast над инфраструктурой, сетевыми настройками, такими как Quality-Of-Service и проводной проверкой подлинности 802.1x, а также новыми настройками конфиденциальности и GDPR.

Для получения дополнительных сведений см. следующие ресурсы. 

- [Справочник по поставщикам служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [Поставщик служб конфигурации SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Политика поставщиков служб конфигурации (CSP), поддерживаемая Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Новые возможности обновления Surface Hub Team 2020](surface-hub-2020-update-whats-new.md)

## <a name="quality-of-service-qos-settings"></a>Параметры качества обслуживания (QoS)

Чтобы обеспечить оптимальное качество видео и звука на Surface Hub 2, добавьте следующие параметры качества обслуживания в устройстве. 

### <a name="microsoft-teams-qos-settings"></a>Параметры качества обслуживания Microsoft Teams 

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


### <a name="skype-for-business-qos-settings"></a>Параметры качества обслуживания Skype для бизнеса

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

## <a name="microsoft-teams-settings"></a>Параметры Microsoft Teams

Вы можете настроить различные параметры Microsoft Teams с помощью Intune.

### <a name="modes"></a>Режимы

Surface Hub 2 поставляется с установленным Microsoft Teams в режиме 0, поддерживающем Microsoft Teams и Skype для бизнеса. Режимы функционируют, как описано ниже:

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — Microsoft Teams с функциональностью Skype для бизнеса для запланированных собраний.
- Режим 2 — только Microsoft Teams.

Чтобы настроить режим, добавьте следующие параметры в настраиваемый [профиль конфигурации устройства.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Имя | Описание | OMA-URI | Тип | Значение |
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0 или 1 или 2|

### <a name="coordinated-meetings-and-proximity-join"></a>Координированные собрания и регистрация близости

Функции команд координируемых собраний и близости можно настроить через [XML-файл,](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) развернутый с помощью профиля Intune.
