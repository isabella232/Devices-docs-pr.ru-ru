---
title: Включение клавиатуры Surface ноутбука в развертывание MDT
description: При использовании MDT для развертывания Windows 10 на компьютерах с контактными портативными компьютерами необходимо импортировать драйверы клавиатуры для использования в среде Windows PE.
keywords: поверхность Windows 10, Автоматизация, Настройка, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834715"
---
# Включение клавиатуры Surface ноутбука в развертывание MDT

В этой статье рассматривается подход к развертыванию, в котором используется Microsoft Deployment Toolkit (MDT). Эти сведения также можно применить к другим методологиям развертывания. На большинстве типов устройств Surface клавиатура должна работать во время установки с помощью облегченного сенсорного ввода (LTI). Тем не менее, для портативного компьютера Surface требуется наличие некоторых дополнительных драйверов для использования клавиатуры. Для устройств Surface (1-го и Surface) необходимо подготовить структуру папок и профили выбора, позволяющие указывать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI. Дополнительные сведения об этой структуре папок можно найти в [статье Развертывание образа Windows 10 с помощью MDT: шаг 5: подготовка репозитория драйверов](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!NOTE]
> В настоящее время вы не можете добавить драйверы клавиатуры для ноутбука Surface 2 и Surface 3 в одном экземпляре загрузки Windows PE из-за конфликта драйверов. Вместо этого используйте отдельные экземпляры.

> [!IMPORTANT]
> При развертывании образа Windows 10 на ноутбуке Surface с предварительно установленной операционной системой Windows 10 ознакомьтесь со статьей KB [4032347, возникающими при развертывании Windows на Surface Devices с предварительно установленной операционной системой Windows 10 в режиме s](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

Чтобы добавить драйверы клавиатуры в профиль выбора, выполните указанные ниже действия.

1. Скачайте MSI-файл для портативного компьютера Surface из соответствующих местоположений:
    - [Драйверы и встроенное по для ноутбука Surface (1-го поколения)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Драйверы и встроенное по для ноутбука Surface 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [ПК Surface 3 с драйверами и встроенным по для процессора Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Извлеките содержимое MSI-файла Surface, в папку, которую можно легко найти (например, c:\ surface_laptop_drivers). Чтобы извлечь содержимое, откройте окно командной строки с повышенными привилегиями и выполните команду из следующего примера:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Откройте средство развертывания и разверните узел **Общие ресурсы развертывания** и общий доступ к развертыванию, а затем перейдите в папку **WindowsPEX64** .

   ![Изображение, которое показывает расположение папки WindowsPEX64 в Workbench для развертывания](./images/surface-laptop-keyboard-1.png)

4. Щелкните правой кнопкой мыши папку **WindowsPEX64** и выберите команду **Импорт драйверов**.
5. Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки Drivers в папку WindowsPEX64.  

> [!NOTE]
>  Проверьте скачанный пакет MSI, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (устаревших MSI-файлов) или SurfaceUpdate (более поздних MSI-файлов) в зависимости от того, когда был освобожден пакет MSI. 

Чтобы обеспечить поддержку ноутбука Surface (1-го поколения), импортируйте следующие папки:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Для поддержки портативного компьютера Surface 2 импортируйте следующие папки:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Для поддержки портативного компьютера Surface 3 с помощью процессора Intel импортируйте следующие папки:

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

Импорт следующих папок включает функцию полной клавиатуры, сенсорной панели и сенсорного ввода в PE для ноутбука Surface 3.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  Проверьте скачанный пакет MSI, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (устаревших MSI-файлов) или SurfaceUpdate (более поздних MSI-файлов) в зависимости от того, когда был освобожден пакет MSI. 

    Чтобы обеспечить поддержку ноутбука Surface (1-го поколения), импортируйте следующие папки:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Для поддержки портативного компьютера Surface 2 импортируйте следующие папки:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Либо для более новых MSI-файлов, начинающихся с "SurfaceUpdate", используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Для поддержки портативного компьютера Surface 3 с помощью процессора Intel импортируйте следующие папки:

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Для портативного компьютера Surface 3 с процессором Intel модель — Surface ноутбука 3. Оставшиеся драйверы для портативного компьютера Surface находятся в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 3.

6. Убедитесь, что в папке WindowsPEX64 есть импортированные драйверы. Папка должна выглядеть следующим образом:  

   ![Изображение, в котором показаны только что импортированные драйверы в папке WindowsPEX64 в Workbench для развертывания.](./images/surface-laptop-keyboard-2.png)

7. Настройте профиль выделения, использующий папку WindowsPEX64. Профиль выделения должен выглядеть следующим образом:  

   ![Рисунок, на котором показана папка WindowsPEX64, выбранная в составе профиля выбора](./images/surface-laptop-keyboard-3.png)

8. Настройте свойства Windows PE для общего доступа к развертыванию MDT, чтобы использовать новый профиль выделения, как описано ниже.  

   - На вкладке **платформа**выберите **x64**.
   - Для **профиля выбора**выберите новый профиль.
   - Выберите **включить все драйверы из профиля выбора**.
   
   ![Изображение, показывающее свойства общего доступа развертывания MDT для Windows PE](./images/surface-laptop-keyboard-4.png)

9. Убедитесь, что вы настроили оставшиеся драйверы портативного компьютера Surface, используя либо профиль выделения, либо переменную **DriverGroup001** .  
   - Для Surface ноутбука (1-го поколения) модель — это **ноутбук Surface**. Оставшиеся драйверы для ноутбука на компьютере Surface должны находиться в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука, как показано на рисунке ниже.
   - Для ноутбука Surface 2 модель — **Surface ноутбука 2**. Оставшиеся драйверы для ноутбука на компьютере Surface должны находиться в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 2. 
   - Для портативного компьютера Surface 3 с процессором Intel модель — Surface ноутбука 3. Оставшиеся драйверы для портативного компьютера Surface находятся в папке \MDT развертывание Share\Out-of-Box Drivers\Windows10\X64\Surface ноутбука 3.

   ![Изображение стандартных драйверов ноутбука Surface (1-го поколения) в папке "ноутбук Surface" в Workbench для развертывания](./images/surface-laptop-keyboard-5.png)

После того как вы настраиваете общий доступ к развертыванию MDT для использования нового профиля выбора и связанных параметров, продолжайте процесс развертывания, как описано в разделе [развертывание образа Windows 10 с помощью MDT: Step 6: Создание последовательности задач развертывания](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).
