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
ms.date: 02/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1d1b836c18a41982497bb28c57f379408c04f8a5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836635"
---
# Управление Surface Hub 2S с помощью Intune

## Регистрация Surface Hub 2S в Intune

Surface Hub 2S позволяет ИТ-администраторам управлять параметрами и политиками с помощью службы управления мобильными устройствами (MDM). Surface Hub 2S содержит встроенный компонент управления для взаимодействия с сервером управления, поэтому нет необходимости устанавливать на устройстве дополнительные клиенты.

### Регистрация вручную

1. Войдите в качестве локального администратора в Surface Hub 2S и откройте приложение **Параметры**. Откройте **Surface Hub** > **Управление устройством** и выберите **+** для добавления.
2. После проверки подлинности устройство будет автоматически зарегистрировано в Intune.

   ![Регистрация Surface Hub 2S в Intune](images/sh2-set-intune1.png)<br>

### Автоматическая регистрация — связь с Azure Active Directory

В процессе начальной настройки, когда выполняется связывание Surface Hub с клиентом Azure AD с включенной автоматической регистрацией в Intune, устройство автоматически регистрируется в Intune. Дополнительные сведения см. в статье [Способы регистрации в Intune для устройств Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Связывание с Azure AD и автоматическая регистрация в Intune требуются для того, чтобы Surface Hub было "соответствующим требованиям устройством" в Intune. 

## Параметры выпуска Windows 10 для совместной работы

Выберите Windows 10 для совместной работы в качестве предварительно заданных ограничений устройств для Surface Hub и Surface Hub 2.

 ![Настройка ограничений устройства для Surface Hub 2.](images/sh2-set-intune3.png) <br>

К этим параметрам относятся пользовательский интерфейс и поведение приложения, регистрация в службе аналитики журналов Azure, настройка окон обслуживания, параметры сеансов и параметры Miracast. Полный список доступных параметров Windows 10 для совместной работы см. в статье [Поставщик служб конфигурации SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp).

## Дополнительные поддерживаемые поставщики служб конфигурации (CSP)

Дополнительные сведения см. в разделе [Поставщики службы конфигурации Surface Hub в Windows 10](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

## Параметры качества обслуживания (QoS)

Чтобы обеспечить оптимальное качество видео и звука на Surface Hub 2, добавьте следующие параметры качества обслуживания в устройстве. 

### Параметры качества обслуживания Microsoft Teams 

|**Имя**|**Описание**|**OMA-URI**|**Тип**|**Значение**|
|:------ |:------------- |:--------- |:------ |:------- |
|**Звуковые порты**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Строка  | 3478-3479 |
|**DSCP звука**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | целое число | 46 |
|**Видеопорт**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Строка  | 3480 |
|**DSCP видео**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | целое число | 34 |
|**Звуковые порты P2P**| Диапазон звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Строка  | 50000-50019 |
|**DSCP звука P2P**| Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | целое число | 46 |
|**Видеопорты P2P**| Диапазон видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Строка  | 50020-50039 |
|**DSCP видео P2P**| Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | целое число | 34 |


### Параметры качества обслуживания Skype для бизнеса

| Имя               | Описание         | OMA-URI                                                                  | Тип    | Значение                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| Звуковые порты        | Диапазон звуковых портов    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | Строка  | 50000-50019                    |
| DSCP звука         | Маркировка звуковых портов | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | целое число | 46                             |
| Источник звука | Имя приложения Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | Строка  | Microsoft.PPISkype.Windows.exe |
| Видеопорты        | Диапазон видеопортов    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | Строка  | 50020-50039                    |
| DSCP видео         | Маркировка видеопортов | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | целое число | 34                             |
| Источник видео | Имя приложения Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | Строка  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Обе таблицы содержат диапазоны портов, используемые по умолчанию. Администраторы могут изменить диапазоны портов в панели управления Skype для бизнеса и Teams.

## Параметры режима Microsoft Teams

Вы можете настроить приложение Microsoft Teams с помощью Intune. Surface Hub 2 поставляется с установленным Microsoft Teams в режиме 0, поддерживающем Microsoft Teams и Skype для бизнеса. Вы можете настроить режимы, как показано ниже.

### Режимы:

- Режим 0 — Skype для бизнеса с функциональностью Microsoft Teams для запланированных собраний.
- Режим 1 — Microsoft Teams с функциональностью Skype для бизнеса для запланированных собраний.
- Режим 2 — только Microsoft Teams.

Чтобы настроить режимы, добавьте следующие параметры в пользовательский профиль конфигурации устройства.

|**Имя**|**Описание**|**OMA-URI**|**Тип**|**Значение**|
|:--- |:--- |:--- |:--- |:--- |
|**ИД приложения Teams**|Имя приложения|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Строка| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Режим приложения Teams**|Режим Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|целое число| 0 или 1 или 2|
