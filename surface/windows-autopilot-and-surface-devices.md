---
title: Windows Autopilot и устройства Surface
ms.reviewer: ''
manager: laurawi
description: Узнайте о вариантах развертывания Windows для автопилота для устройств Surface.
keywords: Автопилот, Windows 10, поверхность, развертывание
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834619"
---
# Windows Autopilot и устройства Surface

Windows Pilot — это облачная технология развертывания в Windows 10. Вы можете использовать автопилот Windows для удаленного развертывания и настройки устройств в процессе с нулевым сенсорным подключением прямо из поля.

При первом запуске Windows автоматически загружаются зарегистрированные устройства по Интернету с помощью уникальной подписи устройства, которая называется *хэшем оборудования*. Они автоматически регистрируются и настраиваются с помощью современных решений для управления, таких как Azure Active Directory (Azure AD) и управление мобильными устройствами.

Устройства Surface можно зарегистрировать на этапе приобретения из Surface Partner, которая включена для Windows автопилота. Эти партнеры могут поставлять новые устройства непосредственно вашим пользователям. Устройства будут автоматически регистрироваться и настроены при первом включении. Этот процесс исключает reimaging во время развертывания, что позволяет реализовать новые гибкие методы управления и распространения устройств.

## Современные средства управления

Автопилот — рекомендуемый вариант развертывания для устройств Surface, в том числе Surface Pro 7, Surfaceing 3 и Surface Pro X, которые специально разработаны для развертывания с помощью автопилота.

 Рекомендуется регистрировать устройства Surface с помощью поставщика облачных решений (Майкрософт). Этот шаг позволяет управлять параметрами встроенного по UEFI прямо из Intune. Это позволяет устранить необходимость физически сенсорных устройств для управления сертификатами. Дополнительные сведения см. в разделе [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md) .

## Вопросы о версии Windows

Широкое развертывание Surface Devices с помощью Windows автопилота, включая регистрацию для партнеров по Surface на момент приобретения, требует Windows 10 версии 1709 (обновления для создателя обновлений) или более поздней версии.

Эти версии Windows поддерживают хэш-значение 4 000-Byte, которое однозначно определяет устройства для Windows для автоматического развертывания, которое необходимо для развертывания в масштабе. Все новые Surface Devices, в том числе Surface Pro 7, Surface Pro X и Surface 3, поставляются в Windows 10 версии 1903 или более поздней.

## Exchange на поверхностных устройствах, требующих восстановления или замены

Корпорация Майкрософт автоматически проверяет все поверхности для автоматической регистрации и будет отменять регистрацию устройства в клиенте.  Корпорация Майкрософт гарантирует, что заменяющее устройство будет зарегистрировано в Windows с помощью автопилота, когда вы вернете замену клиенту. Эта услуга доступна во всех заказах на обслуживание устройств обмена устройствами прямо в Microsoft.

> [!NOTE]
> Когда клиенты используют партнера для возврата устройств, он отвечает за управление процессом Exchange, включая отмену регистрации и регистрацию устройств в Windows автопилот.

## Партнеры Surface, включенные для Windows автопилота

Выберите "Партнеры Surface" могут регистрировать устройства Surface в Windows "Автопилот" на момент приобретения. Кроме того, они могут поставлять зарегистрированные устройства непосредственно вашим пользователям. Устройства можно настроить полностью с помощью нулевого сенсорного процесса с помощью Windows для автоматического развертывания, Azure AD и управления мобильными устройствами.

Участники Surface, включенные для Windows автопилота, включают:

| Партнеры США | Глобальные партнеры | Дистрибьюторы США |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [ОДНОВРЕМЕННО](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Соединение](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Подробнее

Дополнительные сведения о Windows Pilot можно найти в следующих статьях:
- [Общие сведения о Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Требования к Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)