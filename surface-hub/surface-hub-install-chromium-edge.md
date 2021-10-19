---
title: Управление Microsoft Edge на Surface Hub
description: В этой статье описываются Microsoft Edge параметры политики и средства настройки параметров браузера.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100717"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Управление Microsoft Edge на Surface Hub

Используйте [Microsoft Edge браузера для](/deployedge/microsoft-edge-policies) настройки параметров браузера в Microsoft Edge с помощью любого из следующих методов:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Ваш предпочтительный поставщик управления мобильными устройствами (MDM), который поддерживает ADMX Ingestion](/deployedge/configure-edge-with-mdm)
- [Подготовка пакетов с использованием ADMX Ingestion в Windows Конструктор конфигурации](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> Чтобы выйти из полноэкранного режима, свайп вниз из верхней части экрана требует двух пальцев с новым Microsoft Edge. Полноэкранное действие выхода также доступно в контексте меню, отображаемом после касания с длительным нажатием.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Политики Microsoft Edge по умолчанию для Surface Hub

Microsoft Edge предварительно с помощью следующих задатков политики, чтобы обеспечить оптимизированный опыт для Surface Hub.


> [!TIP]
> Рекомендуется сохранить значение по умолчанию для этих параметров политики.

| Параметр политики                                                                                                   | Рекомендуемый опыт                                                                                                                                                                                                                                               | Значение по умолчанию |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Не импортировать автоматически типики и параметры данных из устаревшая версия Microsoft Edge. Это позволяет избежать изменения профилей пользователей с общими настройками из Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Разрешить Microsoft Edge процессы в фоновом режиме даже после закрытия последнего окна браузера, что позволяет быстрее получать доступ к веб-приложениям во время сеанса.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Не позволяйте пользователям создавать новые профили в Microsoft Edge. Это упрощает возможности просмотра и подписи.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Позволяет только одному пользователю войти в Microsoft Edge. Это упрощает возможности просмотра и подписи                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Позволяет пользователям пользоваться единой Sign-On (SSO) в Microsoft Edge. Когда пользователь подписан в Surface Hub, его учетные данные могут перетекать на поддерживаемые веб-сайты, не требуя от них повторной проверки подлинности.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Предотвращает установку новых расширений в Microsoft Edge. Чтобы настроить список расширений, которые будут установлены по умолчанию, используйте [ExtensionInstallForcelist.](/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Скрывает первый опыт запуска и экран всплеска, который обычно отображается при первом запуске Microsoft Edge пользователей. Поскольку Surface Hub является общим устройством, это упрощает пользовательский интерфейс.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Отключает режим InPrivate. Так как в конце сеанса уже очищаются данные просмотра, это упрощает просмотр и личные данные.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Отображает Office 365 каналов на новых страницах вкладок. При входе пользователя в Surface Hub доступ к его файлам и контенту в Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | При подписании пользователя в Surface Hub будет создан не съемный профиль с помощью его учетной записи организации. Это упрощает опыт единой Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Отключает печать в Microsoft Edge. Surface Hub не поддерживает печать.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Позволяет Microsoft Edge с помощью службы Майкрософт. Это упрощает опыт единой Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Автоматически сохраняет файлы в папку Downloads, а не запрашивает у пользователей, где сохранить файл. Это упрощает просмотр.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Развертываемые прогрессивные веб-приложения (PWAs) в настоящее время не поддерживаются в Windows 10 для совместной работы операционной системе.  Обратите внимание также, Microsoft Edge параметр [политики WebAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist) не поддерживается Surface Hub.

### <a name="configure-microsoft-edge-updates"></a>Настройка Microsoft Edge обновлений

По умолчанию Microsoft Edge обновляется автоматически. Используйте [Microsoft Edge политики обновления](/deployedge/microsoft-edge-update-policies) для настройки параметров для Центр обновления Microsoft Edge. Обратите внимание, Surface Hub не поддерживает параметр **политики CreateDesktopShortcut,** так как Surface Hub не использует ярлыки рабочего стола.

> [!TIP]
> Для работы этих функций в Microsoft Edge требуется подключение к Интернету. Добавьте [необходимые URL-адреса домена](/deployedge/microsoft-edge-security-endpoints) в список Разрешить, чтобы обеспечить связь с помощью брандмауэров и других механизмов безопасности.

## <a name="related-links"></a>Дополнительные ссылки

- [Документация по Microsoft Edge](/microsoft-edge/)