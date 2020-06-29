---
title: Использование диспетчера конфигураций конечных точек Microsoft для управления устройствами с помощью SEMM (Surface)
description: Сведения об управлении корпоративным режимом Microsoft Surface Management (SEMM) с диспетчером конфигурации конечной точки.
keywords: регистрация, обновление, сценарии, параметры
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: bba99d202d5d0dc5085c454202ae9a95df56109c
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835523"
---
# Использование диспетчера конфигураций конечных точек Microsoft для управления устройствами с помощью SEMM

Функция режима корпоративного управления Surface (SEMM) для устройств UEFI Surface позволяет администраторам управлять конфигурацией параметров UEFI Surface и помогать им в защите. Для большинства организаций этот процесс выполняется путем создания пакетов установщика Windows (MSI) с помощью средства конфигуратора UEFI Microsoft Surface. Эти пакеты затем выполняются или развертываются на клиентских устройствах Surface для регистрации устройств в SEMM и обновления конфигурации параметров UEFI Surface.

Для организаций, использующих диспетчер конфигураций конечных точек Microsoft, вы можете использовать процесс конфигуратора UEFI Microsoft Surface. msi для развертывания и администрирования SEMM. Microsoft Surface UEFI Manager — это упрощенная программа установки, которая делает необходимые сборки для управления SEMM доступными на устройстве. Установив эти сборки с помощью Microsoft Surface UEFI Manager на управляемом клиенте, SEMM можно администрировать в Configuration Manager с помощью сценариев PowerShell, развернутых в качестве приложений. Благодаря этому процессу управление SEMM выполняется в Configuration Manager, что устраняет необходимость в использовании внешней программы конфигуратора UEFI Surface (Майкрософт).

> [!Note]
> Несмотря на то, что описанный в этой статье процесс может работать с более ранними версиями диспетчера конфигураций конечных точек или с другими решениями для управления сторонними компаниями, управление SEMM с помощью Microsoft Surface UEFI Manager и PowerShell поддерживается только в текущей ветви диспетчера конфигураций конечных точек.

#### Предварительные условия

Перед началом процесса, описанным в этой статье, ознакомьтесь с приведенными ниже технологиями и инструментами.

