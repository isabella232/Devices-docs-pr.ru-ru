---
title: Реализация качества обслуживания на Surface HUB
ms.reviewer: ''
manager: laurawi
description: Узнайте, как настроить QoS на Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470487"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Реализация качества обслуживания (QoS) на Surface Hub

Качество службы (QoS) — это сочетание сетевых технологий, которое позволяет администраторам оптимизировать взаимодействие аудио- и видео- и приложений в режиме реального времени.
 
Настройка [QoS для Skype для](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) бизнеса на Surface Hub может быть сделана с помощью поставщика управления мобильными устройствами [(MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью пакета [обеспечения.](provisioning-packages-for-surface-hub.md) 
 
 
Эта процедура объясняет, как настроить QoS для Surface Hub с помощью Microsoft Intune. 

1. В Intune [создайте настраиваемую политику.](https://docs.microsoft.com/intune/custom-settings-configure)

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана диалогового номера создания настраиваемой политики в Intune](images/qos-create.png)

2. В **настраиваемом параметре OMA-URI**выберите **Добавить**. Для каждого добавленного параметра введите имя, описание (необязательно), тип данных, OMA-URI и значение.

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана пустого диалоговое окно параметра OMA-URI](images/qos-setting.png)

3. Добавьте следующие настраиваемые параметры OMA-URI:<br/><br/>

    Имя | Тип данных | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Значение
    --- | --- | --- | ---
    Порт источника аудио | Строка |  /HubAudio/SourcePortMatchCondition  |   Получите значения от администратора Skype
    DSCP звука | целое число |  /HubAudio/DSCPAction  |   46
    Порт источника видео | Строка |  /HubVideo/SourcePortMatchCondition   |  Получите значения от администратора Skype
    DSCP видео | целое число |  /HubVideo/DSCPAction   |   34
    Имя процесса аудио | Строка |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Имя процесса видео | Строка |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Каждый **путь OMA-URI** начинается с `./Device/Vendor/MSFT/NetworkQoSPolicy` . Полный путь для параметра порта источника звука, например, будет `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .

4. После создания политики разверни ее в Surface Hub.


>[!WARNING]
>В настоящее время невозможно настроить параметр **IPProtocolMatchCondition** в [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) Если этот параметр настроен, политика не будет применяться.
 
