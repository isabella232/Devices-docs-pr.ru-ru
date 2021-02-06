---
title: Подготовка среды для Microsoft Surface Hub (v1)
description: В этом разделе описывается процедура подготовки среды для использования всех возможностей Microsoft Surface Hub.
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: подготовка среды, возможности Surface Hub, создание и тестирование учетной записи устройства, проверка доступности сети
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
appliesto:
- Surface Hub
ms.openlocfilehash: 95b575e5213e3e11685b342cb2a7b77eb3e868a0
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314402"
---
# Подготовка среды для Microsoft Surface Hub (v1)


Этот раздел содержит обзор зависимостей и процесса установки. Ознакомьтесь с этим разделом, чтобы подготовить свою среду и собрать сведения, необходимые для настройки Surface Hub.


## Инфраструктурные зависимости
Изучите эти зависимости, чтобы убедиться, что в вашей ИТ-инфраструктуре будут работать все функции Surface Hub.

| Зависимость        | Назначение           |
|-------------|------------------|
| Active Directory или Azure Active Directory (Azure AD) | <p>Surface Hub использует учетную запись Active Directory или Azure AD (которая называется **учетной записью устройства**) для доступа к службам Exchange и Skype для бизнеса. Surface Hub требуется подключение к вашему контроллеру домена Active Directory или к вашему клиенту Azure AD для проверки учетных данных учетной записи устройства, а также доступа к таким данным, как отображаемое имя, псевдоним, сервер Exchange Server и SIP-адрес устройства.</p>Вы также можете присоединить свое устройство Surface Hub к домену или к Azure AD, чтобы разрешить группе авторизованных пользователей настраивать параметры на Surface Hub. |
| Exchange (Exchange2013 или более поздней версии либо Exchange Online) и Exchange ActiveSync | <p>Exchange используется для поддержки почты и календаря, а также позволяет пользователям отправлять приглашения на собрания на Surface Hub и присоединяться к собраниям одним касанием.</p>ActiveSync используется, чтобы синхронизировать календарь и почту учетной записи устройства с Surface Hub. Если устройство не может использовать ActiveSync, оно не будет отображать собрания на экране приветствия, а функции присоединения к собраниям и отправки досок по почте будут недоступны. |
| Skype для бизнеса (Lync Server2013 или более поздней версии либо Skype для бизнеса Online)  | Skype для бизнеса используется для различных конференц-функций, таких как видеовызовы, мгновенные сообщения и демонстрация экрана.|
| Решение для управления мобильными устройствами (MDM) (Microsoft Intune, Microsoft Endpoint Configuration Manager или поддерживаемый сторонний поставщик MDM) | Если вы хотите применять параметры и устанавливать приложения дистанционно и на нескольких устройствах одновременно, вам необходимо установить решение MDM и зарегистрировать свое устройство в этом решении. См. раздел [Управление параметрами с помощью поставщика MDM](manage-settings-with-mdm-for-surface-hub.md). |
| Microsoft Operations Management Suite (OMS)   | OMS используется для контроля работоспособности устройств Surface Hub. См. раздел [Отслеживание устройства Surface Hub](monitor-surface-hub.md). |
| Доступ к сети и Интернету   | Для правильной работы у Surface Hub должен быть доступ к проводной или беспроводной сети. Предпочтительным является проводное подключение. Проверка подлинности 802.1x поддерживается как в проводных, так и в беспроводных подключениях.</br></br></br>**Проверка подлинности 802.1X:** в Windows 10 версии 1703 проверка подлинности 802.1X для проводных и беспроводных подключений включена по умолчанию в Surface Hub. Если ваша организация не использует проверку подлинности 802.1X, настройка не требуется. Surface Hub будет работать в обычном режиме. Если вы используете проверку подлинности 802.1 X, необходимо убедиться, что сертификаты проверки подлинности установлены на Surface Hub. Вы можете передать сертификат на Surface Hub с помощью [поставщика служб конфигурации ClientCertificateInstall](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) в MDM или [создать пакет подготовки](provisioning-packages-for-surface-hub.md) и установить его во время первого запуска либо с помощью приложения "Параметры". После применения сертификата к Surface Hub проверка подлинности 802.1X заработает автоматически.</br>**Примечание.** Дополнительные сведения о включении проверки подлинности по стандарту безопасности 802.1X в проводной сети в Surface Hub см. в разделе [Включение проверки подлинности по стандарту безопасности 802.1x в проводной сети](enable-8021x-wired-authentication.md).</br></br>**Динамический IP-адрес:** Surface Hub нельзя настроить на использование статического IP-адреса. IP-адрес должен назначаться с использованием протокола DHCP.</br></br>**Прокси-серверы:** если топология вашей сети предполагает подключение к прокси-серверу для доступа к интернет-службам, это подключение можно настроить при первом запуске или в приложении «Параметры». Учетные данные прокси-сервера сохраняются в сеансах Surface Hub, поэтому их необходимо указать только один раз. |

Кроме того, обратите внимание, что для Surface Hub должны быть открыты следующие порты:
- HTTPS: 443
- HTTP: 80
- NTP: 123

