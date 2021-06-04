---
title: Инструмент тега актива Surface
description: В этой статье объясняется, как использовать инструмент тега актива Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834747"
---
# Инструмент тега актива Surface

Тег актива Surface — это служебная программа интерфейса командной строки (CLI), позволяющая просматривать, назначать и изменять назначенные значения тегов ресурсов для устройств Surface. Она работает на Surface Pro 3 и всех современных устройствах Surface.

##  <a name="system-requirements"></a>Требования к системе

- Surface Pro 3 или более поздней версии

- Встроенное по UEFI версии 3.9.150.0 или более поздней.

##  <a name="using-surface-asset-tag-"></a>Использование тега актива Surface 

Чтобы запустить тег актива Surface, сделайте следующее:

1.  На устройстве Surface Скачайте **ресурс surface Tag.zip** из [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=46703), извлеките zip-файл и AssetTag.exe сохраните его в нужной папке (в этом примере — C:\\assets).

    > [!NOTE]
    > Для Surface Pro X используйте приложение с именем **AssetTag_x86** в ZIP-файле. 

2.  Откройте командную консоль от имени администратора и запустите AssetTag.exe, указав полный путь к инструменту.

3.  Перезапустите Surface.

###  <a name="asset-tag-tool-commands"></a>Команды инструмента «тег актива»   
В приведенных ниже примерах AssetTag.exe сохраняется в каталоге на локальном компьютере (C:\assets). 

Чтобы получить нужный тег актива, выполните AssetTag-g.

**Пример.**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 Чтобы очистить предложенный тег актива, выполните AssetTag-s.
 
 **Пример.**
 
   ```
C:\assets\AssetTag.exe -s
  ```
Чтобы установить предложенный тег актива, выполните AssetTag-s testassettag12.

**Пример.**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>Значение тега актива должно содержать от 1 до 36 символов. Допустимые символы включают A-Z, a-z, 0-9, точки (.) и дефис (-).


##  <a name="managing-asset-tags"></a>Управление тегами ресурсов

Вы можете просмотреть существующий тег актива в параметрах UEFI в разделе сведения об устройстве (**Панель управления > восстановление > Расширенная загрузка > перезапустить прямо сейчас**.)

На рисунке ниже показаны результаты выполнения инструмента "тег актива" на Surface go.

![Результаты выполнения инструмента тега актива Surface на Surface go.
](images/assettag-fig1.png)

> **Рисунок 1.** Результаты выполнения инструмента тега актива Surface на Surface Go

Кроме того, с помощью WMI можно запросить существующий тег актива на устройстве.

(Get-WmiObject-запрос "SELECT * FROM Win32_SystemEnclosure")

**Пример.**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
###  <a name="using-powershell"></a>Использование PowerShell

Ниже приведен сценарий, который можно использовать для того, чтобы вычислить предлагаемое значение и интерпретировать все ошибки.

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
