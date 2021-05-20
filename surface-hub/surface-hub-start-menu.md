---
title: Настройка меню "Пуск" Surface Hub
description: Используйте MDM для настройки меню "Пуск" устройства Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: cf9649b8d1f747722064793fbbde70116bc7f424
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576849"
---
# <a name="configure-surface-hub-start-menu"></a><span data-ttu-id="9f75f-103">Настройка меню "Пуск" Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9f75f-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="9f75f-104">[Обновление Windows 10 от 17 января 2018 г.](https://support.microsoft.com/help/4057144) (сборка 15063.877) позволяет настраивать меню "Пуск" на устройствах Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9f75f-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="9f75f-105">Вы применяете настраиваемый макет меню "Пуск" с помощью службы управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="9f75f-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="9f75f-106">В этом случае пользователи не смогут закреплять приложения в меню "Пуск", а также откреплять или удалять их.</span><span class="sxs-lookup"><span data-stu-id="9f75f-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a><span data-ttu-id="9f75f-107">Применение настраиваемого меню "Пуск" для Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9f75f-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="9f75f-108">Настраиваемое меню "Пуск" определяется в XML-файла макета меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="9f75f-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="9f75f-109">Создать XML-файл макета меню "Пуск" можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="9f75f-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="9f75f-110">изменить [XML-файл меню "Пуск" Surface Hub по умолчанию;](#default)</span><span class="sxs-lookup"><span data-stu-id="9f75f-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="9f75f-111">-или-</span><span class="sxs-lookup"><span data-stu-id="9f75f-111">-or-</span></span>

- <span data-ttu-id="9f75f-112">настроить требуемое меню "Пуск" на компьютере (закрепив только приложения, доступные на Surface Hub), а затем [экспортировать макет](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="9f75f-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="9f75f-113">Чтобы добавить плитку с веб-ссылкой на меню "Пуск" компьютера, перейдите по ссылке в Microsoft Edge, выберите `...` в верхнем правом углу и выберите **Закрепить эту страницу в меню "Пуск"**.</span><span class="sxs-lookup"><span data-stu-id="9f75f-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="9f75f-114">Пример отображения ссылок в XML-файле см. в разделе [Макет начального экрана, содержащий ссылку Microsoft Edge](#edge).</span><span class="sxs-lookup"><span data-stu-id="9f75f-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="9f75f-115">Чтобы изменить XML-файл по умолчанию или экспортированный макет, изучите раздел [XML-файл макета меню "Пуск"](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span><span class="sxs-lookup"><span data-stu-id="9f75f-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="9f75f-116">Существует несколько [различий между макетом меню "Пуск" на настольном ПК и Surface Hub.](#differences)</span><span class="sxs-lookup"><span data-stu-id="9f75f-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="9f75f-117">После создания XML-файла макета меню "Пуск" [создайте политику MDM для применения макета.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="9f75f-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a><span data-ttu-id="9f75f-118">Отличия между меню "Пуск" на устройстве Surface Hub и настольном компьютере</span><span class="sxs-lookup"><span data-stu-id="9f75f-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="9f75f-119">Существует несколько основных различий между меню "Пуск" для Surface Hub и компьютера Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9f75f-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="9f75f-120">Вы не можете использовать **DesktopApplicationTile** (в XML макета начните, так как Windows настольные приложения (Win32) не поддерживаются https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9f75f-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="9f75f-121">Нельзя использовать XML-файл макета меню "Пуск" для настройки панели задач или экрана приветствия для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9f75f-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="9f75f-122">Политика макета "Начните" должна быть назначена только устройствам, а не пользователям.</span><span class="sxs-lookup"><span data-stu-id="9f75f-122">The Start layout policy should be assigned only to devices, not users.</span></span>
- <span data-ttu-id="9f75f-123">Параметр OMA-URI, который используется в политике,</span><span class="sxs-lookup"><span data-stu-id="9f75f-123">The OMA-URI setting to use in the policy is</span></span> `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- <span data-ttu-id="9f75f-124">Surface Hub поддерживает не более 6столбцов (6плиток 1x1), однако вам **необходимо** определить `GroupCellWidth=8`столбцов, хотя Surface Hub будет отображать только плитки в столбцах 0–5, но не в столбцах 6 и 7.</span><span class="sxs-lookup"><span data-stu-id="9f75f-124">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="9f75f-125">Surface Hub поддерживает максимум 6строк (6 плиток 1x1)</span><span class="sxs-lookup"><span data-stu-id="9f75f-125">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="9f75f-126">, который используется для ссылок, открывают ссылку в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9f75f-126">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a><span data-ttu-id="9f75f-127">Пример: макет меню "Пуск" Surface Hub по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9f75f-127">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a><span data-ttu-id="9f75f-128">Пример: макет меню "Пуск", содержащий ссылку Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9f75f-128">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="9f75f-129">В этом примере показана ссылка на веб-сайт и ссылка на PDF-файл.</span><span class="sxs-lookup"><span data-stu-id="9f75f-129">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="9f75f-130">На вторичной плитке для Microsoft Edge используется значок 150 x 150 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9f75f-130">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="9f75f-131">Значение по умолчанию для светлое; вам не нужно включать в XML, если вы не меняете значение `ForegroundText` `ForegroundText` на темное.</span><span class="sxs-lookup"><span data-stu-id="9f75f-131">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
