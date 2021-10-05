---
title: Комнаты Microsoft Teams на Surface Hub
description: В этой статье представлен обзор Комнаты Microsoft Teams на Surface Hub.
keywords: Комнаты Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: a2f382b1120ba071e7dc709f1464ddb1e5118d28
ms.sourcegitcommit: 7ffb1d2d86a713a3ed4a7faa8ac82cfc49dbd55e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2021
ms.locfileid: "12068469"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Комнаты Microsoft Teams на Surface Hub

Комнаты Teams для Surface Hub автоматически заменит текущее приложение [Surface Hub Teams](hub-teams-app.md) в рамках 4-недельного глобального проката начиная с 30 сентября. Демонстрация нового Teams, доступная в настоящее время в качестве предварительного просмотра с помощью программы Windows Insider, см. в Комнаты Teams на [Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373).

## <a name="whats-new"></a>Что нового?

- Собрания, присоединенные с Surface Hub welcome Screen или новой страницей Повестки дня, присоединяются к "Edge to Edge", чтобы вывести людей на первый план.
- Знакомые функции собраний, в том числе пузырьки чата, реакции, совместное использование настольных компьютеров и приложений, дают и берут управление и аудио, PowerPoint поддержку в прямом эфире, совместном режиме и большой галерее.
- Комнаты Teams на Surface Hub может работать бок о бок с другими приложениями или свести к минимуму.
- Администраторы могут настраивать такие функции, как "Координированная встреча" и "Регистрация близости" для Surface Hub. [XML-файлы](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) поддерживаются и будут перенесены в новую модель параметров.
- Новые параметры QoS и сетевые требования. Дополнительные дополнительные возможности см. в см. в перенастройке сети и качестве обслуживания [для Microsoft Teams Room на Surface Hub.](surface-hub-teams-rooms-networking.md)
- Если по умолчанию еще нет, Teams может быть назначено в **** качестве приложения по умолчанию для собраний и вызовов в Параметры  >  **Surface Hub**  >  **вызовов & аудио**. Дополнительные информацию о режимах собраний и их настройке с помощью политики MDM см. в Surface Hub с [поставщиком MDM.](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls)

## <a name="in-meeting-experience"></a>В ходе собраний

Комнаты Teams в Surface Hub meetings соответствует привычному опыту, который пользователи знают на своих личных устройствах, с помощью корректировок, сделанных для оптимизации для устройства с большим экраном. Открытие Teams на Surface Hub позволяет пользователям получать доступ к ключевым функциям, включая присоединение к собраниям в одно касание, Meet Now и Dial Pad для PSTN или одноранговых вызовов.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Комнаты Teams на Surface Hub повестке дня.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Комнаты Teams на Surface Hub собрании.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>Управление Комнаты Teams на Surface Hub

 Вы можете настроить Teams непосредственно из меню Параметры после ввода административных учетных данных, в том числе:

- Настройка [координируемых собраний](/microsoftteams/rooms/coordinated-meetings) и примыкать к близости.
- Настройка параметров микрофонов, камер и динамиков по умолчанию.
- Проверка клиентской версии и поиск последних обновлений.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Комнаты Teams Параметры.":::

Новый Комнаты Teams для Surface Hub, автоматически применяет существующие параметры, настроенные с помощью XML-файлов, пакетов подготовка или поставщика MDM. Эти методы, описанные в Microsoft Teams конфигурации [Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), будут замещёны новыми облачными решениями, как описано ниже в упрощенном управлении Teams, приходя в [Surface Hub](#simplified-management-of-teams-coming-to-surface-hub).

### <a name="prepare-networking-for-teams-rooms"></a>Подготовка сетей для Комнаты Teams

Чтобы оптимизировать Комнаты Teams, обратитесь к требованиям и рекомендациям, описанным в "Настройка сетевых сетей и качество обслуживания для [Microsoft Teams номеров](surface-hub-teams-rooms-networking.md)на Surface Hub .

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>Упрощенное управление Teams в Surface Hub

Когда Комнаты Teams для Surface Hub будет опубликована в конце этого года, администраторы могут воспользоваться следующими решениями:

- **Teams Центр администрирования.** Teams Центр администрирования предоставляет всеобъемлющую платформу самообуправления для мониторинга и управления Комнаты Teams на Teams устройствах. Teams Центр администрирования будет доступен для Комнаты Microsoft Teams без дополнительных затрат.
- **Комнаты Microsoft Teams управляемой службы.** Управляемый [Комнаты Microsoft Teams](/microsoftteams/rooms/microsoft-teams-rooms-premium) — это облачная служба управления ИТ и мониторинга, которая поддерживает Комнаты Microsoft Teams устройства и периферийные устройства в курсе и активно отслеживается, поддерживая среду, оптимизированую для отличного пользовательского интерфейса.


## <a name="support-for-teams-rooms-in-government-community-cloud-high-gcc-h"></a>Поддержка Комнаты Teams в облако сообщества для государственных организаций High (GCC-H)

Когда Комнаты Teams для Surface Hub в этом году будет опубликовано публичное обновление клиента до версии 1.4.00.25354, чтобы он мог подключаться к клиенту GCC-H, а затем автоматически обновляться:

 - Подтвердите, что в вашем концентраторе установленО накопительное обновление KB5005611 или более позднее Windows накопительное обновление
 - Используйте [Teams_Uninstall_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg) для удаления текущих Комнаты Teams в Surface Hub версии
 - Перезапуск устройства
 - Установите [Teams_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg) для установки версии 1.4.00.25354
 - Снова перезапустите устройство

Подробные действия:

1. Сохраните оба пакета подготовка к корневому диску USB.
2.  Вставьте USB-накопитель в Surface Hub.
3.  В Surface Hub откройте меню , выберите все приложения и выберите Параметры.
4.  Предоставление учетных данных администратора концентратора при запросе.
5.  Перейдите **Surface Hub**  >  **управления устройствами**Добавьте или  >  **удалите**пакет подготовка, а затем **выберите Добавить пакет**.
6.  В **статье Выбор пакета**выберите пакет Teams_Uninstall_win32.ppkg, а затем перезапустите Surface Hub.
7.  В Surface Hub откройте меню , выберите все приложения и выберите Параметры.
8.  Предоставление учетных данных администратора концентратора при запросе.
9.  Перейдите **Surface Hub**  >  **управления устройствами**Добавьте или  >  **удалите**пакет подготовка, а затем **выберите Добавить пакет**.
10. В **статье Выбор пакета**выберите пакет Teams_win32.ppkg, а затем перезапустите Surface Hub.
