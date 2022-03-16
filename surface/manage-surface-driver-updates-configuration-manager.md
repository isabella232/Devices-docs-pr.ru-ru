---
title: Управление обновлениями драйверов Surface в Configuration Manager
description: В этой статье описываются доступные варианты управления и развертывания обновлений прошивки и драйверов для устройств Surface.
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e27f2ade66602c53c1bd0e7ef3d326834f1d95ed
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449182"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>Управление обновлениями драйверов Surface в Configuration Manager

## <a name="summary"></a>Сводка

Начиная с [microsoft System Center Configuration Manager версии 1710](/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), вы можете синхронизировать и развернуть прошивку Microsoft Surface и обновления драйвера непосредственно через клиента Configuration Manager. Процесс напоминает развертывание регулярных обновлений. Однако для получения обновлений драйвера Surface в каталог требуется несколько дополнительных конфигураций.

## <a name="prerequisites"></a>Что вам понадобится

Для управления обновлениями драйвера Surface необходимо удовлетворены следующие необходимые условия:

- Необходимо использовать версию Configuration Manager 1710 или более поздний вариант.
- Все точки обновления программного обеспечения (SUPs) должны запускаться Windows Server 2016 или более поздней версии. В противном случае диспетчер конфигурации игнорирует этот параметр, и драйверы Surface не будут синхронизированы.

