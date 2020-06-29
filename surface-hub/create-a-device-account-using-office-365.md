---
title: Создание учетной записи устройства с помощью пользовательского интерфейса (Surface Hub)
description: Если вы предпочитаете использовать графический пользовательский интерфейс, вы можете создать учетную запись для устройства Microsoft Surface Hub в Office 365 или Центре администрирования Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: Создание учетной записи устройства, Пользовательский интерфейс Office 365, центр администрирования Exchange, центр администрирования Microsoft 365, Skype для бизнеса, политика почтовых ящиков для мобильных устройств
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836744"
---
# Создание учетной записи устройства с помощью пользовательского интерфейса (Surface Hub)


Если вы предпочитаете использовать графический пользовательский интерфейс, вы можете создать учетную запись для устройства Microsoft Surface Hub в [Office 365](#create-device-acct-o365) или [Центре администрирования Exchange](#create-device-acct-eac).

## <a href="" id="create-device-acct-o365"></a>Создание учетной записи устройства с помощью Office 365


1.  [Создайте учетную запись в центре администрирования Microsoft 365](#create-device-acct-o365-admin-ctr).
2.  [Создайте политику почтовых ящиков для мобильных устройств (ActiveSync) в Центре администрирования Microsoft Exchange](#create-device-acct-o365-mbx-policy).
3.  [Завершите создание учетной записи устройства с помощью PowerShell](#create-device-acct-o365-complete-acct).
4.  [Настройте свойства учетной записи, касающиеся Exchange, с помощью PowerShell](#create-device-acct-o365-configure-exch-prop).
5.  [Активируйте учетную запись в Skype для бизнеса](#create-device-acct-o365-skype-for-business).

### <a href="" id="create-device-acct-o365-admin-ctr"></a>Создание учетной записи в центре администрирования

1.  Вход в Office 365 путем посещенияhttps://portal.office.com
2.  Введите учетные данные администратора своего клиента Office 365. Это позволит вам перейти в центр администрирования Microsoft 365.

    ![Центр администрирования Microsoft 365.](images/setupdeviceaccto365-02.png)

3. В центре администрирования перейдите к разделу **ресурсы** на левой панели, а затем щелкните **комнаты & оборудования**.

    ![Комната "комнаты & оборудования" в центре администрирования](images/room-equipment.png)

4. Нажмите кнопку **Добавить** для создания новой учетной записи помещения. Введите отображаемое и адрес электронной почты для учетной записи, а затем нажмите кнопку **Добавить**.

    ![Окно создания новой учетной записи помещения](images/room-add.png)

5. Выберите созданную учетную запись помещения из списка "Активные пользователи". В правой панели отображаются свойства учетной записи и несколько дополнительных действий. Нажмите кнопку **Сброс пароля**, чтобы изменить пароль, и снимите флажок **Обязать этого пользователя изменить пароль при первом входе**, так как изменить пароль при входе в систему на Surface Hub невозможно.

6. Щелкните **Изменить** в разделе **Назначенная лицензия**, а затем щелкните стрелку раскрывающегося меню рядом с соответствующей лицензией, чтобы развернуть сведения. Выберите расположение пользователя, в списке лицензий включите **Skype для бизнеса Online (план 2)**, а затем нажмите кнопку **Сохранить**. Лицензия может быть другая в зависимости от вашей организации (например, у вас может быть план 2 или план 3).

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Создание политики почтового ящика мобильного устройства (ActiveSync) в Центре администрирования Exchange

1.  На левой панели центра администрирования нажмите кнопку **Администратор**и выберите пункт **Exchange**.

    ![Центр администрирования, в котором отображаются активные пользователи Exchange.](images/setupdeviceaccto365-08.png)

2.  В другой вкладке браузера откроется Центр администрирования Exchange, где вы можете создать и настроить почтовый ящик для Surface Hub.

    ![Центр администрирования Exchange.](images/setupdeviceaccto365-09.png)

3.  Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**. Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи. В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.

    ![Центр администрирования Exchange — создание политики почтового ящика мобильного устройства.](images/setupdeviceaccto365-10.png)

4.  Чтобы создать новую политику почтового ящика мобильного устройства Surface Hub, нажмите кнопку **+** над списком политик. Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*). Убедитесь, что политика не требует пароля для устройств, назначенных ей — флажок **Требовать пароль** должен быть снят. Затем нажмите кнопку **Сохранить**.

    ![Изображение, на котором указана новая политика мобильного устройства.](images/setupdeviceaccto365-11.png)

5.  После создания политики почтовых ящиков для мобильных устройств вернитесь в **Центр администрирования Exchange**, где вы увидите новую политику.

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>Использование Windows PowerShell для завершения создания учетной записи устройства

Здесь необходимо завершить процесс создания учетной записи с помощью PowerShell, настроив некоторые параметры конфигурации.

Чтобы выполнить командлеты, используемые этими сценариями PowerShell, необходимы следующие компоненты из консоли PowerShell с правами администратора:

-   [Помощник по входу в Microsoft Online Services для ИТ-специалистов RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [модуль Microsoft Azure Active Directory для Windows PowerShell;](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype для бизнеса Online, модуль Windows PowerShell.](https://www.microsoft.com/download/details.aspx?id=39366)

Установка следующего модуля в PowerShell
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### Подключение к мобильным службам

1.  Запустите Windows PowerShell от имени администратора.

    ![Изображение запуска Windows PowerShell от имени администратора.](images/setupdeviceaccto365-17.png)

2.  Создайте объект учетных данных, затем создайте сеанс, который подключается к Skype для бизнеса Online, введите данные глобальной учетной записи администратора клиента, а затем нажмите кнопку **ОК**.

    ![Изображение запроса учетных данных для Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  Для подключения к Microsoft Online Services выполните команду:

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-19.png)

4.  Теперь для подключения к Skype для бизнеса Online выполните команду:

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-20.png)

5.  Наконец, для подключения к службам Exchange Online выполните команду:

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-21.png)

6.  Теперь необходимо импортировать созданные сеансы Skype для бизнеса Online и Exchange Online, чтобы импортировать команды для Exchange и Skype и использовать их локально.

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    Обратите внимание, что это может занять какое-то время.

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-22.png)

7.  После подключения к веб-службам необходимо выполнить дополнительные командлеты, чтобы настроить эту учетную запись как учетную запись устройства Surface Hub.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>Использование PowerShell для настройки свойства учетной записи Exchange

После подключения к веб-службам можно завершить настройку учетной записи устройства. Вы используете электронный адрес учетной записи устройства для:

-   изменения типа почтового ящика с обычного на почтовый ящик помещения;
-   установки пароля и включения учетной записи почтового ящика помещения;
-   изменения различных свойств Exchange;
-   отключения срока действия пароля учетной записи пользователя.

1.  Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Для сохранения значения получите его из почтового ящика:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Отобразите значение:

    ```powershell
    $strEmail
    ```

    Вы увидите правильный электронный адрес.

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-23.png)

2. Запустите следующий командлет:

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-26.png)

5.  Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell. См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>Включение учетной записи Skype для бизнеса

Включите учетную запись устройства в Skype для бизнеса.

Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:

-   Вам потребуется установить автономный план 2 или более позднюю версию Skype для бизнеса Online в плане Office 365. план должен поддерживать возможности проведения конференций;
-   Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для Surface Hub, вам понадобится Skype для бизнеса Online автономный план 3.
-   у пользователей клиента должны быть почтовые ящики Exchange.
-   Для вашей учетной записи Surface Hub требуется лицензия на автономный план 2 для Skype для бизнеса Online либо отдельная версия Skype для бизнеса Online, но для нее не требуется лицензия на Exchange Online.

1.  Начните с создания удаленного сеанса PowerShell на компьютере.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Создание учетной записи устройства с помощью Центра администрирования Exchange

>[!NOTE]
>Этот метод будет работать только в том случае, если вы синхронизируются из локальной службы каталогов Active Directory.

Вы можете создать учетную запись устройство с помощью Центра администрирования Exchange.

1.  [Создайте учетную запись и почтовый ящик в Центре администрирования Exchange](#create-device-acct-exch-admin-ctr).
2.  [Создайте политику почтовых ящиков для мобильных устройств в Центре администрирования Exchange](#create-device-acct-exch-mbx-policy).
3.  [Настройте учетную запись с помощью PowerShell](#create-device-acct-exch-powershell-conf).
4.  [Активируйте учетную запись в Skype для бизнеса](#create-device-acct-exch-skype-for-business).

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Создание учетной записи и почтового ящика в Центре администрирования Exchange

1.  Войдите в Центр администрирования Exchange, используя учетные данные администратора Exchange.
2.  Перейдите в раздел **Получатели** на левой панели.

    ![Изображения почтовых ящиков в Центре администрирования Exchange.](images/setupdeviceacctexch-01.png)

3.  Нажмите кнопку **+** над списком почтовых ящиков, чтобы создать новый, заполните поля **Отображаемое имя**, **Имя**, **Имя пользователя для входа** и нажмите кнопку **Сохранить**.

    ![Изображение создания почтового ящика.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Создание политики почтовых ящиков для мобильных устройств в Центре администрирования Exchange

>[!NOTE]
>Если вы хотите создать и назначить политику для созданной учетной записи и используете Exchange 2010, найдите соответствующие сведения о создании политики и назначении политики при использовании EMC (консоль управления Exchange).

 

1.  Откройте Центр администрирования Exchange.

    ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-03.png)

2.  Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**. Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи. В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.

    ![Изображение использования Центра администрирования Exchange для создания политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-05.png)

3.  Чтобы создать новую политику почтового ящика учетной записи мобильного устройства, нажмите кнопку **+** над списком политик. Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*). Политика не должна быть защищена паролем, поэтому убедитесь, что флажок **Требовать пароль** снят, а затем нажмите кнопку **Сохранить**.

    ![Изображение новой политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-06.png)

4.  После создания политики почтовых ящиков для мобильных устройств вернитесь в Центр администрирования Exchange, где вы увидите новую политику.

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceacctexch-07.png)

5.  Чтобы применить политику ActiveSync без PowerShell, можно сделать следующее.

    -   В Центре администрирования Exchange выберите элементы **Получатели** &gt; **Почтовые ящики**, а затем — почтовый ящик.

        ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-08.png)

    -   В области **сведений** прокрутите содержимое окна до раздела **Функции телефона и голосовой почты** и выберите команду **Просмотреть сведения**, чтобы открыть экран **Сведения о мобильном устройстве**.

        ![Изображение, на котором показаны сведения о почтовом ящике.](images/setupdeviceacctexch-09.png)

    -   Появится политика почтовых ящиков для мобильных устройств, которая назначена в текущий момент. Чтобы изменить эту политику, нажмите кнопку **Обзор**.

        ![Изображение, на котором указана назначенная политика почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-10.png)

    -   Выберите нужную политику из списка, последовательно нажмите кнопки **ОК** и **Сохранить**.

        ![Изображение, на котором показан список политик почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>Настройка учетной записи с помощью PowerShell

После подключения к веб-службам можно завершить настройку учетной записи устройства. Вы используете электронный адрес учетной записи устройства для:

-   изменения типа почтового ящика с обычного на почтовый ящик помещения;
-   изменения различных свойств Exchange;
-   отключения срока действия пароля учетной записи пользователя.

1.  Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Для сохранения значения получите его из почтового ящика:

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Покажите значение, выполнив следующую команду:

    ``` syntax
    $strEmail
    ```

    Вы увидите правильный электронный адрес.

2.  Вам нужно преобразовать учетную запись в почтовый ящик комнаты, поэтому выполните следующие действия:

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  Чтобы учетная запись устройства прошла проверку подлинности на Surface Hub, нужно включить учетную запись почтового ящика помещения и задать пароль. Тогда устройство сможет использовать учетную запись для получения данных собрания с помощью ActiveSync и входа в Skype для бизнеса.

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания. Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Теперь мы должны настроить некоторые свойства в AD. Для этого нужен псевдоним учетной записи (это часть имени участника-пользователя до "@").

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  Пользователь должен быть включен в AD для проверки подлинности на устройстве Surface Hub. Запустите следующую команду:

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell. См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>Включение учетной записи Skype для бизнеса

Включите учетную запись устройства в Skype для бизнеса.

Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:

-   Вам потребуется установить автономный план 2 или более позднюю версию Skype для бизнеса Online в плане Office 365. план должен поддерживать возможности проведения конференций;
-   Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для Surface Hub, вам понадобится Skype для бизнеса Online автономный план 3.
-   у пользователей клиента должны быть почтовые ящики Exchange.
-   Для вашей учетной записи Surface Hub требуется лицензия на автономный план 2 для Skype для бизнеса Online либо отдельная версия Skype для бизнеса Online, но для нее не требуется лицензия на Exchange Online.

1.  Начните с создания удаленного сеанса PowerShell на компьютере.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Получение пула регистратора учетных записей Surface HUB

Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





