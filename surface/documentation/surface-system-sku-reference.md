---
title: Справочник по номерам SKU системы Surface
description: В этой статье приводятся ссылки на названия SKU системы, которые можно использовать для быстрого определения состояния компьютера конкретного устройства.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835104"
---
# Справочник по SKU системы Surface
Этот документ содержит ссылки на названия SKU системы, которые можно использовать для быстрого определения состояния компьютера на конкретном устройстве с помощью PowerShell, WMI и связанных с ними средств. 

SKU системы — это переменная (вместе с системной и другой), сохраненная в таблицах системного управления BIOS (SMBIOS) на уровне UEFI устройств Surface.  Используйте имя системной конфигурации, если вам нужно отличать устройства с помощью одного и того же имени системной модели, например Surface Pro и Surface Pro, с помощью LTE дополнительно. 

| **Устройство**| **Модель системы** | **SKU системы**|
| --- | ---| --- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE на&т                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 для Северной Америки по LTE                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE за пределами Северной Америки и T-Mobile в Японии | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro с функцией LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Потребитель переходов Surface                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Профессиональная переход на Surface                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Потребитель Surface Pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Профессиональная профессиональная (версия для Surface Pro 6)                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Потребитель ноутбука 2 Surface                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Профессиональная Подложка "ноутбук" 2                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## Использование переменных SKU системы 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### Сведения о системе
Вы также можете найти конфигурацию системы и модель системы для устройства в разделе "сведения о системе". 
- Нажмите кнопку **Пуск**  >   **msinfo32**.  

### Инструментарий WMI
Переменные конфигурации системы можно использовать в описании WMI последовательности задач в Microsoft Deployment Toolkit (MDT) или диспетчере конфигураций Microsoft Endpoint. Пример 

    - Пространство имен WMI — Root\WMI
    - WQL-запрос: SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"

 
 
 


