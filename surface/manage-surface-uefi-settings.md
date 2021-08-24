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
ms.date: 04/13/2021
ms.openlocfilehash: 60ace1e2b9344faeb9f130a56686ffac4643fc37
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911324"
---
# <a name="manage-surface-uefi-settings"></a>Управление параметрами UEFI Surface

 Устройства Surface PC предназначены для использования уникального интерфейса прошивки единой надежной прошивки (UEFI), разработанного корпорацией Майкрософт специально для этих устройств. Параметры Surface UEFI предоставляют возможность включить или отключить встроенные устройства и компоненты, защитить параметры UEFI от изменения и настроить параметры загрузки устройств Surface.

## <a name="supported-products"></a>Поддерживаемые продукты

Управление UEFI поддерживается следующим образом:

- Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1-й ген), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4
- Surface Studio (1-й gen), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## <a name="support-for-cloud-based-management"></a>Поддержка облачного управления

С учетом профилей интерфейса конфигурации микропрограммных программ (DFCI), встроенных в Microsoft Intune (теперь доступны для общего просмотра), управление Surface UEFI расширяет современный стек управления до уровня оборудования UEFI. DFCI поддерживает установку без касания, устраняет пароли BIOS, обеспечивает контроль параметров безопасности, включая параметры загрузки и встроенные периферийные устройства, и закладывая основу для расширенных сценариев безопасности в будущем. В настоящее время DFCI доступен для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 и Surface Pro X.  Дополнительные сведения см. в руководстве [Intune параметров Surface UEFI.](surface-manage-dfci-guide.md)

## <a name="open-surface-uefi-menu"></a>Меню Open Surface UEFI

Чтобы настроить параметры UEFI во время запуска системы:

1. Выключите Surface и подождите около 10 секунд, чтобы убедиться, что она отключена.
2. Нажмите и удерживайте кнопку **Volume-up** и одновременно нажмите кнопку Power и **отпустите ее.**
3. По мере того как логотип Microsoft или Surface появится на экране, продолжайте удерживать кнопку **тома** до тех пор, пока не появится экран UEFI.

## <a name="uefi-pc-information-page"></a>Страница сведений о ПК UEFI

На странице сведений о ПК содержатся подробные сведения о устройстве Surface:

- **Модель** — модель устройства Surface будет отображаться здесь, например Surface Book 2 или Surface Pro 7. Точная конфигурация устройства (например, процессор, размер диска или объем памяти) не отображается.
- **UUID**: уникальный идентификатор устройства, который используется для идентификации устройства во время разработки и управления.

- **Serial Number**: этот номер используется для идентификации устройства Surface во время инвентаризации и поддержки.
- **Asset Tag**: тег актива назначается устройству Surface с помощью [средства Asset Tag](assettag.md).

Кроме того, в этом разделе вы найдете подробные сведения о встроенном ПО устройства Surface. Устройства Surface включают несколько внутренних компонентов, работающих под управлением разных версий встроенного ПО. Версия встроенного ПО каждого из перечисленных ниже устройств отображается на странице **PC information** (как показано на рис. 1):

- UEFI системы;

- контроллер SAM;

- модуль управления Intel;

- встроенный контроллер системы;

- встроенное ПО сенсорного управления.

:::image type="content" alt-text="Сведения о системе и сведения о версии прошивки." source="images/manage-surface-uefi-figure-1.png":::

*Рис. 1. Сведения о системе и версии встроенного ПО*

Вы можете найти актуальные сведения о последней версии встроенного ПО для вашего устройства Surface в [журнале обновлений Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) для этого устройства.

## <a name="uefi-security-page"></a>Страница безопасности UEFI

:::image type="content" alt-text="Настройка параметров безопасности Surface UEFI." source="images/manage-surface-uefi-fig4.png":::

*Рисунок 2. Настройка параметров безопасности UEFI Surface*

Страница Безопасности позволяет установить пароль для защиты параметров UEFI. Этот пароль необходимо ввести при загрузке устройства Surface в режиме UEFI. Пароль может содержать следующие символы (как показано на рисунке 3):

