---
title: Защита от DMA Surface
description: В этой статье описывается Защита канала DMA на совместимых устройствах Surface
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835107"
---
# Защита DMA на Surface Devices

Защита от прямого доступа к памяти (DMA) разработана для устранения потенциальных уязвимостей системы безопасности, связанных с использованием съемных твердотельных накопителей или внешних запоминающих устройств. Новые устройства Surface включены по умолчанию с защитой DMA. К ним относятся 7 Surface Pro, Ноутбуки 3 и Surface Pro X.  Чтобы проверить наличие функции защиты DMA на вашем устройстве, откройте окно "сведения о системе" (**Start**  >  **msinfo32.exe**), как показано на рисунке ниже.

![Сведения о системе, на которой включена защита DMA](images/systeminfodma.png)

Если съемный SSD Surface подделкиется, устройство будет shutoff Power. Результирующая перезагрузка вызывает очистку памяти, чтобы удалить все остаточные данные.
