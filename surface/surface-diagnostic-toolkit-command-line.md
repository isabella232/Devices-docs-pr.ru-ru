---
title: Запуск набора средств диагностики Surface для бизнеса с помощью команд
description: Запуск средства диагностики Surface набор средств в командной консоли
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327333"
---
# Запуск набора средств диагностики Surface для бизнеса с помощью команд

Для запуска средства диагностики Surface набор средств (SDT) в командной консоли требуется загрузить консоль приложения SDT. После установки SDT можно запустить в командной консоли Windows (cmd.exe) или с помощью Windows PowerShell, в том числе интегрированной среды сценариев PowerShell (ISE), которая обеспечивает поддержку автозаполнения команд, копирования и вставки и других функций.  Список поддерживаемых устройств Surface в SDT можно найти в набор средств Диагностика [Surface для бизнеса.](surface-diagnostic-toolkit-business.md)

>[!NOTE]
>Чтобы запустить SDT с помощью команд, необходимо выполнить вставку в учетную запись администратора или учетную запись, которая является членом группы администраторов на устройстве Surface.

##  <a name="running-sdt-app-console"></a>Запуск консоли приложения SDT

Скачайте и установите консоль приложения SDT со страницы [загрузки средств Surface для ИТ-разработчиков.](https://www.microsoft.com/download/details.aspx?id=46703) Вы можете использовать командную cmd.exe Windows или Windows PowerShell: 

- Соберет все файлы журнала.
- Запуск диагностики состояния с помощью анализатора лучших методик.
- Проверьте, нет ли обновлений для микропрограмм или драйверов.

>[!NOTE]
>В этом выпуске консоль приложения SDT поддерживает только одну команду. Для запуска нескольких параметров командной строки необходимо отдельно запускать exe консоли для каждой команды. 

По умолчанию выходные файлы сохраняются в том же расположении, что и консольное приложение. Полный список команд можно найти в следующей таблице.

Команда | Заметки
--- | ---
-DataCollector "output file" | Собирает сведения о системе в ZIP-файл. "Выходной файл" — это путь к файлу для создания ZIP-файла сведений о системе.<br><br>**Пример**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Проверяет несколько параметров и индикаторов состояния на устройстве. "Выходной файл" — это путь к файлу для создания отчета HTML.<br><br>**Пример**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Проверяет серверы Windows Update Online на наличие отсутствующих обновлений микропрограмм и/или драйверов.<br><br>**Пример**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Проверяет сведения о гарантии на устройстве (допустимые или недопустимые). Необязательный "выходной файл" — это путь к файлу для создания XML-файла. <br><br>**Пример**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"


>[!NOTE]
>Для удаленного запуска консоли приложения SDT на целевых устройствах можно использовать такое средство управления конфигурацией, как Microsoft Endpoint Configuration Manager. Кроме того, можно создать ZIP-файл, содержащий консольное приложение и соответствующие команды консоли, и развернуть его в процессе распространения программного обеспечения организации. 

##  <a name="running-best-practice-analyzer"></a>Запуск анализатора лучших практик 

Вы можете выполнить тесты BPA для ключевых компонентов, таких как BitLocker, безопасная загрузка и доверенный платформенного модуля (TPM), а затем выходные результаты в файл для совместной работы. Средство создает серию таблиц с цветными заголовками и дескрипторами условий, а также руководство по решению проблемы. 

- Зеленый цвет указывает, что компонент работает в оптимальном состоянии (оптимальном).
- Оранжевый означает, что компонент работает не в оптимальном состоянии (не оптимальный).
- Красный цвет указывает, что компонент находится в ненормальном состоянии. 

###  <a name="sample-bpa-results-output"></a>Пример вывода результатов BPA

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включен ли BitLocker на системный диск.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Защита в ветвях</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Настоятельно рекомендуется включить BitLocker для защиты данных.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Безопасная загрузка</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включена ли безопасная загрузка.</td></tr>
<tr><td><strong>Значение:</strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Настоятельно рекомендуется включить безопасную загрузку для защиты компьютера.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Доверенный платформенный модуль</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Гарантирует, что TPM работает.</td></tr>
<tr><td><strong>Значение:</strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Без функционального TPM функции безопасности, такие как BitLocker, могут работать неправильно.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Режим ожидания с подключением</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включен ли режим ожидания с подключением.</td></tr>
<tr><td><strong>Значение:</strong></td><td>True</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Режим ожидания с подключением позволяет устройству Surface получать обновления и уведомления без использования. Для лучшего опыта следует включить режим ожидания с подключением.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, Bluetooth ли включена.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Включено</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Режим отлаживания</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, находится ли операционная система в режиме отлаживания.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Обычный</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Параметр загрузки отладки включает или отключает отладку ядра операционной системы Windows. Включение этого параметра может привести к стабильности системы и предотвратить воспроизведение защищенного мультимедиа drM (управление цифровыми правами).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Тестовая подпись</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, включена ли тестовая подпись.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Обычный</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Тестовая подпись — это параметр запуска Windows, который следует использовать только для тестирования предварительных драйверов.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Активный план питания</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, активен ли правильный план питания.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Сбалансированная</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Настоятельно рекомендуется использовать "сбалансированный" план питания для повышения производительности и заряда батареи.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Центр обновления Windows</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет, обновлено ли устройство с обновлениями Windows.</td></tr>
<tr><td><strong>Значение:</strong></td><td>Microsoft Silverlight (KB4023307), обновление определений для антивирусной программы Защитник Windows — KB2267602 (определение 1.279.1433.0)</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="ff9500">Не оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Обновление до последних окон позволяет убедиться, что вы на последних версиях микропрограмм и драйверов. Рекомендуется всегда поддерживать устройство в состоянии "в курсе".</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Свободное место на жестком диске</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет наличие малого свободного места на жестком диске.</td></tr>
<tr><td><strong>Значение:</strong></td><td>66%</td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Для максимальной производительности на жестком диске должно быть не менее 10 % свободного места.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Неавционционные устройства</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Список неауправленных устройств в диспетчере устройств.</td></tr>
<tr><td><strong>Значение:</strong></td><td></td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Не функционируемые устройства в диспетчере устройств могут привести к непредсказуемым проблемам с устройствами Surface, таким как отсутствие экономии электроэнергии для соответствующего аппаратного компонента.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Внешний монитор</font></th></tr>
<tr><td><strong>Описание:</strong></td><td>Проверяет внешний монитор, который может иметь проблемы совместимости.</td></tr>
<tr><td><strong>Значение:</strong></td><td></td></tr>
<tr><td><strong>Условие:</strong></td><td><font color="00ff00">Оптимальный</font></td></tr>
<tr><td><strong>Руководство:</strong></td><td>Обратитесь к производителю оборудования на совместимость с устройством Surface.</td></tr>
</table>
