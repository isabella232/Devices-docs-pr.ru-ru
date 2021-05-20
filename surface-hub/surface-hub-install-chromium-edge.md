---
title: Установка и настройка нового браузера Microsoft Edge на Surface Hub
description: Установка и настройка нового Microsoft Edge на Surface Hub.
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576729"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>Установка и настройка нового браузера Microsoft Edge на Surface Hub

Windows 10 для совместной работы 2020 обновление поддерживает новый Microsoft Edge на основе Chromium (версия 85 и выше) в качестве рекомендуемого браузера для Surface Hub 2S и Surface Hub (v1). В этой статье рассказывается об установке браузера с помощью одного из трех методов: пакета предварительной Microsoft Intune или сторонних поставщиков управления мобильными устройствами (MDM).

> [!IMPORTANT]
> По умолчанию Surface Hub устройства предустановлены устаревшая версия Microsoft Edge (версия 44). После установки обновления [2020](surface-hub-2020-update.md)рекомендуется перейти на новый браузер Microsoft Edge; поддержка [устаревшая версия Microsoft Edge](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) завершится 9 марта 2021 г.

> [!NOTE]
> Чтобы выйти из полноэкранного режима, свайп вниз из верхней части экрана требует двух пальцев с новым Microsoft Edge. Полноэкранное действие выхода также доступно в контексте меню, отображаемом после касания с длительным нажатием.


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>Установка Microsoft Edge с помощью пакета подготовка

1. С компьютера скачайте пакет [Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) в корневую папку USB-диска.
2. Вставьте usb-накопитель в Surface Hub.
3. С Surface Hub откройте **Параметры** и введите учетные данные администратора при запросе.
4. Перейдите к **Surface Hub** > **Управление устройствами**. В разделе **Пакеты подготовки** выберите **Добавить или удалить пакет подготовки**.
5. Выберите **Добавить пакет**.
6. Выберите пакет Microsoft Edge и выберите **Добавить**.
7. Вы увидите сводку изменений, которые применяются к пакету подготовка. Выберите **Да, добавить**.
8. Дождись завершения Microsoft Edge установки. После установки перейдите в меню Surface Hub Пуск, чтобы получить доступ к новому Microsoft Edge.              

> [!NOTE]
> Если имеется более новая версия Microsoft Edge, она будет автоматически обновляться.
 
## <a name="install-microsoft-edge-using-intune"></a>Установка Microsoft Edge с помощью Intune
 
> [!NOTE]
> Чтобы использовать этот метод установки, Surface Hub устройство должно быть зарегистрироваться и управляться с помощью Intune. Дополнительные сведения см. в [Surface Hub 2S с помощью MDM.](manage-settings-with-mdm-for-surface-hub.md)
 

