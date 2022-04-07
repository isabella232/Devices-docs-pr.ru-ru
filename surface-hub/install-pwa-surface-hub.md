---
title: Установка прогрессивных веб-приложения на Surface Hub
description: Объясняет, как администраторы могут устанавливать веб-приложения (PWA) на Surface Hub с помощью Intune или пакета подготовки.
keywords: Surface Hub, PWA, приложение
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: ea30f25451b0be54bd2b6eaa2552036e0d78ff27
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472756"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Установка прогрессивных веб-приложения на Surface Hub

Администраторы могут удаленно устанавливать веб-приложения [(PWA)](/microsoft-edge/progressive-web-apps-chromium/) на Устройствах Surface Hub с помощью поставщика управления мобильными устройствами (MDM), например Microsoft Intune или пакета подготовки. Модули PWA могут работать так же, как установленные собственные приложения на поддерживаемых платформах, и работать как обычные веб-сайты в других браузерах. Когда администраторы устанавливают PWA на Surface Hub, пользователи могут запускать их непосредственно из меню "Приложение". 

> [!IMPORTANT]
> Перед установкой PWA убедитесь, что Surface Hub установлен [kB5011543](https://support.microsoft.com/help/5011543) (или Windows обновления). Дополнительные сведения о последних Windows 10 для совместной работы обновлениях см. в Surface Hub [журнала обновлений](surface-hub-update-history.md). 

- [Установка PWA на Surface Hub с помощью Intune](#install-pwas-via-intune)
- [Установка PWA на Surface Hub с помощью пакета подготовки](#install-pwas-via-provisioning-package)

Пользователи также могут устанавливать PWA для использования во время сеанса Центра. По завершении сеанса ШИМ удаляются. Дополнительные сведения см. в статье [об установке,](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113) администрировании и удалении приложений в Microsoft Edge

## <a name="install-pwas-via-intune"></a>Установка ШИМ через Intune

Используйте Intune или другого поставщика MDM для установки PWA на Surface Hub. Дополнительные сведения см. в разделе " [Управление параметрами с помощью поставщика MDM"](manage-settings-with-mdm-for-surface-hub.md).

### <a name="get-started"></a>Начало работы

1. Войдите на портал Intune в Microsoft Endpoint Manager [**администрирования**](https://endpoint.microsoft.com/).
2. Перейдите **к** **профилю DevicesConfiguration** >  **PoliciesCreate** > .**** 
3. В разделе "Платформа **" выберите Windows 10 и более поздних версий**. В разделе "Тип профиля" выберите **"Шаблоны"**. В разделе "Имя шаблона" выберите **"Административные шаблоны".**
4. Нажмите **кнопку "Создать".**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Создание Intune конфигурации" :::

5. Приведите имя профиля, введите необязательное описание и нажмите кнопку **"Далее"**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Профиль имени" :::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Настройка принудительно установленной политики веб-приложения (Intune)

1. Выберите **Microsoft Edge конфигурации** и в поле поиска введите принудительно **установленную,** **выберите принудительно** установленный веб-приложения и нажмите кнопку **"Включено"**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Настройка принудительно установленных веб-приложения" :::

2. В **разделе URL-веб-приложения** для автоматической установки создайте XML-фрагмент из следующего синтаксиса или скопируйте его из [приведенного](#example-pwas) ниже примера. 

    ```
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```
    
#### <a name="example-pwas"></a>Примеры ШИМ

В этом примере устанавливаются PWA для YoutTube, Webex, Zoom и Uber.

```
    [
{ "url": "https://www.youtube.com/",       "default_launch_container": "window" },
{ "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
{ "url": "https://zoom.us/join",           "default_launch_container": "window" },
{ "url": "https://www.uber.com/",          "default_launch_container": "tab"}
]
```

3. Введите фрагмент кода, содержащий URL-адреса для приложений, которые требуется установить.
4. Введите необязательные теги области и нажмите кнопку **"Далее".**
5. Назначьте пользователей соответствующим образом.
6. Назначьте группе, содержащей устройства Surface Hub, на которые вы хотите нацелить. Дополнительные сведения см. в статье ["Добавление групп для организации пользователей и устройств"](/mem/intune/fundamentals/groups-add)
7. Просмотрите и нажмите кнопку **"Создать"**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Создание профиля" :::
    

8. При необходимости синхронизируются целевые устройства.
9. На Surface Hub запустите Edge. Модули PWA устанавливаются и отображаются в меню  "Все приложения".

## <a name="install-pwas-via-provisioning-package"></a>Установка PWA с помощью пакета подготовки

Вы можете установить PWA, применив пакет подготовки к Surface Hub с помощью USB-накопителя. Дополнительные сведения см. в [статье "Создание пакетов подготовки"](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>начало работы подготовкой

1. На отдельном компьютере с Windows 10 или Windows 11 установите [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) из Microsoft Store.
2. В WCD создайте новый Project. Выберите **"Подготовка настольных устройств",** укажите имя проекта и нажмите кнопку **"Готово".**
3. Выберите **"Переключиться в расширенный редактор** " и нажмите **кнопку "Да** ", чтобы подтвердить.

### <a name="configure-msedgepolicy"></a>Настройка MSEdgePolicy

1. В области "Доступные настройки" в WCD выберите **\Runtime Параметры\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. В области редактирования настроек введите имя приложения **MSEdgePolicy** и нажмите кнопку **"Добавить"**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Введите имя приложения в формате MSEdgePolicy" :::

3. В области "Доступные настройки" выберите **AppName: MSEdgePolicy** , а затем в области редактирования измените **SettingType** на **"Политика** " и нажмите кнопку **"Добавить"**.
4. В области "Доступные настройки" выберите **SettingType: Policy** (Политика) и в области редактирования задайте **для AdmxFileUid** значение **MSEdgePolicy и** нажмите кнопку **"Добавить"**.
5. В области "Доступные настройки" выберите **AdmxFileUid: MSEdgePolicy** и в области редактирования задайте **MSEdgePolicy** , введя следующий код в виде одной строки текста:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Ввод кода для MSEdgePolicy" :::   
   
    ```
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```
 
### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Настройка принудительно установленной политики веб-приложения (пакет подготовки)

1. В области доступных настроек в WCD перейдите в папку **\Runtime Параметры\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. В области редактирования настроек введите Areaname как **MSEdgePolicy~Policy~microsoft_edge и** нажмите **кнопку "Добавить"**.
3. В области "Доступные настройки" выберите **AreaName: MSEdgePolicy~Policy~microsoft_edge** и в области редактирования задайте имя политики **WebAppInstallForceList** и нажмите кнопку **"Добавить"**.****
4. На панели "Доступные настройки" выберите **PolicyName: WebAppInstallForceList** и в области редактирования для **WebAppInstallForceList** введите следующий код в виде одной строки текста.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Введите код для принудительно установленной веб-приложения политики" :::   

 > [!TIP]
 > В этом примере в качестве PWA устанавливается PWA. Замените URL-адрес соответствующим образом. 

```
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
```    

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Экспорт пакета подготовки и применение к Surface Hub

1. В строке меню выберите " **Экспорт**" **, выберите "** Пакет подготовки" и следуйте инструкциям, чтобы создать PPKG-файл.
2. Вставьте пустой USB-накопитель флэш-памяти. Выберите расположение выходных данных, чтобы перейти к расположению пакета. Скопируйте PPKG-файл на USB-накопитель.
3. Примените пакет подготовки с помощью Параметры приложения или во время первой установки. Дополнительные сведения см. в [статье "Создание пакетов подготовки".](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

## <a name="learn-more"></a>Подробнее

- [Справочник по WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Обзор прогрессивных веб-приложений (PWA)](/microsoft-edge/progressive-web-apps-chromium/)
