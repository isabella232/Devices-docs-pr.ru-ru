---
title: Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub
description: В этой статье описано, как настроить учетные записи не глобального администратора для управления Surface Hub и Surface Hub 2S.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 03359a7d8ea028a8094c064c1fcb82cc9a53fe6a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576769"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub

Обновление Windows 10 для совместной работы 2020 добавляет поддержку для настройки учетных записей администраторов, не вступив в глобальный администратор, которые ограничивают разрешения на управление приложением Параметры на Surface Hub устройствах, присоединившись к домену Azure AD. Это позволяет использовать разрешения администратора только для Surface Hub и предотвращать потенциально нежелательный доступ администратора во всем домене Azure AD. Перед началом работы убедитесь, что Surface Hub присоединились к Azure AD и Автозарегистру Intune. Если нет, вам потребуется Surface Hub и выполнить первую, вне-коробку (OOBE) программу установки, выбрав вариант присоединиться к Azure AD.

## <a name="summary"></a>Сводка 

Процесс создания учетных записей не глобального администратора включает в себя следующие действия: 

1. В Microsoft Intune создайте группу безопасности, содержащую администраторов, назначенных для управления Surface Hub.
2. Получение SID группы Azure AD с помощью PowerShell.
3. Создание XML-файла, содержащего SID группы Azure AD.
4. Создайте группу безопасности, содержащую Surface Hub устройства, которые будут управляться группой безопасности не глобальных администраторов.
5. Создайте настраиваемый профиль конфигурации, нацеленный на группу безопасности, которая содержит Surface Hub устройства. 


## <a name="create-azure-ad-security-groups"></a>Создание групп безопасности Azure AD

Сначала создайте группу безопасности, содержащую учетные записи администратора. Затем создайте другую группу безопасности для Surface Hub устройств.  

### <a name="create-security-group-for-admin-accounts"></a>Создание группы безопасности для учетных записей администратора

1. Вопишитесь в Intune через [центр администрирования Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)выберите группы > группы и в соответствии с ****  >  **** типом группы выберите **Безопасность.** 
2. Введите имя группы ( например, **Surface Hub локальных администраторов),** а затем выберите **Create.** 

     ![Создание группы безопасности для администраторов концентраторов](images/sh-create-sec-group.png)

3. Откройте группу, выберите **Членов,** а затем выберите Добавить участников, чтобы ввести учетные записи администратора, которые вы хотите назначить не глобальными администраторами в Surface Hub. **** Дополнительные информацию о создании групп в Intune см. в добавлении [групп для организации пользователей и устройств.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-security-group-for-surface-hub-devices"></a>Создание группы безопасности для Surface Hub устройств

1. Повторите предыдущую процедуру, чтобы создать отдельную группу безопасности для устройств Hub; например, **Surface Hub устройства.** 

     ![Создание группы безопасности для устройств Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Получение SID группы Azure AD с помощью PowerShell

1. Запустите PowerShell с повышенными привилегиями учетной записи **(Запустите**в качестве администратора) и убедитесь, что ваша система настроена для запуска сценариев PowerShell. Чтобы узнать больше, обратитесь [к политике выполнения](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Установка Azure PowerShell модуля](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Вопишитесь в клиента Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. При подписании в клиенте запустите следующую команду. В нем будет предложено ввести "Введите ID объекта вашей группы Azure AD".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. В Intune выберите группу, созданную ранее, и скопируйте объект id, как показано на следующем рисунке. 

     ![Скопируйте id объекта группы безопасности](images/sh-objectid.png)

6. Запустите следующий командлет, чтобы получить SID группы безопасности:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Введите id объекта в командлет PowerShell, нажмите **кнопку Ввод,** а затем скопируйте SID **Группы Azure AD в** текстовый редактор. 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Создание XML-файла, содержащего SID группы Azure AD

1. Скопируйте следующее в текстовый редактор: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > Не удалять члена администратора по умолчанию из XML-файла.

2. Замените SID-держателя (начиная с S-1-12-1) на sid **azure AD Group,** а затем сохраните файл в качестве XML; например, **aad-local-admin.xml**. 

## <a name="create-custom-configuration-profile"></a>Создание настраиваемой конфигурации профиля

1. В Endpoint Manager выберите **профили конфигурации устройств**Создание  >  ****  >  **профиля**. 
2. В платформе **выберите Windows 10 и более поздней стадии.** В профиле выберите **Настраиваемый,** а затем выберите **Создать.**
3. Добавьте имя и описание, а затем выберите **Далее.**
4. В **параметрах**  >  **Конфигурация OMA-URI Параметры**выберите **Добавить**.
5. В области Добавить строку добавьте имя и в     **OMA-URI**добавьте следующую строку: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. В соответствии с типом Data выберите **Строку XML** и откройте XML-файл, созданный на предыдущем этапе. 

     ![отправка локального файла конфигурии администратора xml](images/sh-local-admin-config.png)

7. Нажмите кнопку **Сохранить**.
8. Щелкните **Выберите группы, чтобы** включить и выбрать группу [безопасности,](#create-security-group-for-surface-hub-devices) созданную ранее **(Surface Hub устройства).** Нажмите кнопку **Далее**
9. В соответствии с правилами применимости при желании добавьте правило. В противном случае **выберите Далее,** а затем выберите **Создать**.

Дополнительные данные о пользовательских профилях конфигурации с помощью строк OMA-URI см. в странице Использование настраиваемых параметров для Windows 10 устройств [в Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)


## <a name="non-global-admins-managing-surface-hub"></a>Не глобальные администраторы, управляющие Surface Hub

Теперь члены **группы Surface Hub** локальных администраторов могут войти в приложение Параметры на Surface Hub и управлять настройками.

> [!IMPORTANT]
> По умолчанию доступ глобальных администраторов к приложению Параметры удаляется (если они также не являются членами этой новой группы безопасности).
