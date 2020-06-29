---
title: Свойства Microsoft Exchange (Surface Hub)
description: Для оптимальной работы функции собраний на Microsoft Surface Hub некоторым свойствам Microsoft Exchange учетной записи устройства необходимо присвоить определенные значения.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Свойства Microsoft Exchange, учетная запись устройства, Surface Hub, командлет Windows PowerShell
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836240"
---
# Свойства Microsoft Exchange (Surface Hub)


Для оптимальной работы функции собраний на Microsoft Surface Hub некоторым свойствам Microsoft Exchange учетной записи устройства необходимо присвоить определенные значения. В приведенной ниже таблице перечислены свойства Exchange на основе параметров командлетов PowerShell, их функции и значения, которые им следует присвоить.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Свойство</th>
<th align="left">Описание</th>
<th align="left">Значение</th>
<th align="left">Влияние</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>Параметр AutomateProcessing включает и отключает обработку календаря на почтовом ящике.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Surface Hub будет автоматически принимать или отклонять приглашения на собрание в зависимости от доступности.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>Параметр AddOrganizerToSubject определяет, используется ли имя организатора собрания как тема приглашения на собрание.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>На экране приветствия организатор не будет показан дважды.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>Параметр AllowConflicts указывает, следует ли разрешить конфликтующие приглашения на собрание.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub будет отклонять приглашения на собрание, конфликтующие с временем другого собрания.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>Параметр DeleteComments определяет, нужно ли удалять или сохранять текст сообщений входящих приглашений на собрание.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Текст сообщений собраний можно сохранять и извлекать с устройства Surface Hub, если это необходимо во время собрания.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>Параметр DeleteSubject определяет, нужно ли удалять или сохранять тему входящих приглашений на собрание.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Темы приглашения на собрание могут отображаться на устройстве Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>Параметр RemovePrivateProperty определяет, следует ли удалять пометку «частное» для входящих приглашений на собрание.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Темы частных собраний будут отображаться на экране приветствия с пометкой «частное».</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>Параметр AddAdditionalResponse указывает, будут ли передаваться дополнительные сведения из почтового ящика ресурса при ответе на приглашения на собрание.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>Когда на приглашение на собрание отправляется ответ, в нем будет указан настраиваемый текст.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>Параметр AdditionalResponse указывает дополнительные сведения, которые следует включить в ответы на приглашения на собрание.</p>
<div class="alert">
<strong>Примечание </strong> . Этот текст не будет отправлен, если только для AddAdditionalResponse не задано значение "$true".
</div>
<div>
 
</div></td>
<td align="left"><p>Вы можете использовать дополнительный ответ, чтобы рассказать, как использовать Surface Hub или сообщить о полезных ресурсах.</p></td>
<td align="left"><p>В дополнительном ответном сообщении можно описать, как использовать Surface Hub на собрании.</p></td>
</tr>
</tbody>
</table>

 

 

 





