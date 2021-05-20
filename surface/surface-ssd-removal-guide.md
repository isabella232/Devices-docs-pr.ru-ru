---
title: Удаление SSD на совместимых устройствах Surface
description: В этой статье, предназначенной для квалифицированных ИТ-специалистов, описываются рекомендуемые рекомендации по удалению и замене SSD в Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X и Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576909"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="bc3c6-103">Лучшие практики для удаления SSD с совместимых устройств Surface</span><span class="sxs-lookup"><span data-stu-id="bc3c6-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc3c6-104">Эта статья предназначена только для использования квалифицированными ИТ-специалистами в организации предприятия.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="bc3c6-105">В нем описываются рекомендуемые рекомендации для использования квалифицированными ИТ-специалистами при удалении и замене SSD в следующих совместимых устройствах Surface:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="bc3c6-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="bc3c6-106">Surface Pro 7+</span></span>
- <span data-ttu-id="bc3c6-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="bc3c6-107">Surface Pro X</span></span>
- <span data-ttu-id="bc3c6-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="bc3c6-108">Surface Laptop Go</span></span>
- <span data-ttu-id="bc3c6-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="bc3c6-109">Surface Laptop 3</span></span>
- <span data-ttu-id="bc3c6-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="bc3c6-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="bc3c6-111">Открытие устройств и замена компонентов устройств могут представлять угрозы для электрошока, повреждения устройства, пожара и личных повреждений, а также другие опасности.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="bc3c6-112">Всегда используйте осторожность, когда вы проводите такие действия.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="bc3c6-113">Следуйте мерам предосторожности и процедурам, которые определены в руководстве по удалению [rSSD для](https://www.microsoft.com/download/100440)Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="bc3c6-114">Мы рекомендуем вам получить профессиональную помощь, если вы не можете соблюдать меры предосторожности и процедуры, указанные в "руководстве по удалению rSSD для Enterprise".</span><span class="sxs-lookup"><span data-stu-id="bc3c6-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc3c6-115">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="bc3c6-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc3c6-116">В этой статье предполагается, что вы понимаете общие политики и процедуры, описанные в "руководстве по удалению rSSD для Enterprise".</span><span class="sxs-lookup"><span data-stu-id="bc3c6-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="bc3c6-117">Подготовка к удалению SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="bc3c6-118">Установка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="bc3c6-118">Install the latest updates</span></span> 

<span data-ttu-id="bc3c6-119">Перед началом работы убедитесь, что в Windows версии Windows установлены последние обновления:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="bc3c6-120">Перейдите **к Параметры**обновления & безопасности и выберите  >  \*\*\*\*  >  \*\*\*\* Check **for updates**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="bc3c6-121">Установка всех доступных обновлений.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-121">Install all available updates.</span></span>
3. <span data-ttu-id="bc3c6-122">Проверка всех паролей, необходимых для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="bc3c6-123">"Управление BitLocker"</span><span class="sxs-lookup"><span data-stu-id="bc3c6-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="bc3c6-124">В этом разделе содержатся рекомендации для организаций, которые BitLocker шифрование для жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="bc3c6-125">Дополнительные сведения см. [в BitLocker руководстве по восстановлению.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="bc3c6-126">Если BitLocker шифрование отключено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="bc3c6-127">Если устройство можно расшифровать до удаления и замены SSD, выполните следующие действия, чтобы отключить BitLocker:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="bc3c6-128">В **Параметры**введите **BitLocker** и выберите **Управление BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="bc3c6-129">Выберите **отключение BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="bc3c6-130">Питание устройства.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="bc3c6-131">Если BitLocker включено шифрование во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="bc3c6-132">Если устройство зашифровано до удаления и замены SSD, выполните следующие действия, чтобы создать ключ восстановления BitLocker и сохранить его в хранилище USB:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="bc3c6-133">В **Параметры**введите **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="bc3c6-134">Выберите **Управление BitLocker**Создание BitLocker  > **восстановления**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="bc3c6-135">Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="bc3c6-136">Сохраните ключ восстановления в хранилище USB.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="bc3c6-137">Удалите USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="bc3c6-138">Питание устройства.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="bc3c6-139">Удаление и замена SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="bc3c6-140">Удалите SSD с помощью соответствующих инструкций для устройства, включенных в [руководство по удалению rSSD](https://www.microsoft.com/download/100440)для Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="bc3c6-141">Поместите исходный SSD в новое устройство и подключите новое устройство к подключению к интернету с проводной связью.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="bc3c6-142">Питание на новом устройстве.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-142">Power on the new device.</span></span> <span data-ttu-id="bc3c6-143">Устройство может проходить обновление прошивки во время запуска.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="bc3c6-144">После удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="bc3c6-145">Управление незашифрованными SSD</span><span class="sxs-lookup"><span data-stu-id="bc3c6-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="bc3c6-146">Если SSD не расшифрована во время передачи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="bc3c6-147">Перейдите **к пароль параметрам для**  >  **входов** (представленный значком ключа слева).</span><span class="sxs-lookup"><span data-stu-id="bc3c6-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="bc3c6-148">Введите пароль и войдите в ожидании завершения двух факторов проверки подлинности (если это применимо).</span><span class="sxs-lookup"><span data-stu-id="bc3c6-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="bc3c6-149">После полной регистрации перейдите к **запуску**  >  **регистрации**  >  **учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="bc3c6-150">Во входе с помощью пароля и настройка Windows Hello и ПИН-кода при запросе.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="bc3c6-151">Если устройство было отключено BitLocker для облегчения удаления и замены SSD, и вы хотите включить \*\*\*\* BitLocker после замены, перейдите в BitLocker  >  **Управление BitLocker**Резюме  >  **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="bc3c6-152">Запустите службу диагностики [поверхности Майкрософт набор средств для бизнеса](surface-diagnostic-toolkit-for-business-intro.md) (SDT), чтобы проверить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="bc3c6-153">Проверьте активацию Windows путем навигации по **Параметры**  >  **активации.**</span><span class="sxs-lookup"><span data-stu-id="bc3c6-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="bc3c6-154">Если вы видите сообщения об ошибках, выберите **устранение неполадок.**</span><span class="sxs-lookup"><span data-stu-id="bc3c6-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="bc3c6-155">Проверьте учетную запись Office, **открыв приложение Office,** перейдите к учетной записи **файла,** а затем проверьте все  >  \*\*\*\* сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="bc3c6-156">Управление зашифрованными SSD-кодами</span><span class="sxs-lookup"><span data-stu-id="bc3c6-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="bc3c6-157">Для чтения ключа восстановления BitLocker, сохраненного на USB-диске, необходимо иметь второе устройство.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="bc3c6-158">Если SSD зашифрован во время передачи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bc3c6-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="bc3c6-159">Вставьте USB-накопитель, содержащий ключ BitLocker восстановления во втором устройстве.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="bc3c6-160">Откройте файл .txt, содержащий ключ восстановления Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="bc3c6-161">Вручную введите BitLocker восстановления на новом устройстве, которое содержит исходный SSD.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="bc3c6-162">После успешного вступив в BitLocker ключ восстановления, перейдите в пароль параметра **Sign-In**(представленный значком ключа  >  \*\*\*\* слева).</span><span class="sxs-lookup"><span data-stu-id="bc3c6-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="bc3c6-163">Введите пароль и войдите, пока не будет завершена двух-факторная проверка подлинности (если это применимо).</span><span class="sxs-lookup"><span data-stu-id="bc3c6-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="bc3c6-164">После полной регистрации перейдите к **запуску**  >  **регистрации**  >  **учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="bc3c6-165">Войте обратно, используя пароль, а затем Windows Hello и добавьте ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="bc3c6-166">Если устройство было отключено BitLocker для облегчения удаления и замены SSD, и если вы хотите \*\*\*\* включить BitLocker после замены, перейдите к Параметры  >  **BitLocker**  >  **Управление BitLocker**Возобновить  >  **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="bc3c6-167">Запустите **[SDT,](surface-diagnostic-toolkit-for-business-intro.md)** чтобы проверить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="bc3c6-168">Чтобы проверить Windows активацию, **выберите Параметры**  >  **активацию.**</span><span class="sxs-lookup"><span data-stu-id="bc3c6-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="bc3c6-169">Если вы видите сообщения об ошибках, выберите **устранение неполадок.**</span><span class="sxs-lookup"><span data-stu-id="bc3c6-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="bc3c6-170">Чтобы проверить состояние учетной записи Office, откройте **приложение Office,** а затем перейдите в **файл**учетную запись, чтобы проверить сообщения об  >  \*\*\*\* ошибках.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="bc3c6-171">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bc3c6-171">Learn more</span></span>

- [<span data-ttu-id="bc3c6-172">руководство по удалению rSSD для Enterprise</span><span class="sxs-lookup"><span data-stu-id="bc3c6-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="bc3c6-173">Руководство по восстановлению BitLocker</span><span class="sxs-lookup"><span data-stu-id="bc3c6-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="bc3c6-174">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="bc3c6-174">Still need help?</span></span> <span data-ttu-id="bc3c6-175">Перейдите в [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bc3c6-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>