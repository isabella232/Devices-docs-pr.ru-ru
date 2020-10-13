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
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
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
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114577"
---
# Пробуждение при подаче питания для устройств Surface

Устройства Surface можно отключить, не выходя из него, или настроить режим гибернации, чтобы сэкономить время работы от аккумулятора. Чтобы улучшить управляемость этих устройств, функция Wake on Power позволяет автоматически запускать совместимые устройства Surface при повторном подключении к Power. Чтобы настроить функцию пробуждения Power On, вы можете использовать режим корпоративного управления Surface (SEMM) в качестве конфигуратора UEFI Surface или диспетчера UEFI.

Функция Wake on Power On поддерживается на следующих устройствах:

- Surface Book 3
- Surface Pro 7
- Surface ноутбук 3
- Ноутбук Surface Go
- Surface Pro X 


## Общие сведения и требования

Конфигуратор UEFI Surface позволяет сохранить индивидуальные параметры UEFI в пакете установщика Windows Installer. msi для распространения на целевые устройства. 

> [!NOTE]
> В этой статье предполагается, что вы знаете, как использовать SEMM. Дополнительные сведения можно найти в разделе Документация по [режиму управления предприятием в Surface (SEMM)](surface-enterprise-management-mode.md) .

## Включение функции пробуждения на Power On

1.  Скачайте последнюю версию [конфигуратора UEFI Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Войдите на устройство Surface с помощью учетной записи администратора, откройте **Конфигуратор UEFI Surface**, выберите **Surface Devices**и нажмите кнопку **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  Нажмите кнопку **Пуск**и выберите команду **создать** в разделе **пакет конфигурации**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
4.  Выберите **Защита сертификата**и добавьте PFX-файл сертификата. 
5. Введите пароль, нажмите кнопку **Далее**, добавьте **защиту паролем**, а затем нажмите кнопку **Далее**.
6.  На странице **выберите тип поверхности, на которую вы хотите сделать это** , выберите нужные оконечные устройства. Например, выберите **Surface Pro 7**.
7.  На странице **Дополнительные функции** выберите пункт **пробуждение по питанию**, установите для параметра значение **вкл**., а затем нажмите кнопку **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее."::: 
8.  На странице **успешно** нажмите кнопку **завершить**.

    > [!NOTE]
    > Если вы используете параметры устройства в первый раз, вам будет предложено также предоставить два последних символа отпечатка сертификата. 
9.  Сохраните пакет MSI. 

## Применение MSI-пакета 

Пакет MSI можно применить к устройствам в сети с помощью таких средств распространения программного обеспечения, как Microsoft Endpoint Configuration Manager. Ниже приведены инструкции по установке пакета на локальном компьютере. 

1.  В командной строке с повышенными привилегиями введите полный путь к MSI-файлу, чтобы запустить пакет MSI. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  В диалоговом окне **предупреждение** нажмите кнопку **ОК** или отключите BitLocker, если это необходимо.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
3.  На странице приветствия нажмите кнопку **Далее** , чтобы запустить пакет и применить только что настроенный параметр UEFI.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Выберите пункт устройства Surface и нажмите кнопку Далее.":::
4.  Перезапустите устройство. 

Теперь вы настроили функцию пробуждения на Power On. Чтобы проверить параметры, отключите устройство, отключите электроэнергию и подключитесь к электросети. Устройство должно запускаться автоматически. 

## Ссылок

Дополнительные сведения можно найти в следующих статьях. 

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Пробуждение по локальной сети для устройств Surface](wake-on-lan-for-surface-devices.md)

Все еще нужна помощь? Перейдите в [сообщество Майкрософт](https://answers.microsoft.com/).