---
title: Управление обновлениями драйвера Surface в Configuration Manager
description: В этой статье описаны доступные параметры для управления и развертывания микропрограмм и обновлений драйверов для устройств Surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, встроенное ПО, обновление, устройство, управление, развертывание, драйвер, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835867"
---
# Управление обновлениями драйвера Surface в Configuration Manager

## Краткий обзор

Начиная с [Microsoft System Center Configuration Manager версии 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), вы можете выполнять синхронизацию и развертывание встроенного по и обновлений для Surface (Майкрософт) прямо через клиент Configuration Manager. Процесс напоминает развертывание регулярных обновлений. Однако некоторые дополнительные конфигурации необходимы для получения обновлений драйвера Surface в каталог.

## Предварительные условия

Для управления обновлениями драйверов Surface должны выполняться следующие требования:

- Необходимо использовать Configuration Manager версии 1710 или более поздней версии.
- Все точки обновления программного обеспечения (SUPs) должны работать под управлением Windows Server 2016 или более поздней версии. В противном случае Configuration Manager не пропустит этот параметр и драйверы Surface не будут синхронизироваться.

> [!NOTE]
> Если ваша среда не отвечает требованиям, ознакомьтесь с [альтернативными методами](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) для развертывания драйверов Surface и обновлений микропрограмм в разделе " [вопросы и ответы](#frequently-asked-questions-faq) ".

## Полезные файлы журнала

Следующие журналы особенно полезны при управлении обновлениями драйверов Surface.

|Имя журнала|Описание|
|---|---|
|WCM. log|Записывает сведения о настройке точки обновления программного обеспечения и подключения к серверу WSUS для подписок на обновления, классификаций и языков.|
|WsyncMgr. log|Записываются сведения о процессе синхронизации обновлений программного обеспечения.|

Эти журналы находятся на сервере сайта, который управляет SUPм, или на самом SUP, если он установлен непосредственно на сервере сайта.
Полный список журналов Configuration Manager можно найти [в разделе файлы журнала в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).

## Включение управления обновлениями драйверов Surface

Чтобы включить управление обновлениями драйверов Surface в диспетчере конфигураций, выполните указанные ниже действия.

1. На консоли Configuration Manager перейдите на сайт " **Administration**  >  **Общие сведения об**администрировании сайтов"  >  **Site Configuration**  >  **Sites**.
1. Выберите сайт, содержащий сервер SUP верхнего уровня для вашей среды.
1. На ленте выберите пункт **Настройка компонентов сайта**, а затем — **пункт Обновление программного обеспечения**. Либо щелкните сайт правой кнопкой мыши и выберите пункт **Настройка**  >  **точки обновления программного обеспечения**для компонентов сайта.
1. На вкладке **классификации** установите флажок **включить драйверы Microsoft Surface Driver и обновления встроенного по** .

   ![Свойства компонента точки обновления программного обеспечения](images/manage-surface-driver-updates-1.png)

1. При появлении следующего сообщения с предупреждением нажмите кнопку **ОК**.

   ![Configuration Manager;](images/manage-surface-driver-updates-2.png)

1. На вкладке продукты выберите продукты, которые вы хотите обновить, и нажмите кнопку **ОК**.

   Большинство факторов относятся к следующим группам продуктов:

   - Драйверы Windows 10 и более поздних версий
   - Драйверы обслуживания & обновления для Windows 10 и более поздних версий
   - Годовщина Windows 10 и более поздние версии драйверов обслуживания
   - Обновления и более поздние версии драйверов для Windows 10 & обслуживания
   - Windows 10 — создатели обновлений и более поздних версий драйверов обслуживания
   - Обновления Windows 10 для дизайнеров и более поздних версий & драйверов обслуживания
   - Обновления Windows 10 и более поздние версии драйверов обслуживания
   - Обновление и более поздние версии драйверов для Windows 10 & обслуживания
   - Драйверы обслуживания Windows 10 и более поздних версий
   - Драйверы Windows 10 S версии 1709 и более поздних версий для тестирования
   - Windows 10 S версии 1709 и более поздних версий & обслуживание драйверов для тестирования

   > [!NOTE]
   > Большинство драйверов Surface относятся к нескольким группам продуктов Windows 10. Возможно, вам не придется выделять все продукты, которые перечислены здесь. Чтобы уменьшить количество продуктов, которые заполняют каталог обновлений, мы рекомендуем выбирать только те продукты, которые необходимы вашей среде для синхронизации.

## Проверка конфигурации

Чтобы убедиться в правильности настройки SUP, выполните указанные ниже действия.