1. [Скачайте Microsoft Edge установщика](https://www.microsoft.com/edge/business/download).
    - Используйте текущую версию [канала Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выберите **Windows 64-bit**
2. [Добавьте установщик Microsoft Edge в качестве бизнес-приложения](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)для Microsoft Intune.
    - Если вы решите использовать Центр обновления Microsoft Edge для обработки автоматических обновлений для Microsoft Edge, не забудьте настроить **** версию приложения **Ignore,** задав информационную области Приложения. При переходе этого параметра на **да**Microsoft Intune не будет применяться версия приложения, установленная на Surface Hub устройстве.

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>Установка Microsoft Edge с помощью сторонного поставщика MDM

1. [Скачайте Microsoft Edge установки из Microsoft](https://www.microsoft.com/edge/business/download).
    - Используйте текущую версию [канала Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(версия 85)**
    - Выберите **Windows 64-bit**
2. Этап установки Microsoft Edge в расположении, например в локальном файле (\\server\share\MicrosoftEdgeEnterpriseX64.msi). Устройство Surface Hub должно иметь разрешение на доступ к расположению.
3. Чтобы установить Microsoft Edge, используйте поставщика служб конфигурации [EnterpriseDesktopAppManagement (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) через поставщика MDM.

## <a name="configure-microsoft-edge"></a>Настройка Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>Политики Microsoft Edge по умолчанию для Surface Hub

Microsoft Edge предварительно с помощью следующих задатков политики, чтобы обеспечить оптимизированный опыт для Surface Hub.
 
> [!TIP]
> Рекомендуется сохранить значение по умолчанию для этих параметров политики.
 

| Параметр политики                                                                                                   | Рекомендуемый опыт                                                                                                                                                                                                                                               | Значение по умолчанию |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Не импортировать автоматически типики и параметры данных из устаревшая версия Microsoft Edge. Это позволяет избежать изменения профилей пользователей с общими настройками из Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Разрешить Microsoft Edge процессы в фоновом режиме даже после закрытия последнего окна браузера, что позволяет быстрее получать доступ к веб-приложениям во время сеанса.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Не позволяйте пользователям создавать новые профили в Microsoft Edge. Это упрощает возможности просмотра и подписи.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Позволяет только одному пользователю войти в Microsoft Edge. Это упрощает возможности просмотра и подписи                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Позволяет пользователям пользоваться единой Sign-On (SSO) в Microsoft Edge. Когда пользователь подписан в Surface Hub, его учетные данные могут перетекать на поддерживаемые веб-сайты, не требуя от них повторной проверки подлинности.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Предотвращает установку новых расширений в Microsoft Edge. Чтобы настроить список расширений, которые будут установлены по умолчанию, используйте [ExtensionInstallForcelist.](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Скрывает первый опыт запуска и экран всплеска, который обычно отображается при первом запуске Microsoft Edge пользователей. Поскольку Surface Hub является общим устройством, это упрощает пользовательский интерфейс.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Отключает режим InPrivate. Так как в конце сеанса уже очищаются данные просмотра, это упрощает просмотр и личные данные.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Отображает Office 365 каналов на новых страницах вкладок. При входе пользователя в Surface Hub доступ к его файлам и контенту в Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | При подписании пользователя в Surface Hub будет создан не съемный профиль с помощью его учетной записи организации. Это упрощает опыт единой Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Отключает печать в Microsoft Edge. Surface Hub не поддерживает печать.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Позволяет Microsoft Edge с помощью службы Майкрософт. Это упрощает опыт единой Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Автоматически сохраняет файлы в папку Downloads, а не запрашивает у пользователей, где сохранить файл. Это упрощает просмотр.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Развертываемые прогрессивные веб-приложения (PWAs) в настоящее время не поддерживаются в Windows 10 для совместной работы операционной системе.  Обратите внимание также, Microsoft Edge параметр [политики WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) не поддерживается Surface Hub. 

### <a name="configure-microsoft-edge-policy-settings"></a>Настройка параметров Microsoft Edge политики

Используйте [Microsoft Edge для](https://docs.microsoft.com/deployedge/microsoft-edge-policies) настройки параметров браузера в Microsoft Edge. Эти политики можно применять с помощью:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- Ваш предпочтительный поставщик управления мобильными устройствами [(MDM), который поддерживает ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm), или
- [Подготовка пакетов с использованием ADMX Ingestion в Windows Конструктор конфигурации](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### <a name="configure-microsoft-edge-updates"></a>Настройка Microsoft Edge обновлений

По умолчанию Microsoft Edge обновляется автоматически. Используйте [Microsoft Edge политики обновления](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) для настройки параметров для Центр обновления Microsoft Edge.
Обратите внимание, Surface Hub не поддерживает следующие политики Microsoft Edge обновления:

- **Allowsxs** — Surface Hub канал Microsoft Edge всегда заменяет устаревшая версия Microsoft Edge.
- **CreateDesktopShortcut** — Surface Hub не использует ярлыки рабочего стола.

> [!TIP]
>  Для работы этих функций в Microsoft Edge требуется подключение к Интернету. Убедитесь, [что необходимые URL-адреса домена](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) добавлены в список Разрешить для обеспечения связи с помощью брандмауэров и других механизмов безопасности.

## <a name="related-links"></a>Дополнительные ссылки

- [Документация по Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)