- Прописные буквы: A–Z

- Строчные буквы: a–z

- Цифры: 1–10

- Специальные символы: !@#$%^&*()?<>{} []-_=+|.;:'"

Пароль должен состоять по крайней мере из 6 символов и вводится с учетом регистра.

![Добавьте пароль для защиты параметров Surface UEFI.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Рисунок 3. Добавление пароля для защиты параметров UEFI Surface*

На странице Security также можно изменить конфигурацию безопасной загрузки устройства Surface. Технология безопасной загрузки предотвращает загрузку несанкционированного кода на устройстве Surface, обеспечивая защиту от заражений буткитами и руткитами. Вы можете отключить безопасную загрузку, чтобы на устройстве Surface можно было загружать сторонние операционные системы и загрузочные носители. Можно также настроить secure Boot для работы с сторонними сертификатами, как показано на рисунке 4. Дополнительные сведения о [безопасной загрузке](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) см. в библиотеке TechNet.

![Настройка безопасной загрузки.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Рисунок 4. Настройка безопасной загрузки*

В зависимости от устройства вы также можете узнать, включена или отключена TPM. Если вы не видите параметр **Включить TPM,** откройте tpm.msc в Windows, чтобы проверить состояние, как показано на рисунке 5. TPM используется для проверки подлинности при шифровании данных устройства с помощью BitLocker. Дополнительные сведения см. в [обзоре BitLocker.](/windows/security/information-protection/bitlocker/bitlocker-overview)

![Консоль TPM.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Рисунок 5. Консоль TPM*

## <a name="uefi-menu-devices"></a>Меню UEFI: Устройства

Страница Devices позволяет включить или отключить определенные устройства и компоненты, включая:

- Стыковка USB-порта

- разъем для карты MicroSD или SD;

- задняя камера;

- лицевая камера;

- инфракрасная камера;

- Wi-Fi и Bluetooth;

- встроенная аудиосистема (динамики и микрофон).

Каждое устройство перечислены с помощью кнопки ползунок, которую можно переместить в положение **Включено** (включено) или Отключено **** (отключено), как показано на рисунке 6.

:::image type="content" alt-text="Включить и отключить определенные устройства." source="images/manage-surface-uefi-fig5a.png":::

*Рисунок 6. Включение и отключение устройств*

## <a name="uefi-menu-boot-configuration"></a>Меню UEFI: конфигурация загрузки

Страница Конфигурация загрузки позволяет изменить порядок загрузки устройств, а также включить или отключить загрузку следующих устройств:

- диспетчер загрузки Windows;

- USB-накопитель;

- сеть PXE;

- внутренняя память.

Вы можете мгновенно загрузить систему с определенного устройства или провести пальцем влево по этому устройству в списке. Вы также можете мгновенно загрузить систему на USB-устройство или USB-адаптер для Ethernet, когда устройство Surface отключено, одновременно нажав кнопки **уменьшения громкости** и **включения**.

Чтобы указанный порядок загрузки вступил в силу, необходимо установить параметр **Включить** альтернативную последовательность загрузки **для On,** как показано на рисунке 7.

:::image type="content" alt-text="Настройка порядка загрузки для устройства Surface." source="images/manage-surface-uefi-fig6.png":::

*Рисунок 7. Настройка порядка загрузки для устройства Surface*

Вы также можете включать и отключать поддержку IPv6 для PXE с помощью параметра **Enable IPv6 for PXE Network Boot**, например во время развертывания Windows с помощью PXE, если сервер PXE настроен только для IPv4.  

## <a name="uefi-menu-management"></a>Меню UEFI: управление

Страница Управление позволяет управлять использованием управления Zero Touch UEFI и другими функциями на соответствующих устройствах, включая Surface Pro 7, Surface Pro X и Surface Laptop 3.  

:::image type="content" alt-text="Управление доступом к управлению UEFI Zero Touch и другими функциями." source="images/manage-surface-uefi-fig7a.png":::

*Рисунок 8. Управление доступом к управлению UEFI Zero Touch и другими функциями*

Zero Touch UEFI Management позволяет удаленно управлять настройками UEFI с помощью профиля устройства в Intune под названием Интерфейс конфигурации микропрограммных устройств (DFCI). Если этот параметр не настроен, возможность управления подходящими устройствами с **** помощью DFCI заданной. Чтобы предотвратить DFCI, выберите **opt-Out**.

> [!NOTE]
> Страница ПАРАМЕТРОВ управления UEFI и использование DFCI в настоящее время доступны для Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 и Surface Pro X. Дополнительные новости см. в [руководстве Intune параметров Surface UEFI.](surface-manage-dfci-guide.md)

## <a name="uefi-menu-exit"></a>Меню UEFI: выход

Чтобы **выйти** из **** параметров UEFI, используйте кнопку Перезапустить теперь, как показано на рисунке 9.

:::image type="content" alt-text="Выйдите из UEFI Surface и перезапустите устройство." source="images/manage-surface-uefi-fig7.png":::

*Рисунок 9. Нажмите "Restart Now", чтобы выйти из меню UEFI Surface и перезагрузить устройство*

## <a name="surface-uefi-boot-screens"></a>Экраны загрузки UEFI Surface

При обновлении встроенного ПО устройства Surface с помощью центра обновления Windows или ручной установки обновления применяются к устройству не сразу, а во время следующего цикла перезагрузки. Дополнительные новости о процессе обновления прошивки Surface можно узнать в "Управление и развертывание обновлений [драйвера и прошивки Surface".](manage-surface-driver-and-firmware-updates.md) Выполнение обновления встроенного ПО отображается на экране с помощью индикаторов разных цветов, соответствующих встроенному ПО каждого компонента. Планка прогресса каждого компонента показана в рисунках 9-18.

![Обновление прошивки Surface UEFI с синей панели прогресса.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Рисунок 10. Обновление встроенного ПО UEFI Surface с синим индикатором выполнения*

![Прошивка встроенного контроллера системы с зеленой планкой прогресса.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Рисунок 11. Обновление встроенного ПО встроенного контроллера системы с зеленым индикатором выполнения*

![Обновление прошивки контроллера SAM с оранжевой панели прогресса.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Рисунок 12. Обновление встроенного ПО контроллера SAM с оранжевым индикатором выполнения*

![Прошивка Intel Management Engine с красной панели прогресса.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Рисунок 13. Обновление встроенного ПО Intel Management Engine с красным индикатором выполнения*

![Прошивка Surface touch с серой панели прогресса.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Рисунок 14. При обновлении встроенного ПО сенсорных элементов Surface отображается серый индикатор выполнения*

![Прошивка Surface KIP с светло-зеленой планкой прогресса.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Рис. 15. Обновление прошивки Surface KIP отображает светло-зеленую планку прогресса*

![Прошивка Surface ISH с розовым штрихом прогресса.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Рис. 16 Обновление прошивки Surface ISH отображает светло-розовую планку прогресса*

![Прошивка Surface Trackpad с серой панелью прогресса.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Рис. 17. Обновление прошивки Surface Trackpad отображает розовую планку прогресса*

![Прошивка Surface TCON с светло-серой панели прогресса.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Рисунок 18. Обновление прошивки Surface TCON отображает светло-серую планку прогресса*

![Прошивка Surface TPM с светло-фиолетовой панели прогресса.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Рисунок 19. Обновление прошивки Surface TPM отображает фиолетовую планку прогресса*

>[!NOTE]
>Отображается дополнительное предупреждение, которое указывает на отключение безопасной загрузки, как показано на рисунке 19.

![Экран загрузки surface, на который указывается отключена безопасная загрузка.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Рисунок 20. Экран загрузки Surface, указывающий, что безопасная загрузка отключена в параметрах UEFI Surface*

## <a name="references"></a>Ссылки

1. Surface Go и Surface Go 2 используют сторонний UEFI и не поддерживают DFCI.

## <a name="related-topics"></a>Статьи по теме

- [Управление параметрами UEFI Surface в Intune](surface-manage-dfci-guide.md)

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
