---
title: Управление параметрами UEFI Surface
description: Узнайте, как включать и отключать устройства или компоненты, настраивать параметры безопасности и загрузки устройства Surface с помощью параметров UEFI.
keywords: встроенное ПО, безопасность, функции, настройка, оборудование
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/25/2021
ms.openlocfilehash: af9eac171dea5d29ce9776766a2c5842bea9eb8c
ms.sourcegitcommit: 1b12ea363785697ddc705b0a0cc7bb35cad6b327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "11300700"
---
# Управление параметрами UEFI Surface

 Устройства Surface PC предназначены для использования уникального интерфейса UEFI, разработанного корпорацией Майкрософт специально для этих устройств. Параметры UEFI Surface позволяют включить или отключить встроенные устройства и компоненты, защитить параметры UEFI от изменения и настроить параметры загрузки устройства Surface. 

## Поддерживаемые продукты

Управление UEFI поддерживается в следующих системах: 

- Surface Pro 4, Surface Pro (5-е поколения), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1-е поколения), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go
- Surface Studio (1-е поколения), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## Поддержка облачного управления

Благодаря профилям интерфейса конфигурации встроенного ПО устройства (DFCI), встроенным в Microsoft Intune (теперь доступно в общедоступных версиях), управление UEFI Surface расширяет современный стек управления до уровня оборудования UEFI. DFCI поддерживает нулевую настройку, исключает пароли BIOS, обеспечивает управление настройками безопасности, включая параметры загрузки и встроенные периферийные устройства, и создает основу для расширенных сценариев безопасности в будущем. В настоящее время DFCI доступен для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 и Surface Pro X.  Дополнительные сведения см. в управлении [Intune для параметров UEFI Surface.](surface-manage-dfci-guide.md)

## Откройте меню UEFI Surface

Чтобы настроить параметры UEFI во время запуска системы:

1. Выключите Surface и подождите около 10 секунд, чтобы убедиться, что она отключена.
2. Нажмите и удерживайте кнопку **"Громкость"** и одновременно нажмите и отпустите **кнопку питания.**
3. По мере того как на экране появится **** логотип Microsoft или Surface, продолжайте удерживать кнопку "Громкость" до тех пор, пока не появится экран UEFI.

## Страница сведений о ПК UEFI

На странице сведений о компьютере содержатся подробные сведения о вашем устройстве Surface: 

- **Модель** — здесь будет отображаться модель устройства Surface, например Surface Book 2 или Surface Pro 7. Точная конфигурация устройства (например, процессор, размер диска или объем памяти) не отображается. 
- **UUID**: уникальный идентификатор устройства, который используется для идентификации устройства во время разработки и управления. 

