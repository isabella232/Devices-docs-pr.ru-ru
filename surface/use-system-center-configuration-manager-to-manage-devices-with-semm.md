---
title: Использование Microsoft Endpoint Configuration Manager для управления устройствами с помощью SEMM
description: Узнайте, как управлять режимом управления microsoft Surface Enterprise (SEMM) с помощью диспетчера конфигурации конечных точек.
keywords: регистрация, обновление, сценарии, параметры
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 9f3db9428e188aa20399d26c066507d76c90ba57
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708790"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>Использование Microsoft Endpoint Configuration Manager для управления устройствами с помощью SEMM

Функция Microsoft Surface Enterprise (SEMM) устройств Surface UEFI позволяет администраторам управлять и обеспечивать безопасность конфигурации параметров Surface UEFI. Для большинства организаций этот процесс выполняется путем создания пакетов Windows (.msi) с помощью средства настройки Microsoft Surface UEFI. Затем эти пакеты запускаются или развертываются на клиентских устройствах Surface для регистрации устройств в SEMM и обновления конфигурации параметров Surface UEFI.

Для организаций с Microsoft Endpoint Configuration Manager существует альтернатива использованию процесса настройки microsoft Surface UEFI .msi для развертывания и администрирования SEMM. Microsoft Surface UEFI Manager — это легкий установщик, который делает необходимые сборки для управления SEMM доступными на устройстве. Установив эти сборки с помощью Microsoft Surface UEFI Manager на управляемом клиенте, SEMM может управляться диспетчером конфигурации с помощью сценариев PowerShell, развернутых в качестве приложений. С помощью этого процесса управление SEMM выполняется в диспетчере конфигурации, что устраняет необходимость в внешнем средстве настройки Microsoft Surface UEFI.

> [!Note]
> Хотя описанный в этой статье процесс может работать с более ранними версиями Endpoint Configuration Manager или с другими сторонними решениями управления, управление SEMM с Microsoft Surface UEFI Manager и PowerShell поддерживается только с текущим филиалом Endpoint Configuration Manager.

#### <a name="prerequisites"></a>Предварительные требования

