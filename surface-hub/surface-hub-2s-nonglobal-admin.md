---
title: Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub
description: В этой статье описывается настройка учетных записей администраторов, отличных от глобальных, для управления Surface Hub и Surface Hub 2S.
keywords: Surface Hub, Surface Hub версии 1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497702"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub

Обновление Windows 10 для совместной работы 2020 г. добавляет поддержку настройки учетных записей администраторов, отличных от глобальных, которые ограничивают разрешения на управление приложением Параметры на Surface Hub устройствах, присоединенных к домену Azure AD. Это позволяет ограничить разрешения администратора только для Surface Hub и предотвратить потенциально нежелательный административный доступ во всем Azure AD домене. Прежде чем начать, убедитесь, что Surface Hub присоединен к Azure AD и Intune регистрацию. В противном случае вам потребуется сбросить Surface Hub и завершить программу установки при первом запуске (OOBE), выбрав вариант присоединения к Azure AD.

Windows 10 для совместной работы 2020 с обновлением 2 добавлена поддержка поставщика служб конфигурации [LocalUsersAndGroups](/windows/client-management/mdm/policy-csp-localusersandgroups). Это заменяет [CSP RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups), который остается доступным, но больше не рекомендуется, как описано ниже.

## <a name="summary"></a>Сводка

Процесс создания учетных записей администраторов, отличных от глобальных, состоит из следующих этапов.

1. В Microsoft Intune создайте группу безопасности, содержащую администраторов, назначенных для управления Surface Hub.
2. Получите Azure AD безопасности группы с помощью PowerShell.
3. Создайте XML-файл, содержащий Azure AD безопасности группы.
4. Создайте группу безопасности, содержащую Surface Hub устройства, которые будут управляться группой безопасности администраторов, не являющегося глобальными администраторами. 
5. Создайте настраиваемый профиль конфигурации, предназначенный для группы безопасности, которая содержит Surface Hub устройств.

## <a name="create-azure-ad-security-groups"></a>Создание Azure AD безопасности

Сначала создайте группу безопасности, содержащую учетные записи администратора. Затем создайте еще одну группу безопасности для Surface Hub устройств.  

### <a name="create-security-group-for-admin-accounts"></a>Создание группы безопасности для учетных записей администраторов

1. Войдите в Intune центра [администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), выберите **группу** **GroupsNew** >  > и в разделе "Тип группы" выберите "**Безопасность".**
2. Введите имя группы ( например, **Surface Hub локальных администраторов**) и нажмите кнопку **"Создать".**

     ![Создайте группу безопасности для администраторов Концентратора.](images/sh-create-sec-group.png)

3. Откройте группу **, выберите "** Участники" и **** выберите "Добавить участников", чтобы ввести учетные записи администратора, которые вы хотите назначить не глобальными администраторами в Surface Hub. Дополнительные сведения о создании групп в Intune см. в статье "Добавление [групп для организации пользователей и устройств"](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Создание группы безопасности для Surface Hub устройств

1. Повторите предыдущую процедуру, чтобы создать отдельную группу безопасности для центральных устройств. Например, Surface Hub **устройства.**

     ![Создайте группу безопасности для центральных устройств.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Получение Azure AD группы с помощью PowerShell

1. Запустите PowerShell с повышенными привилегиями **учетной** записи (запуск от имени администратора) и убедитесь, что система настроена для выполнения сценариев PowerShell. Дополнительные сведения см. в [разделе "О политиках выполнения"](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [Установите Azure PowerShell модуля](/powershell/azure/install-az-ps).
3. Войдите в Azure AD клиента.

    ```powershell
    Connect-AzureAD
    ```

4. Войдите в клиент, выполнив следующий командлет. Появится запрос "Введите идентификатор объекта Azure AD группы".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. В Intune выберите созданную ранее группу и скопируйте идентификатор объекта, как показано на следующем рисунке.

     ![Скопируйте идентификатор объекта группы безопасности.](images/sh-objectid.png)

6. Выполните следующий командлет, чтобы получить идентификатор безопасности группы безопасности:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. Вставьте идентификатор объекта в командлет PowerShell, нажмите клавишу **ВВОД** **и скопируйте Azure AD группы** в текстовый редактор.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Создание XML-файла, содержащего Azure AD безопасности группы

1. Скопируйте следующий код в текстовый редактор:

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. Замените идентификатор безопасности заполнителя (начиная с S-1-12-1) идентификатором безопасности группы Azure AD **** и сохраните файл в формате XML, например **aad-local-admin.xml**.

      > [!NOTE]
      > Хотя группы должны быть указаны с помощью идентификатора безопасности, если вы хотите добавить пользователей Azure напрямую, укажите их имена субъектов-пользователей (UPN) в следующем формате: `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>Создание настраиваемого профиля конфигурации

1. В Endpoint Manager выберите **профиль** **DevicesConfiguration** >  **profilesCreate** > .
2. В разделе "Платформа **" Windows 10 и более поздних версий.** В разделе "Профиль" выберите **TemplatesCustomCreate** > **** > **.**
3. Добавьте имя и описание, а затем нажмите кнопку **"Далее".**
4. В **разделе configuration settingsOMA-URI** >  **Параметры** нажмите кнопку **"Добавить"**.
5. В области "Добавить строку" добавьте имя и в     **OMA-URI** добавьте следующую строку:

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > Параметр **политики RestrictedGroups/ConfigureGroupMembership** также позволяет настраивать участников (пользователей или AAD группы) в локальную Windows 10 группу. Однако он позволяет полностью заменить существующие группы только новыми участниками. Нельзя выборочно добавлять или удалять элементы.  В обновлении 2 Windows 10 для совместной работы 2020 рекомендуется использовать параметр политики **LocalUsersandGroups** вместо параметра политики RestrictedGroups. Применение обоих параметров политики к Surface Hub не поддерживается и может привести к непредсказуемым результатам.

6. В разделе "Тип данных" выберите **String XML** и перейдите, чтобы открыть XML-файл, созданный на предыдущем шаге.

     ![отправка XML-файла конфигурации локального администратора.](images/sh-local-admin-config.png)

7. Нажмите кнопку **Сохранить**.
8. **Щелкните "Выбрать группы"**, чтобы включить и выбрать созданную ранее группу [безопасности (](#create-security-group-for-surface-hub-devices)**Surface Hub устройства).** Нажмите кнопку **Далее**
9. При необходимости в разделе "Правила применимости" добавьте правило. В противном случае **нажмите кнопку "Далее** ", а затем нажмите **кнопку "Создать"**.

Дополнительные сведения о настраиваемых профилях конфигурации, использующих строки OMA-URI, см. в статье "Использование настраиваемых параметров для Windows 10 устройств [в Intune"](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>Не глобальные администраторы, управляющие Surface Hub

Теперь участники группы **Surface Hub** локальных администраторов могут войти в приложение Параметры в Surface Hub и управлять параметрами.

> [!IMPORTANT]
> По умолчанию доступ глобальных администраторов к приложению Параметры удаляется (если только они не являются членами этой новой группы безопасности).
