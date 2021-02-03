---
title: Применение политик ActiveSync к учетным записям устройств (Surface Hub)
description: Для синхронизации почты и календаря в учетной записи устройства Microsoft Surface Hub используется протокол ActiveSync. Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, политики ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: b5f828ee6757c150b1287e8210c81592e970b74a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311965"
---
# Применение политик ActiveSync к учетным записям устройств (Surface Hub)


Для синхронизации почты и календаря в учетной записи устройства Microsoft Surface Hub используется протокол ActiveSync. Это позволяет пользователям присоединяться к запланированным собраниям и начинать их с устройства Surface Hub, а также отправлять доски по почте.

Чтобы эти компоненты можно было использовать, политики ActiveSync вашей организации необходимо настроить следующим образом.

-   Не должно быть глобальных политик, которые блокируют синхронизацию почтового ящика ресурса, используемого учетной записью устройства Surface Hub. Если такая политика блокировки существует, необходимо добавить Surface Hub в качестве разрешенного устройства.
-   Необходимо настроить политику почтового ящика мобильного устройства, параметру **PasswordEnabled** которой присвоено значение False. Другие параметры политики почтового ящика мобильного устройства не совместимы с Surface Hub.

## Разрешение DeviceID

В организации может использоваться глобальная политика, которая блокирует синхронизацию учетных записей, подготовленных на устройствах Surface Hub. Сведения о настройке этого свойства см. в разделе [Разрешение идентификаторов устройств для ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## Настройка параметра PasswordEnabled

Учетная запись устройства должна использовать политику ActiveSync, атрибут **PasswordEnabled** которое имеет значение False или 0. Сведения о настройке свойства см. в разделе [Создание политики Microsoft Exchange ActiveSync, совместимой с Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