- **Serial Number**: этот номер используется для идентификации устройства Surface во время инвентаризации и поддержки.
- **Asset Tag**: тег актива назначается устройству Surface с помощью [средства Asset Tag](https://docs.microsoft.com/surface/assettag). 

Кроме того, в этом разделе вы найдете подробные сведения о встроенном ПО устройства Surface. Устройства Surface включают несколько внутренних компонентов, работающих под управлением разных версий встроенного ПО. Версия встроенного ПО каждого из перечисленных ниже устройств отображается на странице **PC information** (как показано на рис. 1): 

- UEFI системы; 

- контроллер SAM; 

- модуль управления Intel; 

- встроенный контроллер системы; 

- встроенное ПО сенсорного управления. 

![Сведения о системе и версии встроенного ПО](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*Рис. 1. Сведения о системе и версии встроенного ПО*

Вы можете найти актуальные сведения о последней версии встроенного ПО для вашего устройства Surface в [журнале обновлений Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) для этого устройства. 

## Страница "Безопасность UEFI" 

![Настройка параметров безопасности UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Рисунок 2. Настройка параметров безопасности UEFI Surface*

На странице "Безопасность" можно настроить пароль для защиты параметров UEFI. Этот пароль необходимо ввести при загрузке устройства Surface в режиме UEFI. Пароль может содержать следующие символы (как показано на рисунке 3): 

- Прописные буквы: A–Z 

- Строчные буквы: a–z 

- Цифры: 1–10 

- Специальные символы: !@#$%^&*()?<>{} []-_=+|.;:''" 

Пароль должен состоять по крайней мере из 6 символов и вводится с учетом регистра. 

![Добавление пароля для защиты параметров UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Рисунок 3. Добавление пароля для защиты параметров UEFI Surface*

На странице Security также можно изменить конфигурацию безопасной загрузки устройства Surface. Технология безопасной загрузки предотвращает загрузку несанкционированного кода на устройстве Surface, обеспечивая защиту от заражений буткитами и руткитами. Вы можете отключить безопасную загрузку, чтобы на устройстве Surface можно было загружать сторонние операционные системы и загрузочные носители. Вы также можете настроить безопасную загрузку для работы со сторонними сертификатами, как показано на рисунке 4. Дополнительные сведения о [безопасной загрузке](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) см. в библиотеке TechNet.

![Настройка безопасной загрузки](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Рисунок 4. Настройка безопасной загрузки*

В зависимости от устройства вы также можете увидеть, включен ли ваш TPM. Если параметр "Включить **TPM"**  не отображается, откройте tpm.msc в Windows, чтобы проверить состояние, как показано на рисунке 5. TPM используется для проверки подлинности при шифровании данных устройства с помощью BitLocker. Дополнительные сведения см. в [обзоре BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) 

![Консоль TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Рисунок 5. Консоль TPM*


## Меню UEFI: устройства 

На странице "Устройства" можно включить или отключить определенные устройства и компоненты, в том числе:

- порты док-станций и USB; 

- разъем для карты MicroSD или SD; 

- задняя камера; 

- лицевая камера; 

- инфракрасная камера; 

- Wi-Fi и Bluetooth; 

- встроенная аудиосистема (динамики и микрофон). 

Каждое устройство отображается с кнопкой ползуна, которую **** можно переместить в положение "Включено" или "Отключено", как показано на рисунке 6. **** 

![Включение и отключение устройств](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Рисунок 6. Включение и отключение устройств*

## Меню UEFI: конфигурация загрузки 

На странице "Конфигурация загрузки" можно изменить порядок загрузки устройств, а также включить или отключить загрузку следующих устройств: 

- диспетчер загрузки Windows; 

- USB-накопитель; 

- сеть PXE; 

- внутренняя память. 

Вы можете мгновенно загрузить систему с определенного устройства или провести пальцем влево по этому устройству в списке. Вы также можете мгновенно загрузить систему на USB-устройство или USB-адаптер для Ethernet, когда устройство Surface отключено, одновременно нажав кнопки **уменьшения громкости** и **включения**. 

Чтобы указанный порядок загрузки вступил в **** силу, необходимо включить параметр "Включить альтернативную последовательность загрузки", **** как показано на рисунке 7. 

![Настройка порядка загрузки для устройства Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Рисунок 7. Настройка порядка загрузки для устройства Surface* 

Вы также можете включать и отключать поддержку IPv6 для PXE с помощью параметра **Enable IPv6 for PXE Network Boot**, например во время развертывания Windows с помощью PXE, если сервер PXE настроен только для IPv4.  

## Меню UEFI: управление
Страница "Управление" позволяет управлять использованием управления UEFI Zero Touch и другими функциями на соответствующих устройствах, включая Surface Pro 7, Surface Pro X и Surface Laptop 3.  

![Управление доступом к управлению UEFI zero Touch и другими ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *функциями, рис. 8. Управление доступом к управлению UEFI zero Touch и другими функциями* 


Zero Touch UEFI Management позволяет удаленно управлять настройками UEFI с помощью профиля устройства в Intune под названием Device Firmware Configuration Interface (DFCI). Если этот параметр не настроен, возможность управления подходящими устройствами с помощью DFCI устанавливается в **"Готово".** Чтобы запретить DFCI, **выберите "Отказаться".** 

> [!NOTE]
> Страница параметров управления UEFI и использование DFCI в настоящее время доступны для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 и Surface Pro X. Дополнительные см. в руководстве по управлению [Intune для параметров UEFI Surface.](surface-manage-dfci-guide.md)

## Меню UEFI: выход 

Используйте **кнопку "Перезапустить сейчас"** на странице **"Выход",** чтобы выйти из параметров UEFI, как показано на рисунке 9. 

![Выход из меню UEFI Surface и перезагрузка устройства](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Рисунок 9. Нажмите "Restart Now", чтобы выйти из меню UEFI Surface и перезагрузить устройство*

## Экраны загрузки UEFI Surface

При обновлении встроенного ПО устройства Surface с помощью центра обновления Windows или ручной установки обновления применяются к устройству не сразу, а во время следующего цикла перезагрузки. Вы можете узнать больше о процессе обновления встроенного ПО Surface на странице [Управление обновлениями драйверов и встроенного ПО Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). Выполнение обновления встроенного ПО отображается на экране с помощью индикаторов разных цветов, соответствующих встроенному ПО каждого компонента. Ход выполнения каждого компонента показан на рисунках 9–18.

![Обновление встроенного ПО UEFI Surface с синим индикатором выполнения](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Рисунок 10. Обновление встроенного ПО UEFI Surface с синим индикатором выполнения*

![Встроенное ПО встроенного контроллера системы с зеленым индикатором выполнения](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Рисунок 11. Обновление встроенного ПО встроенного контроллера системы с зеленым индикатором выполнения*

![Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Рисунок 12. Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения*

![Встроенное ПО Intel Management Engine с красным индикатором выполнения](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Рисунок 13. Обновление встроенного ПО Intel Management Engine с красным индикатором выполнения*

![Встроенное ПО сенсорных элементов Surface с серым индикатором выполнения](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Рисунок 14. При обновлении встроенного ПО сенсорных элементов Surface отображается серый индикатор выполнения*

![Микропрограмма SURFACE KIP с светло-зеленым ходом выполнения](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Рис. 15. Обновление микропрограммы SURFACE KIP отображает светло-зеленую планку хода выполнения*

![Микропрограмма ISH Surface с розовая гряду хода выполнения](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Рис. 16. Обновление по isH Surface отобразит светло-розовую планку хода выполнения*

![Микропрограмма Surface Trackpad с серым ходом выполнения](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Рис. 17. Обновление микропрограмм Surface Trackpad отображает розовую панель хода выполнения*

![Микропрограмма TCON Surface с светло-серым ходом выполнения](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Рисунок 18. Обновление микропрограммы TCON surface отображает светло-серую планку хода выполнения*


![Микропрограмма TPM Surface с светло-сиреневым ходом выполнения](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Рисунок 19. Обновление прошивки TPM Surface отображает сиреневую планку хода выполнения*


>[!NOTE]
>Отображается дополнительное предупреждение о том, что безопасная загрузка отключена, как показано на рисунке 19.

![Экран загрузки Surface, указывающий, что безопасная загрузка отключена](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Рисунок 20. Экран загрузки Surface, указывающий, что безопасная загрузка отключена в параметрах UEFI Surface*

## Ссылок

1. Surface Go и Surface Go 2 используют сторонний UEFI и не поддерживают DFCI. 

## Статьи по теме

- [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md)

-  [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
