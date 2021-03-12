---
title: Сброс или восстановление концентратора Surface
description: Описывает процессы сброса и восстановления surface Hub и содержит инструкции.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: сброс Surface Hub, восстановление
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406652"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="541d7-104">Сброс или восстановление концентратора Surface</span><span class="sxs-lookup"><span data-stu-id="541d7-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="541d7-105">В этой статье описано, как сбросить или восстановить концентратор Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="541d7-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="541d7-106">[Сброс Surface Hub возвращает](#reset-a-surface-hub) операционную систему последнего накопительного обновления Windows и удаляет все локальные файлы пользователей и сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="541d7-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="541d7-107">Удаленная информация включает в себя следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="541d7-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="541d7-108">учетная запись устройства;</span><span class="sxs-lookup"><span data-stu-id="541d7-108">The device account</span></span>
- <span data-ttu-id="541d7-109">Сведения об учетных записях локальных администраторов устройства</span><span class="sxs-lookup"><span data-stu-id="541d7-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="541d7-110">Сведения о присоединиться к домену или Azure AD-join</span><span class="sxs-lookup"><span data-stu-id="541d7-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="541d7-111">Сведения об управлении мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="541d7-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="541d7-112">Сведения о конфигурации, задатые с помощью MDM или приложения Settings</span><span class="sxs-lookup"><span data-stu-id="541d7-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="541d7-113">[Восстановление концентратора surface hub из облака](#recover-a-surface-hub-from-the-cloud) также удаляет эту информацию.</span><span class="sxs-lookup"><span data-stu-id="541d7-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="541d7-114">Кроме того, Surface Hub загружает новое изображение операционной системы и устанавливает его.</span><span class="sxs-lookup"><span data-stu-id="541d7-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="541d7-115">Можно указать, сохраняет ли процесс восстановления другие сведения, хранимые на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="541d7-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="541d7-116">Одно и то же изображение операционной системы используется средством восстановления [Surface Hub,](surface-hub-recovery-tool.md) если требуется восстановить surface Hub, для которого не может использоваться ни один из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="541d7-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="541d7-117">Сброс концентратора Surface</span><span class="sxs-lookup"><span data-stu-id="541d7-117">Reset a Surface Hub</span></span>

<span data-ttu-id="541d7-118">Возможно, вам придется сбросить surface Hub по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="541d7-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="541d7-119">Вы повторно очищает устройство для нового пространства собраний и хотите перенастроить его.</span><span class="sxs-lookup"><span data-stu-id="541d7-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="541d7-120">вам нужно поменять метод локального управления устройством.</span><span class="sxs-lookup"><span data-stu-id="541d7-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="541d7-121">Потеряно имя пользователя или пароль для учетной записи устройства или учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="541d7-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="541d7-122">После установки обновления производительность устройства снижается.</span><span class="sxs-lookup"><span data-stu-id="541d7-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="541d7-123">Во время процесса сброса, если вы видите пустой экран в течение длительных периодов времени, пожалуйста, подождите и не принимайте никаких действий.</span><span class="sxs-lookup"><span data-stu-id="541d7-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="541d7-124">Процесс сброса устройства может занять до шести часов.</span><span class="sxs-lookup"><span data-stu-id="541d7-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="541d7-125">Не отключите или отключите Концентратор Surface, пока процесс не завершится.</span><span class="sxs-lookup"><span data-stu-id="541d7-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="541d7-126">Если прерывать процесс, устройство становится неоперабельным.</span><span class="sxs-lookup"><span data-stu-id="541d7-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="541d7-127">Устройство требует гарантийной службы, чтобы снова стать функциональным.</span><span class="sxs-lookup"><span data-stu-id="541d7-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="541d7-128">На Surface Hub откройте приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="541d7-128">On your Surface Hub, open **Settings**.</span></span>

   ![Изображение, на которое показано приложение Параметры для Surface Hub.](images/sh-settings.png)

2. <span data-ttu-id="541d7-130">Выберите **обновление & безопасности**.</span><span class="sxs-lookup"><span data-stu-id="541d7-130">Select **Update & Security**.</span></span>

   ![Изображение, на которое & группы безопасности в приложении Settings для Surface Hub.](images/sh-settings-update-security.png)

3. <span data-ttu-id="541d7-132">Выберите **Восстановление,** а затем в **устройстве Reset**выберите **Начало**работы.</span><span class="sxs-lookup"><span data-stu-id="541d7-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="541d7-133">Убедитесь, что у вас есть ключ BitLocker перед сбросом устройства, как вам будет предложено для него позже.</span><span class="sxs-lookup"><span data-stu-id="541d7-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="541d7-134">Дополнительные дополнительные информации [см. в см. в ленте Сохранить ключ BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="541d7-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="541d7-135">При перезагрузке концентратора в раздел восстановления будет предложено ввести ключ BitLocker.</span><span class="sxs-lookup"><span data-stu-id="541d7-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="541d7-136">Пропуск этого запроса приведет к сбойу сброса.</span><span class="sxs-lookup"><span data-stu-id="541d7-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Изображение, отображающее параметр Сброс устройства в приложении Параметры для Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="541d7-138">После завершения процесса сброса surface Hub снова запускает [первую программу запуска.](first-run-program-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="541d7-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="541d7-139">Если в процессе сброса возникает проблема, он возвращает surface Hub на ранее существующее изображение операционной системы, а затем отображает экран Welcome.</span><span class="sxs-lookup"><span data-stu-id="541d7-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="541d7-140">Восстановление Surface Hub из облака</span><span class="sxs-lookup"><span data-stu-id="541d7-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="541d7-141">Если по какой-либо причине Surface Hub становится непригодным для использования, его можно восстановить из облака без помощи Службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="541d7-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="541d7-142">Surface Hub может скачать новое изображение операционной системы из облака и использовать его для переустановки своей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="541d7-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="541d7-143">Возможно, вам придется использовать этот тип процесса восстановления при следующих обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="541d7-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="541d7-144">Концентратор Surface или связанные с ним учетные записи ввели нестабильное состояние</span><span class="sxs-lookup"><span data-stu-id="541d7-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="541d7-145">Концентратор Surface заблокирован</span><span class="sxs-lookup"><span data-stu-id="541d7-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="541d7-146">Для **восстановления от облачного** процесса требуется проводное подключение, которое обеспечивает открытое подключение к Интернету (без прокси-серверов или других подсказок проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="541d7-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="541d7-147">Восстановление Surface Hub в плохом состоянии</span><span class="sxs-lookup"><span data-stu-id="541d7-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="541d7-148">Если учетная запись устройства попадает в нестабильное состояние или у учетной записи администратора возникают проблемы, вы можете запустить процесс восстановления облака с помощью приложения Параметры.</span><span class="sxs-lookup"><span data-stu-id="541d7-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="541d7-149">Процесс восстановления облака следует использовать [](#reset-a-surface-hub) только в том случае, если процесс сброса устройства не устраняет проблему.</span><span class="sxs-lookup"><span data-stu-id="541d7-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="541d7-150">В центре Surface выберите **параметры** &gt; **Update & восстановления** &gt; **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="541d7-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="541d7-151">В **статье Восстановление из облака**выберите **Перезапустить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="541d7-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![восстановление из облака](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="541d7-153">Восстановление заблокированного Surface Hub</span><span class="sxs-lookup"><span data-stu-id="541d7-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="541d7-154">В редких случаях в Surface Hub может возникнуть ошибка при очистке данных пользователя и приложения в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="541d7-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="541d7-155">Когда это произойдет, устройство автоматически перезапускует и снова пробует операцию.</span><span class="sxs-lookup"><span data-stu-id="541d7-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="541d7-156">Но если эта операция не удается повторно, устройство автоматически блокируется для защиты пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="541d7-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="541d7-157">Чтобы разблокировать его, необходимо [сбросить](#reset-a-surface-hub) устройство или, если оно не работает, восстановить его из облака.</span><span class="sxs-lookup"><span data-stu-id="541d7-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="541d7-158">Найдите переключатель питания в нижней части Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="541d7-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="541d7-159">Переключатель питания находится рядом с подключением к шнуру питания.</span><span class="sxs-lookup"><span data-stu-id="541d7-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="541d7-160">Дополнительные сведения о коммутаторе питания см. в руководстве по готовности к сайту [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="541d7-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="541d7-161">В то время как surface Hub отображает экран Welcome, используйте переключатель питания, чтобы отключить Концентратор Surface.</span><span class="sxs-lookup"><span data-stu-id="541d7-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="541d7-162">Чтобы включить surface Hub, используйте переключатель питания.</span><span class="sxs-lookup"><span data-stu-id="541d7-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="541d7-163">Устройство запускает и отображает экран логотипа Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="541d7-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="541d7-164">Когда вы видите вращающиеся точки под логотипом Surface Hub, используйте переключатель питания, чтобы снова отключить Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="541d7-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="541d7-165">Повторите шаг 3 три раза или до тех пор, пока surface Hub не отобразит сообщение "Подготовка автоматического ремонта".</span><span class="sxs-lookup"><span data-stu-id="541d7-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="541d7-166">После отображения этого сообщения surface Hub отображает экран RE Windows.</span><span class="sxs-lookup"><span data-stu-id="541d7-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="541d7-167">Выберите **сброс для повторной установки Windows.**</span><span class="sxs-lookup"><span data-stu-id="541d7-167">Select **Reset to re-install Windows**.</span></span> 
![сброс, чтобы переустановить](images/recover-from-cloud.png)

8. <span data-ttu-id="541d7-169">Выберите **загрузку Cloud.**</span><span class="sxs-lookup"><span data-stu-id="541d7-169">Select **Cloud download.**</span></span> 

   ![Загрузка облака](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="541d7-171">Если вы получаете сообщение об ошибке, указывающее на **невозможное скачивание,** выберите **Отмена** и попробуйте еще раз.</span><span class="sxs-lookup"><span data-stu-id="541d7-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="541d7-172">Выберите **полностью очистить диск.**  
![ восстановление и полное очистка диска</span><span class="sxs-lookup"><span data-stu-id="541d7-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="541d7-173">Вам будет **предложено, готовы ли вы сбросить это устройство?**.</span><span class="sxs-lookup"><span data-stu-id="541d7-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="541d7-174">Нажмите кнопку **Сбросить**.</span><span class="sxs-lookup"><span data-stu-id="541d7-174">Select **Reset**.</span></span> 
![восстановление и подтверждение сброса](images/recover-confirm-reset.png)

11. <span data-ttu-id="541d7-176">Загрузка начинается, а процесс восстановления указывает на **сброс этого устройства.**</span><span class="sxs-lookup"><span data-stu-id="541d7-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![восстановление, показанные в процессе](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="541d7-178">обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="541d7-178">Contact Support</span></span>

<span data-ttu-id="541d7-179">Если у вас есть вопросы или вам нужна помощь, вы можете [создать запрос на поддержку.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="541d7-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="541d7-180">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="541d7-180">Related topics</span></span>

[<span data-ttu-id="541d7-181">Управление Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="541d7-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="541d7-182">Руководство администратора Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="541d7-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
