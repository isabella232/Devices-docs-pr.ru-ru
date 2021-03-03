---
title: Подготовка среды для Surface Hub 2S
description: Узнайте, что нужно сделать для подготовки среды к Surface Hub 2S.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385147"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>Подготовка среды для Surface Hub 2S

## <a name="office-365-readiness"></a>Готовность Office 365

Если вы используете Exchange Online, Skype для бизнеса Online, Microsoft Teams или Microsoft Whiteboard и собираетесь управлять Surface Hub 2S с помощью Intune, сначала просмотрите требования [Office 365](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)для конечных точек.

Конечные точки Office 365 помогают оптимизировать сеть, отправляя все надежные сетевые запросы Office 365 непосредственно через брандмауэр, минуя все дополнительные проверки или обработки на уровне пакетов. Эта функция снижает задержку и требования к емкости периметра.

Корпорация Майкрософт регулярно обновляет службу Office 365 новыми функциями и функциями, которые могут изменять необходимые порты, URL-адреса и IP-адреса. Чтобы оценить, настроить и оставаться в курсе изменений, подпишитесь на [IP-адрес Office 365 и веб-службу URL-адресов.](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

> [!NOTE]
> Surface Hub работает с Microsoft Teams, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 или Skype для бизнеса Online.
Более ранние платформы, например Lync Server 2013, не поддерживаются. Surface Hub не поддерживается в GCC-High средах doD.


## <a name="device-affiliation"></a>Присоединение к устройству

Использование принадлежности к устройству для управления доступом пользователей к приложению Параметры на Surface Hub 2S.
С операционной системой Windows 10 Team (которая работает на Surface Hub 2S) только уполномоченные пользователи могут настраивать параметры с помощью приложения Параметры. Так как выбор принадлежности может повлиять на доступность компонентов, запланируйте соответствующий план, чтобы пользователи могли получать доступ к функциям по назначению.

> [!NOTE]
> Присоединение к устройству можно установить только во время начальной установки OOBE. Если необходимо сбросить присоединение к устройству, необходимо повторить установку OOBE.

## <a name="no-affiliation"></a>Отсутствие аффилированности

Отсутствие присоединений не похоже на наличие Surface Hub 2S в группе с другой учетной записью локального администратора на каждой surface Hub 2S. Если вы выбираете "Нет принадлежности", необходимо локально сохранить [ключ BitLocker на usb-накопителе.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq) Вы по-прежнему можете записать устройство с помощью Intune; Однако только локальный администратор может получить доступ к приложению Параметры с помощью учетных данных учетных записей, настроенных во время OOBE. Пароль учетной записи администратора можно изменить из приложения Параметры.

## <a name="active-directory-domain-services"></a>Доменные службы Active Directory

Если вы присоединены к Surface Hub 2S с локальной службой домена Active Directory, необходимо управлять доступом к приложению Settings с помощью группы безопасности на домене. Это позволяет гарантировать, что у всех участников группы безопасности есть разрешения на изменение параметров в Surface Hub 2S. Также обратите внимание на следующее:

- При присоединении Surface Hub 2S к локальной службе домена Active Directory ключ BitLocker можно сохранить в схеме Active Directory. Дополнительные сведения см. в [сайте Prepare your organization for BitLocker: Planning and policies.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)

- Доверенные корневые CAs организации передвигаются в один контейнер в Surface Hub 2S, что означает, что импортировать их с помощью пакета предварительного обеспечения не требуется.

- Вы по-прежнему можете зарегистрировать устройство с помощью Intune для централизованного управления настройками на surface Hub 2S.

## <a name="azure-active-directory"></a>Azure Active Directory

При присоединении Surface Hub 2S к Azure Active Directory (Azure AD) любой пользователь группы глобальной безопасности администраторов может войти в приложение Параметры на Surface Hub 2S. Кроме того, можно настроить учетные записи администратора, которые ограничивают разрешения на управление приложением "Параметры" на Surface Hub 2S. Это позволяет использовать разрешения администратора только для Surface Hub 2S и предотвращать потенциально нежелательный доступ администратора во всем домене Azure AD. 

Если вы включили автоматическую регистрацию Intune для своей организации, Surface Hub 2S автоматически зарегистрируется в Intune. Клавиша BitLocker устройства автоматически сохранена в Azure AD. 

Дополнительные информацию об управлении Surface Hub с Помощью Azure AD см. в этой ссылке. 

 - [Управление группой администраторов](admin-group-management-for-surface-hub.md)
 - [Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub 2S](surface-hub-2s-nonglobal-admin.md)

