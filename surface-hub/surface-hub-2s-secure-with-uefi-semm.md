---
title: Защита и управление Surface Hub 2S с помощью SEMM
description: Дополнительные новости о защите Surface Hub 2S с помощью SEMM.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911044"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>Защита и администрирование Surface Hub 2S с помощью SEMM и UEFI

Новая Surface Hub 2S позволяет использовать SEMM для управления параметром UEFI устройства.
Для управления следующими компонентами используйте конфигуратор Microsoft Surface UEFI:

- Проводная сеть
- Камеры
- Bluetooth
- Wi-Fi
- Датчик занятости

Чтобы включить или отключить следующие параметры UEFI, используйте настраиватель Microsoft Surface UEFI:

- Загрузка

    - IPv6 для загрузки PXE
    - Альтернативная загрузка
    - Блокировка порядка загрузки
    - USB-загрузка
- Передняя страница UEFI

    - Устройства
    - Загрузка
    - Дата и время

## <a name="create-uefi-configuration-image"></a>Создание образа конфигурации UEFI

В отличие от других устройств Surface, вы не можете использовать файл MSI или изображение Win PE для применения этих параметров Surface Hub 2S. Вместо этого необходимо создать USB-изображение для загрузки на устройство. Чтобы создать Surface Hub конфигурации 2S UEFI, скачайте и установите последнюю версию конфигуратора Microsoft Surface UEFI на странице [Surface Tools для](https://www.microsoft.com/download/details.aspx?id=46703) ИТ в Центре загрузки Майкрософт. Дополнительные сведения об использовании UEFI и SEMM см. в [Enterprise Microsoft Surface.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)

## <a name="to-configure-uefi-on-surface-hub-2s"></a>Настройка UEFI на Surface Hub 2S

1. Запустите настраиватель UEFI и выберите пакет конфигурации на первом **экране.**<br><br>
![* Запустите настраиватель UEFI и выберите пакет конфигурации*.](images/sh2-uefi1.png) <br> <br>
2. Чтобы добавить сертификат в пакет, необходимо иметь действительный сертификат с закрытым ключом в формате файла .pfx, чтобы подписать пакет и защитить его. Выберите **+ Защита сертификатов.** <br>
![* Выберите + Защита сертификатов *.](images/sh2-uefi2.png) <br><br>
3. Введите пароль закрытого ключа сертификата.<br>
![* Введите пароль частного ключа сертификата *.](images/sh2-uefi3.png) <br><br>
4. После импорта закрытого ключа продолжайте создавать пакет.<br>
![* Продолжить создание пакета *.](images/sh2-uefi4.png) <br><br>
5. В **качестве** цели для пакета конфигурации UEFI выберите концентратор и **Surface Hub 2S.**<br>
![* Выберите концентратор Surface Hub 2S в качестве цели для пакета конфигурации UEFI *.](images/sh2-uefi5.png) <br><br>
6. Выберите компоненты и параметры, которые необходимо активировать или отключить в Surface Hub 2S.<br>
![* Выберите компоненты и параметры, которые необходимо активировать или отключить *.](images/sh2-uefi6.png) <br><br>
7. Чтобы экспортировать файл, используйте usb-параметр.<br>
![* Используйте usb-параметр для экспорта файла *.](images/sh2-uefi8.png) <br><br>
8. Вставьте и выберите USB-диск, который вы хотите использовать для этого пакета. Usb-диск будет отформатирован, и вы потеряете все сведения, которые у вас есть на нем.<br>
![* Вставьте и выберите USB-диск для пакета *.](images/sh2-uefi9.png) <br><br>
9. После успешного создания пакета конфигуратор отображает два последних символа отпечатка пальца сертификата. Эти символы необходимы при импорте в конфигурацию Surface Hub 2S.<br>
![* Успешная конфигурация пакета *.](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>Загрузка в UEFI

Отключите Surface Hub 2S. Нажмите и удерживайте **кнопку Volume Up** и нажмите **кнопку Power** Button. Держите кнопку Volume Up до тех пор, пока не появится меню UEFI.