* [UEFI Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [Surface Enterprise Management Mode (SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [Сценарии PowerShell](https://technet.microsoft.com/scriptcenter/dd742419)
* [Развертывание приложения System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* Управление сертификатами

> [!Note]
> Вам понадобится также доступ к сертификату, который вы хотите использовать для защиты SEMM. Сведения о требованиях для этого сертификата можно найти в разделе [требования к сертификату режима управления предприятием в Surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).
> 
> Очень важно, чтобы этот сертификат хранился в безопасном месте и был правильно сохранен в резервной копии. Если этот сертификат теряется или не годен для использования, невозможно сбросить UEFI Surface, изменить параметры UEFI управляемой поверхности или удалить SEMM с устройства, на котором зарегистрирована поверхность.

#### Скачать Диспетчер UEFI Surface (Майкрософт)

Для управления SEMM с помощью Configuration Manager требуется установка Microsoft Surface UEFI Manager на каждом клиентском устройстве Surface. Вы можете скачать Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) со страницы [инструменты Surface для ИТ](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки Майкрософт.

#### Скачайте сценарии SEMM для Configuration Manager

После установки Microsoft Surface UEFI Manager на клиентском устройстве Surface SEMM разворачивается и управляется с помощью сценариев PowerShell. Вы можете скачать примеры [сценариев управления SEMM](https://www.microsoft.com/download/details.aspx?id=46703) в центре загрузки.

## Развертывание диспетчера UEFI Surface (Майкрософт)

Развертывание диспетчера UEFI Surface (Майкрософт) — это типичное развертывание приложения. Файл установщика Microsoft Surface UEFI Manager — это стандартный файл установщика Windows, который можно установить со [стандартным параметром quiet](https://msdn.microsoft.com/library/windows/desktop/aa367988).

Для установки диспетчера Microsoft Surface UEFI Manager необходимо выполнить следующие команды.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

Ниже приведена команда для удаления диспетчера UEFI Surface (Майкрософт).

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Чтобы создать новое приложение и развернуть его в коллекции, содержащей устройства Surface, выполните указанные ниже действия.

1. Откройте консоль Configuration Manager на **начальном** экране или в меню " **Пуск** ".
2. В левом нижнем углу окна выберите **Библиотека программного обеспечения** .
3. Разверните узел **Управление приложениями** библиотеки программного обеспечения, а затем выберите пункт **приложения**.
4. Нажмите кнопку " **создать приложение** " под вкладкой " **Главная** " в верхней части окна. Запустится мастер создания приложений.
5. Мастер создания приложений предоставляет ряд шагов.

   * **Общие** : параметр **автоматически определяет сведения об этом приложении из файлов установки** по умолчанию установлен. В поле **тип** **(файл. msi)** также выбрано по умолчанию. Нажмите кнопку **Обзор** , перейдите к пункту **SurfaceUEFIManagerSetup.msi**и нажмите кнопку **Далее**.
   
      > [!Note]
      > Расположение SurfaceUEFIManagerSetup.msi должно находиться в сетевой папке и находиться в папке, которая не имеет других файлов. Нельзя использовать локальное расположение файлов.

   * **Импорт данных** — мастер создания приложений проанализирует MSI-файл и прочтите **имя приложения** и **код продукта**. SurfaceUEFIManagerSetup.msi должны быть указаны в качестве единственного файла **содержимого**строки, как показано на рисунке 1. Нажмите кнопку **Далее** , чтобы продолжить.

      ![Данные из программы установки диспетчера UEFI Surface автоматически анализируются](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Рисунок 1. Сведения от программы установки Microsoft Surface UEFI Manager автоматически анализируются*

   * **Общие сведения** — вы можете изменить имя приложения и сведения о его издателе и версии, а также добавить примечания на этой странице. Команда установки для Microsoft Surface UEFI Manager отображается в поле программы установки. Поведение по умолчанию при установке для системы позволяет диспетчеру UEFI Microsoft Surface устанавливать необходимые сборки для SEMM, даже если пользователь не вошел на устройство Surface. Нажмите кнопку **Далее** , чтобы продолжить.
   * **Summary (сводка** ) — данные, которые были проанализированы на этапе **импорта данных** , и выбранные на странице " **Общие сведения** " отображаются на этой вкладке. Нажмите кнопку **Далее** , чтобы подтвердить выборку и создать приложение.
   * **Ход выполнения** — отображает индикатор выполнения и состояние при импорте и добавлении приложения в библиотеку программного обеспечения.
   * **Завершение** — подтверждение успешного создания приложения отображается по завершении процесса создания приложения. Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания приложений.

После того как приложение создано в Configuration Manager, вы можете распространить его на точки распространения и развернуть в коллекции, в том числе на Surface Devices. Это приложение не установит и не включит SEMM на устройстве Surface. Она предоставляет только сборки, необходимые для включения SEMM с помощью сценария PowerShell.

Если вы не хотите устанавливать сборки Microsoft Surface UEFI Manager на устройствах, которые не будут управляться с помощью SEMM, можно настроить диспетчер Microsoft Surface UEFI в качестве зависимости от сценариев Configuration Manager SEMM. Этот сценарий рассматривается в разделе [сценарии SEMM Configuration Manager для развертывания](#deploy-semm-configuration-manager-scripts) в этой статье ниже.

## Создание и изменение сценариев Configuration Manager SEMM

После установки на устройствах необходимых сборок процесс регистрации устройств в SEMM и настройки UEFI Surface выполняется с помощью сценариев PowerShell и развернут как приложение сценария с помощью Configuration Manager. Эти сценарии можно изменить в соответствии с потребностями Организации и среды. Например, вы можете создать несколько конфигураций для управляемых устройств Surface в разных подразделениях или ролях. Вы можете скачать примеры сценариев для SEMM и Configuration Manager из ссылки в разделе [необходимые условия](#prerequisites) в начале этой статьи.

Для выполнения развертывания SEMM с помощью Configuration Manager вам понадобятся два основных сценария.

* **ConfigureSEMM.ps1** — используйте этот сценарий для создания пакетов конфигурации для устройств Surface с помощью параметров UEFI, необходимых для применения указанных параметров к устройству Surface, для регистрации устройства в SEMM и для настройки ключа реестра, используемого для определения регистрации устройства в SEMM.
* **ResetSEMM.ps1** — используйте этот сценарий для сброса SEMM на устройстве Surface, который отменяет его из SEMM и удаляет элемент управления для параметров UEFI Surface.

Примеры сценариев включают в себя примеры того, как задавать параметры UEFI Surface и управлять разрешениями для этих параметров. Эти параметры можно изменить на Secure UEFI Surface и установить параметры UEFI Surface в соответствии с потребностями вашей среды. В следующих разделах этой статьи описаны сценарии ConfigureSEMM.ps1 и рассматриваются изменения, которые необходимо внести в сценарий в соответствии с вашими потребностями.

> [!NOTE]
> Сценарии Configuration Manager SEMM и экспортированный файл сертификата SEMM (PFX) следует размещать в той же папке, где нет других файлов, прежде чем они будут добавлены в Configuration Manager.

### Указание имен сертификатов и пакетов

Первый регион сценария, который необходимо изменить, — это часть, которая определяет и загружает сертификат SEMM, а также указывает SurfaceUEFIManager версию и имена пакета конфигурации SEMM и SEMM сброса пакета. Имя сертификата и SurfaceUEFIManager версия указываются в строках 56 – 73 в сценарии ConfigureSEMM.ps1.

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

Замените значение **FabrikamSEMMSample. pfx** для переменной **$certName** именем вашего файла сертификата SEMM в строке 58. Сценарий создаст рабочую папку (с именем config) в папке, в которой находятся ваши сценарии, а затем скопирует файл сертификата в этот рабочий каталог.

Пакет владельца и пакет сброса будут также созданы в каталоге конфигурации и содержат конфигурацию для параметров UEFI Surface и разрешений, создаваемых сценарием.

В строке 73 замените значение переменной **$Password** из **1234** на пароль для файла сертификата. Если пароль не требуется, удалите текст **1234** .

> [!Note]
> Последние два символа отпечатка сертификата необходимы для регистрации устройства в SEMM. Этот сценарий отобразит эти цифры для пользователя, который позволит пользователю или специалисту записать эти цифры перед перезагрузкой системы, чтобы зарегистрировать устройство в SEMM. Для этого в сценарии используется следующий код, найденный в строках 150-155.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Администраторы, у которых есть доступ к файлу сертификата (PFX), могут в любое время прочитать отпечаток, открыв PFX-файл в CertMgr. Чтобы просмотреть отпечаток с помощью CertMgr, выполните указанные ниже действия.

1. Щелкните PFX-файл правой кнопкой мыши и выберите команду **Открыть**.
2. Разверните папку в области навигации.
3. Выберите **Сертификаты**.
4. Щелкните правой кнопкой мыши свой сертификат в основной области и выберите команду **Открыть**.
5. Откройте вкладку **сведения** .
6. В раскрывающемся меню **Показать** должны быть выбраны только **все** или **свойства** .
7. Выберите **отпечаток**поля.

> [!NOTE]
> Имя сертификата SEMM и пароль также должны быть введены в этом разделе сценария ResetSEMM.ps1, чтобы настроить Configuration Manager для удаления SEMM с устройства с помощью действия удаления.

### Настройка разрешений

Первый регион сценария, в котором вы укажете конфигурацию UEFI Surface, — это область " **Настройка разрешений** ". Этот регион начинается со строки 210 в сценарии Sample с примечанием **# Настройка разрешений** и переход к строке 247. В следующем фрагменте кода сначала устанавливаются разрешения для всех параметров UEFI Surface, так что они могут быть изменены только в SEMM, а затем добавлены явные разрешения, позволяющие локальному пользователю изменять пароль UEFI Surface, TPM и передние и задние камеры.

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

Каждая переменная **$uefiV 2** определяет параметр UEFI Surface, задавая имя или идентификатор, а затем настраивает разрешения для одного из следующих значений:

* **$ownerOnly** — разрешение на изменение этого параметра предоставляется только в SEMM.
* **$ownerAndLocalUser** — разрешение на изменение этого параметра предоставлено локальному пользователю, загружается в UEFI Surface и SEMM.

Сведения о доступных именах параметров и идентификаторах для UEFI Surface можно найти в разделе [Параметры и идентификаторы](#settings-names-and-ids) этой статьи.

### Настройка параметров

Вторая область сценария, в которой вы укажете конфигурацию UEFI Surface, — это область " **Настройка параметров** " сценария ConfigureSEMM.ps1, который позволяет настроить включение или отключение каждого параметра. В примере сценария содержатся инструкции по заданию значений по умолчанию для всех параметров. Затем сценарий предоставляет явные инструкции по отключению IPv6 для загрузки PXE и оставлению пароля администратора UEFI Surface без изменений. Этот регион можно найти, начиная с комментария " **# Настройка параметров** " в строке 291 – 335 в примере сценария. Область выглядит следующим образом.

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

Так же, как и разрешения, заданные в разделе " **Настройка разрешений** " сценария, настройка каждого из параметров UEFI Surface выполняется путем определения переменной **$uefiV 2** . Для каждой строки, определяющей переменную **$uefiV 2** , параметр UEFI Surface определяется с помощью параметра Name (имя) или ID, для которого задано значение **Enabled (включено** ) или **Disabled (отключить**).

Если вы не хотите изменять конфигурацию UEFI Surface, например, чтобы не пропустить пароль администратора UEFI Surface при сбросе параметров UEFI Surface по умолчанию, можно использовать **ClearConfiguredValue ()** для принудительного изменения этого параметра. В примере сценарий используется в строке 323 для предотвращения очистки пароля администратора UEFI Surface, определенного в образце сценария с помощью идентификатора параметра, **501**.

Сведения о доступных именах параметров и идентификаторах для UEFI Surface можно найти в разделе [Параметры и идентификаторы](#settings-names-and-ids) ниже в этой статье.

### Раздел "Параметры" в реестре

Чтобы определить зарегистрированные системы для Configuration Manager, в сценарии ConfigureSEMM.ps1 записываются разделы реестра, которые можно использовать для определения зарегистрированных систем в том виде, в котором они были установлены с помощью сценария конфигурации SEMM. Эти разделы можно найти в следующем расположении.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

Следующий фрагмент кода, который находится в строках 380-477, используется для записи этих разделов реестра.

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### Имена и идентификаторы параметров

Чтобы настроить параметры UEFI Surface или разрешения для параметров UEFI Surface, необходимо обратиться к каждому параметру, указав его имя параметра или идентификатор параметра. После каждого нового обновления для UEFI Surface можно добавить новые параметры. Лучший способ получить полный список параметров, доступных на устройстве Surface (вместе с именем и идентификатором параметров), — использовать сценарий ShowSettingsOptions.ps1 из SEMM_Powershell.zip [для загрузок средства Surface для IT downloads](https://www.microsoft.com/download/details.aspx?id=46703) . 

На компьютере, на котором запущен ShowSettingsOptions.ps1, должен быть установлен диспетчер Microsoft Surface UEFI Manager, но для этого сценария не требуется устройство Surface.

Лучший способ просмотреть наиболее актуальные имена параметров и идентификаторов для устройств — использовать сценарий ConfigureSEMM.ps1 или ConfigureSEMM- <device name> . ps1 из SEMM_Powershell.zip в разделе [средства для загрузки для загрузок](https://www.microsoft.com/download/details.aspx?id=46703).

Имена параметров и идентификаторы для всех устройств можно просмотреть в сценарии ConfigureSEMM.ps1.

В сценариях ConfigureSEMM-. ps1 можно просматривать имена параметров и идентификаторов для определенных устройств <device name> . Например, параметры names и ID для Surface Pro X можно найти в сценарии ConfigureSEMM – ProX.ps1.

## Развертывание сценариев Configuration Manager SEMM

После того как сценарии будут подготовлены для настройки и включения SEMM на клиентском устройстве, следующий шаг — добавить эти сценарии как приложение в Configuration Manager. Прежде чем открыть Configuration Manager, убедитесь в том, что указанные ниже файлы находятся в общей папке, не включающей другие файлы.

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Сертификат SEMM (например, SEMMCertificate. pfx)

Сценарии Configuration Manager SEMM будут добавлены в Configuration Manager как приложение сценария. Команда для установки SEMM с ConfigureSEMM.ps1 описана ниже.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

Команда для удаления SEMM с ResetSEMM.ps1 описана ниже.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Чтобы добавить в приложение Configuration Manager сценарии Configuration Manager SEMM, выполните указанные ниже действия.

1. Запустите мастер создания приложений, выполнив действия 1 – 5 из раздела [развертывание ДИСПЕТЧЕРА UEFI Surface (Майкрософт](#deploy-microsoft-surface-uefi-manager) ), описанного выше в этой статье.

2. Выполните описанные ниже действия с помощью мастера создания приложений.

   - **General (общие** ) — **Укажите сведения о приложении вручную**, а затем нажмите кнопку **Далее**.

   - **Общие сведения** : введите имя приложения (например, SEMM) и любые другие сведения, такие как издатель, версия или комментарии на этой странице. Нажмите кнопку **Далее** , чтобы продолжить.

   - **Каталог приложений** — поля на этой странице можно оставить, указав значения по умолчанию. Выберите **Далее**.

   - **Типы развертывания** : нажмите кнопку **Добавить** , чтобы запустить мастер создания типа развертывания.

   - Следуйте указаниям мастера создания типа развертывания, как описано ниже.

     * **Общие** — выберите **Установщик сценариев** в раскрывающемся меню **Type (тип** ). Параметр " **сведения о типе развертывания** " будет выбран автоматически. Нажмите кнопку **Далее** , чтобы продолжить.
     * **Общие сведения** : введите имя для типа развертывания (например, SEMM), а затем нажмите кнопку **Далее** , чтобы продолжить.
     * **Содержимое** : нажмите кнопку **Обзор** рядом с полем **расположение содержимого** , а затем выберите папку, в которой находятся ваши сценарии Configuration Manager SEMM. В поле **программа установки** введите [команду установки](#deploy-semm-configuration-manager-scripts) , описанную ранее в этой статье. В поле **Удаление программы** введите [команду](#deploy-semm-configuration-manager-scripts) удаления, описанную ранее в этой статье (на рис. 2). Нажмите кнопку **Далее** , чтобы перейти на следующую страницу.
    
     ![Настройка сценариев Configuration Manager SEMM в качестве команд установки и удаления](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Рисунок 2. Настройка сценариев Configuration Manager SEMM в качестве команд установки и удаления*

     * **Метод обнаружения** — выберите **Add (добавить** ), чтобы добавить правило обнаружения разделов реестра для сценария диспетчера конфигураций SEMM. Откроется окно " **правило обнаружения** ", как показано на рисунке 3. Используйте следующие параметры:

       - Выберите **раздел реестра** в раскрывающемся меню **тип параметра** .
       - В раскрывающемся меню **куст** выберите пункт **HKEY_LOCAL_MACHINE** .
       - Введите **SOFTWARE\Microsoft\Surface\SEMM** в поле " **ключ** ".
       - Введите **CertName** в поле **value (значение** ).
       - В раскрывающемся меню **тип данных** выберите пункт **строка** .
       - Выберите **этот параметр реестра должен соответствовать следующему правилу, которое указывает на наличие кнопки приложения** .
       - Введите имя сертификата, введенного в строке 58 сценария, в поле **value (значение** ).
       - Нажмите кнопку **ОК** , чтобы закрыть окно **правила обнаружения** .

     ![Использование раздела реестра для определения устройств, зарегистрированных в SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Рисунок 3. Использование раздела реестра для определения устройств, зарегистрированных в SEMM*

     * Нажмите кнопку **Далее** , чтобы перейти к следующей странице.
     
     * **Взаимодействие с пользователем** : выберите пункт **установить для системы** в раскрывающемся меню **поведение при установке** . Если вы хотите, чтобы ваши пользователи записали и ввели отпечаток сертификата, оставьте требование для входа в систему **только в том случае, если у пользователя есть учетные**данные. Если вы хотите, чтобы ваши администраторы **выписали** отпечаток для пользователей и не должны видеть отпечаток, укажите, входит ли пользователь в раскрывающемся меню " **необходимость входа** в систему".

     * **Требования** : сценарий ConfigureSEMM.ps1 автоматически проверяет, является ли устройство Surface устройством, прежде чем попытаться включить SEMM. Тем не менее, если вы планируете развертывать это приложение этого сценария в коллекции с использованием SEMM, вы можете добавить требования для обеспечения того, что это приложение будет выполняться только на устройствах Surface или устройствах, которыми вы планируете управлять с помощью SEMM. Нажмите кнопку **Далее** , чтобы продолжить.
     
     * **Зависимости** : нажмите кнопку **Добавить** , чтобы открыть окно **Добавление зависимости** .

       * Нажмите кнопку **Добавить** , чтобы открыть окно **укажите требуемое приложение** .

          - Введите имя для зависимостей SEMM в поле **имя группы зависимостей** (например, *SEMM сборки*).

          - В списке **доступных приложений** и типа развертывания MSI выберите **Microsoft Surface UEFI Manager** , а затем нажмите кнопку **ОК** , чтобы закрыть окно **Указание требуемого приложения** .
          
         *   Если вы хотите, чтобы диспетчер Microsoft Surface UEFI автоматически устанавливался на устройствах при попытке включить SEMM с помощью сценариев Configuration Manager, не устанавливайте флажок " **Автоматическая установка** ". Нажмите кнопку **ОК** , чтобы закрыть окно **Добавление зависимости** .

     * Нажмите кнопку **Далее** , чтобы продолжить.
     
     * **Summary (сводка** ): сведения, введенные в мастере создания типа развертывания, отображаются на этой странице. Нажмите кнопку **Далее** , чтобы подтвердить выбор.
     
     * **Ход выполнения** — индикатор выполнения и состояние, так как тип развертывания добавляется для приложения сценария SEMM, отображается на этой странице.
     
     * **Завершение** — подтверждение создания типа развертывания отображается по завершении процесса. Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания типа развертывания.

   - **Сводка** : на экране будут показаны данные, введенные в мастере создания приложений. Нажмите кнопку **Далее** , чтобы создать приложение.

   - **Ход выполнения** : на этой странице отображается индикатор выполнения и состояние, которое приложение добавляет в библиотеку программного обеспечения.

   - **Завершение** — подтверждение успешного создания приложения отображается по завершении процесса создания приложения. Нажмите кнопку **Закрыть** , чтобы завершить работу мастера создания приложений.

После того как приложение сценария будет доступно в библиотеке программного обеспечения Configuration Manager, вы можете распространять и развертывать SEMM с помощью сценариев, подготовленных к устройствам или коллекциям. Если вы настроили сборки Microsoft Surface UEFI Manager как зависимость, которая будет автоматически установлена, вы можете развернуть SEMM за один шаг. Если вы не настроили сборки в качестве зависимости, они должны быть установлены на устройствах, которыми вы планируете управлять, прежде чем включать SEMM.

При развертывании SEMM с помощью этого приложения сценария и конфигурации, видимой для конечного пользователя, сценарий PowerShell запускается и отпечаток сертификата будет отображаться в окне PowerShell. Пользователи могут записать этот отпечаток и ввести его в ответ на запрос UEFI Surface после перезагрузки устройства.

Кроме того, можно настроить автоматическую перезагрузку приложения и установить невидимый для пользователя. В этом случае специалисту потребуется ввести отпечаток на каждом устройстве при перезагрузке. Любой специалист, у которого есть доступ к файлу сертификата, может прочитать отпечаток, просматривая сертификат с помощью CertMgr. Инструкции по просмотру отпечатка с помощью CertMgr находятся в разделе [Создание или изменение сценариев Configuration Manager SEMM](#create-or-modify-the-semm-configuration-manager-scripts) , описанных в этой статье.

Удаление SEMM с устройства, развернутого в Configuration Manager, с помощью этих сценариев так же просто, как и удаление приложения в Configuration Manager. Это действие запускает сценарий ResetSEMM.ps1 и соответствующим образом отменяет регистрацию устройства с помощью того же файла сертификата, который использовался при развертывании SEMM.

> [!NOTE]
> Microsoft Surface рекомендует создавать сбрасывать пакеты только в том случае, если нужно отменить регистрацию устройства. Эти пакеты обычно действительны только для одного устройства, определяемого их порядковым номером. Тем не менее, вы можете создать универсальный пакет сброса, который будет работать для любого устройства, зарегистрированного в SEMM с помощью этого сертификата.
> 
> Настоятельно рекомендуем защитить универсальный пакет сброса так же, как и сертификат, который вы использовали для регистрации устройств в SEMM. Помните, что, точно так же, как и сам сертификат, этот универсальный пакет сброса можно использовать, чтобы отдать заявку на доступ к устройствам Surface из компании SEMM.
> 
> При установке пакета сброса значение, равное минимальному значению (LSV), сбрасывается до значения 1. Вы можете повторно зарегистрировать устройство, используя существующий пакет конфигурации. Устройство будет запрашивать отпечаток сертификата перед тем, как будет сделан владелец.
> 
> По этой причине для повторной регистрации устройства в SEMM потребуется создать и установить на нем новый пакет. Так как это действие является новой регистрацией, а не изменением в конфигурации устройства, уже зарегистрированного в SEMM, устройство будет запрашивать отпечаток сертификата, прежде чем будет сделан владелец.
