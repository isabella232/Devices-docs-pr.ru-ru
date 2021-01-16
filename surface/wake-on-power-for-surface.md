---
title: How to enable Wake on Power for Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: В этой статье описывается, как включить и отключить wake on Power для устройств Surface.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271563"
---
# Пробуждение при подаче питания для устройств Surface

Устройства Surface можно отключить, пока вы не на рабочем месте, или настроить режим гибернации для экономии заряда батареи. Чтобы повысить управляемость этих устройств, с помощью Wake on Power можно автоматически запускать совместимые устройства Surface при повторном под подключением к электросети. Чтобы настроить режим восстановления после питания, можно использовать режим управления Surface Enterprise (SEMM) с помощью настройщика UEFI Surface или диспетчера UEFI.

Функция Wake on Power доступна на следующих устройствах:

- Surface Pro 7 и более
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Laptop Go
- Surface Pro X 


## Обзор и предварительные условия

Настройщик UEFI Surface позволяет сохранять отдельные параметры UEFI в MSI-пакете установщика Windows для распространения на целевые устройства. 

> [!NOTE]
> В этой статье предполагается, что вы знаете, как использовать SEMM. Дополнительные сведения см. в [документации по режиму управления Surface Enterprise (SEMM).](surface-enterprise-management-mode.md)

## Чтобы включить wake on Power

1.  Скачайте последнюю версию [настройщика UEFI Surface.](https://www.microsoft.com/download/confirmation.aspx?id=46703)
2.  Во sign in to your Surface device as an administrator, open **Surface UEFI Configurator,** select **Surface Devices,** and then select **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите устройства Surface и выберите "Далее".":::
3.  Выберите **"Начните"** и выберите **"Создать** в **пакете конфигурации".**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите "Создать пакет конфигурации".":::
4.  Выберите **"Защита сертификатов"** и добавьте PFX-файл сертификата. 
5. Введите пароль, выберите **"Далее",** **"Добавить защиту**паролем" и затем **"Далее".**
6.  На странице **"Выбор типа Surface", на которую** вы хотите нацелить, выберите нужные целевые устройства. Например, выберите **Surface Pro 7.**
7.  На странице **"Дополнительные функции"** выберите **"Будить на питание",** установите для функции "В сети" и выберите **"Далее".** ****

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Select Wake on Power and set to On."::: 
8.  На странице **"Успешно"** выберите **"Конец".**

    > [!NOTE]
    > Если вы в первый раз предоставляете параметры на устройстве, вам также будет предложено предоставить два последних символа отпечатка сертификата. 
9.  Сохраните MSI-пакет. 

## Применение пакета MSI 

Пакет MSI можно применить к устройствам в сети с помощью таких средств распространения программного обеспечения, как Microsoft Endpoint Configuration Manager. Эта процедура включает действия по установке пакета на локальном компьютере. 

1.  В командной подсказке с повышенными повышенными уровнями введите полный путь к MSI-файлу, чтобы запустить MSI-пакет. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  В **диалоговом** окне предупреждения выберите "ОК" или отключите BitLocker, если это необходимо. ****

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Выберите "ОК" или отключите BitLocker соответствующим образом.":::
3.  На странице приветствия выберите **"Далее",** чтобы запустить пакет, и примените только что настроенный параметр UEFI.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="На странице приветствия выберите "Далее".":::
4.  Перезапустите устройство. 

Теперь настроено питание от питания. Чтобы проверить параметры, отключите устройство, отключите питание и снова подключите его. Устройство должно запускаться автоматически. 

## Ссылок

Дополнительные сведения см. в следующих статьях. 

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Будить в локальной сети для устройств Surface](wake-on-lan-for-surface-devices.md)

Все еще нужна помощь? Перейдите в [Сообщество Майкрософт.](https://answers.microsoft.com/)