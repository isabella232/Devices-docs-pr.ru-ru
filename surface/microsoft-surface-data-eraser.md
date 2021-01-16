---
title: Microsoft Surface Data Eraser (Surface)
description: Узнайте, как надежно стирать данные с устройств Surface с помощью средства Microsoft Surface Data Eraser.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: средство, USB, данные, очистка
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 2ae1b7b3af93c1449b96bf6307c830a928c1f0a7
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271413"
---
# Microsoft Surface Data Eraser


Узнайте, как надежно стирать данные с устройств Surface с помощью средства Microsoft Surface Data Eraser.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) — это средство, которое загружается с USB-накопителя и позволяет выполнять надежное удаление всех данных с совместимого устройства Surface. Для использования USB-накопителя с Microsoft Surface Data Eraser требуется только возможность загрузки с USB. Благодаря простому графическому интерфейсу пользоваться им очень просто; прибегать к командной строке не требуется. Создать USB-носитель легко можно с помощью предусмотренного в средстве мастера, который называется Microsoft Surface Data Eraser Wrapper. Подробнее о возможностях и методиках стирания данных, которые корпорация Майкрософт использует при сервисном обслуживании Surface, см. в статье [Защита персональных данных в случае отправки планшета Surface в сервисный центр](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Средство Microsoft Surface Data Eraser использует команду в формате NVM Express (NVMe) для удаления данных согласно разрешениям в [специальном издании NIST 800-88 (редакция 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf). 

В число совместимых устройств Surface входят:

- Surface Book (все выпуски)
- Surface Go (все выпуски)
- Surface Pro X (все выпуски)
- Surface Laptop (все выпуски)
- Surface Laptop Go
- Surface Studio (все выпуски)
- Surface Pro 2 и более поздние
- Windows 10 Pro и Корпоративная на Surface Hub 2

Используйте Microsoft Surface Data Eraser при:

-   подготовке устройства к отправке на ремонт;

-   выводе устройства Surface из эксплуатации на предприятии или в организации;

-   перепрофилировании устройства Surface для передачи в другой отдел или другому пользователю;

-   В качестве стандартной практики при пересоздании образов для устройств с конфиденциальными данными

>[!NOTE]
>Устройства сторонних производителей, устройства Surface под управлением Windows RT (включая Surface и Surface 2), а также Surface Pro несовместимы с Microsoft Surface Data Eraser.

>[!NOTE]
>Поскольку для запуска Microsoft Surface Data Eraser требуется возможность загрузки с USB, если устройство не настроено для загрузки с USB или если ему не удается загрузиться либо пройти POST, Microsoft Surface Data Eraser работать не будет.

>[!NOTE]
>Загрузка Surface Data Eraser на Surface Studio и Surface Studio 2 может занять до 6 минут, прежде чем произойдет стирание диска.


## Как создать USB-накопитель с Microsoft Surface Data Eraser


Чтобы создать USB-накопитель с Microsoft Surface Data Eraser, сначала скачайте программу установки Microsoft Surface Data Eraser из Центра загрузки Майкрософт, перейдя по ссылке в начале этой статьи. Для *создания* USB-накопителя устройство Surface не требуется. После скачивания установочного файла на свой компьютер сделайте следующее, чтобы установить средство создания Microsoft Surface Data Eraser:

1.  Запустите DataEraserSetup.msi установки, загруженный из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=46703)

2.  Установите флажок, чтобы принять условия лицензионного соглашения, а затем нажмите кнопку **Install**.

3.  Нажмите кнопку **Finish**, чтобы закрыть окно установки Microsoft Surface Data Eraser.

Установив средство создания Microsoft Surface Data Eraser, сделайте следующее, чтобы создать USB-накопитель с Microsoft Surface Data Eraser. Прежде чем приступить, убедитесь, что к компьютеру подключен накопитель стандарта USB3.0 емкостью 4ГБ или более.

1. Запустите Microsoft Surface Data Eraser из меню "Пуск" или с начального экрана.

2. Нажмите кнопку **Build**, чтобы запустить процесс создания USB-накопителя с Microsoft Surface Data Eraser. 

3. Нажмите кнопку **Start**, чтобы подтвердить, что к компьютеру подключен USB-накопитель емкостью 4ГБ или более, как показано на рисунке1.

   ![Запуск средства Microsoft Surface Data Eraser](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Рис. 1. Запуск средства Microsoft Surface Data Eraser*
4.  Выберите **x64** для большинства устройств Surface или **** **ARM64** для Surface Pro X на странице "Выбор архитектуры", как показано на рисунке 2. Выберите пункт **Продолжить**.

    ![Выбор архитектуры](images/dataeraser-arch.png "Architecture Selection")<br>
       *Рисунок 2. Выбор архитектуры устройства*
    

4. Выберите выбранный USB-накопитель **** на странице выбора USB-накопителя, как показано на рисунке 3, и нажмите кнопку "Начните", чтобы начать процесс создания USB-накопителя. **** Выбранный накопитель будет отформатирован, и все имеющиеся на нем данные будут потеряны.

   >[!NOTE]
   >Если кнопка "Пуск" недоступна, убедитесь, что емкость накопителя составляет не менее 4ГБ.
  
   ![Выбор USB-накопителя](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Рисунок 3. Выбор USB-накопителя*

5. В процессе создания USB-накопитель будет отформатирован, и на него будут скопированы все двоичные файлы. Нажмите кнопку **Success**.

6. После появления экрана **Congratulations** накопитель можно извлечь. Теперь этот накопитель можно вставить в устройство Surface, загрузить с него устройство и стереть данные на устройстве. Нажмите **кнопку** "Готово", чтобы завершить процесс создания USB-накопителя, как показано на рисунке 4.

   ![Процесс создания USB-накопителя с Surface Data Eraser](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Рисунок 4. Завершение процесса создания USB-накопителя с Microsoft Surface Data Eraser*

7. Щелкните **X**, чтобы закрыть Microsoft Surface Data Eraser.

## Как пользоваться USB-накопителем с Microsoft Surface Data Eraser


После создания USB-накопителя с Microsoft Surface Data Eraser загрузить поддерживаемое устройство Surface с USB-накопителя можно следующим образом:

1. Вставьте загрузочный USB-накопитель с Microsoft Surface Data Eraser в поддерживаемое устройство Surface.

2. Загрузите устройство Surface с USB-накопителя Microsoft Surface Data Eraser. Для загрузки с USB-носителя выполните приведенные ниже действия.

   а. Выключите устройство Surface.

   б. Нажмите и удерживайте кнопку **уменьшения громкости**.

   в. Нажмите и отпустите кнопку **питания**.

   г. Отпустите кнопку **уменьшения громкости**.
    
   >[!NOTE]
   >Если устройство не загружается с USB-носителя после выполнения этих шагов, возможно, следует включить параметр **Enable Alternate Boot Sequence** в UEFI Surface. Подробнее о конфигурации загрузки UEFI Surface см. в статье [Управление параметрами UEFI Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. При загрузке устройства Surface отображается текстовый **файл SoftwareLicenseTerms,** как показано на рисунке 5.

   ![Загрузка с USB-накопителя с Microsoft Surface Data Eraser](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Рисунок 5. Загрузка с USB-накопителя с Microsoft Surface Data Eraser*

4. Ознакомьтесь с условиями лицензионного соглашения на использование ПО и закройте файл Блокнота.

5. Отклоните или примите условия лицензионного соглашения, введя **Accept** или **Decline**. Чтобы продолжить, необходимо принять условия лицензионного соглашения.

6. Сценарий Microsoft Surface Data Eraser обнаруживает запоминающие устройства, которые присутствуют на вашем устройстве Surface, и отображает сведения о собственном запоминающем устройстве. Чтобы продолжить, нажмите клавишу **Y** (это действие запускает Microsoft Surface Data Eraser и удаляет все данные с запоминающего устройства) или клавишу **N** (это действие завершает работу устройства без удаления данных).

   >[!NOTE]
   >Средство Microsoft Surface Data Eraser удалит все данные, включая файлы операционной системы Windows, необходимые для загрузки устройства, безопасным и невосстанавливаемым способом. Для загрузки устройства Surface, данные на котором были удалены с помощью Microsoft Surface Data Eraser, сначала необходимо переустановить операционную систему Windows. Чтобы удалить данные с устройства Surface без удаления операционной системы Windows, можно использовать функцию **Возврат компьютера в исходное состояние**. Однако это не помешает восстановлению данных с помощью криминалистических методов или методов восстановления данных. Подробнее см. в разделе [Параметры восстановления в Windows 10](https://support.microsoft.com/help/12415/windows-10-recovery-options).

   ![Отображается стираемый раздел](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Рисунок 6. В Microsoft Surface Data Eraser отображается стираемый раздел*

7. Если вы нажали **Y** на шаге6, появится дополнительное диалоговое окно для подтверждения вашего выбора, поскольку стирание данных— процесс необратимый.

8. Нажмите кнопку **Yes**, чтобы продолжить стирание данных с устройства Surface.

   >[!NOTE]
   >При запуске Surface Data Eraser на USB-накопителе Surface Data Eraser создается файл журнала в папке **SurfaceDataEraserLogs**.

## Изменения и обновления

Корпорация Майкрософт периодически обновляет Microsoft Surface Data Eraser. Далее представлены сведения об изменениях в каждой версии.

### 2.34.139.0
*Дата выпуска: 15 января 2021 г.*

Эта версия Surface Data Eraser:

- Включает исправления ошибок

### 3.33.139
*Дата выпуска: 9 сентября 2020 г.*

Эта версия Surface Data Eraser включает исправления ошибок и добавляет поддержку: 

- Повторное проектирование архитектуры, чтобы уменьшить необходимость обновления с новыми выпусками продуктов
- Уведомление, доступное для новых обновлений инструментов
- Добавления телеметрии
- Windows 10 Pro и Корпоративная на Surface Hub 2


### 3.30.139
*Дата выпуска: 11 мая 2020 г.*

Эта версия Surface Data Eraser поддерживает: 
- Surface Book 3
- Surface Go 2
- Новый SSD в Surface Go

### 3.28.137
*Дата выпуска: 11 ноября 2019 г.*

Эта версия Surface Data Eraser:

- Включает исправления ошибок

### Версия 3.21.137
*Дата выпуска: 21 октября 2019 г.*

Эта версия Surface Data Eraser скомпилна для x86 и добавляет поддержку следующих устройств:

- Surface Pro 7, Surface Pro X и Surface Laptop 3

### Версия 3.2.78.0

*Дата выпуска: 4 декабря 2018 г.*

Эта версия Surface Data Eraser:

- Включает исправления ошибок


### Версия 3.2.75.0

*Дата выпуска: 12 ноября 2018 г.*

Эта версия Surface Data Eraser:

- Добавляет поддержку в Surface Studio 2
- Устранение проблем с SD-картой

### Версия 3.2.69.0

*Дата выпуска: 12 октября 2018 г.*

В этой версии Surface Data Eraser добавлена поддержка следующих вариантов:

- Surface Pro 6
- Surface Laptop 2

### Версия 3.2.68.0

В этой версии Microsoft Surface Data Eraser добавлена поддержка следующих устройств:

- Surface Go


### Версия 3.2.58.0

В этой версии Microsoft Surface Data Eraser добавлена поддержка следующих устройств:

- Дополнительные устройства хранения (диски) для устройств Surface Pro и Surface Laptop


### Версия 3.2.46.0

В этой версии Microsoft Surface Data Eraser добавлена поддержка следующих устройств:

- Surface Pro с функцией LTE Advanced


### Версия 3.2.45.0

В этой версии Microsoft Surface Data Eraser добавлена поддержка следующих устройств:

- Surface Book 2

- Surface Pro 1 ТБ

   >[!NOTE]
   >Surface Data Eraser версии 3.2.45.0 и выше можно использовать для восстановления устройств Surface Pro и Surface Laptop с объемом накопителя 1 ТБ в таком сценарии, когда на устройстве отображаются два отдельных тома по 512 ГБ или возникают ошибки при попытке выполнить развертывание или установку Windows 10. Дополнительные сведения можно найти в разделе [Surface Pro модели 1796 и Surface Laptop 1 ТБ отображают два диска](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives).


### Версия 3.2.36.0

В этой версии Microsoft Surface Data Eraser добавлена поддержка следующих устройств:

- Surface Pro

- Ноутбук Surface

>[!NOTE]
>Средство создания USB-носителей Microsoft Surface Data Eraser не работает в Windows 10 S. Для того чтобы выполнить очистку ноутбука Surface Laptop под управлением Windows 10 S, необходимо сначала создать USB-носитель Microsoft Surface Data Eraser на другом компьютере с Windows 10 Pro или Windows 10 Корпоративная.
