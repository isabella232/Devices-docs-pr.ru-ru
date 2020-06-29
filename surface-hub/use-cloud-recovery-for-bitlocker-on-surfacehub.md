---
title: Использование облачного восстановления для BitLocker на Surface Hub
description: Использование облачного восстановления для BitLocker на Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Параметры специальных возможностей, приложение "Параметры", специальные возможности
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834872"
---
# <span data-ttu-id="5eb61-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5eb61-104">Summary</span></span>

<span data-ttu-id="5eb61-105">В этой статье описано, как использовать функцию восстановления в облаке, если BitLocker неожиданно запрашивается на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5eb61-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="5eb61-106">Выполните эти действия только в том случае, если ключ восстановления BitLocker недоступен.</span><span class="sxs-lookup"><span data-stu-id="5eb61-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="5eb61-107">В ходе этого процесса восстановления содержимое внутреннего диска будет удалено.</span><span class="sxs-lookup"><span data-stu-id="5eb61-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="5eb61-108">Если процесс завершится сбоем, внутренний диск станет полностью пригоден для использования.</span><span class="sxs-lookup"><span data-stu-id="5eb61-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="5eb61-109">В этом случае вам потребуется зарегистрировать запрос на обслуживание в Microsoft для устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="5eb61-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="5eb61-110">После завершения процесса восстановления на устройстве будут восстановлены заводские настройки и возвращено в состояние "нет на работе".</span><span class="sxs-lookup"><span data-stu-id="5eb61-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="5eb61-111">После восстановления Surface Hub необходимо полностью настроить.</span><span class="sxs-lookup"><span data-stu-id="5eb61-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5eb61-112">Для этого процесса требуется открытое подключение к Интернету, которое не использует прокси-сервер или другой способ проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5eb61-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="5eb61-113">Процесс восстановления в облаке</span><span class="sxs-lookup"><span data-stu-id="5eb61-113">Cloud recovery process</span></span>

<span data-ttu-id="5eb61-114">Чтобы выполнить восстановление в облаке, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5eb61-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="5eb61-115">**Нажмите клавишу ESC, чтобы получить доступ к дополнительным параметрам восстановления**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-115">Select **Press Esc for more recovery options**.</span></span>

   ![Снимок экрана: ESC](images/01-escape.png)

1. <span data-ttu-id="5eb61-117">Нажмите кнопку **пропустить этот диск**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-117">Select **Skip this drive**.</span></span>

   ![Снимок экрана: пропуск этого диска](images/02-skip-this-drive.png)

1. <span data-ttu-id="5eb61-119">Выберите команду **восстановить из облака**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-119">Select **Recover from the cloud**.</span></span>

   ![Снимок экрана: восстановление из облака](images/03-recover-from-cloud.png)

1. <span data-ttu-id="5eb61-121">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-121">Select **Yes**.</span></span>

   ![Снимок экрана: Да](images/04-yes.png)

1. <span data-ttu-id="5eb61-123">Нажмите кнопку **переустановить**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-123">Select **Reinstall**.</span></span>

   ![Снимок экрана: повторная установка](images/05a-reinstall.png)

   ![Снимок экрана: Загрузка](images/05b-downloading.png)

1. <span data-ttu-id="5eb61-126">После завершения процедуры восстановления в облаке запустите перенастройку с помощью **функции "нет на месте"**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![Снимок экрана: из окна](images/06-out-of-box.png)

## <span data-ttu-id="5eb61-128">Сообщение об ошибке "что-то пошло не так"</span><span class="sxs-lookup"><span data-stu-id="5eb61-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="5eb61-129">Как правило, эта ошибка возникает при проблемах с сетью, возникающих при загрузке восстановления.</span><span class="sxs-lookup"><span data-stu-id="5eb61-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="5eb61-130">При возникновении этой проблемы не выключайте центр, так как вы не можете перезапустить его.</span><span class="sxs-lookup"><span data-stu-id="5eb61-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="5eb61-131">Если вы получили это сообщение об ошибке, вернитесь к шагу "восстановление из облака", а затем перезапустите процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="5eb61-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="5eb61-132">Нажмите **кнопку Отмена**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-132">Select **Cancel**.</span></span>

   ![Снимок экрана: Отмена](images/07-cancel.png)

1. <span data-ttu-id="5eb61-134">Нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-134">Select **Troubleshoot**.</span></span>

   ![Снимок экрана: Устранение неполадок](images/08-troubleshoot.png)

1. <span data-ttu-id="5eb61-136">Выберите команду **восстановить из облака**.</span><span class="sxs-lookup"><span data-stu-id="5eb61-136">Select **Recover from the cloud**.</span></span>

   ![Снимок экрана: восстановление из облака](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="5eb61-138">Если появляется сообщение об ошибке " **Проводная сеть не обнаружена** ", нажмите **кнопку "Отмена"** и позвольте Surface Hub повторно обнаружить проводную сеть.</span><span class="sxs-lookup"><span data-stu-id="5eb61-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![Снимок экрана: проводная сеть не найдена](images/10-cancel.png)