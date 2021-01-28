---
title: Справочник по номерам SKU системы Surface
description: См. ссылку на имена системной модели и системного SKU для всех устройств Surface.
keywords: uefi, configure, firmware, secure, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/27/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 0fe13750e7e8c8188b52726c114a6b3668434d39
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304832"
---
# Справочник по номерам SKU системы Surface

В этом документе содержится ссылка, которую можно использовать для различных ИТ-задач, таких как регистрация устройств Surface в Windows Autopilot или проверка состояния компьютера конкретного устройства с помощью PowerShell или WMI.

Системная модель и системный SKU — это переменные, которые хранятся в таблицах SYSTEM Management BIOS (SMBIOS) на уровне UEFI устройств Surface. Используйте имя system SKU всякий раз, когда нужно различать устройства с одинаковым именем системной модели, например Surface Pro и Surface Pro с LTE Advanced.

| Устройство   | Системная модель | Системный SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE North America                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE за пределами Северной Америки и Y!mobile в Японии | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro с функцией LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | System Go | Surface_Go_1825_Commercial |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7 и более                                               | Surface Pro 7 и более | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7 и более | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X с процессором SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## Примеры: 

**Искомый SKU с помощью PowerShell**  
Чтобы получить сведения о системном SKU, используйте следующую команду PowerShell:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Искомый SKU с помощью сведений о системе**  
Системную SKU и системную модель для устройства также можно найти в **сведениях о системе.** Для этого выполните указанные ниже действия.

1. Выберите **"Начните"** и введите **MSInfo32** в поле поиска.  
1. Выберите **сведения о системе.**

**Использование SKU в условии WMI последовательности задач**  
Сведения о системном SKU можно использовать в microsoft Deployment набор средств (MDT) или Microsoft Endpoint Configuration Manager как часть условия WMI последовательности задач.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

## Подробнее

- [Справочник по WMI](https://docs.microsoft.com/windows/win32/wmisdk/wmi-reference)
- [Поддержка регистрации Surface для Windows Autopilot](surface-autopilot-registration-support.md)
