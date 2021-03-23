---
title: Пробуждение по локальной сети для устройств Surface
description: Узнайте, как можно использовать wake On LAN для удаленного пробуждения устройств для автоматического выполнения задач управления.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 9c3302616de97cf60b7d750948fed653456a7cba
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442893"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="d90c1-104">Пробуждение по локальной сети для устройств Surface</span><span class="sxs-lookup"><span data-stu-id="d90c1-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d90c1-105">Устройства Surface, которые используют адаптер Surface Ethernet для подключения к проводной сети, могут использовать wake On LAN (WOL) из подключенного ожидания.</span><span class="sxs-lookup"><span data-stu-id="d90c1-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d90c1-106">С помощью WOL можно удаленно разбудить устройства и автоматически выполнять задачи управления с помощью решений управления, таких как Microsoft Endpoint Manager/Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d90c1-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="d90c1-107">Устройства, поддерживаемые WOL</span><span class="sxs-lookup"><span data-stu-id="d90c1-107">WOL-supported devices</span></span>

- <span data-ttu-id="d90c1-108">Адаптер Surface Ethernet</span><span class="sxs-lookup"><span data-stu-id="d90c1-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="d90c1-109">Surface USB-C для Ethernet и USB-адаптер</span><span class="sxs-lookup"><span data-stu-id="d90c1-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="d90c1-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="d90c1-110">Surface Dock 2</span></span>
- <span data-ttu-id="d90c1-111">Surface Pro 6 и более поздние</span><span class="sxs-lookup"><span data-stu-id="d90c1-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="d90c1-112">Surface Book (все поколения)</span><span class="sxs-lookup"><span data-stu-id="d90c1-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="d90c1-113">Surface Laptop (все поколения)</span><span class="sxs-lookup"><span data-stu-id="d90c1-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="d90c1-114">Surface Go (все поколения)</span><span class="sxs-lookup"><span data-stu-id="d90c1-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="d90c1-115">Surface Studio 2 (см. приложение)</span><span class="sxs-lookup"><span data-stu-id="d90c1-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="d90c1-116">Использование WOL Surface</span><span class="sxs-lookup"><span data-stu-id="d90c1-116">Using Surface WOL</span></span>

<span data-ttu-id="d90c1-117">ИТ-администраторы могут запускать устройства с помощью запроса на локальной сети (волшебный пакет), который содержит MAC-адрес компьютера целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="d90c1-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="d90c1-118">Чтобы отправить волшебный пакет и разбудить устройство с помощью WOL, необходимо знать MAC-адрес целевого устройства и адаптер Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d90c1-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d90c1-119">Так как волшебный пакет не использует протокол IP-сети, невозможно использовать IP-адрес или имя DNS устройства.</span><span class="sxs-lookup"><span data-stu-id="d90c1-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d90c1-120">Многие решения управления, такие как Microsoft Endpoint Configuration Manager и сторонние приложения Microsoft Store, предоставляют встроенную поддержку WOL.</span><span class="sxs-lookup"><span data-stu-id="d90c1-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="d90c1-121">Обратите внимание, что устройства должны быть в режиме подключенного режима ожидания (sleep) и подключаться к власти переменного тока.</span><span class="sxs-lookup"><span data-stu-id="d90c1-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="d90c1-122">Дополнительные информацию о бодрствования устройствах с помощью диспетчера конфигурации конечной точки см. в этой ссылке [Configure Wake on LAN - Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="d90c1-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


### <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="d90c1-123">Проверка включения WOL на устройстве</span><span class="sxs-lookup"><span data-stu-id="d90c1-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="d90c1-124">На подключенной к Ethernet устройстве выберите сетевой адаптер и выберите **свойства.**</span><span class="sxs-lookup"><span data-stu-id="d90c1-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Адаптер Surface Ethernet](images/surface-ethernet.png)

2. <span data-ttu-id="d90c1-126">Выберите **Configure**  >  **Advanced**.</span><span class="sxs-lookup"><span data-stu-id="d90c1-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="d90c1-127">Прокрутите **в современный автономный пакет WoL Magic Packet** и убедитесь, что **включен.**</span><span class="sxs-lookup"><span data-stu-id="d90c1-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![Проверка включения WOL на устройстве](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="d90c1-129">Приложение: Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d90c1-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="d90c1-130">Чтобы включить WOL на Surface Studio 2, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="d90c1-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="d90c1-131">Создайте следующие клавиши реестра:</span><span class="sxs-lookup"><span data-stu-id="d90c1-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d90c1-132">Выполнить следующую команду</span><span class="sxs-lookup"><span data-stu-id="d90c1-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="d90c1-133">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d90c1-133">Learn more</span></span>

- [<span data-ttu-id="d90c1-134">Microsoft Surface USB-C для Ethernet и USB-адаптер</span><span class="sxs-lookup"><span data-stu-id="d90c1-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="d90c1-135">Адаптер Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="d90c1-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
