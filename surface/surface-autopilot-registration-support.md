---
title: Поддержка регистрации Surface для Windows Autopilot
description: В этой статье описываются требования к отправке запросов на регистрацию автопилота в Службу поддержки Майкрософт.
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 77881fae189af1ad3773f5fad192a28746e2d983
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449422"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>Поддержка регистрации Surface для Windows Autopilot

Упрощенный процесс регистрации устройств Surface для развертывания Windows автопилота теперь доступен в Службе поддержки Майкрософт. Начиная с сентября 2020 г. клиенты и поставщики облачных решений Microsoft (CSPs) могут регистрировать устройства Surface, отсылая запросы в службу поддержки Майкрософт. На этой странице описаны требования для следующих поддерживаемых сценариев регистрации автопилота:
 
- **Регистрация автопилота surface device**. Отправка запроса на регистрацию устройств Surface в Windows автопилот.
- **Запрос на оборудование surface Device.** Отсылает запрос в службу поддержки Майкрософт, чтобы предоставить вам электронные хеши, которые клиенты или CSP могут использовать для самозарегистра устройств через Microsoft Intune или Центр партнеров Майкрософт.
- **Дерегулирование автопилота surface device.** Отправка запроса на удаление устройств из Windows автопилота, обычно используемых в сценариях конца жизни устройств.

Сведения о том, что необходимо собрать до отправки запросов на регистрацию в Службу поддержки Майкрософт, см. в следующей таблице. Для официальных имен системной модели всех устройств Surface обратитесь к [ссылке Surface System SKU](surface-system-sku-reference.md).
 
**Таблица 1: Необходимые сведения для запросов на регистрацию автопилота**
 

| Необходимые сведения                   | Описание                                                                                                                                                                                                                                                                                    | Регистрация автопилота | Запрос на хаш оборудования | Автопилот<br>Дерегулирование |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory клиента**   | Идентификатор Azure Active Directory является глобальным уникальным идентификатором (GUID), который отличается от имени организации или домена.<br> <br>Чтобы найти ваш знак "ID клиента" на портале Azure [, здесь](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Azure Active Directory доменное имя** | Доменное имя верхнего уровня; например, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Доказательство права собственности**                 | Убедитесь в подлинности, загрузив исходный счет продажи или счета-фактуры в формате PDF. Снимки экрана не принимаются.<br> <br>Счет продажи или счета-фактуры должен включать в себя следующие:<br>Серийные номера устройств.<br>Имя компании.                                                           | Y                      | Y                     | Y                           |
| **Серийные номера устройств**              | Upload Excel файл в формате CSV с каждым серийным номером устройства в новой строке.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## <a name="submit-support-requests"></a>Отправка запросов поддержки

  [![Get Autopilot Registration Support for Surface.](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>Подробнее

- [Windows Autopilot и устройства Surface](windows-autopilot-and-surface-devices.md)
- [Регистрация устройств с Windows в Intune с помощью Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Общие сведения о Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Справочник по номерам SKU системы Surface](surface-system-sku-reference.md)

 
 
 

