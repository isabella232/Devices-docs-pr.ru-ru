---
title: Справочник по SKU системы (Surface)
description: Ознакомьтесь со ссылкой о системной модели и названиях SKU системы.
keywords: UEFI, Настройка, встроенное по, безопасность, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ec1d53a4bdbcaaf6606dcb0e52fc81de92a2a53b
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114547"
---
# Справочная информация о SKU системы

Этот документ содержит ссылку на системную модель и имена SKU системы, которые можно использовать для быстрого определения состояния компьютера определенного устройства с помощью PowerShell или WMI.

Системная модель и SKU системы — это переменные, хранящиеся в таблицах SMBIOS Management BIOS на уровне UEFI устройств Surface. Используйте имя системной конфигурации, если вам нужно отличать устройства с помощью одного и того же имени системной модели, например Surface Pro и Surface Pro, с помощью LTE дополнительно.

| Устройство   | Модель системы | SKU системы       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE на&т                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 для Северной Америки по LTE                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE за пределами Северной Америки и Y! Mobile в Японии | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro с функцией LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13 "                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15 "                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go в коммерческой версии по LTE | Системный переход | Surface_Go_1825_Commercial |
| Потребитель переходов Surface                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Профессиональная переход на Surface                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Потребитель Surface Pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Профессиональная профессиональная (версия для Surface Pro 6)                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Потребитель ноутбука 2 Surface                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Профессиональная Подложка "ноутбук" 2                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X с процессором SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface портативный компьютер 3 13 "Intel | Surface ноутбук 3 | Surface_Laptop_3_1867:1868 |
| Surface портативный компьютер 3 15 "Intel | Surface ноутбук 3 | Surface_Laptop_3_1872      |
| Surface портативный компьютер 3 15 "AMD   | Surface ноутбук 3 | Surface_Laptop_3_1873      | 
| Ноутбук Surface Go  | Ноутбук Surface Go | Surface_Laptop_Go_1943      | 

## Примеры 

**Получение SKU с помощью PowerShell**  
Используйте следующую команду PowerShell для извлечения сведений о конфигурации системы:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Получение SKU с помощью сведений о системе**  
Вы также можете найти конфигурацию системы и модель системы для устройства в разделе " **сведения о системе**". Для этого выполните следующие действия:

1. Нажмите кнопку **Пуск**и введите в поле поиска параметр **msinfo32** .  
1. Выберите пункт **сведения о системе**.

**Использование SKU в условии WMI последовательности задач**  
Вы можете использовать сведения о конфигурации системы в Microsoft Deployment Toolkit (MDT) или диспетчере конфигураций конечных точек Microsoft как часть состояния WMI последовательности задач.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
