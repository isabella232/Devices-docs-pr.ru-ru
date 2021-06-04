---
title: Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание
description: В этой статье описаны доступные параметры для управления и развертывания микропрограмм и обновлений драйверов для устройств Surface.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, встроенное ПО, обновление, устройство, управление, развертывание, драйвер, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: 39022ca631e35f4328d3c353b7b0d1e2ebaee6a7
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114637"
---
# Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание

Способ управления драйверами Surface и обновлениями микропрограммного обеспечения зависит от вашей среды и требований Организации. На устройствах Surface встроенное по является драйвером операционной системы и отображается в диспетчере устройств. Это позволяет автоматически обновлять встроенное по и драйверы устройства с помощью центра обновления Windows или центра обновления Windows для бизнеса. Несмотря на то, что этот упрощенный подход может быть пригоден для запуска и малых и средних предприятий, более крупные организации обычно нуждаются в ИТ-администраторах для внутренней рассылки обновлений. Это может привести к подробному планированию, тестированию совместимости приложений, пилотному развертыванию и проверке обновлений перед финальным утверждением и распространением по сети.

> [!NOTE]
> Эта статья предназначена для агентов технической поддержки и ИТ-специалистов, применимых только к устройствам Surface. Если вам нужна помощь в установке обновлений и микропрограмм на домашних устройствах, ознакомьтесь с [обновлением встроенного по Surface и Windows 10](https://support.microsoft.com/help/4023505).

Несмотря на то, что решения для распространения программного обеспечения в масштабах предприятия продолжают развиваться, бизнес-обоснования для централизованного управления обновлениями остаются одинаковыми: поддержание безопасности Surface Devices и поддержание их актуальности с помощью новейшей операционной системы и улучшенных возможностей. Это важно для обеспечения стабильной рабочей среды и для того, чтобы пользователи не блокировали производительность. В этой статье приводятся общие сведения о рекомендуемых средствах и процессах для более крупных организаций для выполнения этих целей.

##  <a name="central-update-management-in-commercial-environments"></a>Централизованное управление обновлениями в коммерческой среде

Корпорация Microsoft предлагает упрощенные инструменты для управления устройствами, включая обновления драйверов и микропрограмм — единым единым интерфейсом, именуемым [центром администрирования Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/) и доступ к которым осуществляется из [devicemanagement.Microsoft.com](https://devicemanagement.microsoft.com/#home).

###  <a name="manage-updates-with-configuration-manager-and-intune"></a>Управление обновлениями с помощью Configuration Manager и Intune

Диспетчер конфигураций конечных точек Microsoft позволяет синхронизировать и развертывать микропрограммы и обновления драйверов в клиенте Configuration Manager. Интеграция с Microsoft Intune позволяет видеть все управляемые, управляемые и управляемые партнерами устройства в одном месте. Это рекомендуемое решение для управления обновлениями Surface в крупных организациях.

Подробные инструкции можно найти в следующих источниках:

- [Управление обновлениями драйверов в Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Развертывание приложений с помощью Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Документация по Configuration Manager для конечной точки](https://docs.microsoft.com/configmgr/)

###  <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Управление обновлениями с помощью набора средств развертывания Microsoft

Набор средств развертывания Microsoft (MDT) входит в Диспетчер конфигурации конечной точки. Она включает в себя необязательные инструменты развертывания, которые можно использовать в зависимости от используемой среды. К ним относятся комплект средств оценки и развертывания Windows (Windows ADK), диспетчер системных образов Windows (Windows SIM), система обслуживания образов развертывания и управления ими (DISM) и средство миграции пользовательской среды (USMT). Последнюю версию MDT можно скачать на [странице загрузки Microsoft Deployment Toolkit](https://www.microsoft.com/download/details.aspx?id=54259).

Подробные инструкции можно найти в следующих источниках:

- [Документация по набору средств развертывания Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Развертывание Windows 10 с помощью Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Развертывание Windows 10 на Surface Devices с помощью набора средств развертывания Microsoft](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Драйверы Surface и обновления микропрограмм упаковываются в файлы установщика Windows (*. msi). Чтобы развернуть эти пакеты установщика Windows, можно использовать диспетчер конфигурации конечной точки или MDT. Сведения о том, как выбрать правильный MSI-файл для устройства и операционной системы, можно найти в руководстве, приведенном ниже в разделе Загрузка MSI-файлов.

Инструкции по развертыванию обновлений с помощью диспетчера конфигурации конечной точки см. в разделе [развертывание приложений в Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Инструкции по развертыванию обновлений с помощью MDT можно найти в разделе [развертывание образа Windows 10 с помощью MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**WindowsPE и программное обеспечение для поверхностей и драйверы**

Диспетчер конфигурации конечной точки и MDT используют среду предварительной установки Windows (WindowsPE) в процессе развертывания. WindowsPE поддерживает только ограниченный набор основных драйверов, например для сетевых адаптеров и контроллеров хранилища. Драйверы для компонентов Windows, которые не являются частью WindowsPE, могут привести к ошибкам. Чтобы предотвратить подобные ошибки, настройте процесс развертывания так, чтобы он использовал только необходимые драйверы на этапе WindowsPE.

###  <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

Начиная с диспетчера конфигурации конечной точки, вы можете синхронизировать и развертывать микропрограммы и обновления драйверов Microsoft Surface с помощью клиента Configuration Manager. Дополнительные сведения можно найти в статьях KB 4098906, [посвященных управлению обновлениями драйвера Surface в диспетчере Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

##  <a name="supported-devices"></a>Поддерживаемые устройства

Загружаемые MSI-файлы доступны для устройств Surface Pro 2 и более поздних версий (за исключением Surface Pro X, работающего под управлением Windows 10 на ARM).

##  <a name="managing-firmware-with-dfci"></a>Встроенное по управления с помощью DFCI

С помощью интерфейса конфигурации встроенного микрокода устройства (DFCI), встроенного в Intune (теперь доступно в общедоступном [предварительном просмотре](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), управление UEFI Surface расширяет современный стек управления до уровня оборудования UEFI. DFCI поддерживает подготовку от нуля, исключаются пароли BIOS, обеспечивает управление параметрами безопасности (в том числе параметрами запуска и встроенными периферийными устройствами), а также размещает основу для более сложных сценариев безопасности в будущем. Дополнительные сведения доступны в следующих статьях.

- [Управление параметрами UEFI Surface в Intune](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: объявляет удаленное управление параметрами UEFI Surface из Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

##  <a name="best-practices-for-update-deployment-processes"></a>Советы и рекомендации по обновлению процесса развертывания

Для поддержания стабильной среды мы настоятельно рекомендуем сохранить четность в последней версии Windows 10.  Рекомендации по [развертыванию обновлений для Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)содержатся в разделе Сборка сборок.

##  <a name="downloadable-surface-update-packages"></a>Загружаемые пакеты обновлений Surface

В некоторых версиях Windows 10 есть отдельные MSI-файлы, каждый из которых содержит все необходимые накопительные обновления драйверов и микропрограмм для устройств Surface. Пакеты обновления могут включать некоторые или все следующие компоненты:

- Wi-Fi и LTE
- Видео
- Твердотельный накопитель
- Модуль агрегации системы (SAM)
- Аккумулятор
- Контроллер клавиатуры
- Встроенный контроллер (EC)
- Механизм управления (я)
- Унифицированный расширяемый интерфейс микропрограмм (UEFI)

###  <a name="downloading-.msi-files"></a>Скачивание MSI-файлов

1. Перейдите в центр загрузки Майкрософт [и загрузите драйверы и встроенное по для Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) .
2. Выберите имя MSI-файла, которое соответствует модели Surface и версии Windows. Имя MSI-файла включает минимальный поддерживаемый номер сборки Windows, необходимый для установки драйверов и встроенного по. Например, на рисунке ниже. Чтобы обновить Surface Book 2, у которого есть сборка 18362 в Windows 10, выберите **SurfaceBook2_Win10_18362_19.101.13994.msi.** Для Surface Book 2, на котором установлена сборка 16299 в Windows 10, выберите **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Рисунок 1. Загрузка обновлений Surface](images/fig1-downloads-msi.png)

    *Рисунок 1. Загрузка обновлений Surface*

###  <a name="surface-.msi-naming-convention"></a>Соглашение об именовании Surface. msi

Так как в августе 2019. MSI-файлы используют следующее соглашение об именовании:

- *Product*_*Windows выпуска*_*номер версии номера сборки для Windows*_*Version number*_, версия номер версии *(обычно ноль)*.

**Пример.**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Это имя файла содержит указанные ниже сведения.

- **Продукт:** SurfacePro6
- **Выпуск Windows:** Win10
- **Сборка:** 18362
- **Version (версия):** 19.073.44195 – Дата и время создания файла, как показано ниже.
  - **Год:** 19 (2019)
  - **Месяц и неделя:** 073 (третья неделя июльа)
  - **Минуты месяца:** 44195
- Версия **:** 0 (первый выпуск этой версии)

###  <a name="legacy-surface-.msi-naming-convention"></a>Устаревшие правила именования Surface. msi

Устаревшие MSI-файлы (файлы, созданные до августа 2019) следуют одной общей формулой именования, но для получения номера версии используется другой метод.

**Пример.**

- SurfacePro6_Win10_16299_1900307_0.msi

Это имя файла содержит указанные ниже сведения.

- **Продукт:** SurfacePro6
- **Выпуск Windows:** Win10
- **Сборка:** 16299
- **Version (версия):** 1900307 — Дата создания файла и его положения в последовательности выпусков, как показано ниже.
  - **Год:** 19 (2019)
  - **Номер выпуска:** 003 (третий выпуск года)
  - **Номер версии продукта:** 07 (Surface Pro 6 официально является седьмой версией Surface Pro)
- Версия **:** 0 (первый выпуск этой версии)

##  <a name="learn-more"></a>Подробнее

- [Загрузка драйверов и встроенного по для Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Управление обновлениями драйвера Surface в Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Развертывание приложений с помощью Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Документация по Configuration Manager для конечной точки](https://docs.microsoft.com/configmgr/)
- [Документация по набору средств развертывания Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Развертывание Windows 10 с помощью Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Развертывание Windows 10 на Surface Devices с помощью набора средств развертывания Microsoft](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Управление параметрами UEFI Surface в Intune](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: объявляет удаленное управление параметрами UEFI Surface из Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Построение кругов развертывания для обновлений Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
