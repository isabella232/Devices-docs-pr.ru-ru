---
title: Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети
description: Политики MDM для проверки подлинности по стандарту безопасности 802.1X в проводной сети были включены на устройствах Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836251"
---
# Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети

[Обновление для Windows 10 от 14 ноября 2017 года](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (сборка 15063.726) позволяет использовать политики MDM для проверки подлинности по стандарту безопасности 802.1X в проводной сети на устройствах Surface Hub. Этот компонент позволяет организациям усилить стандартизированную проверку подлинности по проводной сети с помощью [протокола проверки подлинности IEEE 802.1 x](http://www.ieee802.org/1/pages/802.1x-2010.html). Эта возможность уже доступна для выполнения проверки подлинности по беспроводной сети с помощью профилей беспроводной сети через систему MDM. В этом разделе описывается настроить Surface Hub для использования с проверкой подлинности по проводной сети. 

Применение и включение проводной проверки подлинности по стандарту безопасности 802.1x в Surface Hub можно выполнить с помощью [определения OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) системы MDM. 

Основной конфигурацией, которую следует задать, является политика **LanProfile**. В зависимости от выбранного способа проверки подлинности могут потребоваться другие политики: политика **EapUserData** или политики MDM для добавления сертификатов компьютеров или пользователей (например, [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) для сертификатов пользователей/устройств или [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) для сертификатов устройств). 

##  <a name="lanprofile-policy-element"></a>Элемент политики LanProfile

Чтобы настроить Surface Hub для использования одного из поддерживаемых способов проверки подлинности по стандарту безопасности 802.1x, используйте следующий OMA-URI. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра. XML-файл, предоставляемый в качестве параметра, должен соответствовать [схеме профиля проводной сети LAN](https://msdn.microsoft.com/library/cc233002.aspx), включая элементы из [схемы 802.1X](https://msdn.microsoft.com/library/cc233003.aspx). 

В большинстве случаев администратор или пользователь может экспортировать XML-файл элемента LanProfile из имеющегося компьютера, который уже настроен в сети для стандарта безопасности 802.1X с помощью следующей команды NETSH. 

```
netsh lan export profile folder=.
```

Выполнение этой команды предоставит следующие выходные данные и разместит файл с именем **Ethernet.xml** в текущем каталоге. 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

##  <a name="eapuserdata-policy-element"></a>Элемент политики EapUserData

Если для выбранного способа проверки подлинности необходимо использовать имя пользователя и пароль вместо сертификата, можно использовать элемент **EapUserData**, чтобы задать учетные данные, которые устройство будет применять для выполнения проверки подлинности в сети. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра. XML-файл, предоставляемый в качестве параметра, должен соответствовать [примеру свойств пользователя MS-CHAPv2 PEAP](https://msdn.microsoft.com/library/windows/desktop/bb891979). В этом примере необходимо заменить все экземпляры *test* и *ias-domain* вашими данными.



##  <a name="adding-certificates"></a>Добавление сертификатов

Если вы выбрали метод проверки подлинности на основе сертификата, вам потребуется [создать пакет подготовки](provisioning-packages-for-surface-hub.md), [использовать MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)или импортировать сертификат из параметров (обновление**параметров**  >  **и**  >  **Сертификаты**безопасности), чтобы развернуть эти сертификаты на устройстве Surface Hub в соответствующем хранилище сертификатов. При добавлении сертификатов каждый PFX-файл должен содержать только один сертификат (PFX-файл не может иметь несколько сертификатов).

