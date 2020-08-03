---
title: Включение функции пробуждения Power On для Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: В этой статье описано, как включать и отключать пробуждение Power On для устройств Surface.
keywords: обновление, развертывание, драйвер, WOL, пробуждение по сети
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903022"
---
# Пробуждение Power On для устройств Surface

Чтобы сохранить батарею, устройства Surface можно отключить на рабочем столе или выбрать режим гибернации. Чтобы улучшить управляемость этих устройств, функция Wake on Power включает совместимые устройства Surfaces для автоматического запуска при повторном подключении к Power. Настройка функции Wake on Power On требует использования режима управления Surface Enterprise (SEMM) либо через конфигуратора поверхности UEFI, либо из диспетчера UEFI.

Функция пробуждения Power On доступна на следующих устройствах:

- Surface Book 3
- Surface Pro 7
- Surface ноутбук 3
- Surface Pro X 

## Общие сведения и требования

Вы можете использовать конфигуратор UEFI Surface для настройки отдельных параметров UEFI, сохраненных в пакете установщика Windows Installer. msi для распространения на целевые устройства. 

> [!NOTE]
> В этой статье предполагается, что вы знакомы с использованием SEMM. Дополнительные сведения можно найти в разделе Документация по [режиму управления предприятием в Surface (SEMM)](surface-enterprise-management-mode.md) .

## Включение функции пробуждения на Power On

1.  Скачайте последнюю версию [конфигуратора UEFI Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Войдите на устройство Surface с помощью учетной записи администратора, откройте **Конфигуратор UEFI Surface**, выберите **Surface Devices**и нажмите кнопку **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  Нажмите кнопку **Пуск** , а затем в разделе **пакет конфигурации** выберите **создать**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите команду Создать пакет конфигурации.":::
4.  Нажмите кнопку **Защита сертификата** и добавьте PFX-файл сертификата. После ввода пароля нажмите кнопку **Далее**. Добавьте **защиту паролем**, если это необходимо, и нажмите кнопку **Далее**.
5.  На странице **выберите тип поверхности, на которую вы хотите сделать это** , выберите нужные оконечные устройства. Например, **Surface Pro 7**.
6.  На странице **Advanced Features (дополнительные функции** ) выберите **режим пробуждения** и установите переключатель **вкл**. Выберите **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите параметр "вкл." на вкладке "вкл."."::: 
7.  На странице **успешно** нажмите кнопку **завершить**. Если вы впервые предоставляете параметры для вашего устройства, вам будет предложено указать два последних символа отпечатка сертификата. 
8.  Сохраните пакет MSI. 

## Применение MSI-пакета 

Пакет MSI можно применить к устройствам в сети с помощью средств распространения программного обеспечения, таких как Microsoft Endpoint Configuration Manager. Эта процедура включает инструкции по установке пакета на локальном компьютере. 

1.  Откройте командную команду с повышенными привилегиями и введите полный путь к MSI-файлу, чтобы запустить пакет MSI. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  В диалоговом окне **предупреждение** нажмите кнопку " **ОК** " или отключите BitLocker.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Нажмите кнопку ОК или отключите BitLocker в нужном виде.":::
3.  На странице приветствия нажмите кнопку **Далее** , чтобы запустить пакет и применить только что настроенный параметр UEFI.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="На одной странице приветствия нажмите кнопку Далее.":::
4.  Перезапустите устройство. 

Теперь вы настроили функцию пробуждения на Power On. Чтобы протестировать этот параметр, отключите устройство, отключите электроэнергию и повторно подключитесь к электросети. Устройство запустится автоматически. 

## Дополнительные сведения

Дополнительные сведения можно найти в следующих статьях. 

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Пробуждение по локальной сети для устройств Surface](wake-on-lan-for-surface-devices.md)

Все еще нужна помощь? Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).