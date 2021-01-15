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
# <span data-ttu-id="219a8-103">Защита DMA на устройствах Surface</span><span class="sxs-lookup"><span data-stu-id="219a8-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="219a8-104">Защита прямого доступа к памяти (DMA) предназначена для устранения потенциальных уязвимостей системы безопасности, связанных с использованием съемных SSD или внешних устройств хранения.</span><span class="sxs-lookup"><span data-stu-id="219a8-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="219a8-105">На новых устройствах Surface по умолчанию включена защита DMA.</span><span class="sxs-lookup"><span data-stu-id="219a8-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="219a8-106">К ним относятся Surface Pro 7 и более.</span><span class="sxs-lookup"><span data-stu-id="219a8-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="219a8-107">Surface Pro 7, Surface Laptop 3 и Surface Pro X.  Чтобы проверить наличие функции защиты DMA на устройстве, откройте system Information **(Начните**msinfo32.exe), как показано на  >  \*\* \*\*рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="219a8-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Сведения о системе с включенной защитой DMA](images/systeminfodma.png)

<span data-ttu-id="219a8-109">Если съемный SSD Surface не работает, устройство отключит питание.</span><span class="sxs-lookup"><span data-stu-id="219a8-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="219a8-110">В результате перезагрузки UEFI будет стирать память, стирая все оставшиеся данные.</span><span class="sxs-lookup"><span data-stu-id="219a8-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
