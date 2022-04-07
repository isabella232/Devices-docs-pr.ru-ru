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
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: fa393eca697897ee620732b543ebb6889aa035d1
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472578"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>Применение политик ActiveSync к учетным записям устройств (Surface Hub)

Surface Hub в Windows 10 для совместной работы 1703 и более ранних версий использовали ActiveSync для синхронизации почты & календаря.

Ниже Surface Hub требования к политикам ActiveSync в вашей организации.

-   Не может быть глобальных политик, которые блокируют синхронизацию почтового ящика ресурсов, используемого учетной записью Surface Hub устройства. При наличии такой политики блокировки необходимо добавить Surface Hub как разрешенное устройство.
-   Необходимо настроить политику почтового ящика мобильного устройства, параметру **PasswordEnabled** которой присвоено значение False. Другие параметры политики почтового ящика мобильного устройства не совместимы с Surface Hub.

## <a name="allowing-the-deviceid"></a>Разрешение идентификатора устройства

В организации может использоваться глобальная политика, которая блокирует синхронизацию учетных записей, подготовленных на устройствах Surface Hub. Сведения о настройке этого свойства см. в разделе [Разрешение идентификаторов устройств для ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## <a name="setting-passwordenabled"></a>Настройка параметра PasswordEnabled

Учетная запись устройства должна использовать политику ActiveSync, атрибут **PasswordEnabled** которое имеет значение False или 0. Сведения о настройке свойства см. в разделе [Создание политики Microsoft Exchange ActiveSync, совместимой с Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





