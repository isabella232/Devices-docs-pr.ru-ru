---
title: Включение функции пробуждения Power On для Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: В этой статье описано, как включать и отключать пробуждение Power On для устройств Surface.
keywords: обновление, развертывание, драйвер, WOL, пробуждение по сети
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114577"
---
# <span data-ttu-id="6a757-104">Пробуждение при подаче питания для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="6a757-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="6a757-105">Устройства Surface можно отключить, не выходя из него, или настроить режим гибернации, чтобы сэкономить время работы от аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="6a757-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="6a757-106">Чтобы улучшить управляемость этих устройств, функция Wake on Power позволяет автоматически запускать совместимые устройства Surface при повторном подключении к Power.</span><span class="sxs-lookup"><span data-stu-id="6a757-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="6a757-107">Чтобы настроить функцию пробуждения Power On, вы можете использовать режим корпоративного управления Surface (SEMM) в качестве конфигуратора UEFI Surface или диспетчера UEFI.</span><span class="sxs-lookup"><span data-stu-id="6a757-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="6a757-108">Функция Wake on Power On поддерживается на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="6a757-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="6a757-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="6a757-109">Surface Book 3</span></span>
- <span data-ttu-id="6a757-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="6a757-110">Surface Pro 7</span></span>
- <span data-ttu-id="6a757-111">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="6a757-111">Surface Laptop 3</span></span>
- <span data-ttu-id="6a757-112">Ноутбук Surface Go</span><span class="sxs-lookup"><span data-stu-id="6a757-112">Surface Laptop Go</span></span>
- <span data-ttu-id="6a757-113">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="6a757-113">Surface Pro X</span></span> 


## <span data-ttu-id="6a757-114">Общие сведения и требования</span><span class="sxs-lookup"><span data-stu-id="6a757-114">Overview and prerequisites</span></span>

<span data-ttu-id="6a757-115">Конфигуратор UEFI Surface позволяет сохранить индивидуальные параметры UEFI в пакете установщика Windows Installer. msi для распространения на целевые устройства.</span><span class="sxs-lookup"><span data-stu-id="6a757-115">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="6a757-116">В этой статье предполагается, что вы знаете, как использовать SEMM.</span><span class="sxs-lookup"><span data-stu-id="6a757-116">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="6a757-117">Дополнительные сведения можно найти в разделе Документация по [режиму управления предприятием в Surface (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="6a757-117">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="6a757-118">Включение функции пробуждения на Power On</span><span class="sxs-lookup"><span data-stu-id="6a757-118">To enable Wake on Power</span></span>

1.  <span data-ttu-id="6a757-119">Скачайте последнюю версию [конфигуратора UEFI Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="6a757-119">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="6a757-120">Войдите на устройство Surface с помощью учетной записи администратора, откройте **Конфигуратор UEFI Surface**, выберите **Surface Devices**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a757-120">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  <span data-ttu-id="6a757-122">Нажмите кнопку **Пуск**и выберите команду **создать** в разделе **пакет конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="6a757-122">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
4.  <span data-ttu-id="6a757-124">Выберите **Защита сертификата**и добавьте PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="6a757-124">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="6a757-125">Введите пароль, нажмите кнопку **Далее**, добавьте **защиту паролем**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a757-125">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="6a757-126">На странице **выберите тип поверхности, на которую вы хотите сделать это** , выберите нужные оконечные устройства.</span><span class="sxs-lookup"><span data-stu-id="6a757-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="6a757-127">Например, выберите **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="6a757-127">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="6a757-128">На странице **Дополнительные функции** выберите пункт **пробуждение по питанию**, установите для параметра значение **вкл**., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a757-128">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее."::: 
8.  <span data-ttu-id="6a757-130">На странице **успешно** нажмите кнопку **завершить**.</span><span class="sxs-lookup"><span data-stu-id="6a757-130">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a757-131">Если вы используете параметры устройства в первый раз, вам будет предложено также предоставить два последних символа отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="6a757-131">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="6a757-132">Сохраните пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="6a757-132">Save the .msi package.</span></span> 

## <span data-ttu-id="6a757-133">Применение MSI-пакета</span><span class="sxs-lookup"><span data-stu-id="6a757-133">Apply the MSI package</span></span> 

<span data-ttu-id="6a757-134">Пакет MSI можно применить к устройствам в сети с помощью таких средств распространения программного обеспечения, как Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6a757-134">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="6a757-135">Ниже приведены инструкции по установке пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6a757-135">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="6a757-136">В командной строке с повышенными привилегиями введите полный путь к MSI-файлу, чтобы запустить пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="6a757-136">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="6a757-137">В диалоговом окне **предупреждение** нажмите кнопку **ОК** или отключите BitLocker, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="6a757-137">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  <span data-ttu-id="6a757-139">На странице приветствия нажмите кнопку **Далее** , чтобы запустить пакет и применить только что настроенный параметр UEFI.</span><span class="sxs-lookup"><span data-stu-id="6a757-139">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
4.  <span data-ttu-id="6a757-141">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="6a757-141">Restart your device.</span></span> 

<span data-ttu-id="6a757-142">Теперь вы настроили функцию пробуждения на Power On.</span><span class="sxs-lookup"><span data-stu-id="6a757-142">Wake on Power is now configured.</span></span> <span data-ttu-id="6a757-143">Чтобы проверить параметры, отключите устройство, отключите электроэнергию и подключитесь к электросети.</span><span class="sxs-lookup"><span data-stu-id="6a757-143">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="6a757-144">Устройство должно запускаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="6a757-144">The device should start automatically.</span></span> 

## <span data-ttu-id="6a757-145">Ссылок</span><span class="sxs-lookup"><span data-stu-id="6a757-145">References</span></span>

<span data-ttu-id="6a757-146">Дополнительные сведения можно найти в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="6a757-146">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="6a757-147">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="6a757-147">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="6a757-148">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="6a757-148">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="6a757-149">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="6a757-149">Still need help?</span></span> <span data-ttu-id="6a757-150">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6a757-150">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>