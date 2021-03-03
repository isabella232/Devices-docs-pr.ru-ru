---
title: Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub 2S
description: В этой статье описывается настройка учетных записей администратора, не в том случае глобального, для управления Surface Hub 2S.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385177"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a>Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub 2S

При подстройке Surface Hub 2S к домену Azure AD можно настроить учетные записи не глобального администратора, ограничивающие разрешения на управление приложением "Параметры" на Surface Hub 2S. Это позволяет использовать разрешения администратора только для Surface Hub 2S и предотвращать потенциально нежелательный доступ администратора во всем домене Azure AD. Перед началом работы убедитесь, что surface Hub 2S присоединяется к Azure AD. Если нет, вам потребуется сбросить Surface Hub 2S и выполнить первую, из коробки (OOBE) программу установки, выбрав вариант присоединиться к Azure AD.

## <a name="summary"></a>Сводка 

Процесс создания учетных записей не глобального администратора включает в себя следующие действия: 

1. В Microsoft Intune создайте группу безопасности, содержащую администраторов, назначенных для управления Surface Hub 2S.
2. Получение SID группы Azure AD с помощью PowerShell.
3. Создание XML-файла, содержащего SID группы Azure AD.
4. Создайте группу безопасности, содержащую устройства Surface Hub 2S, которые будут управляться группой безопасности не глобальных администраторов.
5. Создайте настраиваемый профиль конфигурации, нацеленный на группу безопасности, которая содержит устройства Surface Hub 2S. 


## <a name="create-azure-ad-security-groups"></a>Создание групп безопасности Azure AD

Сначала создайте группу безопасности, содержащую учетные записи администратора. Затем создайте другую группу безопасности для устройств Surface Hub.  

### <a name="create-security-group-for-admin-accounts"></a>Создание группы безопасности для учетных записей администратора

1. Во входе в Intune с помощью **** центра администрирования [microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)выберите группу New Group > и в соответствии с типом группы  >  **** выберите **Security.** 
2. Введите имя группы ( например, локальные администраторы **Surface Hub)** и выберите **Create.** 

     ![Создание группы безопасности для администраторов концентраторов](images/sh-create-sec-group.png)

3. Откройте группу, выберите **Членов,** а затем выберите Добавить участников для ввода учетных записей администратора, которые вы хотите назначить не глобальными администраторами в Surface Hub 2S. **** Дополнительные информацию о создании групп в Intune см. в добавлении [групп для организации пользователей и устройств.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-security-group-for-surface-hub-2s-devices"></a>Создание группы безопасности для устройств Surface Hub 2S

1. Повторите предыдущую процедуру, чтобы создать отдельную группу безопасности для устройств Hub; например, **устройства Surface Hub.** 

     ![Создание группы безопасности для устройств Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Получение SID группы Azure AD с помощью PowerShell

1. Запустите PowerShell с повышенными привилегиями учетной записи **(Запустите**в качестве администратора) и убедитесь, что ваша система настроена для запуска сценариев PowerShell. Чтобы узнать больше, обратитесь [к политике выполнения](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Установка модуля Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)
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

2. Замените SID-держателя (начиная с S-1-12-1) на sid **azure AD Group,** а затем сохраните файл в качестве XML; например, **aad-local-admin.xml**. 

## <a name="create-custom-configuration-profile"></a>Создание настраиваемой конфигурации профиля

1. В Endpoint Manager выберите **профили**  >  **конфигурации устройств**  >  **Создание профиля**. 
2. Под платформой выберите **Windows 10 и более поздний.** В профиле выберите **Настраиваемый,** а затем выберите **Создать.**
3. Добавьте имя и описание, а затем выберите **Далее.**
4. В **параметрах Конфигурация**  >  **OMA-URI Параметры**выберите **Добавить**.
5. В области Добавить строку добавьте имя и в     **OMA-URI**добавьте следующую строку: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. В соответствии с типом Data выберите **Строку XML** и откройте XML-файл, созданный на предыдущем этапе. 

     ![отправка локального файла конфигурии администратора xml](images/sh-local-admin-config.png)

7. Нажмите кнопку **Сохранить**.
8. Щелкните **Выберите группы, чтобы** включить и выбрать группу [безопасности,](#create-security-group-for-surface-hub-2s-devices) созданную ранее **(устройства Surface Hub).** Нажмите кнопку **Далее**
9. В соответствии с правилами применимости при желании добавьте правило. В противном случае **выберите Далее,** а затем выберите **Создать**.

Дополнительные данные о пользовательских профилях конфигурации с помощью строк OMA-URI см. в странице Использование настраиваемой настройки для [устройств Windows 10 в Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)


## <a name="non-global-admins-managing-surface-hub-2s"></a>Не глобальные администраторы, управляющие Surface Hub 2S

Теперь члены группы **безопасности локальных** администраторов Surface Hub могут войти в приложение Параметры на Surface Hub 2S и управлять настройками.
