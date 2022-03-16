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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 0ececf7a21b4870c4fb6db2403d9a5e34a67fdba
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449472"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Microsoft Surface Deployment Accelerator

Ускоритель развертывания microsoft Surface (SDA) автоматизирует создание и конфигурацию рекомендованного Microsoft развертывания с помощью бесплатных средств развертывания Майкрософт.

Измененный в апреле 2020 г. для упрощения и автоматизации развертывания изображений Surface в корпоративной среде, средство SDA позволяет создавать "заводской" Windows, который можно настроить под организационные требования.

Инструмент SDA с открытым исходным кодом, управляемый сценарием, использует набор Windows и развертывания (ADK) для Windows 10, облегчая создание Windows изображений (WIM) в тестовых или производственных средах. Если последняя ADK еще не установлена, она будет загружена и установлена при запуске средства SDA.

Полученный образ тесно совпадает с конфигурацией изображений Bare Metal Recovery (BMR) без предварительно установленных приложений, таких как Microsoft Office или приложение Surface UWP.

## <a name="requirements"></a>Требования

1. Usb-накопитель размером не менее 16 ГБ. Usb-накопитель будет отформатирован.
2. Файл .iso с Windows 10/11 Pro или Windows 10/11 Enterprise. Средство создания мультимедиа можно использовать для загрузки Windows 10 или Windows 11 и создания файла .iso. Дополнительные сведения см. в [Windows 10](https://www.microsoft.com/software-download/windows10).
3. Устройство с Windows 10 версии 2004 или более поздней версии с доступом в Интернет.

Подробный [список](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) требований см. в разделе Предварительные условия документа README.

## <a name="how-to-run-the-sda"></a>Запуск SDA

**Для запуска SDA:**

1. Перейдите [в SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) на GitHub. 
2. Просмотрите [документацию README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .
3. На странице [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) нажмите кнопку **Код** и выберите скачать **ZIP** , чтобы сохранить файлы локально на компьютере.
4. Щелкните правой кнопкой мыши .zip файл и нажмите **кнопку Свойства**.
5. На **вкладке General** выберите блокировку **Разблокировки** и нажмите **кнопку ОК**.
6. Извлеките .zip в расположение на жестком диске (например: C:\SDA).
7. Откройте повышенный Windows PowerShell и установите ExecutionPolicy для текущего сеанса на Неограниченное.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Запустите сценарий SDA, указывающий параметры для среды. Скрипт можно использовать для создания изображений для установки Windows 10 или Windows 11 на различных устройствах Surface. Полный список поддерживаемых устройств см. в описании [параметра Device](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) в статье SDA README. 

    Например, следующая команда создаст загружаемый USB-накопитель, который можно использовать для установки Windows 10 на [Surface Hub 2](/surface-hub/surface-hub-2s-migrate-os):

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    Пример вывода сценария приведен ниже.

   ![Запуск ускорителя развертывания Surface.](images/sda1.png)

    Для запуска скрипта потребуется около 45 минут, но это может занять больше времени в зависимости от доступных ресурсов ЦП и диска. 

    После создания Windows, скрипт попросит вставить и подтвердить букву диска USB-диска. Затем USB-накопитель будет форматироваться, настраиваться как загружаемый, а файлы скопированы для установки настраиваемого Windows 10 или Windows 11 изображений для устройств Surface.

9. Вставьте USB-накопитель на устройство, на котором необходимо установить Windows 10 или Windows 11, и перезагружайте его для начала установки. Usb-загрузка должна быть включена в BIOS, для чего может потребоваться временное отключение безопасной загрузки.

> [!IMPORTANT]
> Загрузка с USB-диска сразу же начнет установку ОС. Убедитесь, что устройство готово перед вставкой USB и перезапуском. 

## <a name="related-links"></a>Дополнительные ссылки

 - [Средство развертывания изображений с открытым исходным кодом, выпущенное GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [Загрузка и установка Windows ADK](/windows-hardware/get-started/adk-install)
