---
title: Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание
description: В этой статье содержатся ссылки на загружаемые пакеты, содержащие обновления драйвера и прошивки для устройств Surface, а также разъясняются доступные решения для управления и развертывания.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 8, Surface Go, Surface Laptop, Surface Studio, Surface Pro 3, прошивка, обновление, устройство, управление, развертывание, драйвер, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: f914678f2317ce4e08554d27b74bac4e33e3c641
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449642"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Управление обновлениями драйверов и встроенного ПО Surface, а также их развертывание

Управление обновлениями драйвера и прошивки Surface может отличаться в зависимости от среды и организационных требований. В крупных организациях ИТ-администраторы, как правило, поэтапно развертывают внутренние системы и выделяют время для тестирования обновлений перед их развертыванием на устройствах пользователей.

> [!NOTE]
> Эта статья предназначена для ИТ-специалистов и агентов технической поддержки и применяется только к устройствам Surface. Если вы ищете помощь в установке обновлений Surface или прошивки на домашнем устройстве, см. в справке [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023505).

Несмотря на то, что решения по распространению программного обеспечения корпоративного уровня продолжают развиваться, бизнес-обоснование централизованного управления обновлениями остается тем же: поддерживать безопасность устройств Surface и обновлять их с помощью последней операционной системы и улучшений функций. Это необходимо для поддержания стабильной производственной среды и обеспечения того, чтобы пользователи не блокировали производительность.

## <a name="whats-in-surface-driver-and-firmware-updates"></a>Что происходит в обновлениях драйвера и прошивки Surface

Windows файлы .msi содержат все необходимые накопительные обновления драйвера и прошивки для устройств Surface. Пакеты обновления могут включать некоторые или все следующие компоненты:

- Wi-Fi и LTE
- Видео
- Твердотопливный диск
- Модуль системного агрегатора (SAM)
- Аккумулятор
- Контроллер клавиатуры
- Встроенный контроллер (EC)
- Движок управления (ME)
- Единый extensible интерфейс прошивки (UEFI)

## <a name="download-msi-files"></a>Загрузка .msi файлов

В этом разделе содержатся прямые ссылки на загружаемые пакеты, содержащие обновления драйвера и прошивки для устройств Surface. 

1. Выберите Windows 10 или Windows 11 по мере необходимости. 
2. Для устройств с несколькими .msi файлами выберите имя .msi, которое соответствует модели Surface и версии Windows, развернутой в организации.  


