---
title: Как включить клавиатуру Surface Laptop во время развертывания MDT
description: При использовании MDT для развертывания Windows 10 на ноутбуках Surface необходимо импортировать драйверы клавиатуры для использования в среде Windows PE.
keywords: поверхность Windows 10, автоматизация, настройка, mdt
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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312065"
---
# Как включить клавиатуру Surface Laptop во время развертывания MDT

В этой статье посвящен подход к развертыванию, использующий Microsoft Deployment набор средств (MDT). Эти сведения также можно применить к другим методикам развертывания. На большинстве типов устройств Surface клавиатура должна работать во время установки Lite Touch (LTI). Тем не менее, surface Laptop требует некоторых дополнительных драйверов, чтобы включить клавиатуру. Для устройств Surface Laptop (1-е поколения) и Surface Laptop 2 необходимо подготовить структуру папок и профили выбора, позволяющие указать драйверы клавиатуры для использования на этапе среды предустановки Windows (Windows PE) LTI. Дополнительные сведения об этой структуре папок см. в подстроке "Развертывание образа Windows 10 с помощью [MDT: шаг 5. Подготовка](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)репозитория драйверов".

> [!TIP]    
> При использовании драйверов клавиатуры для Surface Laptop 2 и Surface Laptop 3 в одном экземпляре загрузки Windows PE может потребоваться вручную сбросить микропрограммы, если клавиатура или сенсорная панель не работают в Windows PE:
>
> - Нажмите и удерживайте кнопку питания в течение 30 секунд. Если вы подключены к блоку питания (PSU), нажимайте и удерживайте кнопку питания, пока не увидите свет в конце кнопки PSU, прежде чем снова включите ее.

> [!IMPORTANT]
> Если вы развертываете образ Windows 10 на ноутбуке Surface с предустановленным режимом Windows 10 в S-режиме, см. KB [4032347.](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Проблемы при развертывании Windows на устройства Surface с предустановленной Windows 10 в S-режиме.

Чтобы добавить драйверы клавиатуры в профиль выбора, выполните следующие действия:

1. Скачайте последний MSI-файл Surface Laptop из соответствующих мест:
    - [Драйверы и микропрограммы ноутбука Surface (1-е поколения)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Драйверы и микропрограммы Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 с процессорными драйверами и микропрограммами Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Извлеките содержимое MSI-файла Surface Laptop в папку, которую можно легко найти (например, c:\surface_laptop_drivers). Чтобы извлечь содержимое, откройте окно командной подсказки с повышенными повышенными уровнями и запустите команду из следующего примера:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Откройте Deployment Workbench и разкройте узел **"Папки** развертывания" и обную папку развертывания, а затем перейдите в папку **WindowsPEX64.**

   ![Изображение расположения папки WindowsPEX64 в Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Щелкните правой кнопкой **мыши папку WindowsPEX64** и выберите **"Импорт драйверов".**

5. Следуйте инструкциям мастера импорта драйверов, чтобы импортировать папки драйверов в папку WindowsPEX64.  

    > [!NOTE]
    >  Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен. 

    Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Чтобы поддерживать Surface Laptop 2, импортировать следующие папки:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\serialioi2c
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

     
    Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    Импорт следующих папок позволит использовать полную клавиатуру, trackpad и сенсорные функции в PE для Surface Laptop 3.

    - SerialIOGPIO
    - SerialIOI2C
    - SerialIOSPI
    - SerialIOUART
    - itouch
    - Микросхем
    - ChipsetLPSS
    - ChipsetNorthpeak
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
     >  Проверьте загруженный пакет MSI, чтобы определить формат и структуру каталогов.  Структура каталогов будет начинаться с SurfacePlatformInstaller (старые MSI-файлы) или SurfaceUpdate (новые MSI-файлы) в зависимости от того, когда MSI был выпущен. 

     Чтобы поддерживать ноутбук Surface (1-е поколения), импортировать следующие папки:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Чтобы поддерживать Surface Laptop 2, импортировать следующие папки:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\I2C
    - SurfacePlatformInstaller\Drivers\System\SPI
    - SurfacePlatformInstaller\Drivers\System\UART
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Или для более новых MSI-файлов, начиная с SurfaceUpdate, используйте:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Чтобы поддерживать Surface Laptop 3 с процессором Intel, импортировать следующие папки:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3. Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

6. Убедитесь, что папка WindowsPEX64 теперь содержит импортируемые драйверы. Папка должна быть похожа на следующую:  

   ![Изображение новых импортируемых драйверов в папке WindowsPEX64 deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Настройте профиль выбора, использующий папку WindowsPEX64. Профиль выбора должен иметь следующий сходство:  

   ![Изображение папки WindowsPEX64, выбранной в составе профиля выбора](./images/surface-laptop-keyboard-3.png)

8. Настройте свойства Windows PE для share развертывания MDT, чтобы использовать новый профиль выбора следующим образом:  

   - Для **платформы**выберите **x64**.
   - Для **профиля Selection**выберите новый профиль.
   - Выберите **"Включить все драйверы" из профиля выбора.**
   
   ![Изображение свойств Windows PE из обоймы развертывания MDT](./images/surface-laptop-keyboard-4.png)

9. Убедитесь, что вы настроили оставшиеся драйверы Surface Laptop с помощью профиля выбора или переменной **DriverGroup001.**  
   - Для ноутбуков Surface (1-е поколения) модель **— Surface Laptop.** Оставшиеся драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, как показано на рисунке, который следует за этим списком.
   - Для Surface Laptop 2 **моделью является Surface Laptop 2.** Оставшиеся драйверы Surface Laptop должны находиться в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2. 
   - Для Surface Laptop 3 с процессором Intel моделью является Surface Laptop 3. Остальные драйверы Surface Laptop расположены в папке \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

   ![Изображение обычных драйверов Surface Laptop (1-го поколения) в папке Surface Laptop deployment Workbench](./images/surface-laptop-keyboard-5.png)

Настроив обную долю развертывания MDT для использования нового профиля выбора и связанных параметров, продолжите процесс развертывания, как описано в описании развертывания образа Windows 10 с помощью [MDT: шаг 6. Создание](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)последовательности задач развертывания.
