---
title: Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание
description: В этой статье рассказывается о доступных вариантах управления и развертывания обновлений прошивки и драйверов для устройств Surface.
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
ms.openlocfilehash: afc7b2e82519fb42ca07b107bff73ddea894cfdf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911644"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание

Управление обновлениями драйвера и прошивки Surface зависит от среды и организационных требований. На устройствах Surface прошивка подвергается воздействию операционной системы в качестве драйвера и отображается в диспетчере устройств. Это позволяет автоматически обновлять прошивку устройства и драйверы с Windows обновления Windows для бизнеса. Хотя этот упрощенный подход может быть осуществим для стартапов и малого или среднего бизнеса, крупные организации, как правило, нуждаются в ИТ-администраторах для внутренней распространения обновлений. Это может включать комплексное планирование, тестирование совместимости приложений, а также пилотирование и проверку обновлений перед окончательным утверждением и распространением по сети.

> [!NOTE]
> Эта статья предназначена для агентов технической поддержки и ИТ-специалистов и применяется только к устройствам Surface. Если вы ищете помощь для установки обновлений Surface или прошивки на домашнем устройстве, см. в рублях Обновление прошивки [Surface и Windows 10.](https://support.microsoft.com/help/4023505)

Несмотря на то, что решения по распространению программного обеспечения корпоративного уровня продолжают развиваться, бизнес-обоснование централизованного управления обновлениями остается тем же: поддерживать безопасность устройств Surface и обновлять их с помощью последней операционной системы и улучшений функций. Это необходимо для поддержания стабильной производственной среды и обеспечения того, чтобы пользователи не блокировали производительность. В этой статье представлен обзор рекомендуемых инструментов и процессов для более крупных организаций для достижения этих целей.

## <a name="central-update-management-in-commercial-environments"></a>Управление центральным обновлением в коммерческих средах

Корпорация Майкрософт упорядочена для управления устройствами , включая обновления драйверов и микропрограммных программ, в единый единый интерфейс, который называется Microsoft Endpoint Manager центра администрирования и имеет доступ из [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home). [](https://devicemanagement.microsoft.com/)

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Управление обновлениями с помощью Диспетчер конфигурации и Intune

Microsoft Endpoint Configuration Manager позволяет синхронизировать и развернуть обновления прошивки Surface и драйвера с клиентом Configuration Manager. Интеграция Microsoft Intune позволяет видеть все управляемые, управляемые совместно и управляемые партнерами устройства в одном месте. Это рекомендуемое решение для крупных организаций для управления обновлениями Surface.

Подробные действия см. в следующих ресурсах:

- [Управление обновлениями драйверов Surface в Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Развертывание приложений с помощью диспетчера конфигурации](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Документация по диспетчеру конфигурации конечной точки](https://docs.microsoft.com/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Управление обновлениями с помощью microsoft Deployment набор средств

Программа развертывания майкрософт набор средств (MDT) включена в диспетчер конфигурации конечной точки. Он содержит необязательные средства развертывания, которые можно использовать в зависимости от среды. К ним относятся набор Windows и развертывания (Windows ADK), Windows System Image Manager (Windows SIM), обслуживание и управление изображениями развертывания (DISM) и средство миграции состояния пользователя (USMT). Вы можете скачать последнюю версию MDT с страницы [microsoft Deployment набор средств загрузки](https://www.microsoft.com/download/details.aspx?id=54259).

Подробные действия см. в следующих ресурсах:

- [Документация набор средств развертывания Майкрософт](https://docs.microsoft.com/configmgr/mdt/)
- [Развертывание Windows 10 с помощью Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Развертывание Windows 10 устройств Surface с помощью microsoft Deployment набор средств](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Обновления драйвера surface и прошивки упаковываются в Windows (*.msi). Для развертывания этих Windows установщика можно использовать диспетчер конфигурации конечной точки или MDT. Сведения о том, как правильно выбрать .msi для устройства и операционной системы, обратитесь к руководствам в следующих разделах о загрузке .msi файлов.

Инструкции по развертыванию обновлений с помощью диспетчера конфигурации конечных точек см. в инструкции по развертыванию приложений [с помощью Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications) Инструкции по развертыванию обновлений с помощью MDT см. в Windows 10 изображения с помощью [MDT.](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)

**Прошивка WindowsPE и Surface и драйверы**

Диспетчер конфигурации конечной точки и MDT используют Windows среды предварительной настройки (WindowsPE) во время процесса развертывания. WindowsPE поддерживает только ограниченный набор базовых драйверов, таких как сетевые адаптеры и контроллеры хранения. Драйверы для Windows компонентов, которые не являются частью WindowsPE, могут создавать ошибки. В качестве наилучшей практики можно предотвратить такие ошибки, настроив процесс развертывания, чтобы использовать только необходимые драйверы на этапе WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

Начиная с endpoint Configuration Manager, вы можете синхронизировать и развернуть обновления прошивки Microsoft Surface и драйвера с помощью клиента Configuration Manager. Дополнительные сведения см. в 4098906 KB, как управлять обновлениями [драйвера Surface в Configuration Manager.](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)

## <a name="supported-devices"></a>Поддерживаемые устройства

Загружаемые .msi доступны для Surface Pro 2 и более поздних устройств (за исключением Surface Pro X, который Windows 10 на ARM).

## <a name="managing-firmware-with-dfci"></a>Управление программным обеспечением с помощью DFCI

Благодаря встроению профилей интерфейса конфигурации прошивки устройств (DFCI) в Intune (теперь доступно для общего [просмотра),](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)управление Surface UEFI расширяет современный стек управления до уровня оборудования UEFI. DFCI поддерживает подготовка без касания, устраняет пароли BIOS, обеспечивает контроль параметров безопасности (в том числе параметров запуска и встроенных периферийных устройств) и закладывая основу для расширенных сценариев безопасности в будущем. Дополнительные сведения доступны в следующих статьях.

- [Управление параметрами UEFI Surface в Intune](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: объявление удаленного управления настройками Surface UEFI из Intune.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)

## <a name="best-practices-for-update-deployment-processes"></a>Лучшие практики для процессов развертывания обновления

Для поддержания стабильной среды настоятельно рекомендуется поддерживать паритет с последней версией Windows 10.  Рекомендации по рекомендациям см. в [рекомендациях Build deployment rings for Windows 10 обновлений.](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

## <a name="downloadable-surface-update-packages"></a>Загружаемые пакеты обновлений Surface

Конкретные версии Windows 10 имеют отдельные .msi, каждый из которых содержит все необходимые накопительные обновления драйвера и прошивки для устройств Surface. Пакеты обновления могут включать некоторые или все следующие компоненты:

- Wi-Fi и LTE
- Видео
- Накопитель твердого состояния
- Модуль системного агрегатора (SAM)
- Аккумулятор
- Контроллер клавиатуры
- Встроенный контроллер (EC)
- Движок управления (ME)
- Единый extensible интерфейс прошивки (UEFI)

### <a name="downloading-msi-files"></a>Загрузка .msi файлов

1. Просмотрите [для скачивания драйверов и прошивки для Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) в Центре загрузки Майкрософт.
2. Выберите имя .msi, которое соответствует модели Surface и версии Windows. Имя .msi содержит минимальный поддерживаемый Windows, необходимый для установки драйверов и прошивки. Например, обратитесь к следующему рисунку. Чтобы обновить Surface Book 2 с сборкой 18362 Windows 10, выберите **SurfaceBook2_Win10_18362_19.101.13994.msi.** Для Surface Book 2 с сборкой 16299 Windows 10 выберите **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Рисунок 1. Загрузка обновлений Surface.](images/fig1-downloads-msi.png)

    *Рисунок 1. Загрузка обновлений Surface*

### <a name="surface-msi-naming-convention"></a>Конвенция .msi surface

С августа 2019 г. .msi файлы используют следующую конвенцию именования:

- *Выпуск*_*Windows Windows*_*версии*_**_(как правило,*ноль).*

**Пример**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

В этом имени файла приводится следующая информация:

- **Продукт:** SurfacePro6
- **Windows выпуска:** Win10
- **Сборка:** 18362
- **Версия:** 19.073.44195 — Это показывает дату и время создания файла следующим образом:
  - **Год:** 19 (2019)
  - **Месяц и неделя:** 073 (третья неделя июля)
  - **Минута месяца:** 44195
- **Версия:** 0 (первый выпуск этой версии)

### <a name="legacy-surface-msi-naming-convention"></a>Конвенция .msi имени Legacy Surface

Устаревшие .msi (файлы, которые были построены до августа 2019 г.) следовали той же общей формуле именования, но использовали другой метод для получения номера версии.

**Пример**

- SurfacePro6_Win10_16299_1900307_0.msi

В этом имени файла приводится следующая информация:

- **Продукт:** SurfacePro6
- **Windows выпуска:** Win10
- **Сборка:** 16299
- **Версия:** 1900307 — Это показывает дату создания файла и его положение в последовательности выпуска следующим образом:
  - **Год:** 19 (2019)
  - **Количество выпуска:** 003 (третий выпуск года)
  - **Номер версии продукта:** 07 (Surface Pro 6 официально является седьмой версией Surface Pro)
- **Версия:** 0 (первый выпуск этой версии)

## <a name="learn-more"></a>Подробнее

- [Скачайте драйверы и прошивку для Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Управление обновлениями драйвера Surface в диспетчере конфигурации](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Развертывание приложений с помощью диспетчера конфигурации](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Документация по диспетчеру конфигурации конечной точки](https://docs.microsoft.com/configmgr/)
- [Документация набор средств развертывания Майкрософт](https://docs.microsoft.com/configmgr/mdt/)
- [Развертывание Windows 10 с помощью Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Развертывание Windows 10 устройств Surface с помощью microsoft Deployment набор средств](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Управление параметрами UEFI Surface в Intune](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: объявление удаленного управления настройками Surface UEFI из Intune.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
- [Построение кругов развертывания для обновлений Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
