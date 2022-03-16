---
title: Портал управления Surface
description: В этой статье описывается, как новый портал управления поверхностью предоставляет централизованное решение для самостоятельного обслуживания, управления устройствами Surface и мониторинга их масштабирования.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/02/2021
ms.reviewer: hachinda
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 8c0f4f6c80ff7341b795839c3897dff6733414bc
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448882"
---
# <a name="surface-management-portal-overview"></a>Обзор портала управления Surface

Встроенный Microsoft Endpoint Manager, новый портал управления поверхностью предоставляет централизованное решение для самостоятельного обслуживания, управления устройствами Surface и мониторинга в масштабе.

## <a name="introduction"></a>Введение

В качестве единой среды для конечной видимости корпоративных или пользовательских устройств Surface портал Surface позволяет быстро видеть любые проблемы, которые требуют оперативного внимания, прежде чем они нажмют вашу службу поддержки.

Сведения о соблюдении требований к устройству, действиях поддержки и обеспечении гарантийного покрытия. Быстро см. состояние каждого устройства, которое по-прежнему находится в гарантии или истекающее в ближайшее время, и состояние активных запросов поддержки с поставщиками оборудования.

Когда устройства Surface регистрируются для управления облаками и пользователи в первый раз включались в систему, информация с этих устройств Surface автоматически поступает на портал управления поверхностью, предоставляя вам единую области стекла для действий администратора устройств, определенных surface.

См. также. [Известные проблемы ниже](#known-issues) . 

## <a name="get-started"></a>Начало работы

Войдите в Microsoft Endpoint Manager, щелкните **Все службы**, а затем щелкните **Портал управления поверхностью**.

:::image type="content" source="/surface/images/surface-management-portal/surface-management-portal-start.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-start.png" alt-text="Начните портал управления поверхностью":::

## <a name="monitor-surface-devices"></a>Монитор устройств Surface

Выберите **Монитор** , чтобы отобразить сведения для всех устройств Surface, в том числе:

- Устройства не соответствует требованиям, что может означать, что пользователи не могут получить доступ к информации, требующей входа в Azure AD.
- Устройства, которые не зарегистрированы.
- Устройства с критически низким уровнем хранения, доступные на диске, являются ведущим индикатором потенциальных проблем с опытом пользователей.
- Устройства, требующие обновлений.
- Устройства без включенного шифрования диска.
- Устройства, которые в настоящее время неактивны.

Выберите **отчет View,** чтобы просмотреть сведения о каждой категории сведений, предоставляя диагностические сведения, которые можно настроить и экспортировать.

:::image type="content" source="/surface/images/surface-management-portal/surface-management-portal-view-report.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-view-report.png" alt-text="Получить сведения об устройстве Surface и просмотреть отчет":::

## <a name="device-warranty-and-coverage"></a>Гарантия и покрытие устройств

если вы управляете сотнями или тысячами устройств, особенно полезен прямой доступ к гарантийным состояниям каждого устройства, что позволяет быстро увидеть следующую информацию:

- Устройства в гарантийный период
- Истечение срока действия устройств
- Устройства вне гарантии
- Устройства, имеющие право на необязательный охват

## <a name="support-requests"></a>Запросы на поддержку

Портал управления поверхностью предоставляет полную видимость действий поддержки наряду со статусом каждого запроса.

:::image type="content" source="/surface/images/surface-management-portal/surface-management-portal-support.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-support.png" alt-text="Сведения об активности службы поддержки, а также состояние каждого запроса.":::

## <a name="try-for-free"></a>Попробовать бесплатно

Портал управления поверхностью доступен клиентам, которые используют Microsoft Endpoint Manager и зарегистрировали устройства Surface через Intune. Если вы не в компании Intune, установите клиента Intune сегодня, посетив [Quickstart: Попробуйте Microsoft Intune бесплатно](/mem/intune/fundamentals/free-trial-sign-up).

## <a name="known-issues"></a>Известные проблемы

- Устранена проблема, из-за которую портал не был правильно загружен для небольшого числа клиентов. (3 ноября 2021 г.).

## <a name="learn-more"></a>Подробнее

- [Что такое microsoft Surface Management Portal?](/mem/intune/fundamentals/surface-management-portal?)
- [Microsoft Mechanics](https://youtu.be/_MmutkqNudk)
- [Surface ИТ Pro в блоге: портал управления поверхностью](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-management-portal/ba-p/1419017)
