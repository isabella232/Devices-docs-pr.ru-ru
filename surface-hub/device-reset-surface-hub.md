---
title: Сброс и восстановление Surface HUB
description: Описывает процесс сброса и восстановления для Surface Hub, а также инструкции.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Сброс Surface Hub, восстановление
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104821"
---
# <span data-ttu-id="89b6e-104">Сброс и восстановление Surface HUB</span><span class="sxs-lookup"><span data-stu-id="89b6e-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="89b6e-105">В этой статье описано, как сбросить или восстановить Surface Hub Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89b6e-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="89b6e-106">[Сброс Surface Hub](#reset-a-surface-hub) приводит к возврату операционной системы к последнему накопительному обновлению Windows и удалению всех локальных файлов пользователей и сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89b6e-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="89b6e-107">Удаляемые сведения включают следующее:</span><span class="sxs-lookup"><span data-stu-id="89b6e-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="89b6e-108">учетная запись устройства;</span><span class="sxs-lookup"><span data-stu-id="89b6e-108">The device account</span></span>
- <span data-ttu-id="89b6e-109">Сведения об учетной записи локальных администраторов устройства</span><span class="sxs-lookup"><span data-stu-id="89b6e-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="89b6e-110">Сведения о присоединении к домену или Azure AD-объединение</span><span class="sxs-lookup"><span data-stu-id="89b6e-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="89b6e-111">Сведения о регистрации в службе управления мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="89b6e-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="89b6e-112">Сведения о конфигурации, заданные с помощью MDM или приложения "Параметры"</span><span class="sxs-lookup"><span data-stu-id="89b6e-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="89b6e-113">[Восстановление Surface Hub из облака](#recover-a-surface-hub-from-the-cloud) также приводит к удалению этих данных.</span><span class="sxs-lookup"><span data-stu-id="89b6e-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="89b6e-114">Кроме того, Surface Hub загружает новый образ операционной системы и устанавливает его.</span><span class="sxs-lookup"><span data-stu-id="89b6e-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="89b6e-115">Вы можете указать, сохранит ли процесс восстановления другие данные, хранящиеся на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="89b6e-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="89b6e-116">Сброс Surface HUB</span><span class="sxs-lookup"><span data-stu-id="89b6e-116">Reset a Surface Hub</span></span>

<span data-ttu-id="89b6e-117">Может потребоваться сброс Surface Hub по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="89b6e-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="89b6e-118">Вы повторно purposing устройство для нового места для собрания и хотите изменить его.</span><span class="sxs-lookup"><span data-stu-id="89b6e-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="89b6e-119">вам нужно поменять метод локального управления устройством.</span><span class="sxs-lookup"><span data-stu-id="89b6e-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="89b6e-120">Имя пользователя или пароль учетной записи устройства или учетной записи администратора утеряны.</span><span class="sxs-lookup"><span data-stu-id="89b6e-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="89b6e-121">После установки обновления производительность устройства уменьшается.</span><span class="sxs-lookup"><span data-stu-id="89b6e-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="89b6e-122">В процессе сброса, если вы видите пустой экран в течение длительного периода времени, пожалуйста, подождите и не делайте никаких действий.</span><span class="sxs-lookup"><span data-stu-id="89b6e-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="89b6e-123">Процесс сброса устройства может занять до шести часов.</span><span class="sxs-lookup"><span data-stu-id="89b6e-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="89b6e-124">Не выключайте и не выключайте Surface Hub, пока процесс не завершится.</span><span class="sxs-lookup"><span data-stu-id="89b6e-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="89b6e-125">Если вы прерываете процесс, устройство становится неработоспособным.</span><span class="sxs-lookup"><span data-stu-id="89b6e-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="89b6e-126">Для повторной работы устройства требуется гарантия обслуживания.</span><span class="sxs-lookup"><span data-stu-id="89b6e-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="89b6e-127">На Surface Hub откройте приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-127">On your Surface Hub, open **Settings**.</span></span>

   ![Изображение, показывающее приложение "Параметры" для Surface Hub.](images/sh-settings.png)

1. <span data-ttu-id="89b6e-129">Выберите **обновление & безопасность**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-129">Select **Update & Security**.</span></span>

   ![На рисунке показано, как изменить группу безопасности & в приложении "Параметры" для Surface Hub.](images/sh-settings-update-security.png)

1. <span data-ttu-id="89b6e-131">Нажмите кнопку **Восстановление**, а затем в разделе **Сброс устройства**нажмите кнопку **Начало работы**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![Изображение, показывающее параметр сброса устройства в приложении "Параметры" для Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="89b6e-133">После завершения процесса сброса Surface Hub запускает [программу первого запуска](first-run-program-surface-hub.md) .</span><span class="sxs-lookup"><span data-stu-id="89b6e-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="89b6e-134">Если при сбросе возникает проблема, она переводит Surface Hub обратно на ранее существующий образ операционной системы и отображает экран приветствия.</span><span class="sxs-lookup"><span data-stu-id="89b6e-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="89b6e-135">Восстановление Surface Hub из облака</span><span class="sxs-lookup"><span data-stu-id="89b6e-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="89b6e-136">Если по какой-либо причине Surface Hub становится недоступным, вы можете восстановить его из облака без помощи службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="89b6e-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="89b6e-137">Surface HUB может загрузить из облака обновленный образ операционной системы и использовать его для повторной установки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="89b6e-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="89b6e-138">Вы можете использовать этот тип процесса восстановления в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="89b6e-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="89b6e-139">Surface HUB или связанные с ним учетные записи перешли в состояние нестабильной работы</span><span class="sxs-lookup"><span data-stu-id="89b6e-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="89b6e-140">Surface Hub заблокирован</span><span class="sxs-lookup"><span data-stu-id="89b6e-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="89b6e-141">Для **восстановления из облачного** процесса требуется проводное подключение, обеспечивающее доступ к Интернету (без прокси-сервера или других запросов на проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="89b6e-141">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="89b6e-142">Восстановление Surface Hub в плохом состоянии</span><span class="sxs-lookup"><span data-stu-id="89b6e-142">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="89b6e-143">Если учетная запись устройства находится в нестабильном состоянии или если учетная запись администратора обнаруживает проблемы, вы можете использовать приложение "Параметры", чтобы начать процесс восстановления облака.</span><span class="sxs-lookup"><span data-stu-id="89b6e-143">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="89b6e-144">Процедуру восстановления облака следует использовать только в том случае, если процесс [сброса устройства](#reset-a-surface-hub) не решает проблему.</span><span class="sxs-lookup"><span data-stu-id="89b6e-144">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="89b6e-145">На Surface Hub выберите обновление **параметров** &gt; **&** &gt; **Восстановление**безопасности.</span><span class="sxs-lookup"><span data-stu-id="89b6e-145">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="89b6e-146">В разделе **восстановить из облака**нажмите кнопку **Перезапустить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-146">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![восстановление из облака](images/recover-from-the-cloud.png)

### <span data-ttu-id="89b6e-148">Восстановление заблокированного Surface Hub</span><span class="sxs-lookup"><span data-stu-id="89b6e-148">Recover a locked Surface Hub</span></span>

<span data-ttu-id="89b6e-149">В редких случаях в Surface Hub может возникнуть ошибка при очистке данных пользователя и приложения в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="89b6e-149">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="89b6e-150">Когда это произойдет, устройство автоматически перезапустится и снова попытается выполнить операцию.</span><span class="sxs-lookup"><span data-stu-id="89b6e-150">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="89b6e-151">Но если эта операция завершается сбоем повторно, устройство автоматически блокируется для защиты данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="89b6e-151">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="89b6e-152">Чтобы разблокировать его, необходимо [сбросить устройство](#reset-a-surface-hub) или, если это не поможет, восстановить его из облака.</span><span class="sxs-lookup"><span data-stu-id="89b6e-152">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="89b6e-153">Найдите выключатель включения в нижней части Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="89b6e-153">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="89b6e-154">Выключатель питания находится рядом с подключением шнура питания.</span><span class="sxs-lookup"><span data-stu-id="89b6e-154">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="89b6e-155">Дополнительные сведения о Power Switch можно найти в руководстве сведения о [готовности сайта Surface Hub (PDF)](surface-hub-site-readiness-guide.md).</span><span class="sxs-lookup"><span data-stu-id="89b6e-155">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="89b6e-156">В то время как Surface Hub отображает экран приветствия, отключите его с помощью переключателя Power Hub.</span><span class="sxs-lookup"><span data-stu-id="89b6e-156">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="89b6e-157">Снова включите Surface Hub с помощью переключателя Power.</span><span class="sxs-lookup"><span data-stu-id="89b6e-157">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="89b6e-158">Устройство запускается и отображает экран логотипа Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="89b6e-158">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="89b6e-159">Когда вы видите точки, расположенные под логотипом Surface Hub, снова включите Surface Hub с помощью переключателя Power.</span><span class="sxs-lookup"><span data-stu-id="89b6e-159">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="89b6e-160">Повторяйте шаг 3 3 или до тех пор, пока Surface Hub не отобразит сообщение "Подготовка автоматического восстановления".</span><span class="sxs-lookup"><span data-stu-id="89b6e-160">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="89b6e-161">После отображения этого сообщения Surface Hub отображает экран Windows RE.</span><span class="sxs-lookup"><span data-stu-id="89b6e-161">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="89b6e-162">Выберите **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-162">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="89b6e-163">Выберите команду **восстановить из облака**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-163">Select **Recover from the cloud**.</span></span> <span data-ttu-id="89b6e-164">(При желании вы можете нажать кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-164">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="89b6e-165">Однако для **восстановления из облака** рекомендуется использовать этот подход.)</span><span class="sxs-lookup"><span data-stu-id="89b6e-165">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Восстановление из облака](images/recover-from-cloud.png)
1. <span data-ttu-id="89b6e-167">Если вам будет предложено ввести ключ BitLocker, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="89b6e-167">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="89b6e-168">Чтобы сохранить данные, которые BitLocker защищает на Surface Hub, введите ключ BitLocker.</span><span class="sxs-lookup"><span data-stu-id="89b6e-168">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="89b6e-169">Чтобы отменить защищенную информацию, выберите **пропустить этот диск**</span><span class="sxs-lookup"><span data-stu-id="89b6e-169">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="89b6e-170">При появлении соответствующего запроса нажмите кнопку **переустановить**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-170">When you are prompted, select **Reinstall**.</span></span>

    ![Переустановка](images/reinstall.png)

1. <span data-ttu-id="89b6e-172">Для повторного разбиения диска нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="89b6e-172">To repartition the disk, select **Yes**.</span></span>

   ![Разбиение](images/repartition.png)

   <span data-ttu-id="89b6e-174">Сначала процесс восстановления загружает образ операционной системы из облака.</span><span class="sxs-lookup"><span data-stu-id="89b6e-174">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![загрузка 97&](images/recover-progress.png)

   <span data-ttu-id="89b6e-176">Когда загрузка завершится, процесс восстановления восстановит Surface Hub в соответствии с выбранными параметрами.</span><span class="sxs-lookup"><span data-stu-id="89b6e-176">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="89b6e-177">обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="89b6e-177">Contact Support</span></span>

<span data-ttu-id="89b6e-178">Если у вас возникли вопросы или вам нужна помощь, вы можете [создать запрос в службу поддержки](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="89b6e-178">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="89b6e-179">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="89b6e-179">Related topics</span></span>

[<span data-ttu-id="89b6e-180">Управление Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="89b6e-180">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="89b6e-181">Руководство администратора Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="89b6e-181">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
