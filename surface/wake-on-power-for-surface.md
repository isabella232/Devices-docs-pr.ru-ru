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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903022"
---
# <span data-ttu-id="b8801-104">Пробуждение Power On для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="b8801-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="b8801-105">Чтобы сохранить батарею, устройства Surface можно отключить на рабочем столе или выбрать режим гибернации.</span><span class="sxs-lookup"><span data-stu-id="b8801-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="b8801-106">Чтобы улучшить управляемость этих устройств, функция Wake on Power включает совместимые устройства Surfaces для автоматического запуска при повторном подключении к Power.</span><span class="sxs-lookup"><span data-stu-id="b8801-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="b8801-107">Настройка функции Wake on Power On требует использования режима управления Surface Enterprise (SEMM) либо через конфигуратора поверхности UEFI, либо из диспетчера UEFI.</span><span class="sxs-lookup"><span data-stu-id="b8801-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="b8801-108">Функция пробуждения Power On доступна на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="b8801-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="b8801-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="b8801-109">Surface Book 3</span></span>
- <span data-ttu-id="b8801-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="b8801-110">Surface Pro 7</span></span>
- <span data-ttu-id="b8801-111">Surface ноутбук 3</span><span class="sxs-lookup"><span data-stu-id="b8801-111">Surface Laptop 3</span></span>
- <span data-ttu-id="b8801-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="b8801-112">Surface Pro X</span></span> 

## <span data-ttu-id="b8801-113">Общие сведения и требования</span><span class="sxs-lookup"><span data-stu-id="b8801-113">Overview and prerequisites</span></span>

<span data-ttu-id="b8801-114">Вы можете использовать конфигуратор UEFI Surface для настройки отдельных параметров UEFI, сохраненных в пакете установщика Windows Installer. msi для распространения на целевые устройства.</span><span class="sxs-lookup"><span data-stu-id="b8801-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="b8801-115">В этой статье предполагается, что вы знакомы с использованием SEMM.</span><span class="sxs-lookup"><span data-stu-id="b8801-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="b8801-116">Дополнительные сведения можно найти в разделе Документация по [режиму управления предприятием в Surface (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="b8801-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="b8801-117">Включение функции пробуждения на Power On</span><span class="sxs-lookup"><span data-stu-id="b8801-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="b8801-118">Скачайте последнюю версию [конфигуратора UEFI Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="b8801-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="b8801-119">Войдите на устройство Surface с помощью учетной записи администратора, откройте **Конфигуратор UEFI Surface**, выберите **Surface Devices**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8801-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  <span data-ttu-id="b8801-121">Нажмите кнопку **Пуск** , а затем в разделе **пакет конфигурации** выберите **создать**.</span><span class="sxs-lookup"><span data-stu-id="b8801-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите команду Создать пакет конфигурации.":::
4.  <span data-ttu-id="b8801-123">Нажмите кнопку **Защита сертификата** и добавьте PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="b8801-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="b8801-124">После ввода пароля нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8801-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="b8801-125">Добавьте **защиту паролем**, если это необходимо, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8801-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="b8801-126">На странице **выберите тип поверхности, на которую вы хотите сделать это** , выберите нужные оконечные устройства.</span><span class="sxs-lookup"><span data-stu-id="b8801-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="b8801-127">Например, **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="b8801-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="b8801-128">На странице **Advanced Features (дополнительные функции** ) выберите **режим пробуждения** и установите переключатель **вкл**.</span><span class="sxs-lookup"><span data-stu-id="b8801-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="b8801-129">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8801-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите параметр "вкл." на вкладке "вкл."."::: 
7.  <span data-ttu-id="b8801-131">На странице **успешно** нажмите кнопку **завершить**.</span><span class="sxs-lookup"><span data-stu-id="b8801-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="b8801-132">Если вы впервые предоставляете параметры для вашего устройства, вам будет предложено указать два последних символа отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="b8801-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="b8801-133">Сохраните пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="b8801-133">Save the .msi package.</span></span> 

## <span data-ttu-id="b8801-134">Применение MSI-пакета</span><span class="sxs-lookup"><span data-stu-id="b8801-134">Apply the MSI package</span></span> 

<span data-ttu-id="b8801-135">Пакет MSI можно применить к устройствам в сети с помощью средств распространения программного обеспечения, таких как Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b8801-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="b8801-136">Эта процедура включает инструкции по установке пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8801-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="b8801-137">Откройте командную команду с повышенными привилегиями и введите полный путь к MSI-файлу, чтобы запустить пакет MSI.</span><span class="sxs-lookup"><span data-stu-id="b8801-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="b8801-138">В диалоговом окне **предупреждение** нажмите кнопку " **ОК** " или отключите BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b8801-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Нажмите кнопку ОК или отключите BitLocker в нужном виде.":::
3.  <span data-ttu-id="b8801-140">На странице приветствия нажмите кнопку **Далее** , чтобы запустить пакет и применить только что настроенный параметр UEFI.</span><span class="sxs-lookup"><span data-stu-id="b8801-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="На одной странице приветствия нажмите кнопку Далее.":::
4.  <span data-ttu-id="b8801-142">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="b8801-142">Restart your device.</span></span> 

<span data-ttu-id="b8801-143">Теперь вы настроили функцию пробуждения на Power On.</span><span class="sxs-lookup"><span data-stu-id="b8801-143">Wake on Power is now configured.</span></span> <span data-ttu-id="b8801-144">Чтобы протестировать этот параметр, отключите устройство, отключите электроэнергию и повторно подключитесь к электросети.</span><span class="sxs-lookup"><span data-stu-id="b8801-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="b8801-145">Устройство запустится автоматически.</span><span class="sxs-lookup"><span data-stu-id="b8801-145">The device will start automatically.</span></span> 

## <span data-ttu-id="b8801-146">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b8801-146">More information</span></span>

<span data-ttu-id="b8801-147">Дополнительные сведения можно найти в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="b8801-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="b8801-148">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="b8801-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="b8801-149">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="b8801-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="b8801-150">Все еще нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="b8801-150">Still need help?</span></span> <span data-ttu-id="b8801-151">Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b8801-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>