---
title: Реализация качества обслуживания на Surface HUB
ms.reviewer: ''
manager: laurawi
description: Сведения о том, как настроить качество обслуживания на Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835192"
---
# Реализация качества обслуживания (QoS) на Surface HUB

Качество обслуживания (QoS) — это сочетание сетевых технологий, позволяющее администраторам оптимизировать взаимодействие голосовых и видеофайлов и обмена приложениями в реальном времени.
 
Настройка [QoS для Skype для бизнеса](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) на Surface HUB может быть выполнена с помощью [поставщика управления мобильными устройствами (MDM)](manage-settings-with-mdm-for-surface-hub.md) или с помощью [пакета подготовки](provisioning-packages-for-surface-hub.md). 
 
 
В этой статье объясняется, как настроить качество обслуживания Surface Hub с помощью Microsoft Intune. 

1. В Intune [Создайте настраиваемую политику](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Снимок экрана: диалоговое окно создания настраиваемой политики в Intune](images/qos-create.png)

2. В окне **особые параметры OMA-URI**нажмите кнопку **Добавить**. Для каждого параметра, который вы хотите добавить, введите имя, описание (необязательно), тип данных, OMA-URI и значение.

    ![Снимок экрана: диалоговое окно "пустой параметр OMA-URI"](images/qos-setting.png)

3. Добавьте следующие особые параметры OMA-URI.

    Имя | Тип данных | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Значение
    --- | --- | --- | ---
    Порт источника звуковых данных | Строка |  /HubAudio/SourcePortMatchCondition  |   Получение значений от администратора Skype
    DSCP звука | целое число |  /HubAudio/DSCPAction  |   46
    Порт источника видео | Строка |  /HubVideo/SourcePortMatchCondition   |  Получение значений от администратора Skype
    DSCP видео | целое число |  /HubVideo/DSCPAction   |   34
    Имя звукового процесса | Строка |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Имя видеопроцесса | Строка |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Каждый путь к **OMA-URI** начинается с `./Device/Vendor/MSFT/NetworkQoSPolicy` . Например, можно задать полный путь к порту источника звука `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .




4. После создания политики [разверните ее на Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>В настоящее время вы не можете настроить **IPProtocolMatchCondition** параметров в [поставщике служб шифрования NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Если этот параметр настроен, политика не будет применена.
 
