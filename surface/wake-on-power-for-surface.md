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
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
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
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903398"
---
# <span data-ttu-id="38ff9-104">Пробуждение при подаче питания для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="38ff9-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="38ff9-105">Устройства Surface можно отключить, не выходя из него, или настроить режим гибернации, чтобы сэкономить время работы от аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="38ff9-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="38ff9-106">Чтобы улучшить управляемость этих устройств, функция Wake on Power позволяет автоматически запускать совместимые устройства Surface при повторном подключении к Power.</span><span class="sxs-lookup"><span data-stu-id="38ff9-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="38ff9-107">Чтобы настроить функцию пробуждения Power On, вы можете использовать режим корпоративного управления Surface (SEMM) в качестве конфигуратора UEFI Surface или диспетчера UEFI.</span><span class="sxs-lookup"><span data-stu-id="38ff9-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="38ff9-108">Функция Wake on Power On поддерживается на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="38ff9-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="38ff9-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="38ff9-109">Surface Book 3</span></span>
- <span data-ttu-id="38ff9-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="38ff9-110">Surface Pro 7</span></span>
- <span data-ttu-id="38ff9-111">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="38ff9-111">Surface Laptop 3</span></span>
- <span data-ttu-id="38ff9-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="38ff9-112">Surface Pro X</span></span> 

## <span data-ttu-id="38ff9-113">Общие сведения и требования</span><span class="sxs-lookup"><span data-stu-id="38ff9-113">Overview and prerequisites</span></span>

<span data-ttu-id="38ff9-114">Конфигуратор UEFI Surface позволяет сохранить индивидуальные параметры UEFI в пакете установщика Windows Installer. msi для распространения на целевые устройства.</span><span class="sxs-lookup"><span data-stu-id="38ff9-114">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="38ff9-115">В этой статье предполагается, что вы знаете, как использовать SEMM.</span><span class="sxs-lookup"><span data-stu-id="38ff9-115">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="38ff9-116">Дополнительные сведения можно найти в разделе Документация по [режиму управления предприятием в Surface (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="38ff9-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="38ff9-117">Включение функции пробуждения на Power On</span><span class="sxs-lookup"><span data-stu-id="38ff9-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="38ff9-118">Скачайте последнюю версию [конфигуратора UEFI Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="38ff9-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="38ff9-119">Войдите на устройство Surface с помощью учетной записи администратора, откройте **Конфигуратор UEFI Surface**, выберите **Surface Devices**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-119">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  <span data-ttu-id="38ff9-121">Нажмите кнопку **Пуск**и выберите команду **создать** в разделе **пакет конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-121">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите команду Создать пакет конфигурации.":::
4.  <span data-ttu-id="38ff9-123">Выберите **Защита сертификата**и добавьте PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="38ff9-123">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="38ff9-124">Введите пароль, нажмите кнопку **Далее**, добавьте **защиту паролем**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-124">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="38ff9-125">На странице **выберите тип поверхности, на которую вы хотите сделать это** , выберите нужные оконечные устройства.</span><span class="sxs-lookup"><span data-stu-id="38ff9-125">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="38ff9-126">Например, выберите **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-126">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="38ff9-127">На странице **Дополнительные функции** выберите пункт **пробуждение по питанию**, установите для параметра значение **вкл**., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-127">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите параметр "вкл." на вкладке "вкл."."::: 
8.  <span data-ttu-id="38ff9-129">На странице **успешно** нажмите кнопку **завершить**.</span><span class="sxs-lookup"><span data-stu-id="38ff9-129">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38ff9-130">Если вы используете параметры устройства в первый раз, вам будет предложено также предоставить два последних символа отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="38ff9-130">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="38ff9-131">Сохраните пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="38ff9-131">Save the .msi package.</span></span> 

## <span data-ttu-id="38ff9-132">Применение MSI-пакета</span><span class="sxs-lookup"><span data-stu-id="38ff9-132">Apply the MSI package</span></span> 

<span data-ttu-id="38ff9-133">Пакет MSI можно применить к устройствам в сети с помощью таких средств распространения программного обеспечения, как Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="38ff9-133">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="38ff9-134">Ниже приведены инструкции по установке пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38ff9-134">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="38ff9-135">В командной строке с повышенными привилегиями введите полный путь к MSI-файлу, чтобы запустить пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="38ff9-135">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="38ff9-136">В диалоговом окне **предупреждение** нажмите кнопку **ОК** или отключите BitLocker, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="38ff9-136">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Нажмите кнопку ОК или отключите BitLocker в нужном виде.":::
3.  <span data-ttu-id="38ff9-138">На странице приветствия нажмите кнопку **Далее** , чтобы запустить пакет и применить только что настроенный параметр UEFI.</span><span class="sxs-lookup"><span data-stu-id="38ff9-138">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="На одной странице приветствия нажмите кнопку Далее.":::
4.  <span data-ttu-id="38ff9-140">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="38ff9-140">Restart your device.</span></span> 

<span data-ttu-id="38ff9-141">Теперь вы настроили функцию пробуждения на Power On.</span><span class="sxs-lookup"><span data-stu-id="38ff9-141">Wake on Power is now configured.</span></span> <span data-ttu-id="38ff9-142">Чтобы проверить параметры, отключите устройство, отключите электроэнергию и подключитесь к электросети.</span><span class="sxs-lookup"><span data-stu-id="38ff9-142">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="38ff9-143">Устройство должно запускаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="38ff9-143">The device should start automatically.</span></span> 

## <span data-ttu-id="38ff9-144">Ссылок</span><span class="sxs-lookup"><span data-stu-id="38ff9-144">References</span></span>

<span data-ttu-id="38ff9-145">Дополнительные сведения можно найти в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="38ff9-145">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="38ff9-146">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="38ff9-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="38ff9-147">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="38ff9-147">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="38ff9-148">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="38ff9-148">Still need help?</span></span> <span data-ttu-id="38ff9-149">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="38ff9-149">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>