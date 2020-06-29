---
title: Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети
description: Политики MDM для проверки подлинности по стандарту безопасности 802.1X в проводной сети были включены на устройствах Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836251"
---
# <span data-ttu-id="9bf37-103">Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети</span><span class="sxs-lookup"><span data-stu-id="9bf37-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="9bf37-104">[Обновление для Windows 10 от 14 ноября 2017 года](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (сборка 15063.726) позволяет использовать политики MDM для проверки подлинности по стандарту безопасности 802.1X в проводной сети на устройствах Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9bf37-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="9bf37-105">Этот компонент позволяет организациям усилить стандартизированную проверку подлинности по проводной сети с помощью [протокола проверки подлинности IEEE 802.1 x](http://www.ieee802.org/1/pages/802.1x-2010.html).</span><span class="sxs-lookup"><span data-stu-id="9bf37-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="9bf37-106">Эта возможность уже доступна для выполнения проверки подлинности по беспроводной сети с помощью профилей беспроводной сети через систему MDM.</span><span class="sxs-lookup"><span data-stu-id="9bf37-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="9bf37-107">В этом разделе описывается настроить Surface Hub для использования с проверкой подлинности по проводной сети.</span><span class="sxs-lookup"><span data-stu-id="9bf37-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="9bf37-108">Применение и включение проводной проверки подлинности по стандарту безопасности 802.1x в Surface Hub можно выполнить с помощью [определения OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) системы MDM.</span><span class="sxs-lookup"><span data-stu-id="9bf37-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="9bf37-109">Основной конфигурацией, которую следует задать, является политика **LanProfile**.</span><span class="sxs-lookup"><span data-stu-id="9bf37-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="9bf37-110">В зависимости от выбранного способа проверки подлинности могут потребоваться другие политики: политика **EapUserData** или политики MDM для добавления сертификатов компьютеров или пользователей (например, [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) для сертификатов пользователей/устройств или [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) для сертификатов устройств).</span><span class="sxs-lookup"><span data-stu-id="9bf37-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="9bf37-111">Элемент политики LanProfile</span><span class="sxs-lookup"><span data-stu-id="9bf37-111">LanProfile policy element</span></span>

<span data-ttu-id="9bf37-112">Чтобы настроить Surface Hub для использования одного из поддерживаемых способов проверки подлинности по стандарту безопасности 802.1x, используйте следующий OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="9bf37-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="9bf37-113">Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="9bf37-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="9bf37-114">XML-файл, предоставляемый в качестве параметра, должен соответствовать [схеме профиля проводной сети LAN](https://msdn.microsoft.com/library/cc233002.aspx), включая элементы из [схемы 802.1X](https://msdn.microsoft.com/library/cc233003.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bf37-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="9bf37-115">В большинстве случаев администратор или пользователь может экспортировать XML-файл элемента LanProfile из имеющегося компьютера, который уже настроен в сети для стандарта безопасности 802.1X с помощью следующей команды NETSH.</span><span class="sxs-lookup"><span data-stu-id="9bf37-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="9bf37-116">Выполнение этой команды предоставит следующие выходные данные и разместит файл с именем **Ethernet.xml** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9bf37-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="9bf37-117">Элемент политики EapUserData</span><span class="sxs-lookup"><span data-stu-id="9bf37-117">EapUserData policy element</span></span>

<span data-ttu-id="9bf37-118">Если для выбранного способа проверки подлинности необходимо использовать имя пользователя и пароль вместо сертификата, можно использовать элемент **EapUserData**, чтобы задать учетные данные, которые устройство будет применять для выполнения проверки подлинности в сети.</span><span class="sxs-lookup"><span data-stu-id="9bf37-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="9bf37-119">Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="9bf37-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="9bf37-120">XML-файл, предоставляемый в качестве параметра, должен соответствовать [примеру свойств пользователя MS-CHAPv2 PEAP](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span><span class="sxs-lookup"><span data-stu-id="9bf37-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="9bf37-121">В этом примере необходимо заменить все экземпляры *test* и *ias-domain* вашими данными.</span><span class="sxs-lookup"><span data-stu-id="9bf37-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="9bf37-122">Добавление сертификатов</span><span class="sxs-lookup"><span data-stu-id="9bf37-122">Adding certificates</span></span>

<span data-ttu-id="9bf37-123">Если вы выбрали метод проверки подлинности на основе сертификата, вам потребуется [создать пакет подготовки](provisioning-packages-for-surface-hub.md), [использовать MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)или импортировать сертификат из параметров (обновление**параметров**  >  **и**  >  **Сертификаты**безопасности), чтобы развернуть эти сертификаты на устройстве Surface Hub в соответствующем хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9bf37-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="9bf37-124">При добавлении сертификатов каждый PFX-файл должен содержать только один сертификат (PFX-файл не может иметь несколько сертификатов).</span><span class="sxs-lookup"><span data-stu-id="9bf37-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

