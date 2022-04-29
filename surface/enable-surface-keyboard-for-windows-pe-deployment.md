---
title: Включение клавиатуры Surface Laptop во время развертывания MDT
description: При использовании MDT для Windows 10 ноутбуков Surface необходимо импортировать драйверы клавиатуры для использования в среде Windows PE.
keywords: windows 10 surface, automate, customize, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497922"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Включение клавиатуры Surface Laptop во время развертывания MDT

В этой статье рассматривается подход к развертыванию, использующий microsoft Deployment набор средств (MDT). Эти сведения также можно применить к другим методологиям развертывания. На большинстве типов устройств Surface клавиатура должна работать во время установки Lite Touch (LTI). Однако Surface Laptop для включения клавиатуры требуются дополнительные драйверы. Для Surface Laptop (1-го поколения) и Surface Laptop 2 необходимо подготовить структуру папок и профили выбора, которые позволяют указать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI. Дополнительные сведения об этой структуре папок см. в статье ["Развертывание образа Windows 10 с помощью MDT: шаг 5.](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository) Подготовка репозитория драйверов".

> [!TIP]
> При использовании драйверов клавиатуры для Surface Laptop 2 и Surface Laptop 3 в одном и том же загрузчике Windows PE может потребоваться вручную сбросить встроенное ПО, если клавиатура или сенсорная панель не работают в Windows PE:
>
> - Нажмите и удерживайте кнопку питания в течение 30 секунд. Если вы подключены к блоку питания (PSU), нажимайте и удерживайте кнопку питания, пока не увидите свет в конце кабеля PSU, прежде чем снова включать его.

> [!IMPORTANT]
> Если вы развертываете образ Windows 10 в Surface Laptop с предустановленным Windows 10 в режиме S, см. раздел базы знаний 4032347. Проблемы при развертывании Windows на устройства Surface с предустановленными Windows 10 [в S-режиме](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Добавление драйверов клавиатуры в профиль выбора

1. Скачайте последнюю Surface Laptop .msi из соответствующих расположений:
    - [Surface Laptop (1-го поколения) Драйверы и встроенное ПО](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 драйверов и встроенного ПО](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 с драйверами процессора Intel и встроенным ПО](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 с драйверами процессора Intel и встроенным ПО](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 с драйверами процессора AMD и встроенным ПО](https://www.microsoft.com/download/102923)
    - [Surface Laptop Драйверы и встроенное ПО Студии](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 драйверов и встроенного ПО](https://www.microsoft.com/download/details.aspx?id=103503)

2. Извлеките содержимое файла Surface Laptop .msi в папку, которую можно легко найти (например, c:\surface_laptop_drivers). Чтобы извлечь содержимое, откройте окно командной строки с повышенными привилегиями и выполните команду из следующего примера:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Откройте Deployment Workbench и разверните узел **"Общие** папки развертывания" и общую папку развертывания, а затем перейдите в папку **WindowsPEX64** .
4. Щелкните правой кнопкой **мыши папку WindowsPEX64** и выберите " **Импорт драйверов"**.
5. Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки драйверов в папку WindowsPEX64.

 > [!NOTE]
 > Проверьте загруженный .msi, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (старые .msi-файлы) или SurfaceUpdate (более новые .msi-файлы) в зависимости от того, когда был выпущен .msi файла.

## <a name="import-drivers-for-surface-devices"></a>Импорт драйверов для устройств Surface

Импортируйте следующие папки в соответствии с Surface Laptop устройства.

| Устройство                                    | Импорт папок                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Дополнительные сведения                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Laptop Studio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealaalacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 с процессором Intel** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealaalacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 с процессором AMD**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealaalacpifilter<br>SurfaceUcmUcsiHidClient | Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 3 с процессором Intel** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | Импорт следующих папок обеспечивает полную функциональность клавиатуры, сенсорной панели и сенсорного ввода в pe:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>Itouch<br>Набор микросхем<br>Набор микросхем<br>МикросхемаNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Для новых .msi файлов, начиная с SurfaceUpdate, используйте:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (1-го поколения)**              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Для новых .msi файлов, начиная с **SurfaceUpdate**, используйте:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > Проверьте загруженный .msi, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (старые .msi-файлы) или SurfaceUpdate (более новые .msi-файлы) в зависимости от того, .msi был выпущен.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Проверка импортированных драйверов & настройки Windows PE

1. Убедитесь, что папка WindowsPEX64 теперь содержит импортированные драйверы, как показано на следующем рисунке:

   ![Изображение, на котором показаны недавно импортированные драйверы в папке WindowsPEX64 deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Настройте профиль выбора, использующий папку WindowsPEX64, как показано на следующем рисунке:

   ![Изображение, на котором показана папка WindowsPEX64, выбранная как часть профиля выбора.](./images/surface-laptop-keyboard-3.png)
1. Настройте Windows PE общей папки развертывания MDT, чтобы использовать новый профиль выбора следующим образом:
    - Для **платформы** выберите **x64**.
    - Для **профиля выбора** выберите новый профиль.
    - Выберите **"Включить все драйверы" в профиле выбора**.

    ![Изображение, на котором Windows pe свойств общей папки развертывания MDT.](./images/surface-laptop-keyboard-4.png)
4. Убедитесь, что вы настроили оставшиеся Surface Laptop с помощью профиля выбора или переменной **DriverGroup001**.
    - Для Surface Laptop (1-го поколения) **модель** Surface Laptop. Остальные драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, как показано на следующем рисунке.
    - Для Surface Laptop 2 модель Surface Laptop **2**. Остальные драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Для Surface Laptop 3 с процессором Intel модель Surface Laptop 3. Остальные драйверы Surface Laptop находятся в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Изображение, на котором показаны обычные драйверы Surface Laptop (1-го поколения) в Surface Laptop папке Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

Настроив общую папку развертывания MDT для использования нового профиля выбора и связанных параметров, продолжите процесс развертывания, как описано в разделе "Развертывание образа [Windows 10 с помощью MDT: шаг 6.](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence) Создание последовательности задач развертывания".
