---
title: Установка и настройка нового браузера Microsoft Edge на Surface Hub
description: Установка и настройка нового приложения Microsoft EDGE на Surface Hub.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: fe5f76034b5b8ae4801a8fb403d6db0ed423c144
ms.sourcegitcommit: 75940bb1ab4e08c96736923859c7dd673dcf8d79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009617"
---
# Установка и настройка нового браузера Microsoft Edge на Surface Hub

Обновление для Windows 10 Team 2020 поддерживает новый Microsoft EDGE на основе Chromium (версии 85 и выше) в качестве рекомендуемого браузера для Surface Hub. Вы можете установить Microsoft Edge вручную, используя пакет подготовки, удаленно с помощью Microsoft Intune или вашего основного поставщика услуг управления мобильными устройствами (MDM).

По умолчанию устройства Surface Hub предварительно устанавливаются с Microsoft Edge Legacy (версия 44).
 
Если вы уже установили EDGE, выполните указанные ниже действия.

1. Если вы не знаете версию или хотите подтвердить, откройте браузер EDGE и перейдите в edge://version.
2. Перейдите на **Surface Hub > Управление устройствами**. В разделе **подготовка пакетов**выберите команду **Добавить или удалить пакет подготовки.**
3. Если вы использовали более раннюю версию программы для закрепления Microsoft Edge dev в меню Пуск, выберите в списке пункт **Настраиваемое меню Пуск** и нажмите кнопку **Удалить.**
4. Если вы использовали специальную политику начальных макетов, вам нужно будет изменить ее с помощью последнего пути, как описано в разделе ниже показано, как [отобразить Microsoft EDGE в меню "Пуск" Surface Hub](#display-microsoft-edge-in-the-surface-hub-start-menu).
5. Теперь вы можете подготовить MicrosoftEdgeDevUninstaller. ppkg.
6. После того как приложение Edge будет удалено из **всех приложений**, сначала удалите "MicrosoftEdgeDevInstaller", а затем удалите "MicrosoftEdgeDevUninstaller".
7. Это действие успешно удалено на стороне Microsoft Edge dev. Теперь вы можете установить стандартную версию.

 
 
## Установка Microsoft Edge

### Установка Microsoft Edge с помощью пакета подготовки

1. С компьютера Скачайте [пакет подготовки Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeDevInstaller. ppkg) в корневую папку USB-накопителя.
2. Вставьте USB-накопитель на Surface Hub.
3. Из Surface Hub откройте **Параметры** и введите свои учетные данные администратора при появлении соответствующего запроса.
4. Перейдите к **Surface Hub** > **Управление устройствами**. В разделе **Пакеты подготовки** выберите **Добавить или удалить пакет подготовки**.
5. Выберите **Добавить пакет**.
6. Выберите пакет подготовки Microsoft EDGE и нажмите кнопку **Добавить**.
7. Вы увидите сводку изменений, которые применяют пакет подготовки. Выберите **Да, добавить**.
8. Дождитесь завершения установки Microsoft Edge. После установки откройте меню Пуск Surface Hub, чтобы получить доступ к новому Microsoft Edge.              

> [!NOTE]
> Если доступна более новая версия Microsoft EDGE, она будет автоматически обновлена.
 
### Установка Microsoft Edge с помощью Intune
 
> [!NOTE]
> Устройство Surface Hub должно быть зарегистрировано и управляться с помощью Intune. Дополнительные сведения можно найти [в разделе Управление Surface Hub 2S с помощью Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Скачайте установщик Microsoft Edge из Microsoft](https://www.microsoft.com/edge/business/download).
    - Использовать текущую версию из [стабильного канала](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выберите **Windows 64-bit**
2. [Добавьте установщик Microsoft EDGE в Microsoft Intune в качестве бизнес-приложения](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Если вы решили использовать обновление Microsoft Edge для обработки автоматических обновлений Microsoft EDGE, настройте параметр " **игнорировать версию приложения** " в области **сведений о приложении** . При переключении этого параметра на **Да**Microsoft Intune не будет применять версию приложения, установленную на устройстве Surface Hub.

 
### Установка Microsoft Edge с помощью управления мобильными устройствами

1. [Скачайте установщик Microsoft Edge из Microsoft](https://www.microsoft.com/edge/business/download).
    - Использовать текущую версию из [стабильного канала](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выберите **Windows 64-bit**
2. Поэтапное использование установщика Microsoft EDGE в размещенном расположении, например в локальной папке (\\server\share\MicrosoftEdgeEnterpriseX64.msi). Устройство Surface Hub должно иметь разрешение на доступ к расположению размещения.
3. Чтобы установить Microsoft EDGE, используйте поставщик [службы настройки (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) для поставщика служб MDM.

 

## Настройка Microsoft Edge

### Политики Microsoft Edge для Surface Hub по умолчанию
Microsoft Edge имеет следующие политики для обеспечения оптимальной работы Surface Hub.
 
> [!NOTE]
>  Рекомендуется сохранить значения по умолчанию для этих политик.
 

| Политики Microsoft Edge                                                                                                    | Рекомендуемый опыт                                                                                                                                                                                                                                               | Значение по умолчанию |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Не автоматически импортируйте типы и параметры типов и параметров из Microsoft Edge Legacy. Это позволит избежать изменения профилей пользователей, которые вошли в систему, с общими параметрами из Surface Hub.                                                                                                 | четырехпроцессорном                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Разрешите, чтобы процесс Microsoft Edge оставался на фоне даже после закрытия последнего окна браузера, что позволяет быстрее получать доступ к веб-приложениям во время сеанса.                                                                                                      | 1,1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Не разрешать пользователям создавать новые профили в Microsoft Edge. Это упрощает просмотр и работу со входом.                                                                                                                                                      | до                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Позволяет одному пользователю входить в Microsoft Edge. Это упрощает просмотр и работу со входом.                                                                                                                                                                | до                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Позволяет пользователям работать с единым входом (SSO) в Microsoft Edge. При входе пользователя в Surface Hub их учетные данные могут перетекать на поддерживаемые веб-сайты, не требуя повторной проверки подлинности.  | 1,1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Запрещает пользователям, не являющимся администраторами, устанавливать новые расширения в Microsoft Edge. Чтобы настроить список расширений, которые должны быть установлены по умолчанию, используйте [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Скрывает первый интерфейс и экран-заставку, обычно отображаемые при первом запуске Microsoft Edge пользователем. Поскольку Surface Hub — это общее устройство, это упрощает взаимодействие с пользователем.                                                                      | 1,1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Отключение режима InPrivate. Поскольку конечный сеанс уже очищает данные для просмотра, это упрощает просмотр и вход.                                                                                                                                          | 1,1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | На новых вкладках показана работа с веб-каналами Office 365. При входе пользователя в Surface Hub это обеспечивает быстрый доступ к своим файлам и контенту в Office 365.                                                                                                        | 1,1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | При входе пользователя в Surface Hub создается несъемный профиль с помощью своей учетной записи организации. Это упрощает процесс единого входа (SSO).                                                                                                 | 1,1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Отключение печати в Microsoft Edge. Surface Hub не поддерживает печать.                                                                                                                                                                                              | до                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Включает Microsoft Edge для упреждающего проверки подлинности пользователей, которые вошли в службы Майкрософт. Это упрощает процесс единого входа (SSO).                                                                                                                         | 1,1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Автоматическое сохранение файлов в папку downloads, а не запрос пользователей на сохранение файла. Это упрощает работу с обозревателем.                                                                                                                             | до                 |

> [!IMPORTANT]
> Развертываемые прогрессивные веб-приложения (PWAs) в настоящее время не поддерживаются в операционной системе Windows 10 Team.  Кроме того, обратите внимание на то, что параметр Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) не поддерживается в Surface Hub. 

### Настройка параметров политики Microsoft Edge

Используйте [политики браузера Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) для настройки параметров браузера в Microsoft Edge. Эти политики можно применять в следующих случаях:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Ваш предпочтительный поставщик управления мобильными устройствами (MDM), поддерживающий](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)прием файлов ADMX, или
- [Подготовка пакетов, использующих прием файлов ADMX в конструкторе конфигураций Windows](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### Настройка обновлений Microsoft Edge

По умолчанию Microsoft Edge обновляется автоматически. Настройте параметры обновления Microsoft Edge с помощью [политик обновления Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) .
Обратите внимание, что Surface Hub не поддерживает следующие политики обновления Microsoft Edge.

- **Allowsxs** — на Surface Hub, стабильный канал Microsoft Edge всегда заменяет Microsoft Edge Legacy.
- **CreateDesktopShortcut** — Surface Hub не использует сочетания клавиш на рабочем столе.

> [!NOTE]
>  Для работы этих функций в Microsoft Edge требуется подключение к Интернету. Убедитесь в том, что [необходимые URL-адреса домена](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) добавлены в список разрешений для обеспечения взаимодействия через брандмауэры и другие механизмы обеспечения безопасности.
 
### Отображение Microsoft EDGE в меню "Пуск" Surface HUB

Если вы используете макет меню "Пуск" по умолчанию, вы можете установить меню "Пуск" с пакетом подготовки Microsoft Edge для добавления Microsoft EDGE в качестве закрепленного приложения.
Если вы хотите применить настраиваемый макет меню "Пуск", используйте следующий XML-код, чтобы добавить закрепленную плитку для Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Дополнительные сведения можно найти в разделе [Настройка меню Пуск Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> Новая Microsoft EDGE не поддерживает закрепленные веб-сайты и ссылки с помощью SecondaryTiles.

## Дополнительные ссылки

- [Документация по Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).

