---
title: Управление Microsoft Edge на Surface Hub
description: В этой статье описываются параметры Microsoft Edge политики и средства для настройки параметров браузера.
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
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497732"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Управление Microsoft Edge на Surface Hub

Используйте [Microsoft Edge браузера для](/deployedge/microsoft-edge-policies) настройки параметров браузера в Microsoft Edge с помощью любого из следующих методов:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Предпочитаемый поставщик мобильных Управление устройствами (MDM), который поддерживает прием ADMX](/deployedge/configure-edge-with-mdm)
- [Подготовка пакетов с помощью приема ADMX в Windows конфигурации](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> Чтобы выйти из полноэкранного режима, проведите пальцем вниз от верхней части экрана, чтобы выйти из полноэкранного режима, с помощью нового Microsoft Edge. Выход из полноэкранного действия также доступен в контекстном меню, отображаемом после длительного нажатия.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Политики Microsoft Edge по умолчанию для Surface Hub

Microsoft Edge предварительно настроены с помощью следующих параметров политики, чтобы обеспечить оптимизированный интерфейс для Surface Hub.


> [!TIP]
> Рекомендуется сохранить значение по умолчанию для этих параметров политики.

| Параметр политики                                                                                                   | Рекомендуемый интерфейс                                                                                                                                                                                                                                               | Значение по умолчанию |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Не импортируйте автоматически типы данных и параметры из устаревшая версия Microsoft Edge. Это позволяет избежать изменения профилей вошедщих пользователей с общими параметрами из Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Разрешите Microsoft Edge продолжать работу в фоновом режиме даже после закрытия последнего окна браузера, что обеспечивает более быстрый доступ к веб-приложениям во время сеанса.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Не разрешать пользователям создавать новые профили в Microsoft Edge. Это упрощает просмотр и вход.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Позволяет только одному пользователю войти в Microsoft Edge. Это упрощает просмотр и вход в систему                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Позволяет пользователям пользоваться единым Sign-On (SSO) в Microsoft Edge. При входе пользователя в Surface Hub его учетные данные могут перенаться на поддерживаемые веб-сайты без необходимости повторной проверки подлинности.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Запрещает пользователям без прав администратора устанавливать новые расширения в Microsoft Edge. Чтобы настроить список расширений для установки по умолчанию, используйте [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Скрывает первый запуск и экран-заставку, которые обычно отображаются при первом запуске Microsoft Edge запуска. Так Surface Hub является общим устройством, это упрощает взаимодействие с пользователем.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Отключает режим InPrivate. Так как конечный сеанс уже очищает данные браузера, это упрощает просмотр и вход.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Отображает Office 365 веб-канала на новых страницах вкладок. При входе пользователя в Surface Hub это обеспечивает быстрый доступ к его файлам и содержимому на Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | При входе пользователя в Surface Hub создается не съемный профиль с помощью учетной записи организации. Это упрощает единый Sign-On единого входа.                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Отключает печать в Microsoft Edge. Surface Hub не поддерживает печать.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Позволяет Microsoft Edge выполнять упреждающее аутентификацию пользователей, выполнив вход с помощью службы Майкрософт. Это упрощает единый Sign-On единого входа.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Автоматически сохраняет файлы в папку "Загрузки", а не запрашивает у пользователей место сохранения файла. Это упрощает работу с браузером.                                                                                                                             | 0                 |

> [!TIP]
> Развертываемые прогрессивные веб-приложения (PWA) теперь поддерживаются в Windows 10 для совместной работы операционной системе. Дополнительные сведения см. в [статье "Установка веб-приложения на Surface Hub](install-pwa-surface-hub.md)". 

### <a name="configure-microsoft-edge-updates"></a>Настройка Microsoft Edge обновлений

По умолчанию Microsoft Edge обновляется автоматически. Используйте [Microsoft Edge обновления для](/deployedge/microsoft-edge-update-policies) настройки параметров Центр обновления Microsoft Edge. Обратите внимание, Surface Hub не поддерживает параметр политики **CreateDesktopShortcut**, так как Surface Hub не использует ярлыки рабочего стола.

> [!TIP]
> Для работы этих функций в Microsoft Edge требуется подключение к Интернету. Добавьте [необходимые URL-адреса домена](/deployedge/microsoft-edge-security-endpoints) в список разрешений, чтобы обеспечить обмен данными через брандмауэры и другие механизмы безопасности.

## <a name="related-links"></a>Дополнительные ссылки

- [Документация по Microsoft Edge](/microsoft-edge/)