| Устройство Surface                                                                                                                                        | Загружаемые .msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ и Surface Pro 7+ (LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE)](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface Laptop**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop 4 с процессором Intel](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 с процессором AMD](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 с процессором Intel](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 с процессором AMD](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop Studio**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE)](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) — ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) — Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE) — разблокирован оператор в Северной Америке](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE) — за пределами Северной Америки и Y!mobile в Японии](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub** [**работает Windows 10 Pro или Windows 10 Корпоративная**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 Pro и Enterprise оси Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub обновления Windows 10 Teams 2020 г.**                                                                                                  | - См[. Windows обновления на Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> Для более ранних устройств, которые включают отдельные файлы для различных Windows версий, выберите имя .msi, которое соответствует модели Surface и версии Windows. Имя .msi содержит минимальный поддерживаемый Windows, необходимый для установки драйверов и прошивки. Например, чтобы обновить Surface Book 2 с сборкой 18362 Windows 10, выберите **SurfaceBook2_Win10_18362_19.101.13994.msi.** Для Surface Book 2 с сборкой 16299 Windows 10 выберите **SurfaceBook2_Win10_16299_1803509_3.msi**.

## <a name="central-update-management-in-commercial-environments"></a>Управление центральным обновлением в коммерческих средах

Средства для управления устройствами, включая обновления драйверов и прошивки, включены [в Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/). 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Управление обновлениями с помощью Диспетчер конфигурации и Intune

Microsoft Endpoint Configuration Manager позволяет синхронизировать и развернуть обновления прошивки Surface и драйвера с клиентом Configuration Manager. Интеграция Microsoft Intune позволяет видеть все управляемые, управляемые совместно и управляемые партнерами устройства в одном месте. Это рекомендуемое решение для крупных организаций для управления обновлениями Surface.

Подробные действия см. в следующих ресурсах:

- [Управление обновлениями драйверов Surface в Configuration Manager](manage-surface-driver-updates-configuration-manager.md)
- [Развертывание приложений с помощью диспетчера конфигурации](/configmgr/apps/deploy-use/deploy-applications)
- [Документация по диспетчеру конфигурации конечной точки](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Управление обновлениями с помощью microsoft Deployment набор средств

Служба развертывания Майкрософт набор средств (MDT) включена в диспетчер конфигурации конечных точек. В зависимости от среды он содержит необязательные средства развертывания, которые можно использовать.  К ним относятся набор Windows и развертывание (Windows ADK), Windows System Image Manager (Windows SIM), обслуживание и управление изображениями развертывания (DISM) и средство миграции состояния пользователя (USMT). Последнюю версию MDT можно скачать на странице [Microsoft Deployment набор средств загрузки](https://www.microsoft.com/download/details.aspx?id=54259).

Подробные действия см. в следующих ресурсах:

- [Документация набор средств развертывания Майкрософт](/configmgr/mdt/)
- [Подготовка к развертыванию с помощью MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

Инструкции по развертыванию обновлений с помощью диспетчера конфигурации конечной точки см. в инструкции По развертыванию приложений [с помощью Configuration Manager](/configmgr/apps/deploy-use/deploy-applications). Инструкции по развертыванию обновлений с помощью MDT см. в Windows 10 с помощью [MDT](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Прошивка WindowsPE и Surface и драйверы**

Диспетчер конфигурации конечной точки и MDT используют Windows среды предварительной настройки (WindowsPE) во время процесса развертывания. WindowsPE поддерживает только ограниченный набор основных драйверов, таких как сетевые адаптеры и контроллеры хранения. Драйверы для Windows компонентов, которые не являются частью WindowsPE, могут создавать ошибки. В качестве наилучшей практики можно предотвратить такие ошибки, настроив процесс развертывания, чтобы использовать только необходимые драйверы на этапе WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

Начиная с endpoint Configuration Manager, вы можете синхронизировать и развернуть обновления прошивки Microsoft Surface и драйвера с помощью клиента Configuration Manager. Дополнительные сведения см. в 4098906,Управление обновлениями [драйвера Surface в Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>Поддерживаемые устройства

Загружаемые .msi доступны для Surface Pro 2 и более поздних устройств (за исключением Surface Pro X, который Windows 10 на ARM).

## <a name="managing-firmware-with-dfci"></a>Управление программным обеспечением с помощью DFCI

Благодаря встроению профилей интерфейса конфигурации прошивки устройств (DFCI) в [Intune](/intune/configuration/device-firmware-configuration-interface-windows) управление Surface UEFI расширяет современный стек управления до уровня оборудования UEFI. DFCI поддерживает подготовка без касания, устраняет пароли BIOS, обеспечивает контроль параметров безопасности (в том числе параметров запуска и встроенных периферийных устройств) и закладывая основу для расширенных сценариев безопасности в будущем. Дополнительные сведения см. в следующих разделах:

- [Управление DFCI на устройствах Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: объявление удаленного управления настройками Surface UEFI из Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## <a name="best-practices-for-update-deployment-processes"></a>Лучшие практики для процессов развертывания обновления

Для поддержания стабильной среды настоятельно рекомендуется сохранить паритет с последней версией Windows 10.  Рекомендации по наилучшей практике см. в [рубке Подготовка стратегии обслуживания для Windows клиентских обновлений](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### <a name="surface-msi-naming-convention"></a>Конвенция .msi surface

С августа 2019 г. .msi файлы используют следующую конвенцию именования:

- *Product* _*Windows release*_ *Windows сборка numberVersion*_**_ *numberRevision номера версии (обычно ноль).*.

**Пример**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

В этом имени файла приводится следующая информация:

- **Продукт:** SurfacePro6
- **Windows:** Win10
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
- **Windows:** Win10
- **Сборка:** 16299
- **Версия:** 1900307 — Это показывает дату создания файла и его положение в последовательности выпуска следующим образом:
  - **Год:** 19 (2019)
  - **Количество выпуска:** 003 (третий выпуск года)
  - **Номер версии продукта:** 07 (Surface Pro 6 официально является седьмой версией Surface Pro)
- **Версия:** 0 (первый выпуск этой версии)

## <a name="learn-more"></a>Подробнее

- [Подготовка стратегии обслуживания для обновлений клиентов Windows](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [Управление обновлениями драйверов Surface в Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Развертывание приложений с помощью диспетчера конфигурации](/configmgr/apps/deploy-use/deploy-applications)
- [Документация по диспетчеру конфигурации конечной точки](/configmgr/)
- [Документация набор средств развертывания Майкрософт](/configmgr/mdt/)
- [Подготовка к развертыванию с помощью MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Управление DFCI на устройствах Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: объявление удаленного управления настройками Surface UEFI из Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

