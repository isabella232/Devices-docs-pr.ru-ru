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
# <span data-ttu-id="a057b-104">Свойства Microsoft Exchange (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="a057b-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="a057b-105">Для оптимальной работы функции собраний на Microsoft Surface Hub некоторым свойствам Microsoft Exchange учетной записи устройства необходимо присвоить определенные значения.</span><span class="sxs-lookup"><span data-stu-id="a057b-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="a057b-106">В приведенной ниже таблице перечислены свойства Exchange на основе параметров командлетов PowerShell, их функции и значения, которые им следует присвоить.</span><span class="sxs-lookup"><span data-stu-id="a057b-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a057b-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="a057b-107">Property</span></span></th>
<th align="left"><span data-ttu-id="a057b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a057b-108">Description</span></span></th>
<th align="left"><span data-ttu-id="a057b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="a057b-109">Value</span></span></th>
<th align="left"><span data-ttu-id="a057b-110">Влияние</span><span class="sxs-lookup"><span data-stu-id="a057b-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a057b-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="a057b-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-112">Параметр AutomateProcessing включает и отключает обработку календаря на почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a057b-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="a057b-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-114">Surface Hub будет автоматически принимать или отклонять приглашения на собрание в зависимости от доступности.</span><span class="sxs-lookup"><span data-stu-id="a057b-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a057b-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="a057b-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-116">Параметр AddOrganizerToSubject определяет, используется ли имя организатора собрания как тема приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-117">$False</span><span class="sxs-lookup"><span data-stu-id="a057b-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-118">На экране приветствия организатор не будет показан дважды.</span><span class="sxs-lookup"><span data-stu-id="a057b-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a057b-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="a057b-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-120">Параметр AllowConflicts указывает, следует ли разрешить конфликтующие приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-121">$False</span><span class="sxs-lookup"><span data-stu-id="a057b-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-122">Surface Hub будет отклонять приглашения на собрание, конфликтующие с временем другого собрания.</span><span class="sxs-lookup"><span data-stu-id="a057b-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a057b-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="a057b-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-124">Параметр DeleteComments определяет, нужно ли удалять или сохранять текст сообщений входящих приглашений на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-125">$False</span><span class="sxs-lookup"><span data-stu-id="a057b-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-126">Текст сообщений собраний можно сохранять и извлекать с устройства Surface Hub, если это необходимо во время собрания.</span><span class="sxs-lookup"><span data-stu-id="a057b-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a057b-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="a057b-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-128">Параметр DeleteSubject определяет, нужно ли удалять или сохранять тему входящих приглашений на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-129">$False</span><span class="sxs-lookup"><span data-stu-id="a057b-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-130">Темы приглашения на собрание могут отображаться на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a057b-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a057b-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="a057b-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-132">Параметр RemovePrivateProperty определяет, следует ли удалять пометку «частное» для входящих приглашений на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-133">$False</span><span class="sxs-lookup"><span data-stu-id="a057b-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-134">Темы частных собраний будут отображаться на экране приветствия с пометкой «частное».</span><span class="sxs-lookup"><span data-stu-id="a057b-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a057b-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="a057b-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-136">Параметр AddAdditionalResponse указывает, будут ли передаваться дополнительные сведения из почтового ящика ресурса при ответе на приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-137">$True</span><span class="sxs-lookup"><span data-stu-id="a057b-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-138">Когда на приглашение на собрание отправляется ответ, в нем будет указан настраиваемый текст.</span><span class="sxs-lookup"><span data-stu-id="a057b-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a057b-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="a057b-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-140">Параметр AdditionalResponse указывает дополнительные сведения, которые следует включить в ответы на приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="a057b-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a057b-141">Примечание </strong> . Этот текст не будет отправлен, если только для AddAdditionalResponse не задано значение "$true".</span><span class="sxs-lookup"><span data-stu-id="a057b-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="a057b-142">Вы можете использовать дополнительный ответ, чтобы рассказать, как использовать Surface Hub или сообщить о полезных ресурсах.</span><span class="sxs-lookup"><span data-stu-id="a057b-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a057b-143">В дополнительном ответном сообщении можно описать, как использовать Surface Hub на собрании.</span><span class="sxs-lookup"><span data-stu-id="a057b-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





