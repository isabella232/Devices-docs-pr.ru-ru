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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: a0f04b4dd089309ad44cab12cf738d8203d1526d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449502"
---
# <a name="dma-protection-on-surface-devices"></a>Защита DMA на устройствах Surface

Защита прямого доступа к памяти (DMA) предназначена для устранения потенциальных уязвимостей безопасности, связанных с использованием съемных SSD или внешних устройств хранения. Новые устройства Surface приходят с поддержкой DMA Protection, включенной по умолчанию. К ним относятся Surface Pro, Surface Laptop Studio, Surface Go 3, Surface Laptop SE, Surface Pro 7+, Surface Pro 7, Surface Laptop 3 и Surface Pro  X.  Чтобы проверить наличие функции защиты DMA на устройстве, откройте **Сведения о системе (** > Начните**msinfo32.exe), как **показано на рисунке ниже.

![Сведения о системе, показывающие включенную защиту DMA.](images/systeminfodma.png)

Если съемный SSD Surface будет подделано, устройство отключит питание. В результате перезагрузки UEFI стирает память, стирает остаточные данные.
