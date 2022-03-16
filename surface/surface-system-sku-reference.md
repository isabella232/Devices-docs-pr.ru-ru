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
ms.date: 02/03/2022
ms.reviewer: carlol
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 45fd61ff59273e5ae3fc269058b663f271e641d4
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448692"
---
# <a name="surface-system-sku-reference"></a>Справочник по номерам SKU системы Surface

В этом документе содержится ссылка, которая может использоваться для различных ИТ-задач, таких как выполнение команд или установка драйверов на основе имен модели устройства или SKU. System Model и System SKU — это переменные, хранимые в таблицах System Management BIOS (SMBIOS) в уровне UEFI устройств Surface. Используйте имя SKU system всякий раз, когда необходимо различать устройства с одинаковым именем system Model, например Surface Pro и Surface Pro с LTE Advanced. SkUs, перечисленные в следующей таблице, относятся к коммерческим устройствам, если они не помечены как Consumer. 

| Устройство   | Модель системы | System SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 Wi-FI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Северная Америка                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE за пределами Северной Америки и Y!mobile в Японии | Surface 3        | Surface_3_ROW                    |
| Surface Book 2 13"                                           | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                           | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                           | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                           | Surface Book 3   | Surface_Book_3_1899
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go LTE Commercial                                    | Surface Go       | Surface_Go_1825_Commercial |
| Surface Go 2 Commercial                                      | Surface Go 2     | Surface_Go_2_1926                |
| Surface Go 2 Consumer                                        | Surface Go 2     | Surface_Go_2_1901                |
| Surface Go 2 LTE                                             | Surface Go 2     | Surface_Go_2_1927                |
| Surface Go 3 Commercial                                      | Surface Go 3     | Surface_Go_3_1926                |
| Surface Go 3 Consumer                                        | Surface Go 3     | Surface_Go_3_1901                |
| Surface Go 3 LTE                                             | Surface Go 3     | Surface_Go_3_2022                |
| Surface Hub 2S 50"                                           | Surface Hub 2S   | Surface Hub 2S                   |
| Surface Hub 2S 85"                                           | Surface Hub 2S   | Surface Hub 2S 85                |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Коммерческий                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Laptop 2 Потребительский                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 3 13" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15 " AMD                                     | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop 3 15" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 4 13" AMD                                     | Surface Laptop 4 | Surface_Laptop_4_1958:1959    |
| Surface Laptop 4 13" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop 4 15 " AMD                                     | Surface Laptop 4 | Surface_Laptop_4_1952:1953     |
| Surface Laptop 4 15" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop Go                                            | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop SE                                            | Surface Laptop SE | Surface Laptop SE            |
| Surface Laptop Studio                                        | Surface Laptop Studio | Surface_Laptop_Studio_1964 |
| Surface Pro (5th Gen)                                        | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro с LTE Advanced (5th Gen)                      | Surface Pro      | Surface_Pro_1807                 |
| Surface Pro 6 Коммерческий                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 7                                                | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro 7+                                               | Surface Pro 7+   | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+   | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 8                                                | Surface Pro 8    | Surface_Pro_8_for_Business_1983|
| Surface Pro 8 Consumer                                       | Surface Pro 8    | Surface_Pro_8_1983|
| Surface Pro 8 LTE                                            | Surface Pro 8    | Surface_Pro_8_for_Business_with_LTE_Advanced_1982|
| Surface Pro X с процессором SQ1                             | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X с процессором SQ2                             | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Pro X (Wi-Fi)                                        | Surface Pro X    | Surface_Pro_X_2010        |
| Surface Studio                                               | Surface Studio   | Surface_Studio   |
| Surface Studio 2                                             | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |


## <a name="examples"></a>Примеры:

**Ирисовка SKU с помощью PowerShell**  
Используйте следующую команду PowerShell для получения сведений о SKU system:

 ``` powershell  
(Get-CimInstance -Namespace root\wmi -ClassName MS_SystemInformation).SystemSKU
```

**Повторное использование SKU с помощью Сведения о системе**  
Вы также можете найти системную SKU и системную модель для устройства в **Сведения о системе**. Для этого выполните следующие действия:

1. Выберите **Начните**, а затем введите **MSInfo32** в поле поиска.  
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
