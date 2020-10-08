---
title: Создание пакетов подготовки (Surface Hub)
description: В Windows10 параметры, использующие реестр или поставщика служб конфигурации (CSP), можно настроить с помощью пакетов подготовки.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: добавление сертификата, пакет подготовки
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103803"
---
# Создание пакетов подготовки (Surface Hub)

В этом разделе объясняется, как создать пакет подготовки с помощью конструктора конфигураций Windows и применить его к устройствам Surface Hub. При работе с Surface Hub пакеты подготовки можно использовать для добавления сертификатов, установки приложений универсальной платформы Windows (UWP) и настройки политик и параметров.

Применить пакет подготовки можно с помощью USB-накопителя при первом запуске или с использованием приложения **Параметры**. 


## Преимущества
-   Быстрая настройка устройств без использования поставщика управления мобильными устройствами (MDM).

-   Не требуется подключение к сети.

-   Простота применения.

[Узнайте о преимуществах и возможностях использовании пакетов подготовки.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## Требования 

Чтобы создать и применить пакет подготовки в Surface Hub, потребуется следующее:

-   Конструктор конфигураций Windows, который может быть установлен из Microsoft Store или из комплекта средств для развертывания и оценки Windows10 (ADK). [Узнайте, как установить конструктор конфигураций Windows.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   USB-накопитель.
-   Если пакет применяется с помощью приложения **Параметры**, понадобятся учетные данные администратора устройства.

Вы создадите пакет подготовки на ПК с Windows10, сохраните пакет на USB-диск и развернете его в своем экземпляре Surface Hub.


## Поддерживаемые элементы для пакетов подготовки Surface Hub

С помощью мастера **подготовки устройств Surface Hub** можно:

- зарегистрироваться в Active Directory, Azure Active Directory или MDM; 
- создать учетную запись администратора устройства; 
- добавить приложения и сертификаты;
- настроить параметры прокси-сервера;
- добавить файл конфигурации Surface Hub.

>[!WARNING]
>Необходимо запустить конструктор конфигураций Windows в Windows10 для настройки регистрации Azure Active Directory с помощью мастера.

С помощью редактора расширенной подготовки можно добавить эти элементы в пакеты подготовки для Surface Hub:

- **Политики**— Surface Hub поддерживает подмножество политик в разделе [Поставщик служб конфигурации политик](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies). 
- **Параметры**— в разделе [Поставщик служб конфигурации политик SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) можно настроить любые параметры.

>[!TIP]
> Используйте мастер, чтобы создать пакет с общими параметрами, затем переключитесь в расширенный редактор, чтобы добавить другие параметры.
>
>![открытие расширенного редактора](images/icd-simple-edit.png)

## Использование мастера подготовки Surface Hub

После [установки конструктора конфигураций Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) можно создать пакет подготовки.

### Создание пакета подготовки 

1. Откройте конструктор конфигураций Windows.
   - На начальном экране или на панели поиска меню "Пуск" введите "Конструктор конфигураций Windows" и щелкните ярлык конструктора конфигураций Windows 
    
     или
    
   - если вы установили конструктор конфигураций Windows из ADK, перейдите к `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (на компьютере x64) или `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (на компьютере x86), а затем дважды щелкните **ICD.exe**.

2. Щелкните элемент **Подготовка устройств Surface Hub**.

3. Назначьте имя проекту и нажмите кнопку **Далее**.

### Configure settings

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>To provision the device with a certificate, click <strong>Add a certificate</strong>. Enter a name for the certificate, and then browse to and select the certificate to be used.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings. Surface Hub по умолчанию настроен на автоматическое определение параметров прокси-сервера, поэтому выберите <strong>Нет</strong>, если вам необходим этот параметр. Тем не менее, если ранее инфраструктура требовала использование прокси-сервера, но теперь этого не требует, можно восстановить параметры по умолчанию для устройств Surface Hub с помощью пакета подготовки. Для этого выберите <strong>Да</strong> и <strong>Автоматически определять параметры</strong>. </br></br>Для автоматического определения параметров прокси-сервера необходимо выбрать <strong>Да</strong>. Чтобы настроить параметры вручную, введите URL-адрес в сценарий настройки или адрес статического прокси-сервера. Можно также определить, нужно ли использовать прокси-сервер для локальных адресов, и указать исключения (адреса, к которым Surface Hub должен подключаться непосредственно без использования прокси-сервера).  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Можно зарегистрировать устройство в Active Directory и указать группу безопасности, чтобы использовать приложение «Параметры», зарегистрироваться в Azure Active Directory, чтобы разрешить глобальным администраторам использовать приложение «Параметры», или создать учетную запись локального администратора на устройстве.</br></br>Для регистрации устройства в Active Directory введите учетные данные для учетной записи пользователя с минимальными правами, чтобы подключить устройство к домену, и укажите группу безопасности, чтобы использовать учетные данные администратора на Surface Hub. Если пакет подготовки, регистрирующий устройство в Active Directory, будет применяться к Surface Hub, который был сброшен, учетная запись домена может использоваться, только если она принадлежит администратору домена или если это учетная запись, с помощью которой был изначально установлен Surface Hub. Otherwise, a different domain account must be used in the provisioning package.</br></br>Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>. Параметр <strong>Максимальное количество устройств на одного пользователя</strong> в клиенте Azure AD определяет, сколько раз можно использовать массовый маркер, полученный в мастере. Для регистрации устройства в Azure AD, выберите соответствующий вариант и введите понятное имя для массового маркера, полученного с помощью мастера. Set an expiration date for the token (maximum is 30 days from the date you get the token). Click <strong>Get bulk token</strong>. In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password. Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</br></br>To create a local administrator account, select that option and enter a user name and password. </br></br><strong>Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days. If the password is not changed during that period, the account might be locked out and unable to sign in.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM. </br></br>Если вы выбрали <strong>Да</strong>, необходимо предоставить учетную запись и пароль службы или отпечаток сертификата с правом на регистрацию устройства, а также указать тип проверки подлинности. If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">Learn more about managing Surface Hub with MDM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>You can install multiple Universal Windows Platform (UWP) apps in a provisioning package. For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>. </br></br><strong>Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub. If you include a Classic Win32 app, provisioning will fail. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>You don&#39;t configure any settings in this step. It provides instructions for including a configuration file that contains a list of device accounts. Файл конфигурации не должен содержать заголовки столбцов. Если файл конфигурации Surface Hub имеется на USB-накопителе, то при применении пакета подготовки к Surface Hub можно выбрать учетную запись и понятное имя для устройства из файла. See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</br></br><strong>Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>You can set a password to protect your provisioning package. You must enter this password when you apply the provisioning package to a device.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

After you're done, click **Create**. Это займет несколько секунд. После построения пакета расположение, в котором хранится пакет, отображается как гиперссылка в нижней части страницы.

## Пример файла конфигурации

Файл конфигурации Surface Hub содержит список учетных записей устройства, которые могут использоваться вашим устройством для подключения к Exchange и Skype для бизнеса. При применении пакета подготовки к Surface Hub можно включить файл конфигурации в корневой каталог USB-накопителя, а затем выбрать нужную учетную запись для применения к этому устройству. Файл конфигурации можно применять только при первом включении (OOBE) и использовать исключительно с пакетами подготовки, созданными с помощью конструктора конфигурации Windows, который поставляется с Windows10 версии1703.

Используйте Microsoft Excel или другой редактор CSV для создания CSV-файла с именем `SurfaceHubConfiguration.csv`. В файле введите список учетных записей устройства и понятные имена в следующем формате:

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>Поскольку в файле конфигурации хранятся пароли учетных записей устройства в виде обычного текста, мы рекомендуем обновить пароли после применения пакета подготовки к устройствам. Для обновления паролей через систему MDM можно использовать [узел DeviceAccount](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) в [поставщике служб конфигурации (CSP) Surface Hub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp).


Ниже приведен пример `SurfaceHubConfiguration.csv`. 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## Использование расширенной подготовки

После [установки конструктора конфигураций Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) можно создать пакет подготовки.

### Создание пакета подготовки (расширенное)

1. Откройте конструктор конфигураций Windows.
   - На начальном экране или на панели поиска меню "Пуск" введите "Конструктор конфигураций Windows" и щелкните ярлык конструктора конфигураций Windows 
    
     или
    
   - если вы установили конструктор конфигураций Windows из ADK, перейдите к `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (на компьютере x64) или `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (на компьютере x86), а затем дважды щелкните **ICD.exe**.

2. Щелкните **Расширенная подготовка**.
   
3. Name your project and click **Next**.

4. Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.

    ![ICD new project](images/icd-new-project.png)

5. In the project, under **Available customizations**, select **Common Team settings**.

    ![ICD common settings](images/icd-common-settings.png)


### Добавление сертификата в пакет
Пакеты подготовки можно использовать для установки сертификатов, которые позволяют устройству проходить проверку подлинности в Microsoft Exchange.

> [!NOTE]
> Пакеты подготовки позволяют установить сертификаты только в хранилище устройства (на локальном компьютере), а не в хранилище пользователя. Если для организации требуется установить сертификаты в хранилище пользователя, разверните их с помощью решения управления мобильными устройствами (MDM). Подробнее см. в документации вашего решения MDM.

1. На панели **Доступные настройки** перейдите в раздел **Параметры среды выполнения** > **Сертификаты** > **ClientCertificates**. 

2. Укажите имя сертификата **CertificateName**, затем щелкните **Добавить**. 

2. Введите **CertificatePassword**. 

3. Найдите и выберите сертификат, который следует использовать для **CertificatePath**. 

4. Задайте значение **False** для параметра **ExportCertificate**.

5. Для параметра **KeyLocation** выберите значение **Только программное обеспечение**.


### Добавление приложения универсальной платформы Windows (UWP) в пакет
Прежде чем добавлять в пакет подготовки приложение UWP, необходимо создать пакет приложения (APPX или APPXBUNDLE) и файлы зависимостей. Если вы приобрели приложение в Microsoft Store для бизнеса, вам также потребуется *некодированная* лицензия на приложение. Информацию о загрузке этих элементов из Microsoft Store для бизнеса см. в статье [Распространение автономных приложений](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

1. На панели **Доступные настройки** перейдите в раздел **Параметры среды выполнения** > **UniversalAppInstall** > **DeviceContextApp**.

2. Введите **PackageFamilyName** для приложения, а затем нажмите кнопку **Добавить**. Для согласованности используйте имя семейства пакетов приложения. If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license. Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.

3. For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).

4. В разделе **DependencyAppxFiles** щелкните **Обзор**, чтобы найти и добавить любые зависимости для этого приложения. Для Surface Hub потребуются только версии x64 этих зависимостей.

Если вы приобрели приложение в Microsoft Store для бизнеса, вам также потребуется добавить в пакет подготовки лицензию на приложение.

1. Создайте копию лицензии на приложение и переименуйте ее с расширением **.ms-windows-store-license**. Например, "example.xml" становится "example.ms-windows-store-license".

2. В ICD в области **Доступные настройки** перейдите в раздел **Параметры среды выполнения** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Введите **LicenseProductId**, затем щелкните **Добавить**. Для согласованности используйте идентификатор лицензии приложения из лицензии на приложение. Open the license file using a text editor. Then, in the \<License\> tag, use the value in the **LicenseID** attribute.

4. Select the new **LicenseProductId** node. В **LicenseInstall** щелкните **Обзор**, чтобы найти и выбрать файл лицензии, переименованный в шаге 1.


### Добавление политики в пакет
Surface Hub поддерживает подмножество политик в разделе [Поставщик служб конфигурации политик](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Некоторые из этих политик можно настроить с помощью ICD.

1. На панели **Доступные настройки** перейдите в раздел **Параметры среды выполнения** > **Политики**.

2. Выберите одну из доступных областей политики.

3. Выберите и настройте политику, которую требуется добавить в пакет подготовки.


### Добавление параметров Surface Hub в пакет 

You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package. 

1. In the **Available customizations** pane, go to **Runtime settings** > **SurfaceHub**.

2. Select one of the available setting areas.

3. Выберите и настройте параметр, который требуется добавить в пакет подготовки. 


## Сборка пакета

1. Завершив настройку пакета подготовки, откройте меню **Файл** и щелкните **Сохранить**.

2. Прочитайте предупреждение о том, что файлы проекта могут содержать конфиденциальную информацию, затем нажмите кнопку **ОК**.

    > [!IMPORTANT]
    > При создании пакета подготовки вы можете включить конфиденциальную информацию в файлы проекта и в файл пакета подготовки (PPKG). Несмотря на то что у вас есть возможность шифрования PPKG-файла, файлы проекта не шифруются. Файлы проекта следует хранить в надежном месте, если они больше не требуются, их необходимо удалять.

3. В меню **Экспорт** выберите пункт **Пакет подготовки**.

4. Измените значение параметра **Владелец** на **ИТ-администратор**. Это позволит установить для данного пакета подготовки более высокий приоритет, чем приоритет пакетов подготовки из других источников, примененных к данному устройству.

5. Установите значение для параметра **Версия пакета**, а затем нажмите кнопку **Далее.**

    > [!TIP]
    > Можно внести изменения в существующие пакеты и изменить номер версии для обновления ранее примененных пакетов.

6. Необязательно: можно зашифровать пакет и включить подпись пакета.

    -   **Включить шифрование пакета** — при выборе этого пункта на экране отобразится автоматически созданный пароль.

    -   **Включить подписывание пакета**— при выборе этого пункта необходимо выбрать действительный сертификат, который будет использоваться для подписывания пакета. Вы можете указать сертификат, щелкнув **Обзор...**, а затем выбрав сертификат, который будет использоваться для подписания пакета.

        > [!IMPORTANT]
        > Рекомендуется включить в пакет доверенный сертификат подготовки. Когда пакет применяется к устройству, сертификат добавляется в хранилище системы и впоследствии любой пакет, подписанный с использованием этого сертификата, будет применен автоматически. 

7. Нажмите кнопку **Далее** , чтобы указать выходное расположение, куда нужно поместить пакет подготовки после сборки. По умолчанию Windows ICD использует папку проекта в качестве расположения выходных данных.<p>
Вы также можете нажать **Обзор** , чтобы изменить расположение выходных данных по умолчанию.

8. Нажмите кнопку **Далее**.

9. Щелкните **Выполнить сборку** , чтобы начать сборку пакета. Сведения о проекте отображаются на странице сборки, а индикатор выполнения указывает состояние сборки.<p>
Чтобы отменить построение, нажмите кнопку **Отмена**. Текущий процесс построения будет отменен, мастер закроется и вы вернетесь в раздел **Страница настроек**.

10. В случае сбоя построения отобразится сообщение об ошибке со ссылкой на папку проекта. Вы можете просмотреть журналы, чтобы определить, что вызвало ошибку. После устранения проблемы попробуйте выполнить построение пакета еще раз.<p>
В случае успешного построения отобразятся пакет подготовки, выходной каталог и каталог проекта.

    -   При желании вы можете выполнить построение пакета подготовки снова и выбрать другой путь для выходного пакета. Для этого щелкните **Назад** , чтобы изменить имя и путь выходного пакета, и нажмите кнопку **Далее** , чтобы начать другое построение.
    
    -   Если вы закончили, нажмите кнопку **Готово** , чтобы закрыть мастер и вернуться в раздел **Страница настроек**.

11. Выберите ссылку **Размещение вывода**, чтобы перейти в расположение пакета. Копируйте PPKG-файл на пустой USB-накопитель флэш-памяти.


## Применение пакета подготовки на устройстве Surface Hub

There are two options for deploying provisioning packages to a Surface Hub. [During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings). 


### Apply a provisioning package during first run

> [!IMPORTANT]
> During the first-run program, you can only use provisioning packages to install certificates. Use the **Settings** app to install apps and apply other settings.

1. При первом включении Surface Hub в программе первого запуска отображается [**страница приветствия**](first-run-program-surface-hub.md#first-page). Перед продолжением убедитесь, что параметры настроены правильно.

2. Вставьте USB-устройство флэш-памяти с PPKG-файлом в Surface Hub. Если пакет находится в корневом каталоге диска, программа первого запуска распознает его и спросит, требуется ли настроить устройство. Выберите **Настройка**.

    ![Настроить устройство?](images/provisioningpackageoobe-01.png)

3. На следующем экране появляется запрос о выборе источника подготовки. Выберите **Съемный носитель** и коснитесь **Далее**.

    ![Подготовка этого устройства](images/provisioningpackageoobe-02.png)
    
4. Выберите пакет подготовки (\*.ppkg), который вы хотите применить, а затем коснитесь **Далее**. Обратите внимание, что вы можете установить только один пакет во время первого запуска.

    ![Выберите пакет](images/provisioningpackageoobe-03.png)

5. В программе первого запуска отобразится сводка изменений, которые будут внесены с помощью пакета подготовки. Выберите **Да, добавить**.  

    ![Вы считаете этот пакет надежным?](images/provisioningpackageoobe-04.png)
    
6. Если файл конфигурации включен в корневой каталог USB-накопителя, вы увидите параметр **Выбор конфигурации**. Первая учетная запись устройства в файле конфигурации будет отображаться вместе со сводными данными учетной записи, которые будут применяться к Surface Hub.

    ![выбор конфигурации](images/ppkg-config.png)    

7. В пункте **Выбор конфигурации** выберите имя устройства для применения, а затем нажмите **Далее**.

    ![выбор понятного имени](images/ppkg-csv.png)
    
К устройству будут применены параметры из пакета подготовки и первый запуск будет завершен. После перезагрузки устройства можно удалить USB-накопитель.

### Применение пакета с использованием приложения «Параметры»

1. Вставьте USB-устройство флэш-памяти с PPKG-файлом в Surface Hub.

2. В Surface Hub запустите приложение **Параметры** и введите учетные данные администратора в ответ на соответствующий запрос.

3. Перейдите к **Surface Hub** > **Управление устройствами**. В разделе **Пакеты подготовки** выберите **Добавить или удалить пакет подготовки**.

4. Выберите **Добавить пакет**.

5. Выберите пакет подготовки и щелкните **Добавить**. Возможно, потребуется повторно ввести учетные данные администратора в ответ на соответствующий запрос.

6. Отобразится сводка изменений, которые будут применены пакетом подготовки. Выберите **Да, добавить**.


