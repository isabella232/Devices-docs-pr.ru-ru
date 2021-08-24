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
ms.openlocfilehash: b235ab8e19df42fa63efe5e66ac590c58c50d179
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910954"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Реализация качества службы (QoS) на Surface Hub

Качество службы (QoS) — это сочетание сетевых технологий, которое позволяет администраторам оптимизировать взаимодействие аудио- и видео- и приложений в режиме реального времени.
 
Настройка [QoS для Skype для бизнеса](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) на Surface Hub можно сделать с помощью поставщика управления мобильными устройствами [(MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью пакета [подготовка](provisioning-packages-for-surface-hub.md). 
 
 
Эта процедура объясняет, как настроить QoS для Surface Hub с Microsoft Intune. 

1. В Intune [создайте настраиваемую политику.](https://docs.microsoft.com/intune/custom-settings-configure)

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана диалогового номера создания настраиваемой политики в Intune.](images/qos-create.png)

2. В **настраиваемом OMA-URI Параметры**выберите **Добавить**. Для каждого добавленного параметра введите имя, описание (необязательно), тип данных, OMA-URI и значение.

    > [!div class="mx-imgBorder"]
    > ![Снимок экрана пустого диалогового окна настройки OMA-URI.](images/qos-setting.png)

3. Добавьте следующие настраиваемые параметры OMA-URI:<br/><br/>

    Имя | Тип данных | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Значение
    --- | --- | --- | ---
    Порт источника аудио | Строка |  /HubAudio/SourcePortMatchCondition  |   Получите значения от Skype администратора
    DSCP звука | целое число |  /HubAudio/DSCPAction  |   46
    Порт источника видео | Строка |  /HubVideo/SourcePortMatchCondition   |  Получите значения от Skype администратора
    DSCP видео | целое число |  /HubVideo/DSCPAction   |   34
    Имя процесса аудио | Строка |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Имя процесса видео | Строка |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Каждый **путь OMA-URI** начинается с `./Device/Vendor/MSFT/NetworkQoSPolicy` . Полный путь для параметра порта источника звука, например, будет `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .

4. После создания политики разверни ее в Surface Hub.


>[!WARNING]
>В настоящее время невозможно настроить параметр **IPProtocolMatchCondition** в [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) Если этот параметр настроен, политика не будет применяться.
 
