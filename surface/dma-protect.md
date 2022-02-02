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
ms.date: 12/01/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: ae648f54f7abd97a6397dca5aa204205b582e4b0
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338052"
---
# <a name="dma-protection-on-surface-devices"></a>Защита DMA на устройствах Surface

Защита прямого доступа к памяти (DMA) предназначена для устранения потенциальных уязвимостей безопасности, связанных с использованием съемных SSD или внешних устройств хранения. Новые устройства Surface приходят с поддержкой DMA Protection, включенной по умолчанию. К ним относятся Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Laptop SE, Surface Pro 7+, Surface Pro 7, Surface Laptop 3 и Surface Pro  X.  Чтобы проверить наличие функции защиты DMA на устройстве, откройте **Сведения о системе (** > Начните**msinfo32.exe), как **показано на рисунке ниже.

![Сведения о системе, показывающие включенную защиту DMA.](images/systeminfodma.png)

Если съемный SSD Surface будет подделано, устройство отключит питание. В результате перезагрузки UEFI стирает память, стирает остаточные данные.
