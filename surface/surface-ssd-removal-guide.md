---
title: Удаление SSD в совместимых Surface Devices
description: В этой статье рассказывается о рекомендуемых рекомендациях по удалению и замене твердотельных накопителей на компьютере Surface 3, Surface Pro X и Surface, предназначенные для квалифицированных специалистов в области ИТ.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133174"
---
# <span data-ttu-id="794d9-103">Рекомендации по удалению SSD с совместимых устройств Surface</span><span class="sxs-lookup"><span data-stu-id="794d9-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="794d9-104">Эта статья предназначена для использования квалифицированными специалистами по ИТ в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="794d9-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="794d9-105">В этой статье описаны рекомендуемые рекомендации, которые следует использовать квалифицированными специалистами по ИТ при удалении и замене SSDs на следующих совместимых устройствах Surface.</span><span class="sxs-lookup"><span data-stu-id="794d9-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="794d9-106">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="794d9-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="794d9-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="794d9-107">Surface Pro X</span></span> 
- <span data-ttu-id="794d9-108">Ноутбук Surface Go</span><span class="sxs-lookup"><span data-stu-id="794d9-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="794d9-109">Открытие устройств и замена компонентов устройств могут привести к электрическим электрическим ударам, повреждению устройств, пожару и риску и другим угрозам.</span><span class="sxs-lookup"><span data-stu-id="794d9-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="794d9-110">Всегда будьте внимательны при выполнении таких действий.</span><span class="sxs-lookup"><span data-stu-id="794d9-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="794d9-111">Примите меры предосторожности и процедуры, описанные в руководстве по [удалению rSSD для предприятий](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="794d9-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="794d9-112">Корпорация Майкрософт рекомендует получить профессиональную помощь, если вы не можете соблюдать меры предосторожности и процедуры, указанные в разделе "Руководство по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="794d9-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="794d9-113">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="794d9-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="794d9-114">В этой статье предполагается, что вы понимаете общие меры по безопасности, а также правила и процедуры безопасности, описанные в разделе "Руководство по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="794d9-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="794d9-115">Подготовка к удалению SSD</span><span class="sxs-lookup"><span data-stu-id="794d9-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="794d9-116">Установка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="794d9-116">Install the latest updates</span></span> 

<span data-ttu-id="794d9-117">Прежде чем начать, убедитесь в том, что у вашей версии Windows установлены последние обновления:</span><span class="sxs-lookup"><span data-stu-id="794d9-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="794d9-118">Перейдите к разделу Параметры **запуска**  >  **Settings**  >  **Обновление & безопасность**и выберите пункт **проверить наличие обновлений**.</span><span class="sxs-lookup"><span data-stu-id="794d9-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="794d9-119">Установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="794d9-119">Install all available updates.</span></span>
3. <span data-ttu-id="794d9-120">Проверьте все пароли, необходимые для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="794d9-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="794d9-121">"Управление BitLocker"</span><span class="sxs-lookup"><span data-stu-id="794d9-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="794d9-122">Этот раздел содержит рекомендации для организаций с включенным шифрованием BitLocker для жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="794d9-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="794d9-123">Дополнительные сведения можно найти в  [руководстве руководство по восстановлению BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="794d9-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="794d9-124">Если шифрование BitLocker отключено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="794d9-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="794d9-125">Если перед удалением и заменой SSD вы можете отключить устройство, выполните указанные ниже действия, чтобы отключить BitLocker.</span><span class="sxs-lookup"><span data-stu-id="794d9-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="794d9-126">В окне " **Параметры**" введите **BitLocker** и выберите пункт " **Управление BitLocker**".</span><span class="sxs-lookup"><span data-stu-id="794d9-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="794d9-127">Выберите команду **Выключить BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="794d9-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="794d9-128">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="794d9-128">Power down the device.</span></span> 

### <span data-ttu-id="794d9-129">Если включено шифрование BitLocker во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="794d9-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="794d9-130">Если устройство шифруется до удаления и замены SSD, выполните указанные ниже действия, чтобы создать ключ восстановления BitLocker и сохранить его в USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="794d9-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="794d9-131">В окне " **Параметры**" введите **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="794d9-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="794d9-132">Выберите **Управление BitLocker**  > **Создание ключа восстановления BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="794d9-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="794d9-133">Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="794d9-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="794d9-134">Сохраните ключ восстановления на USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="794d9-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="794d9-135">Выньте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="794d9-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="794d9-136">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="794d9-136">Power down the device.</span></span> 

