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
ms.date: 04/01/2022
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e38fb3ae8a25fddfcb64985a64b41d4d2e084178
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472658"
---
# <a name="manage-surface-uefi-settings"></a>Управление параметрами UEFI Surface

 Устройства Surface PC предназначены для использования уникального интерфейса UEFI, разработанного корпорацией Майкрософт специально для этих устройств. Параметры UEFI Surface позволяют включать или отключать встроенные устройства и компоненты, защищать параметры UEFI от изменения и настраивать параметры загрузки устройства Surface.

## <a name="supported-products"></a>Поддерживаемые продукты

Управление UEFI поддерживается в следующих разделах:

- Surface Pro 4, Surface Pro (5-го поколения), Surface Pro 6, Surface Pro 7, Surface Pro 7+ (только коммерческие номера SKU), Surface Pro 8 (только коммерческие номера SKU), Surface Pro X
- Surface Laptop (1-го поколения), Surface Laptop 2, Surface Laptop 3 (только процессоры Intel), Surface Laptop Go, Surface Laptop 4 (только коммерческие номера SKU), Surface Laptop SE
- Surface Studio (1-го поколения), Surface Studio 2
- Surface Book (все поколения)
- Surface Laptop Studio (только коммерческие номера SKU)
- Surface Go, Surface Go [21<sup></sup>](#references), Surface Go 3 (только коммерческие номера SKU)

>[!TIP]
> Коммерческие номера SKU (например, Surface для бизнеса) выполняются Windows 10 Pro/Enterprise или Windows 11 Pro/Enterprise; номера SKU потребителей Windows 10/Windows 11 Домашняя. В UEFI коммерческие номера SKU являются единственными моделями, которые отображают страницу "Устройства ["](#uefi-devices-page) и [страницу управления](#uefi-management-page). Дополнительные сведения см. в [разделе "Просмотр сведений о системе"](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 


## <a name="support-for-cloud-based-management"></a>Поддержка облачного управления

Благодаря профилям интерфейса конфигурации встроенного ПО устройства (DFCI), встроенным в Microsoft Intune (теперь доступно в общедоступной предварительной версии), управление Surface UEFI расширяет современный стек управления до аппаратного уровня UEFI. DFCI поддерживает подготовку без касания, исключает пароли BIOS, обеспечивает управление параметрами безопасности, включая параметры загрузки и встроенные периферийные устройства, и создает основу для расширенных сценариев безопасности в будущем. Сейчас DFCI доступен для Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 и Surface Pro X. Дополнительные сведения см. [в Intune управления параметрами Surface UEFI](surface-manage-dfci-guide.md).

## <a name="open-surface-uefi-menu"></a>Открытие меню Surface UEFI

Чтобы настроить параметры UEFI во время запуска системы:

1. Завершите работу Surface и подождите около 10 секунд, чтобы убедиться, что она отключена.
2. Нажмите и удерживайте кнопку **"Громкость** " и одновременно нажмите и отпустите **кнопку питания.**
3. Когда на экране появится логотип Microsoft или Surface, продолжайте удерживать кнопку "**** Громкость", пока не появится экран UEFI.

## <a name="uefi-pc-information-page"></a>Страница сведений о компьютере UEFI

На странице сведений о компьютере содержатся подробные сведения о устройстве Surface:

- **Модель** — здесь будет отображаться модель устройства Surface, например Surface Book 2 или Surface Pro 7. Точная конфигурация устройства не отображается (например, процессор, размер диска или размер памяти).
- **UUID**: уникальный идентификатор устройства, который используется для идентификации устройства во время разработки и управления.

- **Серийный номер** — этот номер определяет конкретное устройство Surface для сценариев добавления тегов к ресурсам и поддержки.
- **Asset Tag**: тег актива назначается устройству Surface с помощью [средства Asset Tag](assettag.md).

Кроме того, в этом разделе вы найдете подробные сведения о встроенном ПО устройства Surface. Устройства Surface включают несколько внутренних компонентов, работающих под управлением разных версий встроенного ПО. Версия встроенного ПО каждого из перечисленных ниже устройств отображается на странице **PC information** (как показано на рис. 1):

- UEFI системы;

- контроллер SAM;

- модуль управления Intel;

- встроенный контроллер системы;

- встроенное ПО сенсорного управления.

:::image type="content" alt-text="Сведения о системе и версии встроенного ПО." source="images/manage-surface-uefi-figure-1.png":::

*Рис. 1. Сведения о системе и версии встроенного ПО*

Вы можете найти актуальные сведения о последней версии встроенного ПО для вашего устройства Surface в [журнале обновлений Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) для этого устройства.

## <a name="uefi-security-page"></a>Страница "Безопасность UEFI"

:::image type="content" alt-text="Настройка параметров безопасности Surface UEFI." source="images/manage-surface-uefi-fig4.png":::

*Рисунок 2. Настройка параметров безопасности UEFI Surface*

На странице "Безопасность" можно задать пароль для защиты параметров UEFI. Этот пароль необходимо ввести при загрузке устройства Surface в режиме UEFI. Пароль может содержать следующие символы (как показано на рис. 3):

- Прописные буквы: A–Z

- Строчные буквы: a–z

- Цифры: 1–10

- Специальные символы: !@#$%^&*()?<>{}[]-_=+|.;;:'"

Пароль должен содержать не менее шести символов и с учетом регистра.

![Добавьте пароль для защиты параметров Surface UEFI.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Рисунок 3. Добавление пароля для защиты параметров UEFI Surface*

На странице "Безопасность" можно также изменить конфигурацию безопасной загрузки на устройстве Surface. Технология безопасной загрузки предотвращает загрузку несанкционированного кода на устройстве Surface, обеспечивая защиту от заражений буткитами и руткитами. Вы можете отключить безопасную загрузку, чтобы на устройстве Surface можно было загружать сторонние операционные системы и загрузочные носители. Вы также можете настроить безопасную загрузку для работы со сторонними сертификатами, как показано на рис. 4. Дополнительные сведения см. в [разделе "Безопасная загрузка"](/windows-hardware/design/device-experiences/oem-secure-boot).

![Настройка безопасной загрузки.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Рисунок 4. Настройка безопасной загрузки*

В зависимости от устройства вы также можете узнать, включен или отключен ваш TPM. Если параметр включения **доверенного** платформенного модуля не отображается, откройте файл tpm.msc в Windows, чтобы проверить состояние, как показано на рисунке 5. TPM используется для проверки подлинности шифрования данных устройства с помощью BitLocker. Дополнительные сведения см. в [обзоре BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

![Консоль доверенного платформенного модуля.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Рисунок 5. Консоль доверенного платформенного модуля*

## <a name="uefi-devices-page"></a>Страница "Устройства UEFI"

Страница "Устройства" позволяет включить или отключить определенные компоненты на соответствующих устройствах, включая Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7 и более поздних версий, Surface Pro 7, Surface Pro X, Surface Laptop 4, Surface Laptop 3, Surface Laptop SE и Surface Book 3. Компоненты состоят из следующих компонентов:

- Закрепление USB-порта

- разъем для карты MicroSD или SD;

- задняя камера;

- лицевая камера;

- инфракрасная камера;

- Wi-Fi и Bluetooth;

- встроенная аудиосистема (динамики и микрофон).

Каждое устройство отображается с кнопкой ползунка, которую можно переместить в положение **"** Включено" или "Отключено **" (** отключено), как показано на рис. 6.

:::image type="content" alt-text="Включение и отключение определенных устройств." source="images/manage-surface-uefi-fig5a.png":::

*Рисунок 6. Включение и отключение устройств*

## <a name="uefi-boot-configuration-page"></a>Страница конфигурации загрузки UEFI

Страница "Конфигурация загрузки" позволяет изменить порядок загрузки устройств, а также включить или отключить загрузку следующих устройств:

- диспетчер загрузки Windows;

- USB-накопитель;

- сеть PXE;

- внутренняя память.

Вы можете сразу загрузиться с определенного устройства или провести пальцем влево по записи этого устройства в списке с помощью сенсорного экрана. Вы также можете мгновенно загрузить систему на USB-устройство или USB-адаптер для Ethernet, когда устройство Surface отключено, одновременно нажав кнопки **уменьшения громкости** и **включения**.

Чтобы указанный порядок загрузки вступает в силу, необходимо задать для параметра **"** Включить альтернативную последовательность загрузки" значение **"Включено**", как показано на рисунке 7.

:::image type="content" alt-text="Настройте порядок загрузки для устройства Surface." source="images/manage-surface-uefi-fig6.png":::

*Рисунок 7. Настройка порядка загрузки для устройства Surface*

Вы также можете включить и отключить поддержку IPv6 для PXE с помощью параметра "Включить IPv6 для сетевой загрузки **PXE**", например при развертывании Windows с помощью PXE, где PXE-сервер настроен только для IPv4.  

## <a name="uefi-management-page"></a>Страница "Управление UEFI"

Страница "Управление" позволяет управлять использованием zero Touch UEFI Management и другими функциями на соответствующих устройствах, включая Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Laptop 4, Surface Laptop 3, Surface Laptop SE и Surface Book 3. 

:::image type="content" alt-text="Управление доступом к zero Touch UEFI Management и другим функциям." source="images/manage-surface-uefi-fig7a.png":::

*Рисунок 8. Управление доступом к zero Touch UEFI Management и другим функциям*

Zero Touch UEFI Management позволяет удаленно управлять параметрами UEFI с помощью профиля устройства в Intune интерфейсе конфигурации встроенного ПО устройства (DFCI). Если этот параметр не настроен, возможность управления подходящими устройствами с помощью DFCI устанавливается в состояние **"Готово"**. Чтобы запретить использование DFCI, выберите **"Отказаться"**.

> [!NOTE]
> Страница параметров управления UEFI и использование DFCI в настоящее время доступны для Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 и Surface Pro X.  Дополнительные сведения см[. в Intune управления параметрами Surface UEFI](surface-manage-dfci-guide.md).

## <a name="uefi-exit-page"></a>Страница выхода UEFI

Нажмите **кнопку "Перезапустить сейчас** " на странице **"** Выход", чтобы выйти из параметров UEFI, как показано на рисунке 9.

:::image type="content" alt-text="Выйдите из Surface UEFI и перезапустите устройство." source="images/manage-surface-uefi-fig7.png":::

*Рисунок 9. Нажмите "Restart Now", чтобы выйти из меню UEFI Surface и перезагрузить устройство*

## <a name="surface-uefi-boot-screens"></a>Экраны загрузки UEFI Surface

При обновлении встроенного ПО устройства Surface с помощью клиентский компонент Центра обновления Windows или вручную обновления применяются не сразу к устройству, а во время следующего цикла перезагрузки. Дополнительные сведения о процессе обновления встроенного ПО Surface см. в статье "Управление и развертывание обновлений драйвера и встроенного ПО [Surface"](manage-surface-driver-and-firmware-updates.md). Ход обновления встроенного ПО отображается на экране с индикаторами хода выполнения различных цветов, чтобы указать встроенное ПО для каждого компонента. Индикатор выполнения каждого компонента показан на рисунках с 9 по 18.

![Обновление встроенного ПО Surface UEFI с синей индикатором выполнения.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Рисунок 10. Обновление встроенного ПО UEFI Surface с синим индикатором выполнения*

![Встроенное ПО системного контроллера с зеленой индикатором выполнения.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Рисунок 11. Обновление встроенного ПО встроенного контроллера системы с зеленым индикатором выполнения*

![Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Рисунок 12. Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения*

![Встроенное ПО intel Management Engine с красной индикатором выполнения.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Рисунок 13. Обновление встроенного ПО Intel Management Engine с красным индикатором выполнения*

![Встроенное ПО Сенсорного устройства Surface с серой индикатором выполнения.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Рисунок 14. При обновлении встроенного ПО сенсорных элементов Surface отображается серый индикатор выполнения*

![Встроенное ПО Surface KIP с светло-зеленой индикатором выполнения.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Рис. 15. Обновление встроенного ПО Surface KIP отображает светло-зеленую индикатор выполнения*

![Встроенное ПО Surface ISH с розовым индикатором выполнения.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Рис. 16. Обновление встроенного ПО Surface ISH отображает светло-розовый индикатор выполнения*

![Встроенное ПО Surface Trackpad с серым индикатором выполнения.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Рис. 17. Обновление встроенного ПО Surface Trackpad отображает розовую индикатор выполнения*

![Встроенное ПО TCON Surface с светло-серой индикатором выполнения.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Рисунок 18. Обновление встроенного ПО TCON surface отображает светло-серую индикатор выполнения*

![Встроенное ПО Доверенного платформенного модуля Surface с светло-фиолетовой индикатором выполнения.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Рисунок 19. Обновление встроенного ПО доверенного платформенного модуля Surface отображает фиолетовую индикатор выполнения*

>[!NOTE]
>Появится дополнительное предупреждающее сообщение о том, что безопасная загрузка отключена, как показано на рис. 19.

![Экран загрузки Surface, указывающий, что безопасная загрузка отключена.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Рисунок 20. Экран загрузки Surface, указывающий, что безопасная загрузка отключена в параметрах UEFI Surface*

## <a name="references"></a>Ссылки

1. Surface Go и Surface Go 2 используют сторонний UEFI и не поддерживают DFCI. Сейчас DFCI доступен для Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 и Surface Pro X.

## <a name="related-topics"></a>Статьи по теме

- [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md)

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
