---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator — это простое средство развертывания, с помощью которого организации могут быстро пересоздавать образы устройств Surface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: развертывание, установка, средство
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 0e136bd0a69db7a4c4e5cea7d2c065727dcc8fcc
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016446"
---
# Microsoft Surface Deployment Accelerator

Ускоритель развертывания Microsoft Surface (SDA) автоматизирует создание и настройку рекомендуемого опыта развертывания Майкрософт с помощью бесплатных средств развертывания Microsoft.

В апреле 2020 для упрощения и автоматизации развертывания изображений Surface в корпоративной среде средство SDA позволяет создавать "Заводский" образ Windows, который можно настроить для организационных требований.

Открытый источник, управляемый сценарием SDA использует комплект средств оценки и развертывания Windows (ADK) для Windows 10, который упрощает создание образов Windows (WIM) в тестовых и рабочих средах. Если последнее приложение ADK еще не установлено, оно будет загружено и установлено при запуске средства SDA.

Полученное изображение точно соответствует конфигурации изображений восстановления исходного состояния системы (BMR), без предустановленных приложений, таких как Microsoft Office или приложение UWP Surface.

## Требования

1. Съемный USB-диск с размером не менее 16 ГБ. USB-накопитель будет отформатирован.
2. ISO-файл в Windows 10 Pro или Windows 10 Корпоративная. Средство создания мультимедиа можно использовать для загрузки Windows 10 и создания ISO-файла. Дополнительные сведения можно найти в разделе [Загрузка Windows 10](https://www.microsoft.com/software-download/windows10).

## Как запустить SDA

**Чтобы запустить SDA, выполните указанные ниже действия.**

1. Перейдите на [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) в GitHub. 
2. Ознакомьтесь с документацией по [readmeм](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .
3. На странице [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) нажмите кнопку **код** и выберите **загрузить ZIP** , чтобы сохранить файлы на локальном компьютере.
4. Щелкните ZIP-файл правой кнопкой мыши и выберите пункт **Свойства**.
5. На вкладке **Общие** установите флажок **разблокировать** и нажмите кнопку **ОК**.
6. Извлеките ZIP-файл в папку на жестком диске (например: C:\SDA).
7. Откройте запрос Windows PowerShell с повышенными привилегиями и настройте ExecutionPolicy для текущего сеанса, чтобы он был неограниченным.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Запустите сценарий SDA, указав параметры для своей среды. Например, следующая команда создаст загрузочный USB-накопитель, который можно использовать для установки Windows 10 на Surface Hub 2:

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```

   ![Запуск средства акселератора для развертывания Surface](images/sda1.png)

    Для выполнения сценария потребуется около 45 минут, но это может занять больше времени в зависимости от доступности ресурсов ЦП и дискового пространства. 

    После создания образа Windows сценарий попросит подтвердить букву диска USB. USB-диск будет отформатирован, настроен как загрузочный и скопированы файлы, чтобы включить установку настраиваемого образа Windows 10 для устройств Surface.

9. Вставьте USB-накопитель на устройство, на котором вы хотите установить Windows 10, и перезагрузите компьютер, чтобы начать установку Windows 10. Загрузка с USB-порта должна быть включена в BIOS, при этом может потребоваться временно отключить безопасную загрузку.

> [!IMPORTANT]
> Загрузка с USB-накопителя начнется сразу же после установки Windows 10. Перед вставкой USB и перезапуском убедитесь, что устройство готово к работе. 

## Дополнительные ссылки

 - [Средство развертывания исходного образа, выпущенное в GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Скачивание и установка Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
