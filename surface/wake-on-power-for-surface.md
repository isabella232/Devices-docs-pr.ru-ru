---
title: Пробуждение при подаче питания для устройств Surface
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Описывает, как включить и отключить wake on Power для устройств Surface.
keywords: обновление, развертывание, драйвер, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: e8e4ddbd559fc6aea2d04e61208b911ebef3ec22
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338402"
---
# <a name="wake-on-power-for-surface-devices"></a>Пробуждение при подаче питания для устройств Surface

Устройства Surface могут быть отключены во время работы вне рабочего стола или в режиме спячку, чтобы сохранить время автономной работы. Чтобы повысить управляемость этих устройств, wake on Power позволяет совместимым устройствам Surface автоматически запускаться при повторном присоединении к мощности. Чтобы настроить Wake on Power, можно использовать режим управления surface Enterprise (SEMM) либо через конфигуратор Surface UEFI или UEFI Manager.

Функция Wake on Power доступна на следующих устройствах:

- Surface Pro 8 (только коммерческие skUs)
- Surface Pro 7+ (только коммерческие skUs)
- Surface Pro X (все skUs)
- Surface Pro 7 (все skUs)
- Surface Go 3 (только коммерческие skUs)
- Surface Laptop Studio (только коммерческие skUs)
- Surface Book 3 (все skUs)
- Surface Laptop 4 (только коммерческие skUs)
- Surface Laptop 3 (все skUs)
- Surface Laptop Go (все skUs)


>[!TIP]
> Коммерческие skUs (он же Surface для бизнеса) запускают Windows 10 Pro/Enterprise или Windows 11 Pro/Enterprise; потребительские SKUs запускают Windows 10/Windows 11 Home. Дополнительные сведения см. [в обзоре системных данных](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 

## <a name="overview-and-prerequisites"></a>Обзор и необходимые условия

Конфигуратор Surface UEFI позволяет сохранять отдельные параметры UEFI в пакете Windows установки .msi для распространения на целевые устройства. 

> [!NOTE]
> В этой статье предполагается, что вы знаете, как использовать SEMM. Дополнительные сведения см. в [документации surface Enterprise mode (SEMM](surface-enterprise-management-mode.md)).

## <a name="to-enable-wake-on-power"></a>Включить wake on Power

1.  Скачайте последнюю версию [конфигуратора Surface UEFI](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Во входе на устройство Surface в качестве администратора откройте **настраиватель Surface UEFI**, выберите **Surface Devices** и выберите **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Выберите Surface Devices и выберите Далее.":::
3.  Выберите **Начните**, а затем **выберите Создать** в **пакете конфигурации**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Выберите пакет Create Configuration.":::
4.  Выберите **защиту сертификатов** и добавьте файл сертификата .pfx. 
5. Введите пароль, выберите **Далее**, добавьте **защиту паролей**, а затем выберите **Далее**.
6.  На выберите **тип Surface, который необходимо нацелить** , выберите соответствующие целевые устройства. Например, выберите **Surface Pro 7**.
7.  На странице **Расширенные функции** выберите **Wake on Power**, установите функцию **On** и выберите **Далее**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Выберите Wake on Power и установите в on."::: 
8.  На странице **Успешно выберите** **End**.

    > [!NOTE]
    > Если вы впервые предоставляете параметры на устройстве, вам также будет предложено предоставить два последних символа отпечатка пальца сертификата. 
9.  Сохраните .msi пакет. 

## <a name="apply-the-msi-package"></a>Применение пакета MSI 

Пакет MSI можно применить к устройствам по всей сети с помощью средств распространения программного обеспечения, таких как Microsoft Endpoint Configuration Manager. Эта процедура включает действия по установке пакета на локальном компьютере. 

1.  В командной подсказке на повышенных уровнях введите полный путь .msi для запуска .msi пакета. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  В **диалоговом** окне Предупреждение выберите **ОК** или отключите BitLocker по мере необходимости.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Выберите ОК или отключить BitLocker по мере необходимости.":::
3.  На странице Welcome выберите **Далее** , чтобы запустить пакет и применить недавно настроенный параметр UEFI.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Одну страницу Добро пожаловать выберите Далее.":::
4.  Перезагрузите устройство. 

Теперь настроена настройка Wake on Power. Чтобы проверить параметры, отключите устройство, отключите питание, а затем подключите его. Устройство должно запускаться автоматически. 

## <a name="references"></a>Ссылки

Дополнительные сведения см. в следующих статьях. 

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md)

Все еще нужна помощь? Перейдите в [Microsoft Community](https://answers.microsoft.com/).