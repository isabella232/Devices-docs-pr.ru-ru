---
title: Установка и настройка нового браузера Microsoft Edge на Surface Hub
description: Установите и настройте новый Microsoft Edge на Surface Hub.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/08/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 74ae47e80447f89753110c52a49daf649478dd50
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319173"
---
# Установка и настройка нового браузера Microsoft Edge на Surface Hub

Центр обновления Windows 10 для группы 2020 поддерживает новый Microsoft Edge на основе Chromium (версии 85 и выше) в качестве рекомендованного браузера для Surface Hub 2S и Surface Hub (версия 1). В этой статье объясняется, как установить браузер с помощью одного из трех методов: пакета предоставления, Microsoft Intune или стороне поставщика управления мобильными устройствами (MDM).

> [!IMPORTANT]
> По умолчанию устройства Surface Hub предустановлены с помощью Microsoft Edge Legacy (версия 44). После установки обновления [2020](surface-hub-2020-update.md)рекомендуется переключиться на новый браузер Microsoft Edge; Поддержка [Microsoft Edge Legacy](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) завершится 9 марта 2021 г.

## Установка Microsoft Edge с помощью пакета предоставления

1. На компьютере скачайте пакет предоставления [Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) в корневую папку USB-накопителя.
2. Вставьте USB-накопитель в Surface Hub.
3. В Surface Hub откройте **"Параметры"** и введите учетные данные администратора при запросе.
4. Перейдите к **Surface Hub** > **Управление устройствами**. В разделе **Пакеты подготовки** выберите **Добавить или удалить пакет подготовки**.
5. Выберите **Добавить пакет**.
6. Выберите пакет предоставления Microsoft Edge и выберите **"Добавить".**
7. Вы увидите сводку изменений, которые применяются к пакету подготовка. Выберите **Да, добавить**.
8. Дождись завершения установки Microsoft Edge. После установки перейдите в меню "Пуск" Surface Hub, чтобы получить доступ к новому Microsoft Edge.              

> [!NOTE]
> Если доступна более новая версия Microsoft Edge, она будет автоматически обновлена.
 
## Установка Microsoft Edge с помощью Intune
 
