---
title: Гибридное развертывание (Surface Hub)
description: Гибридное развертывание требует специальной обработки для настройки учетной записи устройства Microsoft Surface Hub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: гибридное развертывание, учетная запись устройства для Surface Hub, Exchange в локальной среде, Exchange в облаке
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836203"
---
# Гибридное развертывание (Surface Hub)

Гибридное развертывание требует специальной обработки для настройки учетной записи устройства Microsoft Surface Hub. Если вы используете гибридное развертывание с различными службами, часть из которых размещена в локальной среде, а часть — в Интернете, конфигурация будет зависеть от того, где размещена каждая служба. В этом разделе рассматриваются гибридные развертывания для [Exchange с локальным размещением](#exchange-on-premises), [Exchange с внешним размещением](#exchange-online), Skype для бизнеса с локальным размещением, Skype для бизнеса Online и Skype для бизнеса гибридный. Так как существует множество вариантов такого типа развертывания, невозможно представить подробные инструкции для каждого из них. Следующий процесс подойдет для многих конфигураций. Если данный процесс вам не подходит, рекомендуем использовать PowerShell (см. [Приложение относительно PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)), чтобы добиться тех же результатов для других вариантов развертывания. Затем следует использовать предоставленный сценарий PowerShell для проверки настроек Surface Hub. (См. статью [Сценарий проверки учетной записи](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)

> [!NOTE]
> В гибридной среде Exchange выполните инструкции для [локального сервера Exchange](#exchange-on-premises). Чтобы переместить объекты Exchange в Office 365, используйте командлет [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .

## Локальное развертывание Exchange

Следуйте этой процедуре, если вы используете локальное решение Exchange.

1. В ходе данной процедуры необходимо использовать средства администратора AD, чтобы добавить адрес электронной почты для локальной учетной записи домена. Она будет синхронизироваться с Office 365.

- В средстве **Active Directory — пользователи и компьютеры** щелкните правой кнопкой мыши папку или подразделение, где будут созданы учетные записи Surface Hub, и щелкните **Создать**&gt; **Пользователь**.
- Введите отображаемое имя из предыдущего командлета в поле **Полное имя** , а псевдоним — в поле **Имя входа пользователя** . Нажмите кнопку **Далее**.<p>

![Поле "Новый объект" для создания пользователя в Active Directory.](images/hybriddeployment-01a.png)

- Введите пароль этой учетной записи. Затем введите подтверждение пароля. Убедитесь, что установлен только флажок **Срок действия пароля не ограничен**.

> **Важно!** Обязательно установите флажок **Срок действия пароля не ограничен** для Skype для бизнеса на Surface Hub. Правила домена могут запрещать применение паролей без срока действия. В этом случае необходимо создать исключение для каждой учетной записи устройства Surface Hub.

![Изображение диалогового окна ввода пароля.](images/hybriddeployment-02a.png)

-   Нажмите кнопку **Готово** , чтобы создать учетную запись.

![Изображение с именем учетной записи, именем входа и паролем для нового пользователя.](images/hybriddeployment-03a.png)

2. Включите удаленный почтовый ящик.

Откройте локальную командную консоль Exchange с правами администратора и запустите этот командлет.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> Если у вас нет локальной среды Exchange для выполнения этого командлета, можно внести те же изменения непосредственно в объекте Active Directory для учетной записи.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. После создания учетной записи выполните синхронизацию службы каталогов. По завершении перейдите на страницу пользователи в центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная в предыдущих шагах, объединена в Интернет.

4. Подключитесь к Microsoft Exchange Online и установите некоторые свойства для учетной записи в Office 365.

Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Microsoft Exchange. Убедитесь, что у вас есть права для запуска соответствующих командлетов.

Дальнейшие действия будут выполняться в клиенте Office 365.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. Создайте политику Exchange ActiveSync или используйте совместимую существующую политику.

После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False. В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.

Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs. После ее создания вы можете применить ту же политику к другим учетным записям устройств.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

После того как у вас есть совместимая политика, необходимо применить ее к учетной записи устройства. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Настройте свойства Exchange.

Настройте свойства Exchange в учетной записи устройства для улучшения возможностей собраний. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Подключитесь к Azure AD.

Сначала необходимо установить модуль Azure AD для PowerShell версии 2. В приглашении PowerShell с повышенными привилегиями выполните следующую команду:

```PowerShell
Install-Module -Name AzureAD
```

Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи. Для этого можно запустить следующий командлет.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Назначьте лицензию Office 365.

У учетной записи устройства должна быть действительная лицензия Office 365 (O365), чтобы Exchange и Skype для бизнеса работали. Если у вас есть лицензия, назначьте расположение использования учетной записи устройства — это определяет, какие продукты будут доступны учетной записи.

Вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.

После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

Затем включите учетную запись устройства в [Skype для бизнеса Online](#skype-for-business-online), [Skype для бизнеса с локальным размещением](#skype-for-business-on-premises) или [Skype для бизнеса гибридный](#skype-for-business-hybrid).

### Skype для бизнеса Online

У пользователей клиента должны быть почтовые ящики Exchange (по крайней мере один почтовый ящик Exchange в клиенте является обязательным). В следующей таблице поясняется, какие планы или дополнительных услуги вам необходимы.

| Сценарий системы комнат Skype | Если у вас есть Office 365 Premium, Microsoft 365 для предприятий или автономный план 2 Skype для бизнеса, вам понадобятся: | Если у вас есть план для предприятий, вам необходимо: | Если у вас есть Skype для бизнеса Server 2015 (локальный или гибридный), вам понадобятся: |
| --- | --- | --- | --- |
| Присоединение к запланированному собранию | Автономный план 1 для Skype для бизнеса | E1, 3, 4, или 5 | Стандартная клиентская лицензия Skype для бизнеса Server |
| Запуск нерегламентированного собрания | Автономный план 2 для Skype для бизнеса | E1, 3, 4 или 5 | Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия для предприятий |
| Запуск нерегламентированного собрания и исходящие звонки на телефонные номера | Автономный план 2 Skype для бизнеса с голосовой Конференцией</br></br>**Примечание.** Выставление счетов за использование ТСОП является необязательным | E1 или E3 с помощью голосовой конференции или| Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия для предприятий |
| Присвоение комнате номера телефона и совершение или прием вызовов в комнате либо участие в конференции посредством подключения по номеру телефона | Самостоятельный план 2 Skype для бизнеса с телефонной системой и планом голосовой связи PSTN | E1 или E3 с телефонной системой и планом голосовой связи PSTN | Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия Plus |

В следующей таблице перечислены планы Office 365 и варианты Skype для бизнеса.

| План O365 | Skype для бизнеса | Телефонная система | Голосовые конференции | Планы звонков |
| --- | --- | --- | --- | --- |
| O365 бизнес базовый | Включено |  |  |  |
| O365 бизнес премиум | Включено |  |  |  |
| E1 | Включено | Дополнительно | Дополнительно | Надстройка (требуется надстройка для телефонной системы) |
| E3 | Включено | Дополнительно | Дополнительно | Надстройка (требуется надстройка для телефонной системы) |
| E5 | Включено | Включено | Включено | Дополнительно  |

1. Для начала создайте удаленную сессию PowerShell с ПК в среде Skype для бизнеса Online.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Назначьте лицензии Skype для бизнеса учетной записи Surface Hub.

 После выполнения предыдущих действий для включений учетной записи Surface Hub в Skype для бизнеса Online вам необходимо назначить лицензию устройству Surface Hub. С помощью административного портала Office 365 вы можете назначить на устройство лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3).

- Войдите в систему как администратор клиента, откройте портал администрирования O365 и щелкните приложение администратора.

- Выберите **Пользователи и группы** и щелкните **Добавление пользователей, сброс паролей и другие действия**.

- Щелкните учетную запись Surface Hub, а затем щелкните значок пера, чтобы изменить данные учетной записи.

- Щелкните **Лицензии**.

- В окне **Назначение лицензий**выберите Skype для бизнеса (план 1) или Skype для бизнеса (план 2), в зависимости от ваших требований лицензирования и голосовой связи в корпоративной среде. Если вы хотите использовать корпоративную голосовую почту на Surface Hub, вам придется использовать лицензию на план 2.

- Нажмите кнопку **Сохранить**.

> [!NOTE]
> Также можно воспользоваться модулем Microsoft Azure Active Directory для Windows PowerShell, чтобы выполнить командлеты, необходимые для назначения одной из этих лицензий, но в настоящей статье это не рассматривается.

Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т. д.) и попробуйте войти в эту учетную запись.

### Skype для бизнеса с локальным размещением

Для выполнения этого командлета необходимо подключиться к одному из клиентов Skype. Откройте Skype PowerShell и запустите:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype для бизнеса гибридный

Если ваша организация настроила [гибридное подключение между Skype для бизнеса Server и Skype для бизнеса Online](https://technet.microsoft.com/library/jj205403.aspx), рекомендации по созданию учетных записей отличаются от стандартного развертывания Surface Hub.

Surface Hub требуется учетная запись Skype типа `meetingroom`, тогда как обычный пользователь будет использовать в Skype учетную запись пользовательского типа. Если сервер Skype настроен для гибридного режима, в котором могут работать как пользователи локального сервера Skype, так и пользователи, размещенные в Office 365, при попытке создания учетной записи Surface Hub может возникнуть ряд проблем.

В гибридной среде Skype для бизнеса Server 2015 любой пользователь, который вы хотите использовать в Skype для бизнеса Online, необходимо сначала создать в локальном развертывании, чтобы создать учетную запись пользователя в доменных службах Active Directory. Затем вы можете переместить пользователя в Skype для бизнеса Online. Перемещение учетной записи пользователя из локальной сети в сеть осуществляется с помощью командлета [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Чтобы переместить объект Csmeetingroom, используйте командлет [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Для использования командлета Move-CsMeetingRoom необходимо установить [накопительный пакет обновления 2017 для 6.0.9319.281 для Skype для бизнеса server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) или [накопительный пакет обновления за Июль 2017 г. 5.0.8308.992 для Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).


## Exchange Online

Следуйте этой процедуре, если вы используете Exchange Online.

1. Создайте учетную запись почты в Office 365.

Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange. Убедитесь, что у вас есть права для запуска соответствующих командлетов.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. Настройка почтового ящика.

После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения. Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.

При изменении существующего почтового ящика ресурса:

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

При создании нового почтового ящика ресурса:

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Создайте политику Exchange ActiveSync.

После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.

Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False. Если это значение задано неправильно, службы Exchange на Surface Hub (почту, календарь и присоединение к собраниям) не будут включены.

Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs. После ее создания вы можете применить ту же политику к другим учетным записям устройств.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

После того как у вас есть совместимая политика, необходимо применить ее к учетной записи устройства. Однако политики можно применять только к учетным записям пользователей, но не почтовым ящикам ресурса. Необходимо преобразовать почтовый ящик в пользовательский тип, применить политику, а затем преобразовать его обратно в почтовый ящик. Возможно, вам также придется повторно включить его и установить пароль.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Настройте свойства Exchange.

В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. Добавьте адрес электронной почты для учетной записи локального домена.

В ходе данной процедуры необходимо использовать средства администратора AD, чтобы добавить адрес электронной почты для локальной учетной записи домена.

- В средстве **Active Directory — пользователи и компьютеры** щелкните правой кнопкой мыши папку или подразделение, где будут созданы учетные записи Surface Hub, и щелкните **Создать**&gt; **Пользователь**.
- Введите отображаемое имя из предыдущего командлета в поле **Полное имя** , а псевдоним — в поле **Имя входа пользователя** . Нажмите кнопку **Далее**.

![Поле "Новый объект" для создания пользователя в Active Directory.](images/hybriddeployment-01a.png)

- Введите пароль этой учетной записи. Затем введите подтверждение пароля. Убедитесь, что установлен только флажок **Срок действия пароля не ограничен**.

> [!IMPORTANT]
> Выбор **срока действия пароля неограничен** для Skype для бизнеса на Surface Hub. Правила домена могут запрещать применение паролей без срока действия. В этом случае необходимо создать исключение для каждой учетной записи устройства Surface Hub.

![Изображение диалогового окна ввода пароля.](images/hybriddeployment-02a.png)

- Нажмите кнопку **Готово** , чтобы создать учетную запись.

![Изображение с именем учетной записи, именем входа и паролем для нового пользователя.](images/hybriddeployment-03a.png)

6. Выполните синхронизацию каталогов.

После создания учетной записи выполните синхронизацию службы каталогов. После завершения перейдите на страницу пользователей и убедитесь, что две учетные записи, созданные ранее, объединились.

7. Подключитесь к Azure AD.

Сначала необходимо установить модуль Azure AD для PowerShell версии 2. В приглашении PowerShell с повышенными привилегиями выполните следующую команду:

```PowerShell
Install-Module -Name AzureAD
```

Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи. Вы можете выполнить этот командлет для подключения:

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Назначьте лицензию Office 365.

У учетной записи устройства должна быть действительная лицензия Office 365 (O365), чтобы Exchange и Skype для бизнеса работали. Если у вас есть лицензия, назначьте расположение использования учетной записи устройства — это определяет, какие продукты будут доступны учетной записи.

Затем вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.

После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

Затем включите учетную запись устройства в [Skype для бизнеса Online](#skype-for-business-online), [Skype для бизнеса с локальным размещением](#skype-for-business-on-premises) или [Skype для бизнеса гибридный](#skype-for-business-hybrid).

### Skype для бизнеса Online

Для включения Skype для бизнеса ваша среда должна соответствовать [необходимым требованиям для Skype для бизнеса Online](#skype-for-business-online).

1. Для начала создайте удаленную сессию PowerShell с ПК в среде Skype для бизнеса Online с ПК.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Назначение лицензии Skype для бизнеса учетной записи Surface Hub

После выполнения предыдущих действий для включений учетной записи Surface Hub в Skype для бизнеса Online вам необходимо назначить лицензию устройству Surface Hub. С помощью административного портала Office 365 вы можете назначить на устройство лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3).

- Войдите в систему как администратор клиента, откройте портал администрирования O365 и щелкните приложение администратора.

- Выберите **Пользователи и группы** и щелкните **Добавление пользователей, сброс паролей и другие действия**.

- Щелкните учетную запись Surface Hub, а затем щелкните значок пера, чтобы изменить данные учетной записи.

- Щелкните **Лицензии**.

- В окне **Назначение лицензий**выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3) в зависимости от вашей лицензии и требований к корпоративной голосовой связи. Необходимо выбрать лицензию с планом 3, если вы хотите использовать корпоративную голосовую связь на устройстве Surface Hub.

- Нажмите кнопку **Сохранить**.

> [!NOTE]
> Также можно воспользоваться модулем Microsoft Azure Active Directory для Windows PowerShell, чтобы выполнить командлеты, необходимые для назначения одной из этих лицензий, но в настоящей статье это не рассматривается.

Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т. д.) и попробуйте войти в эту учетную запись.

### Skype для бизнеса с локальным размещением

Для выполнения этого командлета необходимо подключиться к одному из клиентов Skype. Откройте Skype PowerShell и запустите:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype для бизнеса гибридный

Если ваша организация настроила [гибридное подключение между Skype для бизнеса Server и Skype для бизнеса Online](https://technet.microsoft.com/library/jj205403.aspx), рекомендации по созданию учетных записей отличаются от стандартного развертывания Surface Hub.

Surface Hub требуется учетная запись Skype типа *конференц-зал*, тогда как обычный пользователь будет использовать в Skype учетную запись *пользовательского* типа. Если сервер Skype настроен для гибридного режима, в котором могут работать как пользователи локального сервера Skype, так и пользователи, размещенные в Office 365, при попытке создания учетной записи Surface Hub может возникнуть ряд проблем.

В гибридной среде Skype для бизнеса Server 2015 любой пользователь, который вы хотите использовать в Skype для бизнеса Online, необходимо сначала создать в локальном развертывании, чтобы создать учетную запись пользователя в доменных службах Active Directory. Затем вы можете переместить пользователя в Skype для бизнеса Online. Перемещение учетной записи пользователя из локальной сети в сеть осуществляется с помощью командлета [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Чтобы переместить объект Csmeetingroom, используйте командлет [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Для использования командлета Move-CsMeetingRoom необходимо установить [накопительный пакет обновления 2017 для 6.0.9319.281 для Skype для бизнеса server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) или [накопительный пакет обновления за Июль 2017 г. 5.0.8308.992 для Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).
