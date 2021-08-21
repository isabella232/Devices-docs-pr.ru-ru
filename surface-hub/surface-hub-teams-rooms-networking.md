---
title: Настройка сетей и качества обслуживания для Microsoft Teams в Surface Hub
description: В этой статье разъясняются требования и рекомендации по сетевому обслуживанию и качеству обслуживания для оптимизации Комнаты Microsoft Teams на Surface Hub.
keywords: Комнаты Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909999"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>Настройка сетей и качества обслуживания для Комнаты Microsoft Teams на Surface Hub

В этой статье рассказывается, как подготовить среду для оптимизации Комнаты Microsoft Teams на Surface Hub.

## <a name="create-and-test-a-device-account"></a>Создание и тестирование учетной записи устройства

Учетная запись устройства — это учетная запись, которую клиент Комнаты Microsoft Teams для доступа к функциям из Exchange, например календаря, и для Skype для бизнеса. [См. создание и тестирование учетной записи устройства](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>Проверка доступности сети

> [!TIP]
> Мы настоятельно рекомендуем использовать методы настройки сети, перечисленные в Microsoft 365 [принципов подключения к сети](https://aka.ms/pnc)

Комнаты Teams на Surface Hub должна иметь доступ к сети, которая соответствует этим требованиям:

- Доступ к экземпляру Active Directory или Azure Active Directory (Azure AD)
- Доступ к серверу, который может предоставить IP-адрес с помощью DHCP. Комнаты Microsoft Teams на Surface Hub невозможно настроить с помощью статического IP-адреса.
- Доступ к портам HTTP 80 и 443.
- Порты TCP и UDP настроены так, как описано в требованиях к порту и протоколу для Microsoft 365 и [Office 365 URL-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges) и IP-адресов для Microsoft Teams.

> [!IMPORTANT]
> Комнаты Microsoft Teams не поддерживает проверку подлинности прокси, так как может мешать регулярным операциям Teams. Убедитесь Surface Hub что Microsoft 365 или конечные точки службы были освобождены от проверки подлинности прокси перед началом работы с Комнаты Teams на Surface Hub.

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>Реализация качества службы (QoS) на Surface Hub

Качество службы (QoS) — это сочетание сетевых технологий, которое позволяет администраторам оптимизировать взаимодействие аудио- и видео- и приложений в режиме реального времени.
Настройка QoS для Microsoft Teams на Surface Hub можно сделать с помощью поставщика управления мобильными устройствами [(MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью пакета [обеспечения.](provisioning-packages-for-surface-hub.md)

Настройка QoS для Surface Hub с Microsoft Intune:

1. В Intune [создайте настраиваемую политику.](/intune/custom-settings-configure)

2. В **настраиваемом OMA-URI Параметры**выберите **Добавить**. Для каждого добавленного параметра введите имя, описание (необязательно), тип данных, OMA-URI и значение.

3. Чтобы обеспечить оптимальное качество видео и Surface Hub, добавьте на устройство следующие параметры QoS.

    | Имя                  | Описание           | OMA-URI                                                                        | Тип    | Значение       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **Звуковые порты**       | Диапазон звуковых портов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | Строка  | 50000-50019 |
    | **DSCP звука**        | Маркировка звуковых портов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | целое число | 46          |
    | **Видеопорт**        | Диапазон видеопортов      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | Строка  | 50020-50039 |
    | **DSCP видео**        | Маркировка видеопортов   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | целое число | 34          |
    | **Общий порт**      | Диапазон общего доступа к порту    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | Строка  | 50040-50059 |
    | **Совместное использование DSCP**      | Разметка портов общего доступа | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | целое число | 18          |

4. После создания политики разверни ее в Surface Hub.

## <a name="learn-more"></a>Подробнее

- [Реализация качества службы (QoS) в Microsoft Teams](/microsoftteams/qos-in-teams)
