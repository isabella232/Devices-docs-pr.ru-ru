---
title: Изменение учетной записи устройства Microsoft Surface Hub
description: Вы можете изменить учетную запись устройства в приложении "Параметры", чтобы добавить учетную запись, если она еще не подготовлена, или изменить свойства существующей учетной записи.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: изменение учетной записи устройства, изменения свойств, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836752"
---
# Изменение учетной записи устройства Microsoft Surface Hub


Вы можете изменить учетную запись устройства в приложении "Параметры", чтобы добавить учетную запись, если она еще не подготовлена, или изменить свойства существующей учетной записи.

##  <a name="details"></a>Подробности


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Значение</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Имя участника-пользователя</p></td>
<td align="left"><p>Имя участника-пользователя (UPN) учетной записи устройства.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Пароль</p></td>
<td align="left"><p>Соответствующий пароль учетной записи устройства.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Домен</p></td>
<td align="left"><p>Домен, которому принадлежит учетная запись устройства. Это поле не заполняется для учетных записей Office 365.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Имя пользователя</p></td>
<td align="left"><p>Имя пользователя учетной записи устройства. Это поле не заполняется для учетных записей Office 365.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SIP-адрес</p></td>
<td align="left"><p>SIP-адрес учетной записи устройства.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Сервер Microsoft Exchange Server</p></td>
<td align="left"><p>Это сервер Exchange Server учетной записи устройства. Имя пользователя и пароль учетной записи устройства должны позволять пройти проверку подлинности на указанном сервере Exchange Server.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Включить службы Exchange</p></td>
<td align="left"><p>Если этот флажок установлен, все службы Exchange будут активированы (например, календарь на экране приветствия, отправка досок по почте). Если флажок не установлен, все службы Exchange будут отключены, а сервер Exchange Server не нужно указывать.</p></td>
</tr>
</tbody>
</table>

 

##  <a name="what-happened"></a>Описание процедуры


Имя участника-пользователя и пароль служат для проверки учетной записи в AD и Azure AD. Если проверка закончится ошибкой, вам может потребоваться указать домен и имя пользователя.

Используя предоставленные учетные данные, мы попробуем найти SIP-адрес. Если SIP-адрес не найден, Skype для бизнеса будет применять в качестве SIP-адреса имя участника-пользователя. Если это не SIP-адрес для учетной записи, вам понадобится указать SIP-адрес.

Необходимо указать адрес сервера Exchange Server, если устройство не может найти сервер, связанный с учетными данными для входа. Microsoft Surface Hub будет использовать сервер Exchange Server для взаимодействия с ActiveSync, что требуется некоторыми основными функциями на устройстве.

##  <a name="related-topics"></a>Еще по теме


[Управление Microsoft Surface Hub](manage-surface-hub.md)

[Руководство администратора Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





