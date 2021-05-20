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
ms.reviewer: hachidan
manager: laurawi
ms.date: 04/13/2021
ms.openlocfilehash: ea995eda277ecf235eedd92f3af6edb0b60ae68a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576509"
---
# <a name="manage-surface-uefi-settings"></a><span data-ttu-id="9bcb7-104">Управление параметрами UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="9bcb7-105">Устройства Surface PC предназначены для использования уникального интерфейса прошивки единой надежной прошивки (UEFI), разработанного корпорацией Майкрософт специально для этих устройств.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="9bcb7-106">Параметры Surface UEFI предоставляют возможность включить или отключить встроенные устройства и компоненты, защитить параметры UEFI от изменения и настроить параметры загрузки устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <a name="supported-products"></a><span data-ttu-id="9bcb7-107">Поддерживаемые продукты</span><span class="sxs-lookup"><span data-stu-id="9bcb7-107">Supported products</span></span>

<span data-ttu-id="9bcb7-108">Управление UEFI поддерживается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9bcb7-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="9bcb7-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="9bcb7-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="9bcb7-110">Surface Laptop (1-й ген), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="9bcb7-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span></span>
- <span data-ttu-id="9bcb7-111">Surface Studio (1-й gen), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="9bcb7-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="9bcb7-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="9bcb7-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="9bcb7-113">Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="9bcb7-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <a name="support-for-cloud-based-management"></a><span data-ttu-id="9bcb7-114">Поддержка облачного управления</span><span class="sxs-lookup"><span data-stu-id="9bcb7-114">Support for cloud-based management</span></span>

