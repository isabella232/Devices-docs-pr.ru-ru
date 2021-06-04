---
title: Сохранение ключа BitLocker (Surface Hub)
description: На каждом устройстве Microsoft Surface Hub автоматически устанавливается программное обеспечение для шифрования дисков BitLocker. Корпорация Майкрософт настоятельно рекомендует создавать резервные копии ключей восстановления BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, ключи восстановления Bitlocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836464"
---
# Сохранение ключа BitLocker (Surface Hub)


На каждом устройстве Microsoft Surface Hub автоматически устанавливается программное обеспечение для шифрования дисков BitLocker. Корпорация Майкрософт настоятельно рекомендует создавать резервные копии ключей восстановления BitLocker.

Существует несколько способов управления ключом BitLocker на устройстве Surface Hub.

1.  Если вы присоединили Surface Hub к домену, устройство будет создавать резервную копию ключа в домене и хранить его в объекте компьютера.

    Если вы не можете найти ключ BitLocker после присоединения к домену, возможно, ваше схема Active Directory не поддерживает резервное копирование ключа BitLocker. Если вы не хотите изменить схему, вы можете сохранить ключ BitLocker, открыв приложение «Параметры», и использовать процедуру для учетной записи локального администратора, которая описана далее.

2.  Если вы присоединили Surface Hub к Azure Active Directory (Azure AD), ключ BitLocker будет храниться в учетной записи, которая использовалась для присоединения устройства.

3.  Если вы используете локальную учетную запись администратора для управления устройством, вы можете сохранить ключ BitLocker, перейдя в приложение " **Параметры** " и перейдя к **обновлению &** &gt; **восстановления**безопасности. Вставьте USB-накопитель и выберите параметр сохранения ключа BitLocker. Ключ будет сохранен в текстовый файл на USB-накопителе.


##  <a name="related-topics"></a>Еще по теме

[Управление Microsoft Surface Hub](manage-surface-hub.md)

[Руководство администратора Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





