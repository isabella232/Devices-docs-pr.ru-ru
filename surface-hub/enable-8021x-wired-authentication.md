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
ms.openlocfilehash: dcb2799accfcbccb41e44e09f0df3fd1ac6eb57e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154044"
---
# <a name="enable-8021x-wired-authentication"></a>Включение проверки подлинности по стандарту безопасности 802.1X в проводной сети

Обновление до Windows 10 от [14 ноября 2017](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) г. (сборка 15063.726) включило 802.1x проводную политику проверки подлинности на Surface Hub устройствах. Этот компонент позволяет организациям усилить стандартизированную проверку подлинности по проводной сети с помощью [протокола проверки подлинности IEEE 802.1 x](http://www.ieee802.org/1/pages/802.1x-2010.html). Это уже было доступно для беспроводной проверки подлинности с помощью [профилей WLAN](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) с помощью MDM. В этом разделе описывается настроить Surface Hub для использования с проверкой подлинности по проводной сети. 

Применение и включение проводной проверки подлинности по стандарту безопасности 802.1x в Surface Hub можно выполнить с помощью [определения OMA-URI](/mem/intune/configuration/custom-settings-windows-10) системы MDM. 

Основной конфигурацией, которую следует задать, является политика **LanProfile**. В зависимости от выбранного способа проверки подлинности могут потребоваться другие политики: политика **EapUserData** или политики MDM для добавления сертификатов компьютеров или пользователей (например, [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) для сертификатов пользователей/устройств или [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) для сертификатов устройств). 

## <a name="lanprofile-policy-element"></a>Элемент политики LanProfile

Чтобы настроить Surface Hub для использования одного из поддерживаемых способов проверки подлинности по стандарту безопасности 802.1x, используйте следующий OMA-URI. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра. XML-файл, предоставляемый в качестве параметра, должен соответствовать [схеме профиля проводной сети LAN](/openspecs/windows_protocols/ms-gpwl/c88a926a-087b-405f-9a76-effaf7277bf3), включая элементы из [схемы 802.1X](/openspecs/windows_protocols/ms-gpwl/71f2eda6-d018-4ba3-ad37-32c98b926ebb). 

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

## <a name="eapuserdata-policy-element"></a>Элемент политики EapUserData

Если для выбранного способа проверки подлинности необходимо использовать имя пользователя и пароль вместо сертификата, можно использовать элемент **EapUserData**, чтобы задать учетные данные, которые устройство будет применять для выполнения проверки подлинности в сети. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Этот узел OMA-URI принимает текстовую строку XML-файла в качестве параметра. XML-файл, предоставляемый в качестве параметра, должен соответствовать [примеру свойств пользователя MS-CHAPv2 PEAP](/windows/win32/eaphost/peap-ms-chapv2-user-properties). В этом примере необходимо заменить все экземпляры *test* и *ias-domain* вашими данными.



## <a name="adding-certificates"></a>Добавление сертификатов

Если выбранный метод проверки подлинности основан на сертификатах, вам потребуется создать пакет [подготовка,](provisioning-packages-for-surface-hub.md)использовать [MDM](/windows/client-management/mdm/clientcertificateinstall-csp)или импортировать сертификат из параметров **(Параметры**  >  **Update and Security**  >  **Certificates),** чтобы развернуть эти сертификаты на ваше Surface Hub устройство в соответствующем хранилище сертификатов. При добавлении сертификатов каждый PFX-файл должен содержать только один сертификат (PFX-файл не может иметь несколько сертификатов).

