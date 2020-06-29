---
title: Развертывание приложения Surface с помощью Microsoft Store для бизнеса или Microsoft Store для образования (Surface)
description: Узнайте, как добавить и скачать приложение Surface с помощью Microsoft Store для бизнеса или Microsoft Store для образовательных учреждений, а также установить приложение Surface с помощью PowerShell и MDT.
keywords: приложение Surface, приложение, развертывание, Настройка
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835123"
---
# Развертывание приложения Surface с помощью Microsoft Store для бизнеса и образовательных учреждений

**Относится к:**

- Surface Pro 7
- Surface ноутбук 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go с LTE
- Surface Book 2
- Surface Pro с функцией LTE Advanced (модель 1807)
- Surface Pro (модель 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


Приложение Surface — это упрощенное приложение Microsoft Store, которое обеспечивает управление многими параметрами и параметрами, связанными с определенной поверхностью, в том числе: 

* Включение и отключение кнопки Windows на устройстве Surface 
 

* Регулировка чувствительности ручки Surface 
 

* Настройка действий кнопки ручки Surface 
 

* Включение и отключение расширенных аудиофункций Surface 
 

* Быстрый доступ к документации и сведениям об устройстве

Пользователи, использующие Windows Update, обычно получают приложение Surface в составе автоматических обновлений. Но если ваша организация готовит изображения для развертывания на Surface Devices, вы можете добавить приложение Surface (прежнее название Surface HUB) в процесс создания образа и развертывания, а не требовать от пользователей каждого отдельного устройства загрузить и установить приложение из магазина Microsoft Store или из Microsoft Store для бизнеса. 

> [!NOTE]
> Эта статья не относится к Surface Pro X. Дополнительные сведения можно найти в разделе [развертывание, управление и обслуживание Surface Pro X](surface-pro-arm-app-management.md)

## Общие сведения о приложении Surface

Приложение Surface доступно для бесплатной загрузки из [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Пользователи могут скачать и установить его из Microsoft Store, но если ваша организация использует Microsoft Store для бизнеса, вам нужно будет добавить ее в запасы магазина и, возможно, включить это приложение в рамках процесса развертывания Windows. Эти процессы описаны в этой статье. Дополнительные сведения о Microsoft Store для бизнеса можно найти в [Microsoft Store для бизнеса](https://docs.microsoft.com/microsoft-store/) в центре Windows. 

## Добавление приложения Surface в учетную запись Microsoft Store для бизнеса 

Прежде чем пользователи смогут установить или развернуть приложение из учетной записи Майкрософт магазина компании Microsoft Store для бизнеса, нужные приложения должны быть предоставлены и лицензированы для пользователей компании. 

1. Создайте [учетную запись Microsoft Store для бизнеса](https://www.microsoft.com/business-store), если это еще не сделано. 

2. Войдите на портал. 

3. Включить автономное лицензирование: выберите **управление >параметры магазина**, а затем установите флажок **Показывать лицензируемые приложения для покупок в магазине** , как показано на рисунке 1. Дополнительные сведения о моделях лицензирования приложений Microsoft Store для бизнеса можно найти в статьях [приложения в Microsoft Store для бизнеса и образовательных учреждений](https://docs.microsoft.com/microsoft-store/).<br/> <br/>
   ![Флажок "показывать автономные приложения лицензий"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Рисунок 1. Включение приложений для автономного использования*

4. Добавьте приложение Surface в учетную запись Microsoft Store для бизнеса, выполнив указанные ниже действия.
    * Откройте меню " **произ** .
    * В поле поиска введите **Surface приложение**и щелкните значок Поиск.
    * После того как приложение Surface появится в результатах поиска, щелкните значок приложения.
    * Вы увидите вариант выбора (выберите в **Интернете** или в **автономном режиме**), как показано на рисунке 2.<br/><br/>
    
    ![Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *Рисунок 2. Выбор режима лицензирования в автономном режиме и Добавление приложения в список дел*
    
    * Щелкните **автономно** , чтобы выбрать режим лицензирования в автономном режиме.
    * Нажмите кнопку **получить приложение** , чтобы добавить приложение в инвентаризацию Microsoft Store для бизнеса. Как показано на рис. 3, появится диалоговое окно с запросом о том, что автономные приложения можно развертывать с помощью средства управления или загрузить с инвентарной страницы компании в частном магазине.
    
    ![Окно подтверждения приложения, лицензированное в автономном режиме](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *Рисунок 3. Подтверждение приложения, лицензированное в автономном режиме*
    * Нажмите кнопку **ОК**.

## Скачать приложение Surface из учетной записи Майкрософт магазина для бизнеса
После того как вы добавите приложение в учетную запись Microsoft Store для бизнеса в автономном режиме, вы можете скачать и добавить приложение в качестве AppxBundle в общий доступ к развертыванию.
1. Войдите в учетную запись Microsoft Store для бизнеса по адресу https://businessstore.microsoft.com .
2. Выберите **>приложения & программное обеспечение**. Откроется список всех приложений вашей компании, включая приложение Surface, которое вы добавили в [приложение добавить Surface в раздел учетной записи Microsoft Store для бизнеса](#add-surface-app-to-a-microsoft-store-for-business-account) в этой статье.
3. В разделе **действия**нажмите кнопку с многоточием (**...**), а затем выберите команду **скачать для автономного использования** для приложения Surface.
4. Выберите нужные параметры **платформы** и **архитектуры** из доступных вариантов выбора для выбранного приложения, как показано на рисунке 4.

    ![Пример пакета AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *Рисунок 4. Загрузка пакета AppxBundle для приложения*
5. Нажмите кнопку **загрузить**. Будет загружен пакет AppxBundle. Убедитесь, что путь к скачанному файлу указан, так как это потребуется позже в этой статье.
6. Выберите " **зашифрованная лицензия** " или " **нешифрованная лицензия** ". Используйте закодированную лицензию с помощью средств управления, таких как диспетчер конфигурации конечных точек Майкрософт, или с помощью конструктора конфигураций Windows для создания пакета подготовки. Выберите параметр нешифрованная лицензия при использовании системы обслуживания образов развертывания и управления ими (DISM) и решений для развертывания на основе обработки изображений, включая Microsoft Deployment Toolkit (MDT).
7. Нажмите кнопку " **создать** ", чтобы создать и скачать лицензию для приложения. Убедитесь, что вы запомните путь к файлу лицензии, так как это потребуется позже в этой статье.

>[!NOTE]
>Когда вы загружаете приложение для автономного использования, например приложение Surface, вы можете заметить раздел в нижней части страницы, помеченной **необходимыми платформами**. Для запуска приложения на конечных компьютерах должны быть установлены платформы, поэтому вам может потребоваться повторить процесс загрузки для каждой из необходимых платформ (x86 или x64), а также включить их в развертывание Windows, описанное ниже в этой статье.

На рисунке 5 показаны необходимые платформы для приложения Surface.

![Необходимые платформы для приложения Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*Рисунок 5. Необходимые платформы для приложения Surface*

>[!NOTE]
>Номера версий приложения Surface и требуемой платформы будут изменяться по мере обновления приложений. Проверьте наличие последней версии приложения Surface и каждой платформы в Microsoft Store для бизнеса. Всегда используйте приложение Surface и рекомендуемые версии платформы, предоставленные Microsoft Store для бизнеса. Использование устаревших платформ или неправильных версий может привести к ошибкам или сбою приложения.

Чтобы скачать необходимые платформы для приложения Surface, выполните указанные ниже действия.
1. Нажмите кнопку **загрузить** в разделе **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**. Загрузи Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe. Appx-файл в указанную папку.
2. Нажмите кнопку **загрузить** в разделе **Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**. В указанную папку будет загружен файл Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. appx.

>[!NOTE]
>Для устройств Surface требуется только 64-разрядная (x64) версия каждой платформы. Устройства Surface — это машинные 64-битовые устройства UEFI, несовместимые с 32-разрядной (x86) версиями Windows, для которых требуется 32-разрядные платформы. 

## Установка Surface App на компьютере с помощью PowerShell
Описанная ниже процедура позволяет получить приложение Surface на компьютере и сделать ее доступной для всех учетных записей пользователей, созданных на компьютере.
1. С помощью процедуры, описанной в разделе [Загрузка приложения Surface из раздела учетной записи Microsoft Store для бизнеса](#download-surface-app-from-a-microsoft-store-for-business-account) в этой статье, скачайте файл AppxBundle приложения Surface и License File. 
2. Запустите сеанс Windows PowerShell с повышенными правами.

    >[!NOTE]
    >Если вы не запускаете PowerShell в качестве администратора, сеанс не будет обладать необходимыми разрешениями для установки приложения.
    
3. В сеансе Windows PowerShell с повышенными правами скопируйте и вставьте следующую команду: 
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Где `<DownloadPath>` находится папка, в которой загружен файл AppxBundle и License, из учетной записи Microsoft Store для бизнеса.

    Например, если вы загрузили файлы в c:\Temp, вы можете использовать следующие команды:
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