1. Откройте WsyncMgr. log и найдите следующий элемент:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Если в WsyncMgr. log записано какое – либо из указанных ниже записей, повторно проверьте шаг 4 в предыдущем разделе.

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Откройте средство WCM. log и найдите запись, похожую на приведенную ниже.

   ![Параметры WCM. log](images/manage-surface-driver-updates-3.png)

   Этот элемент является элементом XML, в котором перечислены все группы продуктов и классификация, синхронизированные в настоящее время с помощью сервера SUP. Например, вы можете увидеть запись, которая похожа на приведенную ниже.

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Если вы не можете найти продукты, которые вы выбрали на шаге 6 в предыдущем разделе, проверьте, не сохраняются ли параметры SUP.

   Вы также можете подождать, пока завершится следующая синхронизация, а затем проверить, указаны ли обновления для драйвера Surface и микропрограмм в разделе обновления программного обеспечения на консоли Configuration Manager. Например, консоль может отобразить следующие данные:

   ![Все результаты поиска обновлений программного обеспечения](images/manage-surface-driver-updates-4.png)

## Синхронизация вручную

Если вы не хотите ждать следующей синхронизации, выполните указанные ниже действия, чтобы начать синхронизацию.

1. На консоли Configuration Manager перейдите в раздел Обзор **библиотеки программного**обеспечения, в котором выводятся  >  **Overview**  >  **обновленные**  >  **обновления программного обеспечения**.
1. На ленте выберите **синхронизировать обновления программного обеспечения**. Или щелкните правой кнопкой мыши **Обновление программного обеспечения**, а затем выберите команду **синхронизировать обновление программного обеспечения**.
1. Отслеживайте ход выполнения синхронизации, выполнив поиск по следующим записям в WsyncMgr. log:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## Развертывание микропрограммы и обновлений драйверов Surface

Встроенное по и обновления драйверов можно развертывать так же, как и при развертывании других обновлений.

Дополнительные сведения о развертывании можно найти в статье [System Center 2012 Configuration Manager – part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## Вопросы и ответы

**После выполнения действий, описанных в этой статье, видеодрайверы Surfaces по-прежнему не синхронизируются. Почему?**

Если вы синхронизируются с вышестоящим сервером Windows Server Update Services (WSUS) вместо центра обновления Майкрософт, убедитесь в том, что вышестоящий WSUS-сервер настроен таким, чтобы он поддерживал и синхронизировались обновления драйверов Surface. Все подчиненные серверы ограничены обновлениями, которые присутствуют в базе данных вышестоящего сервера WSUS.

В WSUS более 68 000 обновлений, которые классифицируются как драйверы. Чтобы предотвратить синхронизацию драйверов, не связанных с Surface, с помощью Configuration Manager, Microsoft фильтрует синхронизацию драйверов с разрешающим списком. После публикации и включения нового списка разрешенных в Configuration Manager новые драйверы добавляются на консоль после следующей синхронизации. Корпорация Майкрософт стремится получить драйверы Surface, добавленные в список разрешений ежемесячно с помощью обновления, чтобы сделать их доступными для синхронизации с Configuration Manager.

Если ваша среда Configuration Manager находится в автономном режиме, каждый раз при импорте обновлений для [обслуживания](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) в Configuration Manager будет импортироваться новый список разрешений. Кроме того, вы должны импортировать [новый каталог WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) , содержащий драйверы, прежде чем они будут отображаться в консоли Configuration Manager. Так как в автономной среде WSUS есть больше драйверов, чем SUP Configuration Manager, мы рекомендуем установить среду Configuration Manager, в которой есть возможности Online, и настроить ее для синхронизации драйверов Surface. Это обеспечивает меньший экспорт WSUS, похожий на автономную среду.

Если ваша среда Configuration Manager находится в сети и может определять новые обновления, вы будете получать обновления списка автоматически. Если вы не видите ожидаемых драйверов, ознакомьтесь с разработкой WCM. log и WsyncMgr. log на предмет ошибок синхронизации.

**Моя среда Configuration Manager находится в автономном режиме, можно ли вручную импортировать драйверы Surfaces в WSUS?**

Нет. Несмотря на то, что обновление будет импортировано в WSUS, оно не будет импортировано на консоль Configuration Manager для развертывания, если оно не указано в списке разрешений. Для импорта обновлений для обслуживания в Configuration Manager необходимо использовать [средство подключения служб](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) , чтобы обновить список разрешений.

**Какие альтернативные методы необходимо для развертывания драйверов Surface и обновлений микропрограмм?**

Сведения о том, как развертывать драйверы Surface и обновления встроенного по с помощью альтернативных каналов, можно найти в разделе [Управление обновлениями Surface Driver и микропрограмм](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates). Если вы хотите скачать MSI-или exe-файл, а затем развернуть его через традиционные каналы развертывания программного обеспечения, ознакомьтесь со сведениями о том, как [обновить встроенное по в Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## Дополнительные сведения

Дополнительные сведения об обновлениях драйверов и микропрограмм Surface можно найти в следующих статьях:

- [Скачивание последних версий встроенного ПО и драйверов для устройств Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [Управление обновлениями драйверов и встроенного ПО Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [Рекомендации для Surface и System Center Configuration Manager](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)
