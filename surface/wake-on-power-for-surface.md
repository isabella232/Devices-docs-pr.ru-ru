---
title: How to enable Wake on Power for Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: В этой статье описывается, как включить и отключить wake on Power для устройств Surface.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271563"
---
# <span data-ttu-id="a7b0f-104">Пробуждение при подаче питания для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="a7b0f-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="a7b0f-105">Устройства Surface можно отключить, пока вы не на рабочем месте, или настроить режим гибернации для экономии заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="a7b0f-106">Чтобы повысить управляемость этих устройств, с помощью Wake on Power можно автоматически запускать совместимые устройства Surface при повторном под подключением к электросети.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="a7b0f-107">Чтобы настроить режим восстановления после питания, можно использовать режим управления Surface Enterprise (SEMM) с помощью настройщика UEFI Surface или диспетчера UEFI.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="a7b0f-108">Функция Wake on Power доступна на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="a7b0f-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="a7b0f-109">Surface Pro 7 и более</span><span class="sxs-lookup"><span data-stu-id="a7b0f-109">Surface Pro 7+</span></span>
- <span data-ttu-id="a7b0f-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a7b0f-110">Surface Book 3</span></span>
- <span data-ttu-id="a7b0f-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a7b0f-111">Surface Pro 7</span></span>
- <span data-ttu-id="a7b0f-112">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="a7b0f-112">Surface Laptop 3</span></span>
- <span data-ttu-id="a7b0f-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="a7b0f-113">Surface Laptop Go</span></span>
- <span data-ttu-id="a7b0f-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="a7b0f-114">Surface Pro X</span></span> 


## <span data-ttu-id="a7b0f-115">Обзор и предварительные условия</span><span class="sxs-lookup"><span data-stu-id="a7b0f-115">Overview and prerequisites</span></span>

<span data-ttu-id="a7b0f-116">Настройщик UEFI Surface позволяет сохранять отдельные параметры UEFI в MSI-пакете установщика Windows для распространения на целевые устройства.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="a7b0f-117">В этой статье предполагается, что вы знаете, как использовать SEMM.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="a7b0f-118">Дополнительные сведения см. в [документации по режиму управления Surface Enterprise (SEMM).](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="a7b0f-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="a7b0f-119">Чтобы включить wake on Power</span><span class="sxs-lookup"><span data-stu-id="a7b0f-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="a7b0f-120">Скачайте последнюю версию [настройщика UEFI Surface.](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="a7b0f-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="a7b0f-121">Во sign in to your Surface device as an administrator, open **Surface UEFI Configurator,** select **Surface Devices,** and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите устройства Surface и выберите Далее.":::
3.  <span data-ttu-id="a7b0f-123">Выберите **"Начните"** и выберите **"Создать** в **пакете конфигурации".**</span><span class="sxs-lookup"><span data-stu-id="a7b0f-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите Создать пакет конфигурации.":::
4.  <span data-ttu-id="a7b0f-125">Выберите **"Защита сертификатов"** и добавьте PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="a7b0f-126">Введите пароль, выберите **"Далее",** **"Добавить защиту**паролем" и затем **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="a7b0f-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="a7b0f-127">На странице **"Выбор типа Surface", на которую** вы хотите нацелить, выберите нужные целевые устройства.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="a7b0f-128">Например, выберите **Surface Pro 7.**</span><span class="sxs-lookup"><span data-stu-id="a7b0f-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="a7b0f-129">На странице **"Дополнительные функции"** выберите **"Будить на питание",** установите для функции "В сети" и выберите **"Далее".** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a7b0f-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Select Wake on Power and set to On."::: 
8.  <span data-ttu-id="a7b0f-131">На странице **"Успешно"** выберите **"Конец".**</span><span class="sxs-lookup"><span data-stu-id="a7b0f-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7b0f-132">Если вы в первый раз предоставляете параметры на устройстве, вам также будет предложено предоставить два последних символа отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="a7b0f-133">Сохраните MSI-пакет.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-133">Save the .msi package.</span></span> 

## <span data-ttu-id="a7b0f-134">Применение пакета MSI</span><span class="sxs-lookup"><span data-stu-id="a7b0f-134">Apply the MSI package</span></span> 

<span data-ttu-id="a7b0f-135">Пакет MSI можно применить к устройствам в сети с помощью таких средств распространения программного обеспечения, как Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a7b0f-136">Эта процедура включает действия по установке пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="a7b0f-137">В командной подсказке с повышенными повышенными уровнями введите полный путь к MSI-файлу, чтобы запустить MSI-пакет.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="a7b0f-138">В **диалоговом** окне предупреждения выберите **ОК"** или отключите BitLocker, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Выберите ОК или отключите BitLocker соответствующим образом.":::
3.  <span data-ttu-id="a7b0f-140">На странице приветствия выберите **"Далее",** чтобы запустить пакет, и примените только что настроенный параметр UEFI.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="На странице приветствия выберите Далее.":::
4.  <span data-ttu-id="a7b0f-142">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-142">Restart your device.</span></span> 

<span data-ttu-id="a7b0f-143">Теперь настроено питание от питания.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-143">Wake on Power is now configured.</span></span> <span data-ttu-id="a7b0f-144">Чтобы проверить параметры, отключите устройство, отключите питание и снова подключите его.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="a7b0f-145">Устройство должно запускаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-145">The device should start automatically.</span></span> 

## <span data-ttu-id="a7b0f-146">Ссылок</span><span class="sxs-lookup"><span data-stu-id="a7b0f-146">References</span></span>

<span data-ttu-id="a7b0f-147">Дополнительные сведения см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="a7b0f-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="a7b0f-148">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="a7b0f-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="a7b0f-149">Будить в локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="a7b0f-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="a7b0f-150">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="a7b0f-150">Still need help?</span></span> <span data-ttu-id="a7b0f-151">Перейдите в [Сообщество Майкрософт.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a7b0f-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>