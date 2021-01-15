---
title: Удаление SSD на совместимых устройствах Surface
description: В этой статье, предназначенной для квалифицированных ИТ-специалистов, описываются рекомендации по удалению и замене SSD в Surface Laptop 3, Surface Pro X и Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270634"
---
# <span data-ttu-id="3cb2c-103">Best practices for SSD removal from compatible Surface devices</span><span class="sxs-lookup"><span data-stu-id="3cb2c-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cb2c-104">Эта статья предназначена только для квалифицированных ИТ-специалистов в корпоративной организации.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="3cb2c-105">В нем описываются рекомендации по использованию квалифицированными ИТ-специалистами при удалении и замене SSD на следующих совместимых устройствах Surface:</span><span class="sxs-lookup"><span data-stu-id="3cb2c-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="3cb2c-106">Surface Pro 7 и более</span><span class="sxs-lookup"><span data-stu-id="3cb2c-106">Surface Pro 7+</span></span>
- <span data-ttu-id="3cb2c-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3cb2c-107">Surface Pro X</span></span>
- <span data-ttu-id="3cb2c-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="3cb2c-108">Surface Laptop Go</span></span>
- <span data-ttu-id="3cb2c-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="3cb2c-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="3cb2c-110">Открытие устройств и замена компонентов устройств может привести к повреждению устройства, повреждению устройства, пожару и личным рискам, а также другим рискам.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="3cb2c-111">При таких действиях всегда следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="3cb2c-112">Соблюдайте меры безопасности и процедуры, определенные в руководстве по удалению [RSSD для предприятий.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="3cb2c-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="3cb2c-113">Мы рекомендуем вам получить профессиональную помощь, если вы не можете соблюдать меры безопасности и процедуры, указанные в "руководстве по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="3cb2c-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="3cb2c-114">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="3cb2c-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cb2c-115">В этой статье предполагается, что вы понимаете общие меры предосторожности и политики безопасности и процедуры, описанные в "руководстве по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="3cb2c-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="3cb2c-116">Подготовка к удалению SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="3cb2c-117">Установка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="3cb2c-117">Install the latest updates</span></span> 

<span data-ttu-id="3cb2c-118">Перед началом убедитесь, что в вашей версии Windows установлены последние обновления:</span><span class="sxs-lookup"><span data-stu-id="3cb2c-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="3cb2c-119">Go to **Start**  >  **Settings**  >  **Update & Security**, and select Check for **updates**.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="3cb2c-120">Установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-120">Install all available updates.</span></span>
3. <span data-ttu-id="3cb2c-121">Проверьте все пароли, необходимые для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="3cb2c-122">"Управление BitLocker"</span><span class="sxs-lookup"><span data-stu-id="3cb2c-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="3cb2c-123">В этом разделе содержатся рекомендации для организаций, которые включили шифрование BitLocker для жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="3cb2c-124">Дополнительные сведения см. в [руководстве по восстановлению BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="3cb2c-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="3cb2c-125">Если шифрование BitLocker отключено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="3cb2c-126">Если устройство можно расшифровать до удаления и замены SSD, выполните следующие действия, чтобы отключить BitLocker:</span><span class="sxs-lookup"><span data-stu-id="3cb2c-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="3cb2c-127">В **параметрах введите** **BitLocker** и выберите **"Управление BitLocker".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="3cb2c-128">Выберите **"Отключить BitLocker".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="3cb2c-129">Питание устройства.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-129">Power down the device.</span></span> 

### <span data-ttu-id="3cb2c-130">Если шифрование BitLocker включено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="3cb2c-131">Если устройство зашифровано до удаления и замены SSD, выполните следующие действия, чтобы создать ключ восстановления BitLocker и сохранить его в USB-хранилище:</span><span class="sxs-lookup"><span data-stu-id="3cb2c-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="3cb2c-132">В **параметрах введите** **BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="3cb2c-133">Выберите **"Управление bitLocker**  > **Создать ключ восстановления BitLocker".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="3cb2c-134">Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="3cb2c-135">Сохраните ключ восстановления в USB-хранилище.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="3cb2c-136">Удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="3cb2c-137">Питание устройства.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-137">Power down the device.</span></span> 

## <span data-ttu-id="3cb2c-138">Удаление и замена SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="3cb2c-139">Удалите SSD, используя соответствующие инструкции для вашего устройства, включенные в руководство по удалению [rSSD для предприятий.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="3cb2c-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="3cb2c-140">Поместите исходный SSD на новое устройство и подключите новое устройство к проводной подключении к Интернету.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="3cb2c-141">Питание на новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-141">Power on the new device.</span></span> <span data-ttu-id="3cb2c-142">Устройство может пройти обновление во время запуска.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="3cb2c-143">После удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="3cb2c-144">Управление незашифрованными SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="3cb2c-145">Если во время передачи SSD не зашифрована, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="3cb2c-146">Перейдите **к паролем параметров**для входов  >  \*\*\*\* (представленным значком клавиши в левой части).</span><span class="sxs-lookup"><span data-stu-id="3cb2c-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="3cb2c-147">Введите пароль и войдите в ожидании завершения двух-факторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="3cb2c-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="3cb2c-148">После полного вход в учетную запись перейдите к **выходу из**  >  **учетной**  >  **записи.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="3cb2c-149">Во sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="3cb2c-150">Если устройство было отключено с помощью BitLocker для упрощения удаления и замены SSD, \*\*\*\* и вы хотите включить BitLocker после замены, перейдите к  >  **bitLocker Manage BitLocker**  >  **Resume BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="3cb2c-151">Запустите [Microsoft Surface Diagnostic набор средств for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) для проверки полной функциональности устройства.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="3cb2c-152">Проверьте активацию Windows, переходя к **активации**  >  **параметров.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="3cb2c-153">Если вы видите сообщения об ошибках, выберите **"Устранение неполадок".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="3cb2c-154">Проверьте учетную запись Office, открыв \*\*\*\* приложение **Office,** перейдите к учетной записи файла и найдите сообщения  >  \*\*\*\* об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="3cb2c-155">Управление зашифрованными SSD</span><span class="sxs-lookup"><span data-stu-id="3cb2c-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="3cb2c-156">Для чтения ключа восстановления BitLocker, сохраненного на USB-накопителе, необходимо второе устройство.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="3cb2c-157">Если SSD зашифрован во время передачи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="3cb2c-158">Вставьте USB-накопитель, содержащий ключ восстановления BitLocker, во второе устройство.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="3cb2c-159">Откройте TXT-файл, содержащий ключ восстановления Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="3cb2c-160">Вручную введите ключ восстановления BitLocker на новом устройстве, которое содержит исходный SSD.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="3cb2c-161">После того как вы успешно ввели ключ \*\*\*\* восстановления BitLocker, перейдите в пароль параметров для входов (представленный значком клавиши в  >  \*\*\*\* левой части).</span><span class="sxs-lookup"><span data-stu-id="3cb2c-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="3cb2c-162">Введите пароль и войдите в учетную записи в ожидании завершения двух-факторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="3cb2c-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="3cb2c-163">После полного вход в учетную запись перейдите к **выходу из**  >  **учетной**  >  **записи.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="3cb2c-164">Во sign in by using the password, and then set up Windows Hello and add a PIN.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="3cb2c-165">Если устройство было отключено с помощью BitLocker для упрощения удаления и замены SSD, \*\*\*\* а также если вы хотите включить BitLocker после замены, перейдите к параметрам  >  **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="3cb2c-166">Запустите **[SDT,](surface-diagnostic-toolkit-for-business-intro.md)** чтобы проверить все функциональные возможности устройства.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="3cb2c-167">Чтобы проверить активацию Windows, выберите **"Активация**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="3cb2c-168">Если вы видите сообщения об ошибках, выберите **"Устранение неполадок".**</span><span class="sxs-lookup"><span data-stu-id="3cb2c-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="3cb2c-169">Чтобы проверить состояние учетной записи Office, откройте \*\*\*\* приложение **Office,** а затем перейдите к учетной записи файла, чтобы проверить сообщения об  >  \*\*\*\* ошибках.</span><span class="sxs-lookup"><span data-stu-id="3cb2c-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="3cb2c-170">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3cb2c-170">Learn more</span></span>

- [<span data-ttu-id="3cb2c-171">Руководство по удалению rSSD для предприятий</span><span class="sxs-lookup"><span data-stu-id="3cb2c-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="3cb2c-172">Руководство по восстановлению BitLocker</span><span class="sxs-lookup"><span data-stu-id="3cb2c-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="3cb2c-173">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="3cb2c-173">Still need help?</span></span> <span data-ttu-id="3cb2c-174">Перейдите в [Сообщество Майкрософт.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3cb2c-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>