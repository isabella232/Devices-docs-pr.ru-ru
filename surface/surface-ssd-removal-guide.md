---
title: Удаление SSD в совместимых Surface Devices
description: Как переносить твердотельный SSD с одного устройства Surface на другое.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 00109e4e1bb3873fc2914b2044f58e6fa3b6c211
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104811"
---
# <span data-ttu-id="ccf88-103">Рекомендации по удалению SSD с совместимых устройств Surface</span><span class="sxs-lookup"><span data-stu-id="ccf88-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccf88-104">Эта статья предназначена для использования квалифицированными специалистами по ИТ в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="ccf88-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="ccf88-105">В этой статье описаны рекомендуемые рекомендации, которые следует использовать квалифицированными специалистами по ИТ при удалении и замене твердотельных накопителей на компьютере Surface 3 или Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="ccf88-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in Surface Laptop 3 or Surface Pro X only.</span></span> 

> [!WARNING]
> <span data-ttu-id="ccf88-106">Открытие устройств и замена компонентов устройств могут привести к электрическим электрическим ударам, повреждению устройств, пожару и риску и другим угрозам.</span><span class="sxs-lookup"><span data-stu-id="ccf88-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="ccf88-107">Всегда будьте внимательны при выполнении таких действий.</span><span class="sxs-lookup"><span data-stu-id="ccf88-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="ccf88-108">Примите меры предосторожности и процедуры, описанные в руководстве по [удалению rSSD для предприятий](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="ccf88-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="ccf88-109">Корпорация Майкрософт рекомендует получить профессиональную помощь, если вы не можете соблюдать меры предосторожности и процедуры, указанные в разделе "Руководство по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="ccf88-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="ccf88-110">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="ccf88-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccf88-111">В этой статье предполагается, что вы понимаете общие меры по безопасности, а также правила и процедуры безопасности, описанные в разделе "Руководство по удалению rSSD для предприятий".</span><span class="sxs-lookup"><span data-stu-id="ccf88-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="ccf88-112">Подготовка к удалению SSD</span><span class="sxs-lookup"><span data-stu-id="ccf88-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="ccf88-113">Установка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="ccf88-113">Install the latest updates</span></span> 

<span data-ttu-id="ccf88-114">Прежде чем начать, убедитесь в том, что в вашей версии Windows установлены последние обновления:</span><span class="sxs-lookup"><span data-stu-id="ccf88-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="ccf88-115">Перейдите к разделу Параметры **запуска**  >  **Settings**  >  **Обновление & безопасность**и выберите пункт **проверить наличие обновлений**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="ccf88-116">Установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="ccf88-116">Install all available updates.</span></span> 
2. <span data-ttu-id="ccf88-117">Установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="ccf88-117">Install all available updates.</span></span>
3. <span data-ttu-id="ccf88-118">Убедитесь, что у вас есть пароли, необходимые для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="ccf88-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="ccf88-119">"Управление BitLocker"</span><span class="sxs-lookup"><span data-stu-id="ccf88-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="ccf88-120">Этот раздел содержит рекомендации для организаций с включенным шифрованием BitLocker для жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="ccf88-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="ccf88-121">Дополнительные сведения можно найти в [руководстве по восстановлению BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="ccf88-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="ccf88-122">Если шифрование BitLocker отключено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="ccf88-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="ccf88-123">Если перед удалением и заменой SSD вы можете отключить устройство, выполните указанные ниже действия, чтобы отключить BitLocker.</span><span class="sxs-lookup"><span data-stu-id="ccf88-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="ccf88-124">В окне " **Параметры**" введите **BitLocker**и выберите пункт " **Управление BitLocker**".</span><span class="sxs-lookup"><span data-stu-id="ccf88-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="ccf88-125">Выберите команду **Выключить BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="ccf88-126">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="ccf88-126">Power down the device.</span></span> 

### <span data-ttu-id="ccf88-127">Если включено шифрование BitLocker во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="ccf88-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="ccf88-128">Если устройство шифруется до удаления и замены SSD, выполните указанные ниже действия, чтобы создать ключ восстановления BitLocker и сохранить его в USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="ccf88-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="ccf88-129">В окне " **Параметры**" введите **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="ccf88-130">Выберите **Управление BitLocker**  > **Создание ключа восстановления BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="ccf88-131">Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="ccf88-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="ccf88-132">Сохраните ключ восстановления на USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="ccf88-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="ccf88-133">Выньте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="ccf88-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="ccf88-134">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="ccf88-134">Power down the device.</span></span> 

## <span data-ttu-id="ccf88-135">Удаление и замена SSD</span><span class="sxs-lookup"><span data-stu-id="ccf88-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="ccf88-136">Удалите SSD с помощью инструкций, приведенных в [руководстве по удалению rSSD для предприятия](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="ccf88-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="ccf88-137">Вставьте первоначальный SSD в новое устройство и подключите новое устройство к проводному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ccf88-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="ccf88-138">Включите новое устройство.</span><span class="sxs-lookup"><span data-stu-id="ccf88-138">Power on the new device.</span></span> <span data-ttu-id="ccf88-139">При запуске устройства может пройти обновление встроенного по.</span><span class="sxs-lookup"><span data-stu-id="ccf88-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="ccf88-140">После удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="ccf88-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="ccf88-141">Управление незашифрованными твердотельными накопителями</span><span class="sxs-lookup"><span data-stu-id="ccf88-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="ccf88-142">Если твердотельный SSD в процессе передачи данных остается незашифрованным, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ccf88-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="ccf88-143">Выберите пароль для **входа**в систему  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="ccf88-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="ccf88-144">Введите пароль и войдите в ожидание завершения двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="ccf88-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="ccf88-145">После того как вы полностью вошли в систему, перейдите к разделу **Начало**работы с  >  **учетной записью**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="ccf88-146">Войдите в систему с помощью пароля и настройте Windows Hello и ПИН-код при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="ccf88-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="ccf88-147">Если устройство было отключено BitLocker для упрощения удаления и замены и вы хотите включить BitLocker после замены, перейдите в раздел **BitLocker**  >  **Управление**BitLocker  >  **возобновление BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="ccf88-148">Запустите средство Microsoft Surface Diagnostic Toolkit для бизнеса (SDT), чтобы проверить работоспособность всех устройств.</span><span class="sxs-lookup"><span data-stu-id="ccf88-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="ccf88-149">Проверьте наличие активации Windows, перейдя к **Settings**  >  **активации**параметров.</span><span class="sxs-lookup"><span data-stu-id="ccf88-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="ccf88-150">Если вы видите сообщение об ошибке, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="ccf88-151">Проверьте учетную запись Office, открыв **приложение Office**, перейдите **File**в  >  **учетную запись** файла и проверьте наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ccf88-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="ccf88-152">Управление шифрованными SSDs</span><span class="sxs-lookup"><span data-stu-id="ccf88-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="ccf88-153">Вы должны иметь второе устройство для чтения ключа восстановления BitLocker, сохраненного на USB-накопителе.</span><span class="sxs-lookup"><span data-stu-id="ccf88-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="ccf88-154">Если SSD оставался зашифрованным во время передачи данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ccf88-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="ccf88-155">Вставьте USB-накопитель, который включает ключ восстановления BitLocker, во второе устройство.</span><span class="sxs-lookup"><span data-stu-id="ccf88-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="ccf88-156">Откройте txt файл, содержащий ключ восстановления BitLocker.</span><span class="sxs-lookup"><span data-stu-id="ccf88-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="ccf88-157">Вручную введите ключ восстановления BitLocker на новом устройстве, содержащем исходный SSD.</span><span class="sxs-lookup"><span data-stu-id="ccf88-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="ccf88-158">После того как вы введете ключ восстановления BitLocker, выберите пароль для **входа в учетную**запись  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="ccf88-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="ccf88-159">Введите пароль и войдите в службу, ожидая выполнения двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="ccf88-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="ccf88-160">После того как вы полностью вошли в систему, перейдите к разделу **Начало**работы с  >  **учетной записью**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="ccf88-161">Войдите в систему с помощью пароля, а затем настройте Windows Hello и добавьте ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="ccf88-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="ccf88-162">Если устройство отключено с помощью BitLocker, чтобы упростить удаление и замену, а если вы хотите включить BitLocker после замены, перейдите к разделу **Параметры**  >  **BitLocker**, Управление BitLocker,  >  **Manage Bitlocker**  >  **Восстановление**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="ccf88-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="ccf88-163">Запустите **SDT** , чтобы проверить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="ccf88-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="ccf88-164">Установите флажок Активация Windows, перейдя **Settings**к  >  **активации**параметров.</span><span class="sxs-lookup"><span data-stu-id="ccf88-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="ccf88-165">Если вы видите сообщение об ошибке, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="ccf88-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="ccf88-166">Чтобы проверить состояние учетной записи Office, откройте **приложение Office**, а затем **перейдите к**  >  **учетной записи** , чтобы проверить наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ccf88-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="ccf88-167">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ccf88-167">More information</span></span> 

<span data-ttu-id="ccf88-168">Дополнительные сведения доступны в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="ccf88-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="ccf88-169">Руководство по удалению rSSD для предприятий</span><span class="sxs-lookup"><span data-stu-id="ccf88-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="ccf88-170">Руководство по восстановлению BitLocker</span><span class="sxs-lookup"><span data-stu-id="ccf88-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="ccf88-171">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="ccf88-171">Still need help?</span></span> <span data-ttu-id="ccf88-172">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ccf88-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>