## <span data-ttu-id="794d9-137">Удаление и замена SSD</span><span class="sxs-lookup"><span data-stu-id="794d9-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="794d9-138">Удалите SSD с помощью инструкций, приведенных в [руководстве по удалению rSSD для предприятия](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="794d9-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="794d9-139">Вставьте первоначальный SSD в новое устройство и подключите новое устройство к проводному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="794d9-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="794d9-140">Включите новое устройство.</span><span class="sxs-lookup"><span data-stu-id="794d9-140">Power on the new device.</span></span> <span data-ttu-id="794d9-141">При запуске устройства может пройти обновление встроенного по.</span><span class="sxs-lookup"><span data-stu-id="794d9-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="794d9-142">После удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="794d9-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="794d9-143">Управление незашифрованными твердотельными накопителями</span><span class="sxs-lookup"><span data-stu-id="794d9-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="794d9-144">Если твердотельный SSD не зашифрован во время передачи данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="794d9-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="794d9-145">Выберите пароль для **входа**в систему  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="794d9-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="794d9-146">Введите пароль и войдите в ожидание завершения двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="794d9-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="794d9-147">После того как вы полностью вошли в систему, перейдите к разделу **Начало**работы с  >  **учетной записью**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="794d9-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="794d9-148">Войдите в систему с помощью пароля и настройте Windows Hello и ПИН-код при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="794d9-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="794d9-149">Если устройство было отключено BitLocker для упрощения удаления и замены и вы хотите включить BitLocker после замены, перейдите в раздел **BitLocker**  >  **Управление**BitLocker  >  **возобновление BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="794d9-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="794d9-150">Запустите средство [Microsoft Surface Diagnostic Toolkit для бизнеса](surface-diagnostic-toolkit-for-business-intro.md) (SDT), чтобы проверить работоспособность всех устройств.</span><span class="sxs-lookup"><span data-stu-id="794d9-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="794d9-151">Проверьте наличие активации Windows, перейдя к **Settings**  >  **активации**параметров.</span><span class="sxs-lookup"><span data-stu-id="794d9-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="794d9-152">Если вы видите сообщение об ошибке, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="794d9-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="794d9-153">Проверьте учетную запись Office, открыв **приложение Office**, перейдите **File**в  >  **учетную запись** файла и проверьте наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="794d9-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="794d9-154">Управление шифрованными SSDs</span><span class="sxs-lookup"><span data-stu-id="794d9-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="794d9-155">Вы должны иметь второе устройство для чтения ключа восстановления BitLocker, сохраненного на USB-накопителе.</span><span class="sxs-lookup"><span data-stu-id="794d9-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="794d9-156">Если твердотельный SSD шифруется во время передачи данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="794d9-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="794d9-157">Вставьте USB-накопитель, который включает ключ восстановления BitLocker, во второе устройство.</span><span class="sxs-lookup"><span data-stu-id="794d9-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="794d9-158">Откройте txt файл, содержащий ключ восстановления BitLocker.</span><span class="sxs-lookup"><span data-stu-id="794d9-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="794d9-159">Вручную введите ключ восстановления BitLocker на новом устройстве, содержащем исходный SSD.</span><span class="sxs-lookup"><span data-stu-id="794d9-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="794d9-160">После того как вы введете ключ восстановления BitLocker, выберите пароль для **входа в учетную**запись  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="794d9-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="794d9-161">Введите пароль и войдите в службу, ожидая выполнения двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="794d9-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="794d9-162">После того как вы полностью вошли в систему, перейдите к разделу **Начало**работы с  >  **учетной записью**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="794d9-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="794d9-163">Войдите в систему с помощью пароля, а затем настройте Windows Hello и добавьте ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="794d9-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="794d9-164">Если устройство отключено с помощью BitLocker, чтобы упростить удаление и замену, а если вы хотите включить BitLocker после замены, перейдите к разделу **Параметры**  >  **BitLocker**, Управление BitLocker,  >  **Manage BitLocker**  >  **Восстановление**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="794d9-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="794d9-165">Запустите **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** , чтобы проверить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="794d9-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="794d9-166">Для проверки активации Windows выберите **Параметры**  >  **активации**.</span><span class="sxs-lookup"><span data-stu-id="794d9-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="794d9-167">Если вы видите сообщение об ошибке, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="794d9-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="794d9-168">Чтобы проверить состояние учетной записи Office, откройте **приложение Office**, а затем **перейдите к**  >  **учетной записи** , чтобы проверить наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="794d9-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="794d9-169">Подробнее</span><span class="sxs-lookup"><span data-stu-id="794d9-169">Learn more</span></span>

- [<span data-ttu-id="794d9-170">Руководство по удалению rSSD для предприятий</span><span class="sxs-lookup"><span data-stu-id="794d9-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="794d9-171">Руководство по восстановлению BitLocker</span><span class="sxs-lookup"><span data-stu-id="794d9-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="794d9-172">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="794d9-172">Still need help?</span></span> <span data-ttu-id="794d9-173">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="794d9-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>