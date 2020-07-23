---
title: Установка и настройка нового приложения Microsoft EDGE на Surface HUB
description: Установка и настройка нового приложения Microsoft EDGE на Surface Hub.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: cf4d909a8c06bddf2bb0b3e42259f0b69cd97109
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894105"
---
# Установка и настройка нового приложения Microsoft EDGE на Surface HUB

Обновление для Windows 10 Team 2020 поддерживает новый Microsoft EDGE на основе Chromium (версии 85 и выше) в качестве рекомендуемого браузера для Surface Hub. Вы можете установить Microsoft Edge вручную, используя пакет подготовки, удаленно с помощью Microsoft Intune или вашего основного поставщика услуг управления мобильными устройствами (MDM).

 По умолчанию устройства Surface Hub предварительно устанавливаются с Microsoft Edge Legacy (версия 44).

> [!IMPORTANT]
> Surface Hub требуется версия 85 или более поздней версии нового приложения Microsoft EDGE, с ограниченным доступом[, для](https://docs.microsoft.com/deployedge/microsoft-edge-channels)предоставления администраторам более раннего взгляда на предстоящие функции пограничного предложения и подготовки к следующей бета-версии.  Поддержка канала разработки временно включена для участников программы предварительной оценки Windows, чтобы предварительно просмотреть Microsoft Edge. (Обычно Surface Hub поддерживает только версии, выпускаемые в «стабильный канал»). Дополнительные сведения можно найти в [статье Обзор канала Microsoft Edge.](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
### Установка сборок канала разработки Microsoft Edge 

- По дизайну канал разработки Microsoft Edge устанавливается рядом с Microsoft Edge Legacy, а пользователи увидят как "Microsoft Edge dev" (версия 85) и "Microsoft Edge" (версия 44) в меню Пуск Surface Hub. Напротив, стабильный канал Microsoft Edge заменит Microsoft Edge Legacy в качестве браузера по умолчанию.
- После установки канал разработки Microsoft EDGE не будет автоматически отображаться как закрепленное приложение. Чтобы открыть приложение, выберите команду **запустить**  >  **все приложения**. Напротив, стабильный канал Microsoft EDGE автоматически заменяет Microsoft Edge Legacy на закрепленное приложение в списке все приложения.
- После того как версия 85 будет выдвинута на стабильный канал, канал разработки Microsoft EDGE автоматически исчезнет из меню "Пуск", и вам потребуется установить стабильный канал Microsoft EDGE на Surface Hub.

> [!NOTE]
>  Для удаления нового Microsoft Edge требуется сброс устройства. Дополнительные сведения приведены [в разделе Сброс и восстановление Surface Hub](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) .

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
Хорошо
> [!IMPORTANT]
>  После установки канал разработки Microsoft EDGE не будет автоматически отображаться как закрепленное приложение в меню "Пуск" Surface Hub. Вместо этого пользователи смогут найти его в разделе **Запуск**  >  **всех приложений**. Если вы используете макет меню "Пуск" по умолчанию, вы можете установить меню "Пуск" с [пакетом подготовки Microsoft Edge](https://aka.ms/HubEdge) для добавления Microsoft EDGE в качестве закрепленного приложения. Дополнительные сведения можно найти в разделе " [Отображение Microsoft Edge" в меню "Пуск" Microsoft Edge](#display-start).

> [!NOTE]
> Если доступна более новая версия Microsoft EDGE, она будет автоматически обновлена.
 
### Установка Microsoft Edge с помощью Intune
 
> [!NOTE]
> Устройство Surface Hub должно быть зарегистрировано и управляться с помощью Intune. Дополнительные сведения можно найти [в разделе Управление Surface Hub 2S с помощью Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Скачайте установщик Microsoft Edge из Microsoft](https://www.microsoft.com/edge/business/download).
    - Использовать текущую версию в [канале разработки](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выберите **Windows 64-bit**
2. [Добавьте установщик Microsoft EDGE в Microsoft Intune в качестве бизнес-приложения](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Если вы решили использовать обновление Microsoft Edge для обработки автоматических обновлений Microsoft EDGE, настройте параметр " **игнорировать версию приложения** " в области **сведений о приложении** . При переключении этого параметра на **Да**Microsoft Intune не будет применять версию приложения, установленную на устройстве Surface Hub.

 
### Установка Microsoft Edge с помощью управления мобильными устройствами

1. [Скачайте установщик Microsoft Edge из Microsoft](https://www.microsoft.com/edge/business/download).
    - Использовать текущую версию в [канале разработки](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
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

 
### Настройка политик Microsoft Edge

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
 
### <a name="display-start"></a> Отображение Microsoft EDGE в меню "Пуск" Surface HUB

После установки канал разработки Microsoft EDGE не будет автоматически отображаться как закрепленное приложение в меню "Пуск" Surface Hub. Вместо этого пользователи смогут найти его в разделе **Запуск**  >  **всех приложений**.
Если вы используете макет меню "Пуск" по умолчанию, вы можете установить меню "Пуск" с пакетом подготовки Microsoft Edge для добавления Microsoft EDGE в качестве закрепленного приложения.
Если вы хотите применить настраиваемый макет меню "Пуск", используйте следующий XML-код, чтобы добавить закрепленную плитку для Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge Dev\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Дополнительные сведения можно найти в разделе [Настройка меню Пуск Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> Новая Microsoft EDGE не поддерживает закрепленные веб-сайты и ссылки с помощью SecondaryTiles.

## Дополнительные ссылки

- [Документация по Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).

