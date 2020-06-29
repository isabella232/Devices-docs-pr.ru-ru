---
title: Управление параметрами UEFI Surface
description: Узнайте, как включать и отключать устройства или компоненты, настраивать параметры безопасности и загрузки устройства Surface с помощью параметров UEFI.
keywords: встроенное ПО, безопасность, функции, настройка, оборудование
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835856"
---
# <span data-ttu-id="c9baf-104">Управление параметрами UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="c9baf-105">Во всех текущих и будущих поколениях Surface Devices используется уникальный унифицированный интерфейс микропрограмм (UEFI), разработанный корпорацией Майкрософт для этих устройств.</span><span class="sxs-lookup"><span data-stu-id="c9baf-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="c9baf-106">Параметры UEFI Surface предоставляют возможность включать или отключать встроенные устройства и компоненты, защищать параметры UEFI от изменения и настраивать параметры загрузки устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="c9baf-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="c9baf-107">Поддержка управления на основе облака</span><span class="sxs-lookup"><span data-stu-id="c9baf-107">Support for cloud-based management</span></span>

<span data-ttu-id="c9baf-108">С помощью интерфейса конфигурации встроенного по устройства (DFCI), встроенного в Microsoft Intune (теперь доступно в общедоступном предварительном просмотре), управление UEFI Surface расширяет современный стек управления до уровня оборудования UEFI.</span><span class="sxs-lookup"><span data-stu-id="c9baf-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="c9baf-109">DFCI поддерживает подготовку от нуля, исключаются пароли BIOS, обеспечивает управление параметрами безопасности, включая параметры загрузки и встроенные периферийные устройства, а также предлагает фундамент для более сложных сценариев безопасности в будущем.</span><span class="sxs-lookup"><span data-stu-id="c9baf-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="c9baf-110">DFCI в настоящее время доступно для Surface Pro 7, Surface Pro X и Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c9baf-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="c9baf-111">Дополнительные сведения можно найти в разделе [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="c9baf-112">Открытие меню UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="c9baf-113">Чтобы настроить параметры UEFI во время запуска системы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c9baf-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="c9baf-114">Завершите работу своей поверхности и подождите около 10 секунд, чтобы убедиться, что она отключена.</span><span class="sxs-lookup"><span data-stu-id="c9baf-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="c9baf-115">Нажмите и удерживайте кнопку " **Громкость** " и нажимайте и отпустите **кнопку Power.**</span><span class="sxs-lookup"><span data-stu-id="c9baf-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="c9baf-116">По мере появления логотипа Microsoft или Surface на экране продолжайте навести кнопку " **Громкость** ", пока не появится экран UEFI.</span><span class="sxs-lookup"><span data-stu-id="c9baf-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="c9baf-117">Страница сведений о компьютере UEFI</span><span class="sxs-lookup"><span data-stu-id="c9baf-117">UEFI PC information page</span></span>

<span data-ttu-id="c9baf-118">На странице сведения о компьютере содержатся подробные сведения о вашем устройстве Surface.</span><span class="sxs-lookup"><span data-stu-id="c9baf-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="c9baf-119">**Model (модель** ) — на этой странице будет показана модель устройства Surface, например Surface Book 2 или Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="c9baf-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="c9baf-120">Точная конфигурация устройства (например, процессор, размер диска или объем памяти) не отображается.</span><span class="sxs-lookup"><span data-stu-id="c9baf-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="c9baf-121">**UUID**: уникальный идентификатор устройства, который используется для идентификации устройства во время разработки и управления.</span><span class="sxs-lookup"><span data-stu-id="c9baf-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="c9baf-122">**Serial Number**: этот номер используется для идентификации устройства Surface во время инвентаризации и поддержки.</span><span class="sxs-lookup"><span data-stu-id="c9baf-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="c9baf-123">**Asset Tag**: тег актива назначается устройству Surface с помощью [средства Asset Tag](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="c9baf-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="c9baf-124">Кроме того, в этом разделе вы найдете подробные сведения о встроенном ПО устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="c9baf-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="c9baf-125">Устройства Surface включают несколько внутренних компонентов, работающих под управлением разных версий встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="c9baf-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="c9baf-126">Версия встроенного ПО каждого из перечисленных ниже устройств отображается на странице **PC information** (как показано на рис. 1):</span><span class="sxs-lookup"><span data-stu-id="c9baf-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="c9baf-127">UEFI системы;</span><span class="sxs-lookup"><span data-stu-id="c9baf-127">System UEFI</span></span> 

- <span data-ttu-id="c9baf-128">контроллер SAM;</span><span class="sxs-lookup"><span data-stu-id="c9baf-128">SAM Controller</span></span> 

- <span data-ttu-id="c9baf-129">модуль управления Intel;</span><span class="sxs-lookup"><span data-stu-id="c9baf-129">Intel Management Engine</span></span> 

- <span data-ttu-id="c9baf-130">встроенный контроллер системы;</span><span class="sxs-lookup"><span data-stu-id="c9baf-130">System Embedded Controller</span></span> 

- <span data-ttu-id="c9baf-131">встроенное ПО сенсорного управления.</span><span class="sxs-lookup"><span data-stu-id="c9baf-131">Touch Firmware</span></span> 

![Сведения о системе и версии встроенного ПО](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="c9baf-133">Рис. 1.</span><span class="sxs-lookup"><span data-stu-id="c9baf-133">Figure 1.</span></span> <span data-ttu-id="c9baf-134">Сведения о системе и версии встроенного ПО</span><span class="sxs-lookup"><span data-stu-id="c9baf-134">System information and firmware version information</span></span>*

<span data-ttu-id="c9baf-135">Вы можете найти актуальные сведения о последней версии встроенного ПО для вашего устройства Surface в [журнале обновлений Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) для этого устройства.</span><span class="sxs-lookup"><span data-stu-id="c9baf-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="c9baf-136">Страница безопасности UEFI</span><span class="sxs-lookup"><span data-stu-id="c9baf-136">UEFI Security page</span></span> 

![Настройка параметров безопасности UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="c9baf-138">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="c9baf-138">Figure 2.</span></span> <span data-ttu-id="c9baf-139">Настройка параметров безопасности UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="c9baf-140">На странице "безопасность" можно установить пароль для защиты параметров UEFI.</span><span class="sxs-lookup"><span data-stu-id="c9baf-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="c9baf-141">Этот пароль необходимо ввести при загрузке устройства Surface в режиме UEFI.</span><span class="sxs-lookup"><span data-stu-id="c9baf-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="c9baf-142">Пароль может содержать следующие символы (как показано на рис. 3).</span><span class="sxs-lookup"><span data-stu-id="c9baf-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="c9baf-143">Прописные буквы: A–Z</span><span class="sxs-lookup"><span data-stu-id="c9baf-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="c9baf-144">Строчные буквы: a–z</span><span class="sxs-lookup"><span data-stu-id="c9baf-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="c9baf-145">Цифры: 1–10</span><span class="sxs-lookup"><span data-stu-id="c9baf-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="c9baf-146">Специальные символы:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: ' ".</span><span class="sxs-lookup"><span data-stu-id="c9baf-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="c9baf-147">Пароль должен состоять по крайней мере из 6 символов и вводится с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="c9baf-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![Добавление пароля для защиты параметров UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="c9baf-149">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="c9baf-149">Figure 3.</span></span> <span data-ttu-id="c9baf-150">Добавление пароля для защиты параметров UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="c9baf-151">На странице Security также можно изменить конфигурацию безопасной загрузки устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="c9baf-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="c9baf-152">Технология безопасной загрузки предотвращает загрузку несанкционированного кода на устройстве Surface, обеспечивая защиту от заражений буткитами и руткитами.</span><span class="sxs-lookup"><span data-stu-id="c9baf-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="c9baf-153">Вы можете отключить безопасную загрузку, чтобы на устройстве Surface можно было загружать сторонние операционные системы и загрузочные носители.</span><span class="sxs-lookup"><span data-stu-id="c9baf-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="c9baf-154">Вы также можете настроить безопасную загрузку для работы со сторонними сертификатами, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="c9baf-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="c9baf-155">Дополнительные сведения о [безопасной загрузке](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) см. в библиотеке TechNet.</span><span class="sxs-lookup"><span data-stu-id="c9baf-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Настройка безопасной загрузки](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="c9baf-157">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="c9baf-157">Figure 4.</span></span> <span data-ttu-id="c9baf-158">Настройка безопасной загрузки</span><span class="sxs-lookup"><span data-stu-id="c9baf-158">Configure Secure Boot</span></span>*

<span data-ttu-id="c9baf-159">В зависимости от устройства вы также можете проверить, включен ли доверенный платформенный модуль.</span><span class="sxs-lookup"><span data-stu-id="c9baf-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="c9baf-160">Если вы не видите параметр **включить доверенный платформенный модуль** , откройте TPM. msc в Windows, чтобы проверить состояние, как показано на рисунке 5.</span><span class="sxs-lookup"><span data-stu-id="c9baf-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="c9baf-161">TPM используется для проверки подлинности при шифровании данных устройства с помощью BitLocker.</span><span class="sxs-lookup"><span data-stu-id="c9baf-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="c9baf-162">Дополнительные сведения можно найти в разделе [Общие сведения о BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="c9baf-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Консоль TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="c9baf-164">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="c9baf-164">Figure 5.</span></span> <span data-ttu-id="c9baf-165">Консоль TPM</span><span class="sxs-lookup"><span data-stu-id="c9baf-165">TPM console</span></span>*


## <span data-ttu-id="c9baf-166">Меню UEFI: устройства</span><span class="sxs-lookup"><span data-stu-id="c9baf-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="c9baf-167">На странице устройства вы можете включать и отключать определенные устройства и компоненты, в том числе:</span><span class="sxs-lookup"><span data-stu-id="c9baf-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="c9baf-168">порты док-станций и USB;</span><span class="sxs-lookup"><span data-stu-id="c9baf-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="c9baf-169">разъем для карты MicroSD или SD;</span><span class="sxs-lookup"><span data-stu-id="c9baf-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="c9baf-170">задняя камера;</span><span class="sxs-lookup"><span data-stu-id="c9baf-170">Rear Camera</span></span> 

- <span data-ttu-id="c9baf-171">лицевая камера;</span><span class="sxs-lookup"><span data-stu-id="c9baf-171">Front Camera</span></span> 

- <span data-ttu-id="c9baf-172">инфракрасная камера;</span><span class="sxs-lookup"><span data-stu-id="c9baf-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="c9baf-173">Wi-Fi и Bluetooth;</span><span class="sxs-lookup"><span data-stu-id="c9baf-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="c9baf-174">встроенная аудиосистема (динамики и микрофон).</span><span class="sxs-lookup"><span data-stu-id="c9baf-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="c9baf-175">У каждого устройства есть кнопка с ползунком, с помощью которой можно перейти в положение **вкл** (разрешено) или **выключено** (отключено), как показано на рисунке 6.</span><span class="sxs-lookup"><span data-stu-id="c9baf-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Включение и отключение устройств](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="c9baf-177">Рисунок 6.</span><span class="sxs-lookup"><span data-stu-id="c9baf-177">Figure 6.</span></span> <span data-ttu-id="c9baf-178">Включение и отключение устройств</span><span class="sxs-lookup"><span data-stu-id="c9baf-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="c9baf-179">Меню UEFI: Настройка загрузки</span><span class="sxs-lookup"><span data-stu-id="c9baf-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="c9baf-180">На странице Конфигурация загрузки можно изменить порядок загрузочных устройств, а также включить или отключить загрузку следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="c9baf-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="c9baf-181">диспетчер загрузки Windows;</span><span class="sxs-lookup"><span data-stu-id="c9baf-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="c9baf-182">USB-накопитель;</span><span class="sxs-lookup"><span data-stu-id="c9baf-182">USB Storage</span></span> 

- <span data-ttu-id="c9baf-183">сеть PXE;</span><span class="sxs-lookup"><span data-stu-id="c9baf-183">PXE Network</span></span> 

- <span data-ttu-id="c9baf-184">внутренняя память.</span><span class="sxs-lookup"><span data-stu-id="c9baf-184">Internal Storage</span></span> 

<span data-ttu-id="c9baf-185">Вы можете мгновенно загрузить систему с определенного устройства или провести пальцем влево по этому устройству в списке.</span><span class="sxs-lookup"><span data-stu-id="c9baf-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="c9baf-186">Вы также можете мгновенно загрузить систему на USB-устройство или USB-адаптер для Ethernet, когда устройство Surface отключено, одновременно нажав кнопки **уменьшения громкости** и **включения**.</span><span class="sxs-lookup"><span data-stu-id="c9baf-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="c9baf-187">Чтобы заданный загрузочный заказ **вступил в силу**, необходимо установить параметр **включить альтернативную загрузку последовательности** , как показано на рисунке 7.</span><span class="sxs-lookup"><span data-stu-id="c9baf-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Настройка порядка загрузки для устройства Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="c9baf-189">Рисунок 7.</span><span class="sxs-lookup"><span data-stu-id="c9baf-189">Figure 7.</span></span> <span data-ttu-id="c9baf-190">Настройка порядка загрузки для устройства Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="c9baf-191">Вы также можете включать и отключать поддержку IPv6 для PXE с помощью параметра **Enable IPv6 for PXE Network Boot**, например во время развертывания Windows с помощью PXE, если сервер PXE настроен только для IPv4.</span><span class="sxs-lookup"><span data-stu-id="c9baf-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="c9baf-192">Меню UEFI: Управление</span><span class="sxs-lookup"><span data-stu-id="c9baf-192">UEFI menu: Management</span></span>
<span data-ttu-id="c9baf-193">На странице управления можно управлять использованием средств управления UEFI с нулевым касанием и других функций на подходящих устройствах, в том числе Surface Pro 7, Surface Pro X и Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c9baf-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="c9baf-194">Управление доступом к управлению UEFI с нулевым касанием и другим функциям, ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *показанным на рисунке 8. Управление доступом к сенсорному управлению UEFI и другим функциям*</span><span class="sxs-lookup"><span data-stu-id="c9baf-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="c9baf-195">Управление UEFI с нулевым сенсорным интерфейсом позволяет удаленно управлять параметрами UEFI с помощью профиля устройства в средстве настройки встроенного микрокода устройства (DFCI) в Intune.</span><span class="sxs-lookup"><span data-stu-id="c9baf-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="c9baf-196">Если вы не настраиваете этот параметр, возможность управления подходящими устройствами с помощью DFCI будет настроена как **готовая**.</span><span class="sxs-lookup"><span data-stu-id="c9baf-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="c9baf-197">Чтобы предотвратить DFCI, выберите вариант **отказаться от**использования.</span><span class="sxs-lookup"><span data-stu-id="c9baf-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c9baf-198">Страница параметров управления UEFI и использование DFCI доступны только на Surface Pro 7, Surface Pro X и Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c9baf-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="c9baf-199">Дополнительные сведения можно найти в разделе [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="c9baf-200">Меню UEFI: выход</span><span class="sxs-lookup"><span data-stu-id="c9baf-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="c9baf-201">Нажмите кнопку **Перезапустить сейчас** на странице **выхода** , чтобы выйти из параметров UEFI, как показано на рисунке 9.</span><span class="sxs-lookup"><span data-stu-id="c9baf-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Выход из меню UEFI Surface и перезагрузка устройства](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="c9baf-203">Рисунок 9.</span><span class="sxs-lookup"><span data-stu-id="c9baf-203">Figure 9.</span></span> <span data-ttu-id="c9baf-204">Нажмите "Restart Now", чтобы выйти из меню UEFI Surface и перезагрузить устройство</span><span class="sxs-lookup"><span data-stu-id="c9baf-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="c9baf-205">Экраны загрузки UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="c9baf-206">При обновлении встроенного ПО устройства Surface с помощью центра обновления Windows или ручной установки обновления применяются к устройству не сразу, а во время следующего цикла перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="c9baf-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="c9baf-207">Вы можете узнать больше о процессе обновления встроенного ПО Surface на странице [Управление обновлениями драйверов и встроенного ПО Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="c9baf-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="c9baf-208">Выполнение обновления встроенного ПО отображается на экране с помощью индикаторов разных цветов, соответствующих встроенному ПО каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="c9baf-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="c9baf-209">Индикатор выполнения каждого компонента показан на рисунках 9 – 18.</span><span class="sxs-lookup"><span data-stu-id="c9baf-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Обновление встроенного ПО UEFI Surface с синим индикатором выполнения](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="c9baf-211">Рисунок 10.</span><span class="sxs-lookup"><span data-stu-id="c9baf-211">Figure 10.</span></span> <span data-ttu-id="c9baf-212">Обновление встроенного ПО UEFI Surface с синим индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Встроенное ПО встроенного контроллера системы с зеленым индикатором выполнения](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="c9baf-214">Рисунок 11.</span><span class="sxs-lookup"><span data-stu-id="c9baf-214">Figure 11.</span></span> <span data-ttu-id="c9baf-215">Обновление встроенного ПО встроенного контроллера системы с зеленым индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="c9baf-217">Рисунок 12.</span><span class="sxs-lookup"><span data-stu-id="c9baf-217">Figure 12.</span></span> <span data-ttu-id="c9baf-218">Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Встроенное ПО Intel Management Engine с красным индикатором выполнения](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="c9baf-220">Рисунок 13.</span><span class="sxs-lookup"><span data-stu-id="c9baf-220">Figure 13.</span></span> <span data-ttu-id="c9baf-221">Обновление встроенного ПО Intel Management Engine с красным индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Встроенное ПО сенсорных элементов Surface с серым индикатором выполнения](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="c9baf-223">Рисунок 14.</span><span class="sxs-lookup"><span data-stu-id="c9baf-223">Figure 14.</span></span> <span data-ttu-id="c9baf-224">При обновлении встроенного ПО сенсорных элементов Surface отображается серый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![Встроенное по Surface KIP, светло-зеленый индикатор выполнения](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="c9baf-226">Рис. 15.</span><span class="sxs-lookup"><span data-stu-id="c9baf-226">Figure 15.</span></span> <span data-ttu-id="c9baf-227">На индикаторе обновления встроенного микрокода Surface KIP отображается светло-зеленый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Встроенное по Surface ISH с розовым индикатором выполнения](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="c9baf-229">Рисунок 16. Программа Surface ISH, на которой отображается индикатор прогресса</span><span class="sxs-lookup"><span data-stu-id="c9baf-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Встроенное по Surface сенсорной панели с серым индикатором выполнения](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="c9baf-231">Рис. 17.</span><span class="sxs-lookup"><span data-stu-id="c9baf-231">Figure 17.</span></span> <span data-ttu-id="c9baf-232">В обновлении встроенного по Surface сенсорной панели отображается розовый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Встроенное по Surface TCON, светло-серый индикатор выполнения](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="c9baf-234">Рисунок 18.</span><span class="sxs-lookup"><span data-stu-id="c9baf-234">Figure 18.</span></span> <span data-ttu-id="c9baf-235">В обновлении встроенного по Surface TCON отображается светлый серый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Встроенное по TPM Surface с светло-лиловым индикатором выполнения](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="c9baf-237">Рисунок 19.</span><span class="sxs-lookup"><span data-stu-id="c9baf-237">Figure 19.</span></span> <span data-ttu-id="c9baf-238">В обновлении встроенного по TPM Surface отображается фиолетовый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="c9baf-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="c9baf-239">Появится дополнительное предупреждение с сообщением о том, что отключена безопасная загрузка, как показано на рисунке 19.</span><span class="sxs-lookup"><span data-stu-id="c9baf-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Экран загрузки Surface, указывающий, что безопасная загрузка отключена](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="c9baf-241">Рисунок 20.</span><span class="sxs-lookup"><span data-stu-id="c9baf-241">Figure 20.</span></span> <span data-ttu-id="c9baf-242">Экран загрузки Surface, указывающий, что безопасная загрузка отключена в параметрах UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="c9baf-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="c9baf-243">Связанные темы</span><span class="sxs-lookup"><span data-stu-id="c9baf-243">Related topics</span></span>

- [<span data-ttu-id="c9baf-244">Управление параметрами UEFI Surface в Intune</span><span class="sxs-lookup"><span data-stu-id="c9baf-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="c9baf-245">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="c9baf-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