<span data-ttu-id="9bcb7-115">С учетом профилей интерфейса конфигурации микропрограммных программ (DFCI), встроенных в Microsoft Intune (теперь доступны для общего просмотра), управление Surface UEFI расширяет современный стек управления до уровня оборудования UEFI.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="9bcb7-116">DFCI поддерживает установку без касания, устраняет пароли BIOS, обеспечивает контроль параметров безопасности, включая параметры загрузки и встроенные периферийные устройства, и закладывая основу для расширенных сценариев безопасности в будущем.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="9bcb7-117">В настоящее время DFCI доступен для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 и Surface Pro X.  Дополнительные сведения см. в руководстве [Intune параметров Surface UEFI.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="9bcb7-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="open-surface-uefi-menu"></a><span data-ttu-id="9bcb7-118">Меню Open Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="9bcb7-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="9bcb7-119">Чтобы настроить параметры UEFI во время запуска системы:</span><span class="sxs-lookup"><span data-stu-id="9bcb7-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="9bcb7-120">Выключите Surface и подождите около 10 секунд, чтобы убедиться, что она отключена.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="9bcb7-121">Нажмите и удерживайте кнопку **Volume-up** и одновременно нажмите кнопку Power и **отпустите ее.**</span><span class="sxs-lookup"><span data-stu-id="9bcb7-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="9bcb7-122">По мере того как логотип Microsoft или Surface появится на экране, продолжайте удерживать кнопку **тома** до тех пор, пока не появится экран UEFI.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <a name="uefi-pc-information-page"></a><span data-ttu-id="9bcb7-123">Страница сведений о ПК UEFI</span><span class="sxs-lookup"><span data-stu-id="9bcb7-123">UEFI PC information page</span></span>

<span data-ttu-id="9bcb7-124">На странице сведений о ПК содержатся подробные сведения о устройстве Surface:</span><span class="sxs-lookup"><span data-stu-id="9bcb7-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="9bcb7-125">**Модель** — модель устройства Surface будет отображаться здесь, например Surface Book 2 или Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="9bcb7-126">Точная конфигурация устройства (например, процессор, размер диска или объем памяти) не отображается.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="9bcb7-127">**UUID**: уникальный идентификатор устройства, который используется для идентификации устройства во время разработки и управления.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="9bcb7-128">**Serial Number**: этот номер используется для идентификации устройства Surface во время инвентаризации и поддержки.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="9bcb7-129">**Asset Tag**: тег актива назначается устройству Surface с помощью [средства Asset Tag](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="9bcb7-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="9bcb7-130">Кроме того, в этом разделе вы найдете подробные сведения о встроенном ПО устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="9bcb7-131">Устройства Surface включают несколько внутренних компонентов, работающих под управлением разных версий встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="9bcb7-132">Версия встроенного ПО каждого из перечисленных ниже устройств отображается на странице **PC information** (как показано на рис. 1):</span><span class="sxs-lookup"><span data-stu-id="9bcb7-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="9bcb7-133">UEFI системы;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-133">System UEFI</span></span> 

- <span data-ttu-id="9bcb7-134">контроллер SAM;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-134">SAM Controller</span></span> 

- <span data-ttu-id="9bcb7-135">модуль управления Intel;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-135">Intel Management Engine</span></span> 

- <span data-ttu-id="9bcb7-136">встроенный контроллер системы;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-136">System Embedded Controller</span></span> 

- <span data-ttu-id="9bcb7-137">встроенное ПО сенсорного управления.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-137">Touch Firmware</span></span> 

![Сведения о системе и версии встроенного ПО](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="9bcb7-139">Рис. 1.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-139">Figure 1.</span></span> <span data-ttu-id="9bcb7-140">Сведения о системе и версии встроенного ПО</span><span class="sxs-lookup"><span data-stu-id="9bcb7-140">System information and firmware version information</span></span>*

<span data-ttu-id="9bcb7-141">Вы можете найти актуальные сведения о последней версии встроенного ПО для вашего устройства Surface в [журнале обновлений Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) для этого устройства.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <a name="uefi-security-page"></a><span data-ttu-id="9bcb7-142">Страница безопасности UEFI</span><span class="sxs-lookup"><span data-stu-id="9bcb7-142">UEFI Security page</span></span> 

![Настройка параметров безопасности UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="9bcb7-144">Рисунок 2.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-144">Figure 2.</span></span> <span data-ttu-id="9bcb7-145">Настройка параметров безопасности UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="9bcb7-146">Страница Безопасности позволяет установить пароль для защиты параметров UEFI.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="9bcb7-147">Этот пароль необходимо ввести при загрузке устройства Surface в режиме UEFI.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="9bcb7-148">Пароль может содержать следующие символы (как показано на рисунке 3):</span><span class="sxs-lookup"><span data-stu-id="9bcb7-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="9bcb7-149">Прописные буквы: A–Z</span><span class="sxs-lookup"><span data-stu-id="9bcb7-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="9bcb7-150">Строчные буквы: a–z</span><span class="sxs-lookup"><span data-stu-id="9bcb7-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="9bcb7-151">Цифры: 1–10</span><span class="sxs-lookup"><span data-stu-id="9bcb7-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="9bcb7-152">Специальные символы: !@#$%^&\*()?<>{} []-_=+|.;:'"</span><span class="sxs-lookup"><span data-stu-id="9bcb7-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="9bcb7-153">Пароль должен состоять по крайней мере из 6 символов и вводится с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Добавление пароля для защиты параметров UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="9bcb7-155">Рисунок 3.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-155">Figure 3.</span></span> <span data-ttu-id="9bcb7-156">Добавление пароля для защиты параметров UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="9bcb7-157">На странице Security также можно изменить конфигурацию безопасной загрузки устройства Surface.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="9bcb7-158">Технология безопасной загрузки предотвращает загрузку несанкционированного кода на устройстве Surface, обеспечивая защиту от заражений буткитами и руткитами.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="9bcb7-159">Вы можете отключить безопасную загрузку, чтобы на устройстве Surface можно было загружать сторонние операционные системы и загрузочные носители.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="9bcb7-160">Можно также настроить secure Boot для работы с сторонними сертификатами, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="9bcb7-161">Дополнительные сведения о [безопасной загрузке](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) см. в библиотеке TechNet.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Настройка безопасной загрузки](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="9bcb7-163">Рисунок 4.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-163">Figure 4.</span></span> <span data-ttu-id="9bcb7-164">Настройка безопасной загрузки</span><span class="sxs-lookup"><span data-stu-id="9bcb7-164">Configure Secure Boot</span></span>*

<span data-ttu-id="9bcb7-165">В зависимости от устройства вы также можете узнать, включена или отключена TPM.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="9bcb7-166">Если вы не видите параметр **Включить TPM,** откройте tpm.msc в Windows, чтобы проверить состояние, как показано на рисунке 5.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="9bcb7-167">TPM используется для проверки подлинности при шифровании данных устройства с помощью BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="9bcb7-168">Дополнительные сведения см. [в BitLocker обзоре.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)</span><span class="sxs-lookup"><span data-stu-id="9bcb7-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Консоль TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="9bcb7-170">Рисунок 5.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-170">Figure 5.</span></span> <span data-ttu-id="9bcb7-171">Консоль TPM</span><span class="sxs-lookup"><span data-stu-id="9bcb7-171">TPM console</span></span>*


## <a name="uefi-menu-devices"></a><span data-ttu-id="9bcb7-172">Меню UEFI: Устройства</span><span class="sxs-lookup"><span data-stu-id="9bcb7-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="9bcb7-173">Страница Devices позволяет включить или отключить определенные устройства и компоненты, включая:</span><span class="sxs-lookup"><span data-stu-id="9bcb7-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="9bcb7-174">порты док-станций и USB;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="9bcb7-175">разъем для карты MicroSD или SD;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="9bcb7-176">задняя камера;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-176">Rear Camera</span></span> 

- <span data-ttu-id="9bcb7-177">лицевая камера;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-177">Front Camera</span></span> 

- <span data-ttu-id="9bcb7-178">инфракрасная камера;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="9bcb7-179">Wi-Fi и Bluetooth;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="9bcb7-180">встроенная аудиосистема (динамики и микрофон).</span><span class="sxs-lookup"><span data-stu-id="9bcb7-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="9bcb7-181">Каждое устройство перечислены с помощью кнопки ползунок, которую можно переместить в положение **Включено** (включено) или Отключено \*\*\*\* (отключено), как показано на рисунке 6.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Включение и отключение устройств](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="9bcb7-183">Рисунок 6.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-183">Figure 6.</span></span> <span data-ttu-id="9bcb7-184">Включение и отключение устройств</span><span class="sxs-lookup"><span data-stu-id="9bcb7-184">Enable and disable specific devices</span></span>*

## <a name="uefi-menu-boot-configuration"></a><span data-ttu-id="9bcb7-185">Меню UEFI: конфигурация загрузки</span><span class="sxs-lookup"><span data-stu-id="9bcb7-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="9bcb7-186">Страница Конфигурация загрузки позволяет изменить порядок загрузки устройств, а также включить или отключить загрузку следующих устройств:</span><span class="sxs-lookup"><span data-stu-id="9bcb7-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="9bcb7-187">диспетчер загрузки Windows;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="9bcb7-188">USB-накопитель;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-188">USB Storage</span></span> 

- <span data-ttu-id="9bcb7-189">сеть PXE;</span><span class="sxs-lookup"><span data-stu-id="9bcb7-189">PXE Network</span></span> 

- <span data-ttu-id="9bcb7-190">внутренняя память.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-190">Internal Storage</span></span> 

<span data-ttu-id="9bcb7-191">Вы можете мгновенно загрузить систему с определенного устройства или провести пальцем влево по этому устройству в списке.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="9bcb7-192">Вы также можете мгновенно загрузить систему на USB-устройство или USB-адаптер для Ethernet, когда устройство Surface отключено, одновременно нажав кнопки **уменьшения громкости** и **включения**.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="9bcb7-193">Чтобы указанный порядок загрузки вступил в силу, необходимо установить параметр **Включить** альтернативную последовательность загрузки **для On,** как показано на рисунке 7.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Настройка порядка загрузки для устройства Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="9bcb7-195">Рисунок 7.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-195">Figure 7.</span></span> <span data-ttu-id="9bcb7-196">Настройка порядка загрузки для устройства Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="9bcb7-197">Вы также можете включать и отключать поддержку IPv6 для PXE с помощью параметра **Enable IPv6 for PXE Network Boot**, например во время развертывания Windows с помощью PXE, если сервер PXE настроен только для IPv4.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <a name="uefi-menu-management"></a><span data-ttu-id="9bcb7-198">Меню UEFI: управление</span><span class="sxs-lookup"><span data-stu-id="9bcb7-198">UEFI menu: Management</span></span>
<span data-ttu-id="9bcb7-199">Страница Управление позволяет управлять использованием управления Zero Touch UEFI и другими функциями на соответствующих устройствах, включая Surface Pro 7, Surface Pro X и Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="9bcb7-200">Управление доступом к управлению UEFI Zero Touch и другими ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *функциями рис. 8. Управление доступом к управлению UEFI Zero Touch и другими функциями*</span><span class="sxs-lookup"><span data-stu-id="9bcb7-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="9bcb7-201">Zero Touch UEFI Management позволяет удаленно управлять настройками UEFI с помощью профиля устройства в Intune под названием Интерфейс конфигурации микропрограммных устройств (DFCI).</span><span class="sxs-lookup"><span data-stu-id="9bcb7-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="9bcb7-202">Если этот параметр не настроен, возможность управления подходящими устройствами с \*\*\*\* помощью DFCI заданной.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="9bcb7-203">Чтобы предотвратить DFCI, выберите **opt-Out**.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="9bcb7-204">Страница ПАРАМЕТРОВ управления UEFI и использование DFCI в настоящее время доступны для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 и Surface Pro X. Дополнительные новости см. в [руководстве Intune параметров Surface UEFI.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="9bcb7-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="uefi-menu-exit"></a><span data-ttu-id="9bcb7-205">Меню UEFI: выход</span><span class="sxs-lookup"><span data-stu-id="9bcb7-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="9bcb7-206">Чтобы **выйти** из \*\*\*\* параметров UEFI, используйте кнопку Перезапустить теперь, как показано на рисунке 9.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Выход из меню UEFI Surface и перезагрузка устройства](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="9bcb7-208">Рисунок 9.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-208">Figure 9.</span></span> <span data-ttu-id="9bcb7-209">Нажмите "Restart Now", чтобы выйти из меню UEFI Surface и перезагрузить устройство</span><span class="sxs-lookup"><span data-stu-id="9bcb7-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <a name="surface-uefi-boot-screens"></a><span data-ttu-id="9bcb7-210">Экраны загрузки UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="9bcb7-211">При обновлении встроенного ПО устройства Surface с помощью центра обновления Windows или ручной установки обновления применяются к устройству не сразу, а во время следующего цикла перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="9bcb7-212">Дополнительные новости о процессе обновления прошивки Surface можно узнать в "Управление и развертывание обновлений [драйвера и прошивки Surface".](manage-surface-driver-and-firmware-updates.md)</span><span class="sxs-lookup"><span data-stu-id="9bcb7-212">You can find out more about the Surface firmware update process in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="9bcb7-213">Выполнение обновления встроенного ПО отображается на экране с помощью индикаторов разных цветов, соответствующих встроенному ПО каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="9bcb7-214">Планка прогресса каждого компонента показана в рисунках 9-18.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Обновление встроенного ПО UEFI Surface с синим индикатором выполнения](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="9bcb7-216">Рисунок 10.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-216">Figure 10.</span></span> <span data-ttu-id="9bcb7-217">Обновление встроенного ПО UEFI Surface с синим индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="9bcb7-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Встроенное ПО встроенного контроллера системы с зеленым индикатором выполнения](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="9bcb7-219">Рисунок 11.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-219">Figure 11.</span></span> <span data-ttu-id="9bcb7-220">Обновление встроенного ПО встроенного контроллера системы с зеленым индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="9bcb7-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="9bcb7-222">Рисунок 12.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-222">Figure 12.</span></span> <span data-ttu-id="9bcb7-223">Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="9bcb7-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Встроенное ПО Intel Management Engine с красным индикатором выполнения](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="9bcb7-225">Рисунок 13.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-225">Figure 13.</span></span> <span data-ttu-id="9bcb7-226">Обновление встроенного ПО Intel Management Engine с красным индикатором выполнения</span><span class="sxs-lookup"><span data-stu-id="9bcb7-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Встроенное ПО сенсорных элементов Surface с серым индикатором выполнения](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="9bcb7-228">Рисунок 14.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-228">Figure 14.</span></span> <span data-ttu-id="9bcb7-229">При обновлении встроенного ПО сенсорных элементов Surface отображается серый индикатор выполнения</span><span class="sxs-lookup"><span data-stu-id="9bcb7-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Прошивка Surface KIP с светло-зеленой планкой прогресса](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="9bcb7-231">Рис. 15.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-231">Figure 15.</span></span> <span data-ttu-id="9bcb7-232">Обновление прошивки Surface KIP отображает светло-зеленую планку прогресса</span><span class="sxs-lookup"><span data-stu-id="9bcb7-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Прошивка Surface ISH с розовой планки прогресса](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="9bcb7-234">Рис. 16 Обновление прошивки Surface ISH отображает светло-розовую планку прогресса</span><span class="sxs-lookup"><span data-stu-id="9bcb7-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Прошивка Surface Trackpad с серой панелью прогресса](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="9bcb7-236">Рис. 17.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-236">Figure 17.</span></span> <span data-ttu-id="9bcb7-237">Обновление прошивки Surface Trackpad отображает розовую планку прогресса</span><span class="sxs-lookup"><span data-stu-id="9bcb7-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Прошивка Surface TCON с светло-серой панели прогресса](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="9bcb7-239">Рисунок 18.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-239">Figure 18.</span></span> <span data-ttu-id="9bcb7-240">Обновление прошивки Surface TCON отображает светло-серую планку прогресса</span><span class="sxs-lookup"><span data-stu-id="9bcb7-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Прошивка Surface TPM с светло-фиолетовой панели прогресса](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="9bcb7-242">Рисунок 19.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-242">Figure 19.</span></span> <span data-ttu-id="9bcb7-243">Обновление прошивки Surface TPM отображает фиолетовую планку прогресса</span><span class="sxs-lookup"><span data-stu-id="9bcb7-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="9bcb7-244">Отображается дополнительное предупреждение, которое указывает на отключение безопасной загрузки, как показано на рисунке 19.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Экран загрузки Surface, указывающий, что безопасная загрузка отключена](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="9bcb7-246">Рисунок 20.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-246">Figure 20.</span></span> <span data-ttu-id="9bcb7-247">Экран загрузки Surface, указывающий, что безопасная загрузка отключена в параметрах UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="9bcb7-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <a name="references"></a><span data-ttu-id="9bcb7-248">Ссылки</span><span class="sxs-lookup"><span data-stu-id="9bcb7-248">References</span></span>

1. <span data-ttu-id="9bcb7-249">Surface Go и Surface Go 2 используют сторонний UEFI и не поддерживают DFCI.</span><span class="sxs-lookup"><span data-stu-id="9bcb7-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="9bcb7-250">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9bcb7-250">Related topics</span></span>

- [<span data-ttu-id="9bcb7-251">Управление параметрами UEFI Surface в Intune</span><span class="sxs-lookup"><span data-stu-id="9bcb7-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="9bcb7-252">Surface Enterprise Management Mode</span><span class="sxs-lookup"><span data-stu-id="9bcb7-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
