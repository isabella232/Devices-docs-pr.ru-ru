---
title: Справочник по номерам SKU системы Surface
description: См. ссылку на имена системной модели и SKU системы для всех устройств Surface.
keywords: uefi, настройка, прошивка, безопасность, semm, Автопилот
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/02/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 71ded9892e9dde8de1976a89214ea946e1bd1da4
ms.sourcegitcommit: 657d0d73a51f0dd35ad60740ed523164a55d2e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2021
ms.locfileid: "11720923"
---
# <a name="surface-system-sku-reference"></a>Справочник по номерам SKU системы Surface

В этом документе содержится ссылка, которая может использоваться для различных ИТ-задач, таких как регистрация устройств Surface с помощью Windows автопилота или проверка состояния машины определенного устройства с помощью PowerShell или WMI.

System Model и System SKU — это переменные, которые хранятся в таблицах System Management BIOS (SMBIOS) в уровне UEFI устройств Surface. Используйте имя SKU system всякий раз, когда необходимо различать устройства с одинаковым именем system Model, такие как Surface Pro и Surface Pro с LTE Advanced.

| Устройство   | Модель системы | System SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Северная Америка                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE за пределами Северной Америки и Y!mobile в Японии | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro с функцией LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | Surface Go | Surface_Go_1825_Commercial |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Коммерческий                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Потребительский                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Коммерческий                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X с процессором SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop 4 13" Intel | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop 4 15" Intel | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop 4 15" AMD   | Surface Laptop 4 | Surface_Laptop_4_1952:1953     |
| Surface Laptop 4 13"AMD   | Surface Laptop 4 | Surface_Laptop_4_1958:1959    |
| Surface Hub 2S 50"  | Surface Hub 2S | Surface Hub 2S   |
| Surface Hub 2S 85"  | Surface Hub 2S | Surface Hub 2S 85   |
| Surface Studio | Surface Studio | Surface_Studio   |
| Surface Studio 2 | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |
|

## <a name="examples"></a>Примеры:

**Ирисовка SKU с помощью PowerShell**  
Используйте следующую команду PowerShell для получения сведений о SKU system:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Ирисовка SKU с помощью Сведения о системе**  
Вы также можете найти системную SKU и system Model для устройства в **Сведения о системе.** Для этого выполните следующие действия:

1. Выберите **Начните,** а затем введите **MSInfo32** в поле поиска.  
1. Выберите **Сведения о системе**.

**Использование SKU в состоянии WMI последовательности задач**  
Сведения о SKU system можно использовать в microsoft Deployment набор средств (MDT) или Microsoft Endpoint Configuration Manager как часть состояния WMI последовательности задач.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## <a name="learn-more"></a>Подробнее

- [Справка по WMI](/windows/win32/wmisdk/wmi-reference)
- [Поддержка регистрации Surface для Windows Autopilot](surface-autopilot-registration-support.md)