> [!NOTE]
> Если среда не соответствует необходимым требованиям, обратитесь к альтернативным методам развертывания [](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) обновлений драйвера Surface и прошивки в разделе [часто задаваемой](#frequently-asked-questions-faq) информации.

## <a name="useful-log-files"></a>Полезные файлы журнала

Следующие журналы особенно полезны при управлении обновлениями драйвера Surface.

|Имя журнала|Описание|
|---|---|
|WCM.log|Записывает сведения о конфигурации точки обновления программного обеспечения и подключениях к серверу WSUS для категорий, классификаций и языков, на которые подписаны обновления.|
|WsyncMgr.log|Записи сведений о процессе синхронизации обновлений программного обеспечения.|

Эти журналы расположены на сервере сайта, который управляет SUP, или на самом SUP, если он установлен непосредственно на сервере сайта.
Полный список журналов Configuration Manager см. в [System Center Configuration Manager.](/sccm/core/plan-design/hierarchy/log-files)

## <a name="enabling-surface-driver-updates-management"></a>Включение управления обновлениями драйвера Surface

Чтобы включить управление обновлениями драйвера Surface в Configuration Manager, выполните следующие действия:

1. В консоли Configuration Manager перейдите к **настройкам** **AdministrationOverviewSite** >  >  **ConfigurationSite****** > .
1. Выберите сайт, содержащий сервер SUP верхнего уровня для вашей среды.
1. На ленте выберите **Настройка компонентов сайта**, а затем выберите **точку обновления программного обеспечения**. Или щелкните правой кнопкой мыши сайт, а затем выберите **Пункт** >  обновления компоненты **сайтаSoftware**.
1. На **вкладке "Классификации** " выберите поле **Включить драйверы Microsoft Surface** и обновления прошивки.

   ![Свойства компонентов точки обновления программного обеспечения.](images/manage-surface-driver-updates-1.png)

1. Когда вам будет предложено следующее предупреждение, выберите **ОК**.

   ![Configuration Manager;](images/manage-surface-driver-updates-2.png)

1. На вкладке Продукты выберите продукты, которые необходимо обновить, а затем выберите **ОК**.

   Большинство драйверов относятся к следующим группам продуктов:

   - Windows 10 и более поздних версий
   - Windows 10 и более поздние & драйверы обслуживания
   - Windows 10 юбилейных обновлений и более поздних драйверов обслуживания
   - Windows 10 и более позднее обновление & драйверов обслуживания
   - Windows 10 Creators Update и более поздние драйверы обслуживания
   - Windows 10 Creators Update и более поздние & драйверы обслуживания
   - Windows 10 Fall Creators Update и более поздние драйверы обслуживания
   - Windows 10 Fall Creators Update и более поздние & драйверы обслуживания
   - Windows 10 S и более поздние драйверы обслуживания
   - Windows 10 версии 1709 и более поздних драйверов обслуживания для тестирования
   - Windows 10 S Версии 1709 и более поздней версии & для тестирования

   > [!NOTE]
   > Большинство драйверов Surface относятся к нескольким Windows 10 или Windows 11 группам продуктов. Возможно, вам не придется выбирать все продукты, перечисленные здесь. Чтобы уменьшить количество продуктов, которые заполняют каталог обновлений, рекомендуется выбирать только те продукты, которые необходимы среде для синхронизации.

## <a name="verifying-the-configuration"></a>Проверка конфигурации

Чтобы убедиться, что SUP настроен правильно, выполните следующие действия:

1. Откройте WsyncMgr.log и найдите следующую запись:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Если в WsyncMgr.log зарегистрирована любая из следующих записей, перепроверять шаг 4 в предыдущем разделе:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Откройте WCM.log, а затем найдите запись, которая будет напоминать следующее:

   ![Параметры WCM.log.](images/manage-surface-driver-updates-3.png)

   Эта запись — это элемент XML, который перечисляет каждую группу продуктов и классификацию, синхронизируются с вашим сервером SUP. Например, вы можете увидеть запись, которая похожа на следующую:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Если вы не можете найти продукты, выбранные на шаге 6 в предыдущем разделе, проверьте, сохраняются ли параметры SUP.

   Вы также можете дождаться завершения следующей синхронизации, а затем проверить, перечислены ли обновления драйвера Surface и прошивки в обновлениях программного обеспечения в консоли Configuration Manager. Например, консоль может отображать следующую информацию.

   ![Все обновления программного обеспечения результатов поиска.](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>Ручная синхронизация

Если вы не хотите ждать следующей синхронизации, выполните следующие действия, чтобы запустить синхронизацию:

1. В консоли Configuration Manager перейдите к **программной** **библиотекеOverviewSoftware** >  >  **UpdatesAll** >  **Software UpdatesAll**.
1. На ленте выберите **синхронизацию обновлений программного обеспечения**. Или нажмите правой кнопкой мыши **Все обновления программного обеспечения**, а затем выберите **Синхронизация обновления программного обеспечения**.
1. Отслеживайте ход синхронизации, ищите следующие записи в WsyncMgr.log:

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

## <a name="deploying-surface-firmware-and-driver-updates"></a>Развертывание обновлений прошивки Surface и драйвера

Вы можете развертывать обновления прошивки Surface и драйвера таким же образом, как и другие обновления.

Дополнительные сведения о развертывании [см. в System Center 2012 Configuration Manager-Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## <a name="frequently-asked-questions-faq"></a>Вопросы и ответы

**После последующих действий в этой статье драйверы Surface по-прежнему не синхронизируются. Почему?**

Если вы синхронизируете с сервера Windows Server Update Services (WSUS) вместо Microsoft Update, убедитесь, что сервер WSUS выше по течению настроен для поддержки и синхронизации обновлений драйвера Surface. Все серверы ниже по течению ограничены обновлениями, которые присутствуют в базе данных серверов WSUS.

В WSUS существует более 68 000 обновлений, классифицируются как драйверы. Чтобы предотвратить синхронизацию драйверов, не связанных с Surface, в Диспетчер конфигурации Корпорация Майкрософт фильтрует синхронизацию драйверов со списком допустимых. После публикации и включения нового списка разрешаний в Диспетчер конфигурации новые драйверы добавляются на консоль после следующей синхронизации. Корпорация Майкрософт стремится каждый месяц добавлять драйверы Surface в список разрешаний в соответствии с ежемесячными выпусками обновлений, чтобы сделать их доступными для синхронизации с Configuration Manager.

Если среда Диспетчер конфигурации находится в автономном режиме, каждый раз при импорте обновлений по [](/mem/configmgr/core/servers/manage/use-the-service-connection-tool) обслуживанию в Диспетчер конфигурации импортируется новый список разрешаний. Кроме того, перед отображением обновлений в консоли Configuration Manager необходимо импортировать новый каталог [WSUS](/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) , содержащий драйверы. Так как в независимой среде WSUS содержится больше драйверов, чем SUP configuration Manager, рекомендуется создать среду Configuration Manager, которая имеет возможности в Интернете, и настроить ее для синхронизации драйверов Surface. Это обеспечивает меньший экспорт WSUS, который очень похож на офлайновую среду.

Если среда диспетчера конфигурации находится в Сети и может обнаруживать новые обновления, обновления в список будут получаться автоматически. Если вы не видите ожидаемых драйверов, просмотрите файлы WCM.log и WsyncMgr.log для любых сбоев синхронизации.

**Среда Диспетчер конфигурации отключена. Можно ли вручную импортировать драйверы Surface в WSUS?**

Нет. Даже если обновление импортируется в WSUS, оно не будет импортироваться в консоль Configuration Manager для развертывания, если оно не включено в список допустимых. Чтобы обновить список [разрешаний](/mem/configmgr/core/servers/manage/use-the-service-connection-tool) , необходимо использовать средство подключения к службе для импорта обновлений для обслуживания в Диспетчер конфигурации.

**Какие альтернативные методы необходимо использовать для развертывания обновлений драйвера и прошивки Surface?**

Сведения о развертывании обновлений драйвера и прошивки Surface по альтернативным каналам см. в этой ссылке [: Управление драйвером Surface и обновлениями прошивки](manage-surface-driver-and-firmware-updates.md). Если вы хотите скачать файл .msi или .exe, а затем развернуть через традиционные каналы развертывания программного обеспечения, см. в рубке [Keeping Surface Firmware Updated with Configuration Manager](/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## <a name="additional-information"></a>Дополнительные сведения

Дополнительные сведения об обновлениях драйвера и прошивки Surface см. в следующих статьях:

- [Управление обновлениями драйверов и встроенного ПО Surface](manage-surface-driver-and-firmware-updates.md)
- [Рекомендации для Surface и System Center Configuration Manager](considerations-for-surface-and-system-center-configuration-manager.md)
