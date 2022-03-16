---
title: Запустите консоль приложения командной строки с помощью surface Diagnostic набор средств для бизнеса
description: Запуск surface Diagnostic набор средств в командной консоли
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: bdd91df1f1ce105ecd19ea15e78bd9dc29d0ee95
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448472"
---
# <a name="run-command-line-app-console-with-surface-diagnostic-toolkit-for-business"></a>Запустите консоль приложения командной строки с помощью surface Diagnostic набор средств для бизнеса

Запуск центра диагностики набор средств (SDT) по командной подсказке требует загрузки консоли приложения SDT. После установки SDT можно запустить по командной подсказке через консоль Windows команды (cmd.exe) или с помощью Windows PowerShell, в том числе powerShell Integrated Scripting Environment (ISE), которая обеспечивает поддержку автокомплектации команд, копирования/вставки и других функций.  Список поддерживаемых устройств Surface в SDT со ссылкой на [deploy Surface Diagnostic набор средств для бизнеса](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Чтобы запустить SDT с помощью команд, необходимо войти в учетную запись администратора или в нее в учетную запись, которая входит в группу администратора на устройстве Surface.

## <a name="running-sdt-app-console"></a>Запуск консоли приложения SDT

1. Скачайте и установите консоль приложения SDT со страницы [Surface Tools для скачивания ИТ-приложений](https://www.microsoft.com/download/details.aspx?id=46703).

- Для устройств Intel/AMD скачайте: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- Для ARM устройств скачайте: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. Используйте командную Windows (cmd.exe) или Windows PowerShell:

- Сбор всех файлов журнала
- Запуск диагностики здоровья с помощью анализатора наилучшей практики
- Проверка обновления отсутствующих обновлений прошивки или драйвера

>[!NOTE]
>В этом выпуске консоль приложений SDT поддерживает только отдельные команды. Запуск нескольких параметров командной строки требует отдельного запуска консоли exe для каждой команды.

По умолчанию выходные файлы сохраняются в том же расположении, что и консольное приложение. Полный список команд можно найти в следующей таблице.

Команда | Заметки
--- | ---
-DataCollector "выходной файл" | Собирает сведения о системе в почтовый файл. "Выходной файл" — это путь к созданию системных данных zip-файла.<br><br>**Пример**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "выходной файл" | Проверяет несколько параметров и показателей состояния на устройстве. "Выходной файл" — это путь к созданию htmL-отчета.<br><br>**Пример**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Проверяет Windows обновления веб-серверов на наличие отсутствующих обновлений прошивки и/или драйвера.<br><br>**Пример**:<br>Microsoft.Surface.Diagnostics.App.Console.exe windowsupdate
-warranty "output file" | Проверяет сведения о гарантии на устройстве (допустимые или недействительные). Необязательный "выходной файл" — это путь к созданию xml-файла. <br><br>**Пример**: <br>Microsoft.Surface.Diagnostics.App.Console.exe -гарантия "warranty.xml"

>[!NOTE]
>Для удаленного запуска консоли приложения SDT на целевых устройствах можно использовать средство управления конфигурацией, например Microsoft Endpoint Configuration Manager. Кроме того, можно создать .zip, содержащий консольное приложение и соответствующие команды консоли, и развернуть в организации процессы распространения программного обеспечения.

## <a name="running-best-practice-analyzer"></a>Запуск анализатора наилучшей практики

Можно выполнить тесты BPA в ключевых компонентах, таких как BitLocker, Secure Boot и Trusted Platform Module (TPM), а затем вывод результатов в файл, который можно использовать для обмена данными. Средство создает серию таблиц с цветными заголовками и дескрипторами условий, а также руководства по подходу к решению проблемы.

- Зеленый цвет указывает, что компонент работает в оптимальном состоянии (оптимальном).
- Оранжевый указывает, что компонент работает не в оптимальном состоянии (не оптимальном).
- Красный цвет указывает, что компонент находится в ненормальном состоянии.

### <a name="sample-bpa-results-output"></a>Выборка вывода результатов BPA

<table>
<tr><th colspan="2">BitLocker</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включен ли BitLocker на системных дисках.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Защита на</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Рекомендуется включить BitLocker для защиты данных.</td></tr>
</table>

<table>
<tr><th colspan="2">Безопасная загрузка</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включена ли безопасная загрузка.</td></tr>
<tr><td><strong>Значение: </strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Рекомендуется включить безопасную загрузку для защиты компьютера.</td></tr>
</table>

<table>
<tr><th colspan="2">Доверенный платформенный модуль</th></tr>
<tr><td><strong>Описание:</strong></td><td>Обеспечивает функциональную функцию TPM.</td></tr>
<tr><td><strong>Значение: </strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Без функционального TPM функции, основанные на безопасности, такие как BitLocker, могут работать неправильно.</td></tr>
</table>

<table>
<tr><th colspan="2">Подключенный режим ожидания</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включен ли подключенный режим ожидания.</td></tr>
<tr><td><strong>Значение: </strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Подключение к режиму ожидания позволяет устройству Surface получать обновления и уведомления, пока они не используются. Для лучшего опыта необходимо включить подключение к режиму ожидания.</td></tr>
</table>

<table>
<tr><th colspan="2">Bluetooth</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверка Bluetooth включена.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Включено</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2">Режим отлаживания</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, находится ли операционная система в режиме отлаживания.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Обычный</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Параметр отладки загрузки включает или отключает отладку ядра Windows операционной системы. Включение этого параметра может привести к системной нестабильности и запретить использование защищенных мультимедиа в DRM (управление цифровыми правами).</td></tr>
</table>

<table>
<tr><th colspan="2">Проверка подписи</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включена ли проверка подписи.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Обычный</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Test Signing — это параметр Windows запуска, который следует использовать только для тестирования драйверов предварительного выпуска.</td></tr>
</table>

<table>
<tr><th colspan="2">Active Power Plan</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, активна ли правильная энергоплана.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Сбалансированный</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Рекомендуется использовать план питания "Balanced" для повышения производительности и автономной работы.</td></tr>
</table>

<table>
<tr><th colspan="2">Центр обновления Windows</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, обновлено ли устройство с Windows обновлениями.</td></tr>
<tr><td><strong>Значение: </strong></td><td>Microsoft Silverlight (KB4023307), обновление определения для антивирусная программа  - KB2267602 (определение 1.279.1433.0)</td></tr>
<tr><td><strong>Условие:</strong></td><td>Не оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Обновление до последних окон позволяет убедиться, что вы находитесь на последнем прошивке и драйверах. Рекомендуется всегда поддерживать устройство в курсе</td></tr>
</table>

<table>
<tr><th colspan="2">Свободное пространство жесткого диска</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверка низкого свободного места жесткого диска.</td></tr>
<tr><td><strong>Значение: </strong></td><td>66%</td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Для максимальной производительности жесткий диск должен иметь не менее 10% своей емкости в качестве свободного пространства.</td></tr>
</table>

<table>
<tr><th colspan="2">Не функционируют устройства</th></tr>
<tr><td><strong>Описание:</strong></td><td>Список не функционируюющих устройств в диспетчере устройств.</td></tr>
<tr><td><strong>Значение: </strong></td><td></td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Не функционируют устройства в диспетчере устройств, что может привести к непредсказуемым проблемам с устройствами Surface, такими как, но не ограничившись, отсутствием экономии электроэнергии для соответствующего аппаратного компонента.</td></tr>
</table>

<table>
<tr><th colspan="2">Внешний монитор</th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверка внешнего монитора, который может иметь проблемы с совместимостью.</td></tr>
<tr><td><strong>Значение: </strong></td><td></td></tr>
<tr><td><strong>Условие:</strong></td><td>Оптимальный</td></tr>
<tr><td><strong>Руководство:</strong></td><td>Проверьте у первоначального производителя оборудования совместимость с устройством Surface.</td></tr>
</table>
