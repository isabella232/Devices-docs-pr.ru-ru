---
title: Что нового в Windows 10 (версия 1703 для Surface Hub)
description: Windows 10 версии 1703 (Creators Update) предоставляет ряд новых возможностей в Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924945"
---
# Новые возможности Windows 10 (версия 1703 для Microsoft Surface Hub)

Инженер Surface Hub Джордан Маркезе рассказывает об обновлениях для Microsoft Surface Hub в Windows 10 версии 1703 (Creators Update). 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

Windows 10 версии 1703 (также называемая Creators Update) представляет следующие изменения для Microsoft Surface Hub.

##  <a name="new-settings"></a>Новые параметры

Добавлены параметры для управления мобильными устройствами (MDM) и поставщиками служб настройки (CSP), чтобы расширить возможности управления Surface Hub. [Новые параметры включают](manage-settings-with-mdm-for-surface-hub.md):

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

А также параметры на базе [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) и [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).
</br>

##  <a name="provisioning-wizard"></a>Мастер подготовки

Простой в использовании мастер поможет вам быстро создавать пакеты подготовки, которые можно применить к нескольким устройствам Surface Hub. Он также включает массовое присоединение к Azure Active Directory. [Узнайте, как создать пакет подготовки для Surface Hub.](provisioning-packages-for-certificates-surface-hub.md)

![действия мастера подготовки устройств Surface Hub](images/wcd-wizard.png)
    
##  <a name="miracast-on-your-existing-wireless-network-or-lan"></a>Использование Miracast в существующей беспроводной или локальной сети 

Корпорация Майкрософт добавила возможность [отправки потока Miracast по локальной сети](miracast-over-infrastructure.md) вместо прямого беспроводного соединения. 
    
##  <a name="cloud-recovery"></a>Восстановление в облаке

После сброса устройства Surface Hub вы сможете скачать и установить заводскую сборку операционной системы из облака. [Дополнительные сведения о восстановлении в облаке.](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
>Восстановление в облаке не работает, если вы используете прокси-серверы.
    
![Переустановка](images/reinstall.png)
    
##  <a name="end-session"></a>Завершить сеанс

**Готово** теперь заменено на **Завершить сеанс**. [Узнайте, как использовать функцию "Завершить сеанс".](finishing-your-surface-hub-meeting.md) 

![завершить сеанс](images/end-session.png)



 

 
