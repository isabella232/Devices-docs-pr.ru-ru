---
title: Сброс или восстановление Surface Hub
description: Описывает процессы сброса и восстановления для Surface Hub и предоставляет инструкции.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: сброс Surface Hub, восстановление
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304822"
---
# <span data-ttu-id="cdb4c-104">Сброс или восстановление Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cdb4c-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="cdb4c-105">В этой статье описано, как сбросить или восстановить Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="cdb4c-106">[Сброс Surface Hub](#reset-a-surface-hub) возвращает операционную систему до последнего накопительного обновления Windows и удаляет все локальные файлы пользователей и сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="cdb4c-107">К удаляемой информации относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="cdb4c-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="cdb4c-108">учетная запись устройства;</span><span class="sxs-lookup"><span data-stu-id="cdb4c-108">The device account</span></span>
- <span data-ttu-id="cdb4c-109">Сведения об учетной записи локальных администраторов устройства</span><span class="sxs-lookup"><span data-stu-id="cdb4c-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="cdb4c-110">Сведения о подступе к домену или Azure AD</span><span class="sxs-lookup"><span data-stu-id="cdb4c-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="cdb4c-111">Сведения о регистрации в MDM</span><span class="sxs-lookup"><span data-stu-id="cdb4c-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="cdb4c-112">Сведения о конфигурации, заданная с помощью MDM или приложения "Параметры"</span><span class="sxs-lookup"><span data-stu-id="cdb4c-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="cdb4c-113">[При восстановлении Surface Hub из облака](#recover-a-surface-hub-from-the-cloud) эти сведения также удаляются.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="cdb4c-114">Кроме того, Surface Hub скачивает новый образ операционной системы и устанавливает его.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="cdb4c-115">Можно указать, сохраняет ли процесс восстановления другие сведения, хранимые на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="cdb4c-116">Тот же образ операционной системы используется средством восстановления [Surface Hub,](surface-hub-recovery-tool.md) если вам нужно восстановить Surface Hub, для которого не может использоваться ни один из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <span data-ttu-id="cdb4c-117">Сброс Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cdb4c-117">Reset a Surface Hub</span></span>

<span data-ttu-id="cdb4c-118">Вам может потребоваться сбросить Surface Hub по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="cdb4c-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="cdb4c-119">Вы повторно очищаете устройство для нового пространства для собраний и хотите перенастроить его.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="cdb4c-120">вам нужно поменять метод локального управления устройством.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="cdb4c-121">Имя пользователя или пароль для учетной записи устройства или учетной записи администратора были потеряны.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="cdb4c-122">После установки обновления производительность устройства снижается.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="cdb4c-123">В процессе сброса, если вы видите пустой экран в течение длительного времени, подождите и не принимайте никаких действий.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="cdb4c-124">Процесс сброса устройства может занять до шести часов.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="cdb4c-125">Не отключать и не отключать Surface Hub, пока процесс не завершится.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="cdb4c-126">Если прерывать процесс, устройство становится неоперабельным.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="cdb4c-127">Чтобы устройство снова стало функциональным, требуется служба гарантии.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="cdb4c-128">На Surface Hub откройте приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-128">On your Surface Hub, open **Settings**.</span></span>

   ![Изображение приложения "Параметры" для Surface Hub.](images/sh-settings.png)

2. <span data-ttu-id="cdb4c-130">Select **Update & Security**.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-130">Select **Update & Security**.</span></span>

   ![Изображение группы "Обновление & безопасности" в приложении "Параметры" для Surface Hub.](images/sh-settings-update-security.png)

3. <span data-ttu-id="cdb4c-132">Выберите **"Восстановление",** а затем в области **"Сброс устройства"** выберите **"Начало работы".**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="cdb4c-133">Убедитесь, что ключ BitLocker доступен перед сбросом устройства, так как он вам будет предложен позже.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="cdb4c-134">Дополнительные узнать [см. в под ключе Save your BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="cdb4c-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="cdb4c-135">Когда концентратор перезагружается в раздел восстановления, вам будет предложено ввести ключ BitLocker.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="cdb4c-136">Пропуск этого запроса приведет к сбойу сброса.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Изображение параметра "Сброс устройства" в приложении "Параметры" для Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="cdb4c-138">После завершения процесса сброса Surface Hub снова запускает программу [первого](first-run-program-surface-hub.md) запуска.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="cdb4c-139">Если в процессе сброса возникает проблема, Surface Hub возвращается к ранее существующему образу операционной системы, а затем отображается экран приветствия.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="cdb4c-140">Восстановление Surface Hub из облака</span><span class="sxs-lookup"><span data-stu-id="cdb4c-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="cdb4c-141">Если по какой-либо причине Surface Hub становится непригодным для использования, вы можете восстановить его из облака без помощи службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="cdb4c-142">Surface Hub может скачать новый образ операционной системы из облака и использовать его для переустановки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="cdb4c-143">Этот тип процесса восстановления может потребоваться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="cdb4c-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="cdb4c-144">Surface Hub или связанные с ним учетные записи перешел в нестабильное состояние</span><span class="sxs-lookup"><span data-stu-id="cdb4c-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="cdb4c-145">Surface Hub заблокирован</span><span class="sxs-lookup"><span data-stu-id="cdb4c-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="cdb4c-146">Для **восстановления из облачного** процесса требуется проводное подключение, которое обеспечивает подключение к Интернету (без прокси-сервера или других подсказок проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="cdb4c-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="cdb4c-147">Восстановление Surface Hub в плохом состоянии</span><span class="sxs-lookup"><span data-stu-id="cdb4c-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="cdb4c-148">Если учетная запись устройства находится в нестабильном состоянии или если учетная запись администратора сталкивается с проблемами, вы можете запустить процесс восстановления в облаке с помощью приложения "Параметры".</span><span class="sxs-lookup"><span data-stu-id="cdb4c-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="cdb4c-149">Процесс восстановления в облаке следует [](#reset-a-surface-hub) использовать только в том случае, если процесс сброса устройства не устраняет проблему.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="cdb4c-150">На Surface Hub выберите **параметры** обновления & &gt; **восстановления** &gt; **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="cdb4c-151">В **области "Восстановление из облака" выберите** **"Перезапустить сейчас".**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![восстановление из облака](images/recover-from-the-cloud.png)

### <span data-ttu-id="cdb4c-153">Восстановление заблокированного Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cdb4c-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="cdb4c-154">В редких случаях в Surface Hub может возникнуть ошибка при очистке данных пользователя и приложения в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="cdb4c-155">В этом случае устройство автоматически перезагружается и пытается повторить операцию.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="cdb4c-156">Но если эта операция повторяется, устройство автоматически блокируется для защиты пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="cdb4c-157">Чтобы разблокировать его, необходимо [сбросить](#reset-a-surface-hub) устройство или, если это не работает, восстановить его из облака.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="cdb4c-158">Найдите переключатель питания в нижней части Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="cdb4c-159">Переключатель питания находится рядом с подключением питания.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="cdb4c-160">Дополнительные сведения о коммутаторе питания см. в руководстве по готовности сайта [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="cdb4c-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="cdb4c-161">Хотя Surface Hub отображает экран приветствия, отключите Surface Hub с помощью переключателя питания.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="cdb4c-162">Чтобы снова включить Surface Hub, используйте переключатель питания.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="cdb4c-163">Устройство запускается и отображает экран логотипа Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="cdb4c-164">Когда вы видите вращающиеся точки под логотипом Surface Hub, снова отключите Surface Hub с помощью переключателя питания.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="cdb4c-165">Повторите шаг 3 три раза или до тех пор, пока Surface Hub не отобразит сообщение "Подготовка автоматического восстановления".</span><span class="sxs-lookup"><span data-stu-id="cdb4c-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="cdb4c-166">После отображения этого сообщения Surface Hub отображает экран Windows RE.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

5. <span data-ttu-id="cdb4c-167">Выберите **дополнительные параметры.**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-167">Select **Advanced Options**.</span></span>

6. <span data-ttu-id="cdb4c-168">Выберите **"Восстановить из облака".**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-168">Select **Recover from the cloud**.</span></span> <span data-ttu-id="cdb4c-169">(При желании можно выбрать **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-169">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="cdb4c-170">Однако **рекомендуется использовать восстановление** из облака.)</span><span class="sxs-lookup"><span data-stu-id="cdb4c-170">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Восстановление из облака](images/recover-from-cloud.png)
7. <span data-ttu-id="cdb4c-172">Если вам будет предложено ввести ключ BitLocker, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cdb4c-172">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="cdb4c-173">Чтобы сохранить сведения, которые Bitlocker защищает на Surface Hub, введите ключ Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-173">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="cdb4c-174">Чтобы удалить защищенные сведения, выберите **"Пропустить этот диск"**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-174">To discard the protected information, select **Skip this drive**</span></span>  

8. <span data-ttu-id="cdb4c-175">Когда вам будет предложено, выберите **переустановить.**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-175">When you are prompted, select **Reinstall**.</span></span>

    ![Переустановка](images/reinstall.png)

9. <span data-ttu-id="cdb4c-177">Чтобы повторно разделять диск, выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="cdb4c-177">To repartition the disk, select **Yes**.</span></span>

   ![Разбиение](images/repartition.png)

   <span data-ttu-id="cdb4c-179">Во-первых, процесс восстановления загружает образ операционной системы из облака.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-179">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![загрузка 97&](images/recover-progress.png)

   <span data-ttu-id="cdb4c-181">После завершения скачивания процесс восстановления Surface Hub восстанавливается в соответствии с выбранными вами вариантами.</span><span class="sxs-lookup"><span data-stu-id="cdb4c-181">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="cdb4c-182">обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="cdb4c-182">Contact Support</span></span>

<span data-ttu-id="cdb4c-183">Если у вас возникли вопросы или вам нужна помощь, вы можете [создать запрос в службу поддержки.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="cdb4c-183">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="cdb4c-184">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cdb4c-184">Related topics</span></span>

[<span data-ttu-id="cdb4c-185">Управление Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cdb4c-185">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="cdb4c-186">Руководство администратора Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cdb4c-186">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
