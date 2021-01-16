---
title: Windows Autopilot и устройства Surface
ms.reviewer: ''
manager: laurawi
description: Узнайте о вариантах развертывания Windows Autopilot для устройств Surface.
keywords: autopilot, windows 10, surface, развертывание
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
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271105"
---
# Windows Autopilot и устройства Surface

Windows Autopilot — это облачная технология развертывания в Windows 10. Вы можете использовать Windows Autopilot для удаленного развертывания и настройки устройств в процессе нулевого касания сразу после этого.

Традиционно ИТ-специалисты проводят много времени на создании и настройке образов, которые позже будут развернуты на устройствах, уже установленных на них с совершенно хорошей ОС. Windows Autopilot представляет новый подход к развертыванию без касания с использованием набора технологий для настройки и настройки устройств с Windows. Это позволяет ИТ-отделу настраивать и настраивать образы практически без инфраструктуры для управления и простой и простой процесс. С точки зрения пользователя, для того чтобы surface была эффективной, требуется всего несколько простых действий. На самом деле, единственное взаимодействие, необходимое пользователю, — подключение к сети и проверка его учетных данных. Все после этого полностью автоматизировано.

Windows Autopilot позволяет:

- Автоматически присоединять устройства к Azure Active Directory (Azure AD).
- Автоматическая регистрация устройств в службах MDM, таких как Microsoft Intune (требуется подписка на Azure AD Premium).
- Ограничивать создание учетной записи администратора. Autopilot — единственный способ, с которого первый пользователь, войдя в Windows, войдет в систему как обычный пользователь.
- Создание и автоматическое назначение устройств группам конфигураций на основе профилей устройств.
- Настройка содержимого и фирменности при OOBE в зависимости от организационных требований.
- Включить полную конфигурацию устройств с помощью Intune.
- Удаленное сброс или перезапуск устройств.

## Принцип работы

Устройства, зарегистрированные в Windows Autopilot, идентифицированы через Интернет при первом запуске с помощью уникальной сигнатуры устройства, которая называется аппаратным *hashом.* Они автоматически регистрируются и настраиваются с помощью современных решений управления, таких как Azure Active Directory (Azure AD) и управления мобильными устройствами.

Вы можете зарегистрировать устройства Surface во время покупки у партнера Surface, который включил Windows Autopilot. Эти партнеры могут погрузить новые устройства непосредственно вашим пользователям. Устройства будут автоматически зарегистрированы и настроены при первом включии. Этот процесс исключает переопределение во время развертывания, что позволяет реализовать новые гибкие методы управления устройствами и их распространения.

## Современные средства управления

Autopilot — это рекомендуемый вариант развертывания для устройств Surface, включая Surface Pro 7+, Surface Laptop 3, Surface Pro 7 и Surface Pro X, специально разработанный для развертывания с помощью Autopilot.

 Лучше всего зарегистрировать устройства Surface с помощью поставщика облачных решений Майкрософт. Этот шаг позволяет управлять настройками микропрограмм UEFI на Surface непосредственно из Intune. Это устраняет необходимость физического сенсорного управления сертификатами. Подробные сведения см. в управлении [Intune настройками UEFI Surface.](surface-manage-dfci-guide.md)

## Вопросы, учитывая версию Windows

Для широкого развертывания устройств Surface с помощью Windows Autopilot, включая регистрацию партнеров Surface на момент покупки, требуется Windows 10 версии 1709 (Fall Creators Update) или более поздней версии.

Эти версии Windows поддерживают 4000-byte (4k) значение hash, которое уникальным образом идентифицирует устройства для Windows Autopilot, что необходимо для развертывания в масштабе. Все новые устройства Surface, включая Surface Pro 7+, Surface Pro X и Surface Laptop 3, погрузка с Windows 10 версии 1903 или более поздней версии.

## Работа с Exchange на устройствах Surface, которые нуждаются в восстановлении или замене

Корпорация Майкрософт автоматически проверяет каждую регистрацию Autopilot на Surface и отключит регистрацию устройства в клиенте клиента.  Корпорация Майкрософт гарантирует, что заменяющее устройство будет зарегистрироваться в Windows Autopilot после отправки замены клиенту. Эта служба доступна во всех заказах на обслуживание Exchange устройств напрямую корпорацией Майкрософт.

> [!NOTE]
> Когда клиенты возвращают устройства с помощью партнера, он отвечает за управление процессом обмена, включая регистрацию и регистрацию устройств в Windows Autopilot.

## Регистрация в службе поддержки Майкрософт

Клиенты и поставщики облачных решений Майкрософт могут регистрировать устройства Surface, отсылая запросы в службу поддержки Майкрософт. Дополнительные см. в [подразделе "Поддержка регистрации Surface для Windows Autopilot".](surface-autopilot-registration-support.md)

## Партнеры Surface, включенные для Windows Autopilot

Выберите партнеров Surface, которые могут зарегистрировать устройства Surface в Windows Autopilot для вас во время покупки. Они также могут погрузить зарегистрированные устройства непосредственно вашим пользователям. Устройства можно полностью настроить с помощью процесса нулевого касания с помощью Windows Autopilot, Azure AD и управления мобильными устройствами.

К партнерам Surface, включенным для Windows Autopilot, относятся:

| Партнеры ИЗ США | Глобальные партнеры | Дистрибьюторы в США |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [ТАКЖЕ](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Подключение](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [СИБ](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Защищенная защита доверия](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Подробнее

Дополнительные сведения о Windows Autopilot см. в:
- [Общие сведения о Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Требования к Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Поддержка регистрации Surface для Windows Autopilot](surface-autopilot-registration-support.md)