Если вы используете Surface Hub со Skype для бизнеса, вам потребуется открыть дополнительные порты. Следуйте рекомендациям ниже:
- Если вы используете Skype для бизнеса Online, см. URL-адреса и диапазоны IP-адресов [Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)
- Если вы используете Skype для бизнеса Server, см. "Skype для бизнеса Server: порты и [протоколы для внутренних серверов".](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols) 
- If you use a hybrid of Skype for Business Online and Skype for Business Server, you need to open all documented ports from [Office 365 IP URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) and [Skype for Business Server: Ports and protocols for internal servers](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Корпорация Майкрософт собирает данные диагностики для повышения удобства работы с Surface Hub. Добавьте в свой список разрешенных сайтов следующие:
- Конечная точка клиента данные диагностики: `https://vortex.data.microsoft.com/`
- Параметры параметров данные диагностики: `https://settings.data.microsoft.com/`

### Конфигурация прокси-сервера

Если ваша организация запрещает подключение компьютеров к Интернету, необходимо разрешить ряд URL-адресов, которые должны быть доступны для устройств для использования Microsoft Store для бизнеса. Некоторые из функций Microsoft Store для бизнеса используют приложение Microsoft Store и службы Microsoft Store. Устройствам, использующим Store для бизнеса (для получения, установки или обновления приложений) будет необходим доступ к этим URL-адресам. Если вы используете прокси-сервер для блокировки трафика, разрешите следующие URL-адреса в своей конфигурации.

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com (до Windows10 версии1607)
- www.msftconnecttest.com/connecttest.txt (заменяет www.msftncsi.com, начиная с Windows10 версии1607)


## Работа с другими администраторами

Surface Hub взаимодействует с рядом различных продуктов и служб. В зависимости от величины организации заниматься поддержкой продуктов в вашей среде может несколько человек. В планировании и подготовке развертываний Surface Hub должны принимать участие люди, которые занимаются управлением Exchange, Active Directory (или Azure Active Directory), MDM (средствами управления мобильными устройствами) и сетевыми ресурсами. 


## Создание и проверка учетной записи устройства

Учетная запись устройства— это учетная запись ресурса Exchange, которую Surface Hub использует для отображения календаря собраний, присоединения к звонкам к Skype для бизнеса и (при желании) проверки подлинности в Exchange. Подробные сведения см. в разделе [Создание и тестирование учетной записи устройства](create-and-test-a-device-account-surface-hub.md).

После создания учетной записи устройства убедитесь, что она настроена правильно, запустив сценарии PowerShell для проверки учетной записи устройства Surface Hub. Дополнительные сведения см. в разделе [Сценарии PowerShell для Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md) далее в этом руководстве. 

 

## Подготовка к программе первого запуска 
Существует еще несколько моментов, которые необходимо учесть, прежде чем запускать [программу первого запуска](first-run-program-surface-hub.md).  

### Создание пакетов подготовки (необязательно)
Пакеты подготовки можно использовать для добавления сертификатов, настройки параметров и установки приложений. См. раздел [Создание пакетов подготовки](provisioning-packages-for-certificates-surface-hub.md). Вы можете [установить пакеты подготовки во время первого запуска](first-run-program-surface-hub.md#first-page).

### Настройка групп администраторов
Каждое устройство Surface Hub можно настроить локально с помощью приложения «Параметры» на устройстве. Во избежание несанкционированного изменения параметров для открытия приложения «Параметры» требуются учетные данные администратора. О том, как настроить группы администраторов и управлять ими, см. в разделе [Управление группой администраторов](admin-group-management-for-surface-hub.md). Вам нужно будет [настроить администраторов для устройства при первом запуске](first-run-program-surface-hub.md#setup-admins).

### Изучение и заполнение рабочего плана настройки Surface Hub (необязательно)
При работе с программой первого запуска для Surface Hub вам понадобится ввести некоторые данные. В рабочем плане настройки содержатся эти данные для различных сред. Подробнее об этом: [Рабочий план настройки](setup-worksheet-surface-hub.md).


## В этом разделе

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Статья</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">Создание и тестирование учетной записи устройства</a></p></td>
<td align="left"><p>В этом разделе описано создание и тестирование учетной записи устройства, которую Surface Hub использует для связи со Skype.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">Создание пакетов подготовки</a></p></td>
<td align="left"><p>В Windows 10 параметры, использующие реестр или платформу служб контента (CSP), можно настроить с помощью пакетов подготовки. Вы также можете добавить сертификаты во время первого запуска, используя пакеты подготовки.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">Управление группой администраторов</a></p></td>
<td align="left"><p>Каждое устройство Surface Hub можно настроить индивидуально, открыв приложение "Параметры" на устройстве. Но чтобы несанкционированные пользователи не могли изменить параметры устройства, для открытия приложения "Параметры" и внесения изменений в нем требуются учетные данные локального администратора.</p>
<p>Чтобы открыть приложение "Параметры", необходимы учетные данные локального администратора.</p></td>
</tr>
</tbody>
</table>

## Дополнительные сведения

- [Запись блога: "Surface Hub и список доверенных доменов Skype для бизнеса"](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [Запись блога: "Surface Hub в среде с несколькими доменами"](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [Запись блога: "Настройка прокси-сервера для Surface Hub"](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 





