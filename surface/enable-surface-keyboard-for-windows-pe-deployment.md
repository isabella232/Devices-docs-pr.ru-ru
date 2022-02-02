---
title: Как включить клавиатуру Surface Laptop во время развертывания MDT
description: При развертывании MDT Windows 10 на ноутбуки Surface необходимо импортировать драйверы клавиатуры для использования в Windows PE.
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
ms.openlocfilehash: b65fbcb0221fe923e1e2240b8da163d868b46122
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338272"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Как включить клавиатуру Surface Laptop во время развертывания MDT

В этой статье используется подход к развертыванию, использующий microsoft Deployment набор средств (MDT). Вы также можете применить эти сведения к другим методологиям развертывания. На большинстве типов устройств Surface клавиатура должна работать во время установки lite Touch (LTI). Однако для Surface Laptop требуются дополнительные драйверы, чтобы включить клавиатуру. Для Surface Laptop (1-го gen) и Surface Laptop 2 устройств необходимо подготовить структуру папок и профили выбора, которые позволяют указать драйверы клавиатуры для использования во время Windows предварительной среды (Windows PE) этапа LTI. Дополнительные сведения об этой структуре папок см. в Windows 10 с помощью [MDT: Шаг 5: Подготовка репозитория драйверов](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> При использовании драйверов клавиатуры для Surface Laptop 2 и Surface Laptop 3 в одном экземпляре загрузки Windows PE может потребоваться вручную сбросить прошивку, если клавиатура или сенсорная панель не работают в Windows PE:
>
> - Нажмите кнопку Power и удерживайте ее в течение 30 секунд. Если вы подключены к блоку питания (PSU), нажмите кнопку Power и удерживайте ее до тех пор, пока не увидите свет в конце шнура PSU, а затем отключите его.

> [!IMPORTANT]
> При развертывании Windows 10 изображения в Surface Laptop с предустановленным Windows 10 режимом S см. в 4032347 KB, проблемы при развертывании Windows на устройства Surface с предустановленными [Windows 10 в режиме S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Добавление драйверов клавиатуры в профиль выбора

1. Скачайте последний Surface Laptop .msi из соответствующих местоположений:
    - [Surface Laptop (1-й gen) Драйверы и прошивка](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 драйвера и микропрограммы](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 с драйверами процессоров Intel и программным обеспечением](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 с драйверами процессоров Intel и программным обеспечением](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 с драйверами процессора AMD и программным обеспечением](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 драйверов и прошивки](https://www.microsoft.com/download/details.aspx?id=103503)

2. Извлекать содержимое файла Surface Laptop .msi папку, которую можно легко найти (например, c:\surface_laptop_drivers). Чтобы извлечь содержимое, откройте окно командной подсказки и запустите команду из следующего примера:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Откройте рабочий узел развертывания и расширите узел **"Акции** развертывания" и свою долю развертывания, а затем перейдите в **папку WindowsPEX64** .
4. Щелкните правой кнопкой **мыши папку WindowsPEX64** и выберите **драйверы импорта**.
5. Следуйте инструкциям мастера драйвера импорта для импорта папок драйверов в папку WindowsPEX64.

 > [!NOTE]
 > Проверьте загруженный .msi, чтобы определить структуру формата и каталога.  Структура каталога будет начинаться с SurfacePlatformInstaller (старые .msi файлы) или SurfaceUpdate (более новые .msi файлы) в зависимости от .msi файла.

## <a name="import-drivers-for-surface-devices"></a>Импорт драйверов для устройств Surface

Импорт следующих папок в соответствии с Surface Laptop устройства.  

| Устройство                                | Папки импорта                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Дополнительные сведения                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Laptop Studio                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | Неприменимо |
| Surface Pro 8                         | heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollerhsacomponent<br> |Неприменимо |
| Surface Laptop 4 с процессором Intel | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 с процессором AMD   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |Неприменимо                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 с процессором Intel | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | Импорт следующих папок позволит использовать полную клавиатуру, трекпад и функции касания в PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>Чипсет<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Для новых .msi файлов, начиная с "SurfaceUpdate", используйте:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop (1-й gen)              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Для новых .msi файлов, начиная с "SurfaceUpdate", используйте:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > Проверьте загруженный .msi, чтобы определить структуру формата и каталога.  Структура каталога будет начинаться с SurfacePlatformInstaller (старые .msi файлы) или SurfaceUpdate (новые .msi файлы) в зависимости от того, когда .msi был выпущен.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Проверка импортируемых драйверов & настройки Windows свойств PE

1. Убедитесь, что папка WindowsPEX64 теперь содержит импортируемые драйверы, как показано на следующем рисунке:

   ![Изображение, на которое показаны недавно импортируемые драйверы в папке WindowsPEX64 workbench развертывания.](./images/surface-laptop-keyboard-2.png)
1. Настройте профиль выбора, использующий папку WindowsPEX64, как показано на следующем рисунке:

   ![Изображение, отображаее папку WindowsPEX64, выбранную в рамках профиля выбора.](./images/surface-laptop-keyboard-3.png)
1. Настройте Windows свойств PE для доли развертывания MDT, чтобы использовать новый профиль выбора следующим образом:
    - Для **платформы** выберите **x64**.
    - Для **профиля Selection** выберите новый профиль.
    - Выберите **Включить все драйверы из профиля выбора**.

    ![Изображение, отображаее Windows свойств PE в MDT Deployment Share.](./images/surface-laptop-keyboard-4.png)
4. Убедитесь, что вы настроили оставшиеся Surface Laptop драйверы с помощью профиля выбора или **переменной DriverGroup001**.
    - Для Surface Laptop (1-й gen) **модель Surface Laptop.** Остальные драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, как показано на следующем рисунке.
    - Для Surface Laptop 2 модель Surface Laptop **2**. Остальные драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Для Surface Laptop 3 с процессором Intel модель Surface Laptop 3. Остальные драйверы Surface Laptop находятся в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Изображение, отображаее Surface Laptop драйверов (1-го поколения) в Surface Laptop папке Workbench развертывания.](./images/surface-laptop-keyboard-5.png)

После настройки MDT Deployment Share для использования нового профиля выбора и связанных параметров продолжайте процесс развертывания, как описано в развертывании изображения Windows 10 с помощью [MDT: Шаг 6: Создание](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence) последовательности задач развертывания.
