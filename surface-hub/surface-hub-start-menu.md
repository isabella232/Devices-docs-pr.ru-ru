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
# <a name="configure-surface-hub-start-menu"></a>Настройка меню "Пуск" Surface Hub

[Обновление Windows 10 от 17 января 2018 г.](https://support.microsoft.com/help/4057144) (сборка 15063.877) позволяет настраивать меню "Пуск" на устройствах Surface Hub. Вы применяете настраиваемый макет меню "Пуск" с помощью службы управления мобильными устройствами (MDM).

В этом случае пользователи не смогут закреплять приложения в меню "Пуск", а также откреплять или удалять их. 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>Применение настраиваемого меню "Пуск" для Surface Hub

Настраиваемое меню "Пуск" определяется в XML-файла макета меню "Пуск". Создать XML-файл макета меню "Пуск" можно двумя способами:

- изменить [XML-файл меню "Пуск" Surface Hub по умолчанию;](#default)

    -или-

- настроить требуемое меню "Пуск" на компьютере (закрепив только приложения, доступные на Surface Hub), а затем [экспортировать макет](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).

>[!TIP]
>Чтобы добавить плитку с веб-ссылкой на меню "Пуск" компьютера, перейдите по ссылке в Microsoft Edge, выберите `...` в верхнем правом углу и выберите **Закрепить эту страницу в меню "Пуск"**. Пример отображения ссылок в XML-файле см. в разделе [Макет начального экрана, содержащий ссылку Microsoft Edge](#edge).

Чтобы изменить XML-файл по умолчанию или экспортированный макет, изучите раздел [XML-файл макета меню "Пуск"](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop). Существует несколько [различий между макетом меню "Пуск" на настольном ПК и Surface Hub.](#differences)

После создания XML-файла макета меню "Пуск" [создайте политику MDM для применения макета.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Отличия между меню "Пуск" на устройстве Surface Hub и настольном компьютере

Существует несколько основных различий между меню "Пуск" для Surface Hub и компьютера Windows 10.

- Вы не можете использовать **DesktopApplicationTile** (в XML макета начните, так как Windows настольные приложения (Win32) не поддерживаются https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) Surface Hub.
- Нельзя использовать XML-файл макета меню "Пуск" для настройки панели задач или экрана приветствия для Surface Hub.  
- Политика макета "Начните" должна быть назначена только устройствам, а не пользователям.
- Параметр OMA-URI, который используется в политике, `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- Surface Hub поддерживает не более 6столбцов (6плиток 1x1), однако вам **необходимо** определить `GroupCellWidth=8`столбцов, хотя Surface Hub будет отображать только плитки в столбцах 0–5, но не в столбцах 6 и 7.
- Surface Hub поддерживает максимум 6строк (6 плиток 1x1)
- `SecondaryTile`, который используется для ссылок, открывают ссылку в Microsoft Edge.


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>Пример: макет меню "Пуск" Surface Hub по умолчанию

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

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>Пример: макет меню "Пуск", содержащий ссылку Microsoft Edge

В этом примере показана ссылка на веб-сайт и ссылка на PDF-файл. На вторичной плитке для Microsoft Edge используется значок 150 x 150 пикселей.

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
>Значение по умолчанию для светлое; вам не нужно включать в XML, если вы не меняете значение `ForegroundText` `ForegroundText` на темное.
