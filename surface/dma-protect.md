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
ms.openlocfilehash: d2656b141908ef203f748518ddf49a7fbcbab255
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911354"
---
# <a name="dma-protection-on-surface-devices"></a>Защита DMA на устройствах Surface

Защита прямого доступа к памяти (DMA) предназначена для устранения потенциальных уязвимостей безопасности, связанных с использованием съемных SSD или внешних устройств хранения. Новые устройства Surface приходят с поддержкой DMA Protection, включенной по умолчанию. К ним относятся Surface Pro 7+. Surface Pro 7, Surface Laptop 3 и Surface Pro X.  Чтобы проверить наличие функции защиты DMA на устройстве, откройте Сведения о системе****  >  ** (Начните **msinfo32.exe), как показано на рисунке ниже.

![Сведения о системе, показывающие включенную защиту DMA.](images/systeminfodma.png)

Если съемный SSD Surface будет подделано, устройство отключит питание. В результате перезагрузки UEFI стирает память, стирает остаточные данные.
