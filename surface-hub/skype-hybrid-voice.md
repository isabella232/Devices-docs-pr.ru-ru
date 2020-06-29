---
title: Развертывание в сети или гибридное развертывание с помощью среды гибридной голосовой связи Skype (Surface Hub)
description: В данном разделе описано, как включить облачную УАТС Skype для бизнеса с локальной связью с ТСОП с помощью Cloud Connector Edition или пула Skype для бизнеса2015.
keywords: гибридное развертывание, гибридная голосовая связь Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836432"
---
# Развертывание в сети или гибридное развертывание с помощью среды гибридной голосовой связи Skype (Surface Hub)

В данном разделе описано, как включить облачную УАТС Skype для бизнеса с локальной связью с телефонной сетью общего пользования (ТСОП) с помощью Cloud Connector Edition или пула Skype для бизнеса2015. В этом случае домашние пулы Skype для бизнеса и серверы Exchange располагаются в облаке, а связь устанавливается с помощью ТСОП через локальный пул со Skype для бизнеса2015 или Cloud Connector Edition. [Дополнительные сведения о различных вариантах использования облачной УАТС](https://technet.microsoft.com/library/mt612869.aspx).  

Если у вас развернута облачная УАТС Skype для бизнеса с одним из вариантов гибридной голосовой связи, выполните описанные ниже действия, чтобы включить учетную запись помещения для Surface Hub. Важно сначала создать обычную учетную запись, назначить все параметры гибридной голосовой связи и телефонные номера, а затем преобразовать эту учетную запись в учетную запись помещения. В противном случае вы не сможете назначить гибридный телефонный номер.  

>[!WARNING]
>Если создать учетную запись до настройки гибридной голосовой связи (выполнив команду Enable-CSMeetingRoom), вы не сможете настроить необходимые параметры гибридной голосовой связи. Чтобы настроить параметры гибридной голосовой связи для настроенной ранее учетной записи или изменить телефонный номер, удалите дополнительную лицензию E5 или E3 + облачная УАТС, а затем выполните описанные ниже действия, начиная с шага 3.

1. Создайте новую учетной запись пользователя для Surface Hub. В этом примере используется <strong> surfacehub2@adatum.com </strong> . Учетная запись может быть создана в локальной службе каталогов Active Directory и синхронизирована с облаком, а также создана непосредственно в облаке. 

    ![Новый объект— пользователь](images/new-user-hybrid-voice.png)

2. Установите флажок **Срок действия пароля не ограничен**. Это важно для устройств Surface Hub.

   ![Срок действия пароля не ограничен](images/new-user-password-hybrid-voice.png)

3. В Office365 добавьте лицензию **E5** или дополнительную лицензию **E3 и облачная УАТС** в учетной записи пользователя, созданной для помещения. Это необходимо для работы гибридной голосовой связи.

   ![Добавление лицензии продукта](images/product-license-hybrid-voice.png)

4. Подождите около 15 минут, пока учетная запись пользователя для помещения не появится в Skype для бизнеса Online.

5. После создания учетной записи пользователя для помещения в Skype для бизнеса Online включите ее для использования гибридной голосовой связи в удаленной оболочке PowerShell Skype для бизнеса, выполнив такой командлет:

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Проверьте поток вызовов гибридной голосовой связи, сделав пробные телефонные вызовы с устройства Surface Hub.

7. Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange, выполнив указанные ниже командлеты.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. После запуска сеанса измените учетную запись пользователя для помещения, чтобы добавить ее как **RoomMailboxAccount**, выполнив командлеты ниже. Это поможет учетной записи пройти проверку подлинности на устройстве Surface Hub.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

   Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение **False**. В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.
    
   Если вы еще не создали совместимую политику, используйте указанный ниже командлет (он создаст политику под названием Surface Hubs). После ее создания вы сможете применить эту же политику к другим учетным записям устройств.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   Имея совместимую политику, нужно применить ее к учетной записи устройства. Однако политики можно применять только к учетным записям пользователей, но не почтовых ящиков ресурса. Выполните приведенные ниже командлеты, чтобы преобразовать учетную запись почтового ящика в пользовательскую, применить политику, а затем преобразовать ее обратно в учетную запись почтового ящика. Возможно, вам также понадобится повторно включить учетную запись и установить пароль.
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md). Ниже приведены командлеты, демонстрирующие пример настройки свойств Exchange.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. Добавьте почтовый ящик в качестве устройства для собраний в Skype для бизнеса Online. Запустите следующий командлет, который включает учетную запись в качестве устройства для собрания. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    В результате выполнения этого командлета у пользователей будет отображаться вопрос, находятся ли они в конференц-зале (как показано на изображении ниже). При выборе варианта **Да** отключаются микрофон и динамик.

    ![](images/adjust-room-audio.png)


    
Теперь учетная запись помещения полностью настроена, включая гибридную голосовую связь. Если вы используете локальную версию Skype, то дополнительные атрибуты (такие как описание, расположение и т. д.) можно настроить локально. При создании комнаты в Skype Online эти параметры можно настроить в сети. 

Изображение ниже показывает, как это устройство отображается у пользователей.


![](images/select-room-hybrid-voice.png)
