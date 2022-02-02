---
title: Windows Autopilot и устройства Surface
ms.reviewer: ''
manager: laurawi
description: Узнайте о Windows развертывания автопилота для устройств Surface.
keywords: автопилот, Windows 10, поверхность, развертывание
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
ms.openlocfilehash: bfcb8c09b3228730e3255c4f92948dc4acfea506
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338542"
---
# <a name="windows-autopilot-and-surface-devices"></a>Windows Autopilot и устройства Surface

Windows автопилот — это облачная технология развертывания в Windows 10. Вы можете использовать Windows автопилот для удаленного развертывания и настройки устройств в процессе нулевого касания прямо из окна.

Традиционно ИТ-специалисты тратят много времени на создание и настройку изображений, которые позже будут развернуты на устройствах, которые уже установлены с отличной ОС. Windows автопилот представляет новый подход к развертыванию с нулевой касанием с помощью набора технологий для настройки и настройки Windows устройств. Это позволяет ИТ-отделу настраивать и настраивать изображения практически без инфраструктуры для управления, а процесс прост и прост. С точки зрения пользователя, для того чтобы получить Surface в продуктивное состояние, требуется всего несколько простых действий. На самом деле единственным взаимодействием, требуемом от конечных пользователей, является подключение к сети и проверка их учетных данных. Все после этого полностью автоматизировано.

Windows автопилот позволяет:

- Автоматически присоединяются устройства к Azure Active Directory (Azure AD).
- Автоматические устройства для регистрации в службы MDM, например Microsoft Intune (требуется подписка Azure AD Premium).
- Ограничивать создание учетной записи администратора. Автопилот — это единственный способ ввести первого пользователя, который Windows в качестве стандартного пользователя.
- Создание и автоматическое назначение устройств группам конфигурации на основе профилей устройств.
- Настройка контента и фирменности OOBE (вне полей) в зависимости от организационных требований.
- Включить полную конфигурацию устройства с помощью Intune.
- Сбросить или перезапустить устройства удаленно.

## <a name="how-it-works"></a>Принцип работы

Windows устройства, зарегистрированные на автопилоте, идентифицированы через Интернет при первом запуске с помощью уникальной подписи устройства, которая называется *аппаратным хашом*. Они автоматически регистрируются и настраиваются с помощью современных решений управления, таких как Azure Active Directory (Azure AD) и управления мобильными устройствами.

Устройства Surface можно зарегистрировать во время покупки у партнера Surface, включенного для Windows автопилота. Эти партнеры могут напрямую отгрузки новых устройств пользователям. Устройства будут автоматически зарегистрированы и настроены при первом включе. Этот процесс устраняет переопределение во время развертывания, что позволяет внедрять новые гибкие методы управления и распространения устройств.

## <a name="modern-management"></a>Современные средства управления

Автопилот — это рекомендуемый вариант развертывания для устройств Surface, в том числе Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Pro 7+, Surface Laptop 4 и Surface Pro X, который специально разработан для развертывания с помощью автопилота.

 Лучше всего записать устройства Surface с помощью поставщик облачных решений (Майкрософт). Этот шаг позволяет управлять настройками прошивки UEFI на Surface непосредственно из Intune. Это устраняет необходимость физического касания устройств для управления сертификатами. [Подробные сведения см. в руководстве Intune параметров Surface UEFI](surface-manage-dfci-guide.md).

## <a name="windows-version-considerations"></a>Windows версии

Широкое развертывание устройств Surface Windows автопилотом, включая регистрацию партнерами Surface на момент покупки, требует Windows 10 версии 1709 (Fall Creators Update) или более поздней версии.

Эти Windows поддерживают значение 4000-byte (4k), которое уникально определяет устройства для Windows автопилота, которое необходимо для развертывания в масштабе.

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange на устройствах Surface, которые нуждаются в ремонте или замене

Корпорация Майкрософт автоматически проверяет каждую регистрацию Surface для автопилота и отключит устройство от клиента- клиента.  Корпорация Майкрософт гарантирует, что заменяющее устройство будет Windows автопилот после отправки замены клиенту. Эта служба доступна во всех заказах службы обмена устройствами непосредственно с Корпорацией Майкрософт.

> [!NOTE]
> Когда клиенты используют партнер для возврата устройств, партнер отвечает за управление процессом обмена, включая регистрацию и регистрацию устройств в Windows автопилоте.

## <a name="microsoft-support-registration"></a>Регистрация службы поддержки Майкрософт

Клиенты и поставщики облачных решений Майкрософт могут регистрировать устройства Surface, отсылая запросы в Службу поддержки Майкрософт. Дополнительные дополнительные дополнительные документы см. в Windows surface [Registration Support for Windows автопилоте](surface-autopilot-registration-support.md).

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Партнеры Surface включены для Windows автопилота

Партнеры Surface могут записать устройства Surface в Windows автопилоте для вас на момент покупки. Они также могут отгрузки зарегистрированных устройств непосредственно пользователям. Устройства можно настроить полностью с помощью нулевого касания с помощью Windows автопилота, Azure AD и управления мобильными устройствами.

Партнеры Surface, которые включены для Windows автопилота, включают:

| Партнеры США | Глобальные партнеры | Дистрибьюторы в США |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [ТАКЖЕ](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  ["Подключение"](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI Подключение](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [Защищенный траст](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>Подробнее

Дополнительные сведения о Windows автопилоте см. в

- [Общие сведения о Windows Autopilot](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Требования к Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Поддержка регистрации Surface для Windows Autopilot](surface-autopilot-registration-support.md)
