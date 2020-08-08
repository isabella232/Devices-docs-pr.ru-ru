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
ms.date: 8/7/2020
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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918974"
---
# <span data-ttu-id="80143-103">Рекомендации по удалению SSD на совместимых устройствах Surface</span><span class="sxs-lookup"><span data-stu-id="80143-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80143-104">Эта статья предназначена для использования квалифицированными специалистами по ИТ в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="80143-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="80143-105">В этой статье описаны рекомендуемые рекомендации для использования квалифицированными специалистами по ИТ при удалении и замене твердотельных накопителей на Surface Devices со съемными твердотельными накопителями.</span><span class="sxs-lookup"><span data-stu-id="80143-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="80143-106">Открытие устройств и замена компонентов устройств могут привести к электрическим электрическим ударам, повреждению устройств, пожару и риску и другим угрозам.</span><span class="sxs-lookup"><span data-stu-id="80143-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="80143-107">Всегда будьте внимательны при выполнении таких действий.</span><span class="sxs-lookup"><span data-stu-id="80143-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="80143-108">Примите меры предосторожности и процедуры, описанные в руководстве по удалению rSSD для предприятий.</span><span class="sxs-lookup"><span data-stu-id="80143-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="80143-109">Корпорация Microsoft рекомендует вам найти профессиональную помощь, если вы не можете соблюдать меры предосторожности и процедуры, указанные в руководстве по удалению rSSD для предприятия.</span><span class="sxs-lookup"><span data-stu-id="80143-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="80143-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="80143-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80143-111">В этой статье предполагается, что вы понимаете общие меры по обеспечению безопасности, а также правила и процедуры безопасности, описанные в [руководстве по удалению rSSD для предприятий](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="80143-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="80143-112">Подготовка к удалению SSD</span><span class="sxs-lookup"><span data-stu-id="80143-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="80143-113">Установка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="80143-113">Install the latest updates</span></span> 