> [!NOTE]
> Устройство Surface Hub должно быть зарегистрироваться в Intune и управлять им. Дополнительные сведения см. в под [управлением Surface Hub 2S с помощью Microsoft Intune.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Скачайте установщик Microsoft Edge.](https://www.microsoft.com/edge/business/download)
    - Использование текущей версии канала [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выбор **64-битной версии Windows**
2. Добавьте установщик Microsoft Edge в качестве [бизнес-приложения в Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - Если вы решили использовать Microsoft Edge Update для обработки автоматических обновлений Microsoft Edge, настройте параметр "Игнорировать версию приложения" в области сведений **о** приложении. **** Если вы переключите этот параметр на **"Да",** Microsoft Intune не будет применять версию приложения, установленную на устройстве Surface Hub.

## Установка Microsoft Edge с помощью сторонного поставщика MDM

1. [Скачайте установщик Microsoft Edge от Майкрософт.](https://www.microsoft.com/edge/business/download)
    - Использование текущей версии канала [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выбор **64-битной версии Windows**
2. Разустановка установщика Microsoft Edge в расположении, например в локальном файловом \\server\share\MicrosoftEdgeEnterpriseX64.msi. Устройство Surface Hub должно иметь разрешение на доступ к расположению.
3. Используйте [поставщик служб конфигурации (CSP) EnterpriseDesktopAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) через поставщика MDM для установки Microsoft Edge.

## Настройка Microsoft Edge

### Политики Microsoft Edge по умолчанию для Surface Hub

В Microsoft Edge предварительно настроены следующие наборы политик, которые обеспечивают оптимизированный процесс для Surface Hub.
 
> [!TIP]
> Рекомендуется сохранить значение по умолчанию для этих параметров политики.
 

| Параметр политики                                                                                                   | Рекомендуемый опыт                                                                                                                                                                                                                                               | Значение по умолчанию |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Не импортировать автоматически тип данных и параметры из Microsoft Edge Legacy. Это позволяет избежать изменения профилей во время входящего пользователя с помощью общих параметров Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Разрешить процессам Microsoft Edge продолжать работу в фоновом режиме даже после закрытия последнего окна браузера, что обеспечивает более быстрый доступ к веб-приложениям во время сеанса.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Не разрешайте пользователям создавать новые профили в Microsoft Edge. Это упрощает просмотр и во время его работы.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Позволяет только одному пользователю войти в Microsoft Edge. Это упрощает просмотр и во время его работы                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Позволяет пользователям пользоваться единым Sign-On (SSO) в Microsoft Edge. После входа пользователя в Surface Hub его учетные данные могут поступать на поддерживаемые веб-сайты без необходимости повторной проверки подлинности.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Не позволяет пользователям без администрирования устанавливать новые расширения в Microsoft Edge. Чтобы настроить список расширений, устанавливаемых по умолчанию, используйте [ExtensionInstallForcelist.](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Скрывает первый запуск и экран-заставки, который обычно отображается при первом запуске Microsoft Edge. Так как Surface Hub является общим устройством, это упрощает пользовательский интерфейс.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Отключает режим InPrivate. Так как в конце сеанса уже очищаются данные браузера, это упрощает просмотр и во время сеанса.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Показывает веб-канал Office 365 на новых страницах вкладок. При входе пользователя в Surface Hub это обеспечивает быстрый доступ к его файлам и содержимому в Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Когда пользователь въехал в Surface Hub, с помощью учетной записи организации создается не съемный профиль. Это упрощает единый Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Отключает печать в Microsoft Edge. Surface Hub не поддерживает печать.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Позволяет Microsoft Edge заблаговременно аутентификация во время проверки подлинности пользователей, во время работы с ними, с помощью служб Майкрософт. Это упрощает единый Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Автоматически сохраняет файлы в папку "Загрузки", а не запрашивает у пользователей место сохранения файла. Это упрощает просмотр.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Развертываемые последовательные веб-приложения (PWAs) в настоящее время не поддерживаются в операционной системе Windows 10 Team.  Обратите внимание, что параметр политики Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) не поддерживается на Surface Hub. 

### Настройка параметров политики Microsoft Edge

Используйте [политики браузера Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) для настройки параметров браузера в Microsoft Edge. Эти политики можно применять с помощью:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Предпочитаемый поставщик управления мобильными устройствами (MDM), который поддерживает ADMX Ingestion,](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)или
- [Подготовка пакетов с использованием ADMX Ingestion в конструкторе конфигураций Windows.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Настройка обновлений Microsoft Edge

По умолчанию Microsoft Edge обновляется автоматически. Используйте [политики обновления Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) для настройки параметров обновления Microsoft Edge.
Обратите внимание, что Surface Hub не поддерживает следующие политики обновления Microsoft Edge:

- **Allowsxs** — на Surface Hub канал Microsoft Edge Stable всегда заменяет Microsoft Edge Legacy.
- **CreateDesktopShortcut** — Surface Hub не использует ярлыки рабочего стола.

> [!NOTE]
>  Для работы этих функций в Microsoft Edge требуется подключение к Интернету. Убедитесь, что в список "Разрешить" добавлены [необходимые URL-адреса](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) доменов, чтобы обеспечить связь через брандмауэры и другие механизмы безопасности.
 
### Отображение Microsoft Edge в меню "Пуск" Surface Hub

Если вы используете макет меню "Пуск" по умолчанию, вы можете установить меню "Пуск" с пакетом подготовка Microsoft Edge, чтобы добавить Microsoft Edge в качестве закрепленного приложения.
Если вы хотите применить настраиваемый макет меню "Пуск", добавьте закрепленную плитку для Microsoft Edge с помощью следующего XML-кода.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Дополнительные сведения см. в меню ["Настройка меню "Пуск" Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)
 
> [!NOTE]
> Новый Microsoft Edge не поддерживает закрепленные веб-сайты.

## Дополнительные ссылки

- [Документация по Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/)