Перед началом процесса, описанного в этой статье, ознакомьтесь со следующими технологиями и средствами:

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md)
* [Сценарий PowerShell](/powershell)
* [Развертывание приложений с помощью диспетчера конфигурации](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> Вам также потребуется доступ к сертификату, который вы собираетесь использовать для обеспечения безопасности SEMM. Сведения о требованиях к этому сертификату см. в материале [Surface Enterprise management Mode certificate requirements.](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)
> 
> Очень важно, чтобы этот сертификат был сохранен в безопасном расположении и должным образом сохранен. Если этот сертификат становится потерянным или непригодным для потери, невозможно сбросить Surface UEFI, изменить управляемые параметры Surface UEFI или удалить SEMM с зарегистрированного устройства Surface.

#### <a name="download-microsoft-surface-uefi-manager"></a>Скачайте Microsoft Surface UEFI Manager

Управление SEMM с диспетчером конфигурации требует установки microsoft Surface UEFI Manager на каждое клиентное устройство Surface. Вы можете скачать Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) со страницы [Surface Tools для ИТ](https://www.microsoft.com/download/details.aspx?id=46703) в Центре загрузки Майкрософт.

#### <a name="download-semm-scripts-for-configuration-manager"></a>Скачайте сценарии SEMM для Configuration Manager

После установки microsoft Surface UEFI Manager на клиентский планшет Surface SEMM можно развернуть и управлять с помощью скриптов PowerShell. Получите примеры сценариев [управления SEMM,](https://www.microsoft.com/download/details.aspx?id=46703) скачав SEMM_PowerShell.zip surface Tools для ИТ.

## <a name="deploy-microsoft-surface-uefi-manager"></a>Развертывание microsoft Surface UEFI Manager

Развертывание Microsoft Surface UEFI Manager является типичным развертыванием приложений. Файл установщика Microsoft Surface UEFI Manager является стандартным Windows установщика, который можно установить со стандартным тихим [параметром.](https://msdn.microsoft.com/library/windows/desktop/aa367988)

Команда установки Microsoft Surface UEFI Manager является следующим образом.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

Команда по отображению microsoft Surface UEFI Manager будет выполняться следующим образом.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Чтобы создать новое приложение и развернуть его в коллекцию устройств Surface, выполните следующие действия:

1. Откройте консоль диспетчера конфигурации из меню **"Пуск"** или **"Пуск".**
2. Выберите **библиотеку программного** обеспечения в левом нижнем углу окна.
3. **Расширь** узел управления приложениями библиотеки программного обеспечения, а затем выберите **Приложения.**
4. Выберите **кнопку Создать приложение** в вкладке **Главная** в верхней части окна. Это запускает мастер создания приложений.
5. Мастер создания приложений представляет ряд действий:

   * **General** . **Автоматически обнаруживаемая информация об этом** приложении из параметра файлов установки выбирается по умолчанию. В поле **Type** **Windows (.msi файл)** также выбирается по умолчанию. Выберите **Просмотр,** чтобы перейти к **SurfaceUEFIManagerSetup.msi, **а затем выберите **Далее**.
   
      > [!Note]
      > Расположение SurfaceUEFIManagerSetup.msi должно быть на сетевой совместной основе и расположено в папке, которая не содержит других файлов. Расположение локального файла невозможно использовать.

   * **Сведения о** импорте — мастер создания приложений разобьет файл .msi и прочитает имя приложения **и** код **продукта.** SurfaceUEFIManagerSetup.msi должен быть указан как единственный файл в строке **Content Files,** как показано на рисунке 1. Выберите **Далее,** чтобы продолжить.

      ![Сведения из установки Surface UEFI Manager автоматически размыкаются](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Рисунок 1. Сведения из установки Microsoft Surface UEFI Manager автоматически размыкаются*

   * **Общие сведения** . Вы можете изменить имя приложения и сведения о издателе и версии, а также добавить комментарии на этой странице. Команда установки для Microsoft Surface UEFI Manager отображается в поле Программа установки. По умолчанию установка Установки для системы позволит Microsoft Surface UEFI Manager установить необходимые сборки для SEMM, даже если пользователь не вошел на устройство Surface. Выберите **Далее,** чтобы продолжить.
   * **Сводка** . На этой странице отображаются сведения, которые были разобрано в шаге **Импортная** информация, а также выборы из шага **"Общие** сведения". Выберите **Далее,** чтобы подтвердить выбор и создать приложение.
   * **Progress** — отображает планку прогресса и состояние, так как приложение импортируется и добавляется в библиотеку программного обеспечения.
   * **Завершение** — подтверждение успешного создания приложения отображается после завершения процесса создания приложения. Выберите **Рядом,** чтобы завершить мастер создания приложений.

После создания приложения в диспетчере конфигурации его можно распределить по точкам распространения и развернуть в коллекциях, включая устройства Surface. Это приложение не устанавливает и не включает SEMM на устройстве Surface. Он предоставляет только сборки, необходимые для включения SEMM с помощью сценария PowerShell.

Если вы не хотите устанавливать сборки Microsoft Surface UEFI Manager на устройствах, которые не будут управляться с SEMM, можно настроить Microsoft Surface UEFI Manager в зависимости от скриптов диспетчера конфигурации SEMM. Этот сценарий далее в этой статье см. в разделе Развертывание сценариев конфигурации диспетчера [SEMM.](#deploy-semm-configuration-manager-scripts)

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>Создание или изменение скриптов диспетчера конфигурации SEMM

После установки необходимых сборок на устройствах процесс регистрации устройств в SEMM и настройки Surface UEFI делается с помощью сценариев PowerShell и развертывается в качестве приложения-скрипта с помощью Configuration Manager. Эти скрипты можно изменить, чтобы соответствовать потребностям организации и среды. Например, можно создать несколько конфигураций для управляемых устройств Surface в различных отделах или ролях. Примеры сценариев SEMM и Configuration Manager можно скачать по ссылке в разделе [Предварительные](#prerequisites) условия в начале этой статьи.

Для выполнения развертывания SEMM с помощью Configuration Manager необходимо выполнить два основных сценария:

* **ConfigureSEMM.ps1** . Используйте этот скрипт для создания пакетов конфигурации для устройств Surface с нужными настройками Surface UEFI для применения указанных параметров на устройстве Surface, для регистрации устройства в SEMM и установки ключа реестра, используемого для определения регистрации устройства в SEMM.
* **ResetSEMM.ps1** — используйте этот скрипт для сброса SEMM на устройстве Surface, которое удаляет его из SEMM и удаляет контроль над настройками Surface UEFI.

Примеры сценариев включают примеры установки параметров Surface UEFI и управления разрешениями для этих параметров. Эти параметры можно изменить, чтобы обеспечить безопасность Surface UEFI и установить параметры Surface UEFI в соответствии с потребностями среды. В следующих разделах этой статьи объясняется ConfigureSEMM.ps1 сценарий и изучаются изменения, которые необходимо внести в сценарий, чтобы соответствовать вашим требованиям.

> [!NOTE]
> Скрипты диспетчера конфигурации SEMM и экспортируемого файла сертификата SEMM (.pfx) должны быть помещены в ту же папку без других файлов, прежде чем они будут добавлены в Configuration Manager.

### <a name="specify-certificate-and-package-names"></a>Укажите имена сертификатов и пакетов

Первым регионом скрипта, который необходимо изменить, является часть, которая указывает и загружает сертификат SEMM, а также указывает версию SurfaceUEFIManager, а также имена пакета конфигурации SEMM и пакета сброса SEMM. Имя сертификата и версия SurfaceUEFIManager указаны в строках 56-73 в ConfigureSEMM.ps1 скрипте.

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

Замените **значение FabrikamSEMMSample.pfx** для переменной $certName имя файла сертификата SEMM на строке 58. **** Сценарий создаст рабочий каталог (с именем Config) в папке, где расположены сценарии, а затем копирует файл сертификата в этот рабочий каталог.

Пакет владельца и пакет сброса также будут созданы в каталоге Config и будут удерживать конфигурацию для параметров и разрешений Surface UEFI, созданных сценарием.

На строке 73 **замените** значение переменной $password с **1234** на пароль для файла сертификата. Если пароль не требуется, удалите текст **1234.**

> [!Note]
> Два последних символа отпечатка пальца сертификата необходимы для регистрации устройства в SEMM. Этот скрипт отображает эти цифры пользователю, что позволяет пользователю или технику записывать эти цифры перед перезагрузкой системы для регистрации устройства в SEMM. Для этого скрипт использует следующий код, найденный на строках 150-155.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Администраторы с доступом к файлу сертификата (.pfx) могут прочитать отпечатки пальцев в любое время, открыв файл .pfx в CertMgr. Чтобы просмотреть отпечатки пальцев в CertMgr, выполните этот процесс:

1. Щелкните правой кнопкой мыши файл .pfx и выберите **Открыть**.
2. Расширь папку в области навигации.
3. Выбор **сертификатов**.
4. Щелкните правой кнопкой мыши сертификат на главной области, а затем выберите **Открыть**.
5. Выберите **вкладку Details.**
6. **Все** или **только свойства** должны быть выбраны в выпадаемом меню **Show.**
7. Выберите поле **Thumbprint**.

> [!NOTE]
> Имя и пароль сертификата SEMM также должны быть введены в этом разделе сценария ResetSEMM.ps1, чтобы диспетчер конфигурации удалял SEMM с устройства с помощью действия удаления.

### <a name="configure-permissions"></a>Настройка разрешений

Первым регионом скрипта, в котором будет указана конфигурация surface UEFI, является область **Настройка разрешений.** Этот регион начинается в строке 210 в примере сценария с комментарием **#Configure Permissions** и продолжает строку 247. Следующий фрагмент кода сначала устанавливает разрешения для всех параметров Surface UEFI, чтобы они могли изменяться только SEMM, а затем добавляет явные разрешения, чтобы разрешить местному пользователю изменять пароль Surface UEFI, TPM, а также фронтальная и задняя камеры.

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

Каждая **переменная $uefiV 2** определяет параметр Surface UEFI, задав имя или идентификатор, а затем настраивает разрешения на одно из следующих значений:

* **$ownerOnly** — разрешение на изменение этого параметра предоставляется только SEMM.
* **$ownerAndLocalUser** — разрешение на изменение этого параметра предоставляется локальному пользователю, загружающимся в Surface UEFI, а также SEMM.

Сведения о доступных именах параметров и ID для Surface UEFI можно найти в разделе [Параметры и IDs](#settings-names-and-ids) этой статьи.

### <a name="configure-settings"></a>Настройка параметров

Второй областью сценария, в котором будет указана конфигурация **** surface UEFI, является область Параметры сценария ConfigureSEMM.ps1, которая настраивает, включен ли каждый параметр или отключен. Пример сценария содержит инструкции по настройке всех параметров к значениям по умолчанию. Затем сценарий содержит четкие инструкции по отключению IPv6 для загрузки PXE и оставлению пароля администратора Surface UEFI без изменений. Этот регион можно найти начиная с **комментария #Configure Параметры** строки 291 по строке 335 в примере сценария. Область отображается следующим образом.

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

Как и разрешения, заданная в разделе **Настройка** разрешений сценария, конфигурация каждого параметра Surface UEFI выполняется путем определения **переменной $uefiV 2.** Для каждой строки, определяющей переменную **$uefiV 2,** параметр Surface UEFI определяется по параметру **** имя или ID, а настроенное значение задаваемое значение включено или **отключено.**

Если вы не хотите изменять конфигурацию параметра Surface UEFI, например, чтобы убедиться, что пароль администратора Surface UEFI не очищается действием сброса всех параметров Surface UEFI по умолчанию, вы можете использовать **ClearConfiguredValue()** для обеспечения того, чтобы этот параметр не был изменен. В примере сценария это используется в строке 323 для предотвращения очистки пароля администратора Surface UEFI, установленного в примере скрипта по его параметру ID **501**.

Сведения о доступных именах параметров и ID для Surface UEFI можно найти в разделе Параметры имена и [ID в](#settings-names-and-ids) этой статье.

### <a name="settings-registry-key"></a>Параметры реестра

Чтобы определить зарегистрированные системы для диспетчера конфигурации, ConfigureSEMM.ps1 скрипт записывает ключи реестра, которые можно использовать для идентификации зарегистрированных систем как установленных с помощью сценария конфигурации SEMM. Эти ключи можно найти в следующем расположении.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

Для записи этих ключей реестра используется следующий фрагмент кода, найденный в строках 380-477.

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

### <a name="settings-names-and-ids"></a>Параметры и ID

Чтобы настроить параметры Surface UEFI или разрешения для параметров Surface UEFI, необходимо сослаться на каждый параметр либо по его имени, либо по параметру ID. С каждым новым обновлением для Surface UEFI могут быть добавлены новые параметры. Запуск ShowSettingsOptions.ps1 (от SEMM_Powershell.zip в Surface [Tools для ИТ)предоставляет](https://www.microsoft.com/download/details.aspx?id=46703)сведения о доступных параметрах. На компьютереShowSettingsOptions.ps1 на котором ShowSettingsOptions.ps1, должен быть установлен менеджер Microsoft Surface UEFI, но для сценария не требуется устройство Surface.


## <a name="deploy-semm-configuration-manager-scripts"></a>Развертывание скриптов диспетчера конфигурации SEMM

После подготовки скриптов к настройке и встройке SEMM на клиентских устройствах следующий шаг — добавление этих скриптов в качестве приложения в Configuration Manager. Перед открытием диспетчера конфигурации убедитесь, что следующие файлы находятся в общей папке, которая не включает другие файлы:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Сертификат SEMM (например, SEMMCertificate.pfx)

Скрипты диспетчера конфигурации SEMM будут добавлены в Configuration Manager в качестве приложения скрипта. Команда установки SEMM с ConfigureSEMM.ps1 следующим образом.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

Команда удалить SEMM с помощью ResetSEMM.ps1 следующим образом.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Чтобы добавить скрипты диспетчера конфигурации SEMM в Configuration Manager в качестве приложения, используйте следующий процесс:

1. Начните мастер создания приложений с помощью шага 1-5 из раздела [Развертывание Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) ранее в этой статье.

2. Проследовать через мастер создания приложений следующим образом:

   - **Общие** . Выберите **вручную указать сведения о приложении,** а затем выберите **Далее**.

   - **Общие сведения** — введите имя приложения (например SEMM) и любые другие сведения, такие как издатель, версия или комментарии на этой странице. Выберите **Далее,** чтобы продолжить.

   - **Каталог приложений** — поля на этой странице могут быть оставлены со значениями по умолчанию. Выберите **Далее**.

   - **Типы развертывания** . **Выберите Добавить,** чтобы запустить мастер типа развертывания.

   - Выполните следующие действия мастера типа развертывания:

     * **Общие** — выберите **установщик скриптов** из выпадаемого меню **Type.** Автоматически **будет выбран параметр сведения о** типе развертывания вручную. Выберите **Далее,** чтобы продолжить.
     * **Общие сведения** — введите имя типа развертывания (например, сценарии конфигурации SEMM), а затем выберите **Далее** для продолжения.
     * **Содержимое** — **выберите Обзор** рядом с полем **Расположение** контента, а затем выберите папку, в которой расположены скрипты конфигурации SEMM. В поле **Программа установки** введите команду [установки,](#deploy-semm-configuration-manager-scripts) найденную ранее в этой статье. В поле **Uninstall Program** [](#deploy-semm-configuration-manager-scripts) введите команду удалить, найденную ранее в этой статье (показано на рисунке 2). Выберите **Далее,** чтобы перейти на следующую страницу.
    
     ![Установите скрипты диспетчера конфигурации SEMM в качестве команд установки и списания](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Рисунок 2. Установите скрипты диспетчера конфигурации SEMM в качестве команд установки и списания*

     * **Метод обнаружения** — **выберите пункт Добавить,** чтобы добавить правило обнаружения ключей реестра ключей для реестра скриптов SEMM Configuration Manager. Отображается **окно Правила** обнаружения, как показано на рисунке 3. Используйте следующие параметры:

       - Выберите **реестр из** выпадаемого меню Setting **Type.**
       - Выберите **HKEY_LOCAL_MACHINE** из выпадаемого меню **Hive.**
       - Введите **SOFTWARE\Microsoft\Surface\SEMM** в **поле Key.**
       - Введите **CertName** в поле **Значение.**
       - Выберите **Строку** **из** выпадаемого меню Типа данных.
       - Выберите параметр **Этот реестр, который должен удовлетворять следующему правилу, чтобы указать** наличие этой кнопки приложения.
       - Введите имя сертификата, введенного в строке 58 сценария в поле **Значение.**
       - Выберите **ОК,** чтобы закрыть **окно Правила обнаружения.**

     ![Использование ключа реестра для идентификации устройств, зарегистрированных в SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Рисунок 3. Использование ключа реестра для идентификации устройств, зарегистрированных в SEMM*

     * Выберите **Далее,** чтобы перейти к следующей странице.
     
     * **Пользовательский опыт** . **Выберите Установить для системы из** выпадающее меню поведения установки. **** Если вы хотите, чтобы пользователи сами записывали и вводили отпечатки пальцев сертификата, оставьте требование к логотипу только при входе пользователя в **систему**. Если вы хотите, чтобы администраторы вводили отпечатки пальцев для пользователей, а **** пользователям не нужно видеть отпечатки пальцев, выберите, входит ли пользователь в систему из выпадаемого меню **Logon Requirement.**

     * **Требования** — сценарий ConfigureSEMM.ps1 автоматически проверяет, что устройство является устройством Surface перед попыткой включить SEMM. Однако если вы собираетесь развернуть это приложение-скрипт в коллекцию с устройствами, не управляемыми с ПОМОЩЬЮ SEMM, здесь можно добавить требования, чтобы убедиться, что это приложение будет работать только на устройствах Surface или устройствах, которыми вы собираетесь управлять с ПОМОЩЬЮ SEMM. Выберите **Далее,** чтобы продолжить.
     
     * **Зависимостей** . **Выберите Добавить,** чтобы открыть окно **Добавить зависимость.**

       * Выберите **Добавить,** чтобы открыть **окно "Необходимое приложение".**

          - Введите имя зависимостей SEMM в поле **Имя** группы зависимостей (например, *сборки SEMM).*

          - Выберите **диспетчер UEFI** Microsoft Surface **** из списка доступных приложений и типа **** развертывания MSI, а затем выберите ОК, чтобы закрыть окно **"Обязательное** приложение".
          
         *   Если **вы** хотите, чтобы microsoft Surface UEFI Manager автоматически устанавливался на устройствах, при попытке включить SEMM со скриптами Configuration Manager, выберите поле автоматической установки. Выберите **ОК,** чтобы закрыть **окно Добавить зависимость.**

     * Выберите **Далее,** чтобы продолжить.
     
     * **Сводка.** Сведения, которые вы ввели в мастере типа создания развертывания, отображаются на этой странице. Выберите **Далее,** чтобы подтвердить выбор.
     
     * **Progress** — на этой странице отображается планка прогресса и состояние типа развертывания для приложения-скрипта SEMM.
     
     * **Завершение** — подтверждение создания типа развертывания отображается после завершения процесса. Выберите **Рядом,** чтобы завершить мастер типа развертывания.

   - **Сводка** . Отображаются сведения, которые вы ввели в мастер создания приложений. Выберите **Далее,** чтобы создать приложение.

   - **Progress** — на этой странице отображается планка прогресса и состояние приложения, добавленного в библиотеку программного обеспечения.

   - **Завершение** — подтверждение успешного создания приложения отображается после завершения процесса создания приложения. Выберите **Рядом,** чтобы завершить мастер создания приложений.

После того как приложение скрипта будет доступно в библиотеке конфигурации Диспетчер программного обеспечения, вы можете распространять и развертывать SEMM с помощью сценариев, подготовленных для устройств или коллекций. Если вы настроили сборки Microsoft Surface UEFI Manager в качестве зависимостей, которые будут автоматически установлены, можно развернуть SEMM за один шаг. Если сборки не настроены как зависимость, их необходимо установить на устройствах, которые вы собираетесь управлять, прежде чем включить SEMM.

При развертывании SEMM с помощью этого приложения-скрипта и конфигурации, которая видна конечному пользователю, начнется скрипт PowerShell, а отпечатки пальцев для сертификата будут отображаться в окне PowerShell. Пользователи могут записывать этот отпечатки пальцев и вводить их по запросу Surface UEFI после перезагрузки устройства.

Кроме того, можно настроить установку приложения для автоматической перезагрузки и незримой установки для пользователя. В этом сценарии техник должен будет ввести отпечатки пальцев на каждом устройстве при перезагрузке. Любой специалист с доступом к файлу сертификата может прочитать отпечатки пальцев, просмотрев сертификат с помощью CertMgr. Инструкции по просмотру отпечатка пальца с помощью CertMgr находятся в разделе Создание или изменение скриптов [конфигурации SEMM в](#create-or-modify-the-semm-configuration-manager-scripts) этой статье.

Удаление SEMM с устройства, развернутого с помощью диспетчера конфигурации с помощью этих скриптов, так же просто, как и удаление приложения с помощью Configuration Manager. Это действие запускает сценарий ResetSEMM.ps1 и должным образом разворачивает устройство с тем же файлом сертификата, который использовался во время развертывания SEMM.

> [!NOTE]
> Microsoft Surface рекомендует создавать пакеты сброса только при необходимости открепить устройство. Эти пакеты сброса обычно допустимы только для одного устройства, определенного по его серийному номеру. Однако можно создать универсальный пакет сброса, который будет работать для любого устройства, зарегистрированного в SEMM с помощью этого сертификата.
> 
> Настоятельно рекомендуется защитить универсальный пакет сброса так же тщательно, как сертификат, который вы использовали для регистрации устройств в SEMM. Помните, что, как и сам сертификат, этот универсальный пакет сброса можно использовать для отгрузки любых устройств Surface организации из SEMM.
> 
> При установке пакета сброса минимальное поддерживаемые значения (LSV) сбрасываются до значения 1. Вы можете переокрепить устройство с помощью существующего пакета конфигурации. Устройство будет подсказывать отпечатки пальцев сертификата перед тем, как будет принято право собственности.
> 
> По этой причине для повторного создания устройства в SEMM потребуется создать и установить новый пакет на этом устройстве. Так как это действие является новой регистрацией, а не изменением конфигурации устройства, уже зарегистрированного в SEMM, устройство будет подсказывать отпечатки пальцев сертификата до того, как будет принято право собственности.