<span data-ttu-id="80143-114">Прежде чем начать, убедитесь в том, что в вашей версии Windows установлены последние обновления.</span><span class="sxs-lookup"><span data-stu-id="80143-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="80143-115">Перейдите к разделу Параметры **запуска**  >  **Settings**  >  **Обновление & безопасность** и выберите пункт **проверить наличие обновлений**.</span><span class="sxs-lookup"><span data-stu-id="80143-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="80143-116">Установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="80143-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="80143-117">Убедитесь, что у вас есть пароли, необходимые для доступа к устройству.</span><span class="sxs-lookup"><span data-stu-id="80143-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="80143-118">Управление BitLocker</span><span class="sxs-lookup"><span data-stu-id="80143-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="80143-119">Этот раздел содержит рекомендации для организаций с включенным шифрованием BitLocker для жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="80143-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="80143-120">Дополнительные сведения можно найти в [руководстве по восстановлению BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="80143-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="80143-121">Если шифрование BitLocker отключено во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="80143-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="80143-122">Если перед удалением и заменой SSD вы можете отключить устройство, выполните указанные ниже действия, чтобы отключить BitLocker.</span><span class="sxs-lookup"><span data-stu-id="80143-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="80143-123">В окне " **Параметры**" введите **BitLocker** и выберите **Управление BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="80143-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="80143-124">Выберите команду **Выключить BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="80143-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="80143-125">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="80143-125">Power down the device.</span></span> 

### <span data-ttu-id="80143-126">Если включено шифрование BitLocker во время удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="80143-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="80143-127">Если устройство шифруется до удаления и замены SSD, выполните указанные ниже действия, чтобы создать ключ восстановления BitLocker и сохранить его в USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="80143-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="80143-128">Перейдите в раздел **Параметры** и введите **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="80143-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="80143-129">Выберите **Управление BitLocker**  > **Создание ключа восстановления BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="80143-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="80143-130">Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="80143-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="80143-131">Сохраните ключ восстановления на USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="80143-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="80143-132">Выньте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="80143-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="80143-133">Выключите устройство.</span><span class="sxs-lookup"><span data-stu-id="80143-133">Power down the device.</span></span> 

## <span data-ttu-id="80143-134">Удаление и замена SSD</span><span class="sxs-lookup"><span data-stu-id="80143-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="80143-135">Удалите SSD с помощью инструкций, приведенных в [руководстве по удалению rSSD для предприятия](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="80143-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="80143-136">Поместите исходный SSD в новое устройство и подключите новое устройство к проводному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="80143-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="80143-137">Включите новое устройство.</span><span class="sxs-lookup"><span data-stu-id="80143-137">Power on the new device.</span></span> <span data-ttu-id="80143-138">При запуске устройства может пройти обновление встроенного по.</span><span class="sxs-lookup"><span data-stu-id="80143-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="80143-139">После удаления и замены SSD</span><span class="sxs-lookup"><span data-stu-id="80143-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="80143-140">Управление незашифрованными твердотельными накопителями</span><span class="sxs-lookup"><span data-stu-id="80143-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="80143-141">Если во время передачи твердотельный SSD останется нешифрованным, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="80143-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="80143-142">Выберите пароль для **входа**в систему  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="80143-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="80143-143">Введите пароль и войдите в ожидание завершения двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="80143-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="80143-144">После того как вы завершите работу, перейдите к разделу **Начало**  >  выхода из**учетной записи**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="80143-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="80143-145">Войдите в систему с помощью пароля и настройте Windows Hello и ПИН-код при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="80143-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="80143-146">Если устройство было отключено BitLocker для упрощения удаления и замены и вы хотите включить BitLocker после замены, перейдите на вкладку **BitLocker**  >  **Управление**BitLocker для  >  **восстановления**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="80143-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="80143-147">Запустите **SDT** , чтобы подтвердить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="80143-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="80143-148">Проверьте наличие активации Windows, перейдя к **Settings**  >  **активации**параметров.</span><span class="sxs-lookup"><span data-stu-id="80143-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="80143-149">Если сообщения об ошибках не отображаются, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="80143-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="80143-150">Проверьте учетную запись Office, открыв **приложение Office**, перейдите к **File**  >  **учетной записи** "файл" и проверьте наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="80143-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="80143-151">Управление шифрованными SSDs</span><span class="sxs-lookup"><span data-stu-id="80143-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="80143-152">Для чтения ключа восстановления BitLocker, сохраненного на USB-накопителе, вам понадобится второе устройство.</span><span class="sxs-lookup"><span data-stu-id="80143-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="80143-153">Если SSD оставался зашифрованным во время передачи данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="80143-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="80143-154">Вставьте USB-накопитель с ключом восстановления BitLocker на второе устройство.</span><span class="sxs-lookup"><span data-stu-id="80143-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="80143-155">Откройте txt файл, содержащий ключ восстановления BitLocker.</span><span class="sxs-lookup"><span data-stu-id="80143-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="80143-156">Вручную введите ключ восстановления BitLocker в новое устройство, содержащее исходный SSD.</span><span class="sxs-lookup"><span data-stu-id="80143-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="80143-157">После того как вы введете ключ восстановления BitLocker, выберите пароль для **входа в учетную**запись  >  **Password** (представлен значком ключа в левой части экрана).</span><span class="sxs-lookup"><span data-stu-id="80143-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="80143-158">Введите пароль и войдите в службу, ожидая двухфакторной проверки подлинности (если применимо).</span><span class="sxs-lookup"><span data-stu-id="80143-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="80143-159">После того как вы завершите работу, перейдите к разделу **Начало**  >  выхода из**учетной записи**  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="80143-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="80143-160">Войдите в систему с помощью пароля и настройте Windows Hello и добавьте ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="80143-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="80143-161">Если устройство было отключено BitLocker для упрощения удаления и замены и вы хотите включить BitLocker после замены, перейдите в раздел **Параметры**  >  **BitLocker**, Управление BitLocker,  >  **Manage Bitlocker**  >  **Восстановление**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="80143-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="80143-162">Запустите **SDT** , чтобы подтвердить полную функциональность устройства.</span><span class="sxs-lookup"><span data-stu-id="80143-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="80143-163">Установите флажок Активация Windows, перейдя **Settings**к  >  **активации**параметров.</span><span class="sxs-lookup"><span data-stu-id="80143-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="80143-164">Если сообщения об ошибках не отображаются, нажмите кнопку **Диагностика**.</span><span class="sxs-lookup"><span data-stu-id="80143-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="80143-165">Чтобы проверить учетную запись Office, откройте **приложение Office**, перейдите в раздел **File**  >  **учетная запись** файла и проверьте наличие сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="80143-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="80143-166">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="80143-166">More information</span></span> 

<span data-ttu-id="80143-167">Дополнительные сведения доступны в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="80143-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="80143-168">Руководство по удалению rSSD для предприятий</span><span class="sxs-lookup"><span data-stu-id="80143-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="80143-169">Руководство по восстановлению BitLocker</span><span class="sxs-lookup"><span data-stu-id="80143-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="80143-170">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="80143-170">Still need help?</span></span> <span data-ttu-id="80143-171">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="80143-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>