---
title: Поддержка регистрации Surface для Windows Autopilot
description: В этой статье описываются требования для отправки запросов на регистрацию Autopilot в службу поддержки Майкрософт.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304842"
---
# Поддержка регистрации Surface для Windows Autopilot

Упрощенный процесс регистрации устройств Surface для развертывания Windows Autopilot теперь доступен в службе поддержки Майкрософт. С сентября 2020 г. клиенты и поставщики облачных решений (CPS) Майкрософт могут регистрировать устройства Surface, отсылая запросы в службу поддержки Майкрософт. На этой странице описаны требования для следующих поддерживаемых сценариев регистрации Autopilot:
 
- **Регистрация Autopilot устройства Surface.** Отправка запроса на регистрацию устройств Surface в Windows Autopilot.
- **Запрос на аппаратный hash-запрос устройства Surface.** Отправка запроса в службу поддержки Майкрософт для предоставления вам аппаратных хешей, которые клиенты или CSP могут использовать для самостоятельной регистрации устройств через Microsoft Intune или Центр партнеров Майкрософт.
- **Surface Device Autopilot Deregistration.** Отправка запроса на удаление устройств из Windows Autopilot, обычно используемых в сценариях окончания жизненного года устройства.

Подробные сведения, которые необходимо собрать перед отправкой запросов на регистрацию в службу поддержки Майкрософт, см. в следующей таблице. Официальные имена системных моделей всех устройств Surface можно найти в справочнике по [SKU Surface System.](surface-system-sku-reference.md)
 
**Таблица1. Необходимые сведения для запросов на регистрацию Autopilot**
 

| Необходимые сведения                   | Описание                                                                                                                                                                                                                                                                                    | Регистрация Autopilot | Запрос на аппаратный hash-запрос | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **ИД клиента Azure Active Directory**   | Идентификатор клиента Azure Active Directory — это глобальный уникальный идентификатор (GUID), который отличается от имени организации или домена.<br> <br>Чтобы найти свой ИД клиента, войдите на портал Azure [здесь.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Доменное имя Azure Active Directory** | Доменное имя верхнего уровня; например, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Подтверждение владения**                 | Проверьте право собственности, загрузив исходный счет-фактуру или счет в формате PDF. Снимки экрана не принимаются.<br> <br>Счет за продажу или счет-фактуру должен включать следующие счета:<br>Серийные номера устройств.<br>Название компании.                                                           | Y                      | Y                     | Y                           |
| **Серийные номера устройств**              | Отправка файла Excel в формате CSV с каждым серийным номером устройства в новой строке.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Отправка запросов в службу поддержки

  [![Get Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Подробнее

- [Windows Autopilot и устройства Surface](windows-autopilot-and-surface-devices.md)
- [Регистрация устройств с Windows в Intune с помощью Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Общие сведения о Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Справочник по номерам SKU системы Surface](surface-system-sku-reference.md)

 
 
 

