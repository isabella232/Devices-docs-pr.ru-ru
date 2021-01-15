---
title: Защита DMA для Surface
description: В этой статье описывается защита DMA на совместимых устройствах Surface
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270624"
---
# Защита DMA на устройствах Surface

Защита прямого доступа к памяти (DMA) предназначена для устранения потенциальных уязвимостей системы безопасности, связанных с использованием съемных SSD или внешних устройств хранения. На новых устройствах Surface по умолчанию включена защита DMA. К ним относятся Surface Pro 7 и более. Surface Pro 7, Surface Laptop 3 и Surface Pro X.  Чтобы проверить наличие функции защиты DMA на устройстве, откройте system Information **(Начните**msinfo32.exe), как показано на  >  ** **рисунке ниже.

![Сведения о системе с включенной защитой DMA](images/systeminfodma.png)

Если съемный SSD Surface не работает, устройство отключит питание. В результате перезагрузки UEFI будет стирать память, стирая все оставшиеся данные.
