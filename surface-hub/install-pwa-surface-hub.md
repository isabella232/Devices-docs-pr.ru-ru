---
title: Установка прогрессивных веб-приложений на Surface Hub
description: Объясняет, как администраторы могут устанавливать веб-приложения (PWA) на Surface Hub с помощью Intune или пакета подготовки.
keywords: Surface Hub, PWA, приложение
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497581"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Установка прогрессивных веб-приложений на Surface Hub

Поддержка прогрессивных веб-приложений (PWA) открывает широкий новый источник приложений, который значительно расширяет библиотеку доступных приложений, которые могут выполняться в Suface Hub.  Пользователи могут получить доступ к множеству приложений за пределами Microsoft Store запускать их непосредственно из меню "Приложение".  По сравнению с веб-страницами PWA ведут себя как собственные приложения с автономными функциями, возможностью обновления в фоновом режиме и другими уникальными функциями. Большинство веб-сайтов можно установить в качестве PWA и воспользоваться преимуществами дополнительных функций, включенных веб-разработчиками.

Администраторы могут удаленно устанавливать PWA на Устройствах Surface Hub с помощью поставщиков управления мобильными устройствами (MDM), таких как Microsoft Intune. Кроме того, можно использовать пакет подготовки. В этой статье описываются оба метода с примером кода для установки YouTube, WebEx, Zoom и Uber, а также инструкции по установке собственных PWA. Дополнительные сведения см. [в разделе "Обзор прогрессивных веб-приложения](/microsoft-edge/progressive-web-apps-chromium/)".

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

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Создание Intune конфигурации" lightbox="images/pwa-hubpwainstall.png":::

5. Приведите имя профиля, введите необязательное описание и нажмите кнопку **"Далее"**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Профиль имени" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Настройка принудительно установленной политики веб-приложения (Intune)

1. В **разделе "Параметры** >  **Компьютер** конфигурации" выберите Microsoft Edge **** и в поле поиска введите принудительно **установленную,** **выберите принудительно** установленный веб-приложения и нажмите кнопку "**Включено"**.

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="Включение принудительно установленных веб-приложений" lightbox="images/pwa-enable-force-install.png":::

2. В **разделе URL-веб-приложения** для автоматической установки, скопируйте и введите следующий фрагмент кода, чтобы установить PWA для YouTube, Webex, Zoom и Uber. Или перейдите к следующему шагу, чтобы установить другие PWA.

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="Ввод списка принудительно установленных веб-приложений" lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. Кроме того, можно создать фрагмент кода JSON из следующего синтаксиса, чтобы установить другие PWA.

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. На странице "Теги области" нажмите **кнопку "Далее** ", чтобы пропустить.

5. На странице "Назначения" в разделе " **Включенные группы**" выберите " **Добавить группы"**.

    :::image type="content" source="images/pwa-add-groups.png" alt-text="Добавление групп" lightbox="images/pwa-add-groups.png" :::

6. В **разделе "Выбор групп** для включаемого" введите имя группы, содержащей целевые устройства Surface **** Hub, нажмите кнопку "Выбрать" и нажмите кнопку **"Далее"**. Дополнительные сведения о назначении профиля конфигурации группе см. в статье "Добавление групп для [организации пользователей и устройств"](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/pwa-select-groups.png" alt-text="Выбор групп" lightbox="images/pwa-select-groups.png":::

7. Просмотрите и нажмите кнопку **"Создать"**.

    :::image type="content" source="images/pwa-create-profile.png" alt-text="Создание профиля" lightbox="images/pwa-create-profile.png" :::

8. Чтобы применить профиль конфигурации неизменяемо, выберите **устройства DevicesAll** >  и найдите целевое устройство.**** Откройте область обзора и выберите " **Синхронизация"**.

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="Синхронизация клиента" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > Чтобы завершить установку PWA, перейдите к Surface Hub и запустите Edge. Модули PWA устанавливаются и отображаются в меню  "Все приложения".

 ### <a name="troubleshooting-intune-managed-pwas"></a>Устранение неполадок Intune, управляемых PWA
 
Если вы не видите ШИМ в списке " **Все приложения":**

- Убедитесь, что Surface Hub обновления, в частности [KB5011543](https://support.microsoft.com/help/5011543) (или последующее обновление Windows обновления). Дополнительные сведения о последних Windows 10 для совместной работы обновлениях см. в Surface Hub [журнала обновлений](surface-hub-update-history.md).
- Убедитесь, что профиль конфигурации успешно применен и не конфликтует с другими параметрами. 
- Убедитесь, что профиль конфигурации предназначен для группы безопасности, которая содержит Surface Hub. 
- Не забудьте запустить Edge один раз на Surface Hub, что необходимо для успешной установки управляемых Intune PWA.

## <a name="install-pwas-via-provisioning-package"></a>Установка PWA с помощью пакета подготовки

Вы можете установить PWA, применив пакет подготовки к Surface Hub с помощью USB-накопителя. Дополнительные сведения см. в [статье "Создание пакетов подготовки"](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>начало работы подготовкой

1. На отдельном компьютере с Windows 10 или Windows 11 установите [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) из Microsoft Store.

2. В WCD создайте новый Project. Выберите **"Подготовка настольных устройств",** укажите имя проекта и нажмите кнопку **"Готово".**

3. Выберите **"Переключиться в расширенный редактор** " и нажмите **кнопку "Да** ", чтобы подтвердить.

### <a name="configure-msedgepolicy"></a>Настройка MSEdgePolicy

1. В области "Доступные настройки" в WCD выберите **\Runtime Параметры\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**

2. В области редактирования настроек введите имя приложения **MSEdgePolicy** и нажмите кнопку **"Добавить"**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Введите имя приложения в формате MSEdgePolicy" lightbox="images/pwa-add-edge-policy.png" :::

3. В области "Доступные настройки" выберите **AppName: MSEdgePolicy** , а затем в области редактирования измените **SettingType** на **"Политика** " и нажмите кнопку **"Добавить"**.

4. В области "Доступные настройки" выберите **SettingType: Policy** (Политика) и в области редактирования задайте **для AdmxFileUid** значение **MSEdgePolicy и** нажмите кнопку **"Добавить"**.

5. В области "Доступные настройки" выберите **AdmxFileUid: MSEdgePolicy** и в области редактирования задайте **MSEdgePolicy** , введя следующий код в виде одной строки текста:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Ввод кода для MSEdgePolicy" lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Настройка принудительно установленной политики веб-приложения (пакет подготовки)

1. В области доступных настроек в WCD перейдите в папку **\Runtime Параметры\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**

2. В области редактирования настроек введите Areaname как **MSEdgePolicy~Policy~microsoft_edge и** нажмите **кнопку "Добавить"**.

3. В области "Доступные настройки" выберите **AreaName: MSEdgePolicy~Policy~microsoft_edge** и в области редактирования задайте имя политики **WebAppInstallForceList** и нажмите кнопку **"Добавить"**.****

4. На панели "Доступные настройки" выберите **PolicyName: WebAppInstallForceList** и в области редактирования для **WebAppInstallForceList** введите PWA в виде [](#ppkg-code-samples) одной строки текста.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Введите код для принудительно установленной веб-приложения политики" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>Примеры кода PPKG

- YouTube PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Несколько ШИМ, включая YouTube, Webex, Zoom и Uber:

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Кроме того, можно создать фрагмент кода JSON из следующего синтаксиса, чтобы установить другие PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Экспорт пакета подготовки и применение к Surface Hub

1. В строке меню выберите " **Экспорт**" **, выберите "** Пакет подготовки" и следуйте инструкциям, чтобы создать PPKG-файл.

2. Вставьте пустой USB-накопитель флэш-памяти. Выберите расположение выходных данных, чтобы перейти к расположению пакета. Скопируйте PPKG-файл на USB-накопитель.

3. Примените пакет подготовки с помощью Параметры приложения или во время первой установки. Дополнительные сведения см. в [статье "Создание пакетов подготовки".](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

 ### <a name="troubleshooting-provisioning-package-pwas"></a>Устранение неполадок с PWA пакета подготовки
 
Если вы не видите ШИМ в списке " **Все приложения"**:

- Убедитесь, что Surface Hub обновления, в частности [KB5011543](https://support.microsoft.com/help/5011543) (или последующее обновление Windows обновления). Дополнительные сведения о последних Windows 10 для совместной работы обновлениях см. в Surface Hub [журнала обновлений](surface-hub-update-history.md).

## <a name="learn-more"></a>Подробнее

- [Справочник по WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Обзор прогрессивных веб-приложений (PWA)](/microsoft-edge/progressive-web-apps-chromium/)
