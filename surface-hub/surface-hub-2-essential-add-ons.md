---
title: Основные надстройки для Windows 10/11 Pro и Enterprise на Surface Hub 2
description: В этой статье содержатся сведения о необязательных методах доступа, которые можно использовать с Windows 10/11 Pro или Enterprise на Surface Hub 2.
keywords: Surface Hub, Windows 10, Windows 11, рабочий стол, средство чтения отпечатков пальцев, Windows Hello
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.date: 09/18/2020
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: f146c2085f0d7c06e03da32ed4cc99821bd1abb2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497912"
---
# <a name="essential-add-ons-for-windows-1011-pro-and-enterprise-on-surface-hub-2"></a>Основные надстройки для Windows 10/11 Pro и Enterprise на Surface Hub 2

Если вы перейдите с Windows 10 для совместной работы на Windows 10, Windows 11 Pro или Enterprise на Surface Hub 2, вы можете выбрать один из множества методов доступа, подключаемых через USB-C, USB-A, HDMI или Bluetooth. 

## <a name="surface-hub-2-fingerprint-reader"></a>Surface Hub 2 сканер отпечатков пальцев

Если вы используете Windows 10/11 Pro или Windows 10/11 Enterprise на Surface Hub 2, вы можете войти с помощью необязательного средства чтения отпечатков пальцев Surface Hub 2— биометрической проверки подлинности, [использующей Windows Hello](/windows-hardware/design/device-experiences/windows-hello).

### <a name="ordering"></a>Заказ

Коммерческие клиенты могут размещать заказы через своих торговых посредников устройств Surface Authorized.

**Чтобы использовать Surface Hub 2, выполните следующие действия.**

1. Вставьте средство чтения отпечатков пальцев в любой из портов панели USB C, расположенных на каждой стороне устройства.
2. **Перейти к меню "Пуск"** >  **** >  Параметры **AccountsSign-in** > **** >  **Windows Hello отпечаток** пальца для регистрации отпечатка пальца.

Дополнительные сведения о настройке средства чтения отпечатков пальцев для входа с помощью Windows Hello см. в следующих статьях:

- [Сведения о приложении Windows Hello и его настройке](https://support.microsoft.com/help/4028017/windows-learn-about-windows-hello-and-set-it-up)
- [Windows Hello биометрии на предприятии](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise).

  
### <a name="table-1-surface-hub-2-fingerprint-reader-tech-specs"></a>Таблица 1: Surface Hub технические характеристики средства чтения отпечатков пальцев 2


| Компонент                       | Описание                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **USB**                         | Настраиваемый USB-тип C                                                                                                           |
| **Требования к системе**          | Windows 10/11 Pro, Windows 10/11 Enterprise.                                                                                               |
| **Windows сертификации**       | Windows 10/11                                                                                                                           |
| **False Acceptance Rate (FAR)** | 1/1,5 млн. FAR показывает вероятность того, что биометрическая система безопасности неправильно принимает попытки доступа неавторизованными пользователями. |
| **Частота ложного отклонения (FRR)** | 4.9%. FRR показывает вероятность того, что биометрическая система безопасности неправильно отклонит попытки доступа авторизованными пользователями. |


> [!NOTE]
> Windows 10 для совместной работы, которая выполняется Surface Hub 2S, не поддерживает средство чтения отпечатков Surface Hub 2. Это связано с Windows 10 для совместной работы, что позволяет нескольким пользователям взаимодействовать с устройством в среде конференц-зала. 
 
## <a name="windows-hello-face-recognition"></a>Windows Hello распознавания лиц

Windows 10/11 Pro и Enterprise на Surface Hub 2 поддерживает Windows Hello проверку подлинности и требует Windows Hello доступа к камере. Обратите внимание, что встроенная камера для Surface Hub 2S не предназначена для проверки подлинности и не поддерживает Windows Hello. Дополнительные сведения см[. в Windows Hello.](/windows-hardware/design/device-experiences/windows-hello)


## <a name="audio-and-video-accessories"></a>Аксессуары для аудио- и видеосвязи

Вы можете расширить возможности аудио- и видеосвязи Surface Hub 2 с помощью периферийных устройств аудио- и камеры с помощью портов USB-C или USB-A.

Дополнительные сведения о рекомендуемых методах доступа см. в следующих статьях:

- [USB-аудио- и видеоустройства, сертифицированные для Microsoft Teams](/microsoftteams/devices/usb-devices)
- [IP-телефоны, сертифицированные для Microsoft Teams](/microsoftteams/devices/teams-ip-phones)



## <a name="other-accessories"></a>Другие аксессуары
Surface Hub 2 включает следующие порты для подключения различных устройств. 

- Порт 1 x USB A в вычислительном модуле (за дисплеем)
- 4 порта USB C на панели
- Bluetooth 4.1
- HDMI 2.0

 ![Интерфейсное и нижнее представление подключений ввода-вывода и физических кнопок.](images/hub2s-schematic.png)

Дополнительные сведения см. [в Surface Hub портов и клавиатуры 2S](surface-hub-2s-port-keypad-overview.md)


## <a name="learn-more"></a>Подробнее

- [Настройте Windows 10/11 Pro или Enterprise на Surface Hub 2](surface-hub-2-post-install.md).