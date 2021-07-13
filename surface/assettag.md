---
title: Средство тегов surface Asset
description: В этом разделе объясняется, как использовать средство тегов Surface Asset.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643835"
---
# <a name="surface-asset-tag-tool"></a>Средство тегов surface Asset

Surface Asset Tag — это утилита интерфейса командной строки (CLI), которая позволяет просматривать, назначать и изменять назначенное значение тега активов для устройств Surface. Он работает на Surface Pro 3 и на всех более новых устройствах Surface.

## <a name="system-requirements"></a>Требования к системе

- Surface Pro 3 или более поздней

- Прошивка UEFI версии 3.9.150.0 или более поздней версии

## <a name="using-surface-asset-tag"></a>Использование тега Surface Asset

Для запуска тега Surface Asset:

1. На устройстве Surface скачайте **surface Asset Tag.zip** центра загрузки Майкрософт, извлеките почтовый файл и сохраните AssetTag.exe в нужной папке (в этом примере C:\\assets). [](https://www.microsoft.com/download/details.aspx?id=46703)

    > [!NOTE]
    > Для Surface Pro X используйте приложение с именем **AssetTag_x86** в файле ZIP.

2. Откройте консоль команды в качестве администратора и запустите AssetTag.exe, введите полный путь к инструменту.

3. Перезапустите Surface.

    > [!NOTE]
    > После настройки тега актива требуется вторая перезагрузка, прежде чем он появится в WMI.

### <a name="asset-tag-tool-commands"></a>Команды средств тегов активов

В следующих примерах AssetTag.exe в каталоге локального компьютера (C:\assets).

Чтобы получить предложенный тег активов, **запустите AssetTag -g:**

```console
C:\assets\AssetTag.exe -g
```

Чтобы очистить предложенный тег активов, **запустите AssetTag -s:**

```console
C:\assets\AssetTag.exe -s
```

Чтобы установить предложенный тег активов, **запустите AssetTag -s testassettag12:**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>Значение тега актива должно содержать от 1 до 36 символов. Допустимые символы включают A-Z, a-z, 0-9, period (.) и hyphen (-).

## <a name="managing-asset-tags"></a>Управление тегами активов

Вы можете просмотреть существующий тег актива в параметрах UEFI в статье Сведения об устройстве (панель управления >**восстановления > advanced startup > перезапуска**сейчас.)

На рисунке ниже показаны результаты запуска средства тегов активов в Surface Go.

![Результаты запуска средства Теги surface Asset на Surface Go.](images/assettag-fig1.png)

> **Рисунок 1.** Результаты запуска средства тегов surface Asset на Surface Go

Поочередно можно использовать WMI для запроса существующего тега активов на устройстве:

(Get-WmiObject -query "Select * from Win32_SystemEnclosure")

### <a name="example"></a>Пример

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>Использование PowerShell

Сценарий ниже можно использовать для получения предлагаемого значения и интерпретации ошибок.

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```
