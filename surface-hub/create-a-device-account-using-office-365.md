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
# <span data-ttu-id="2c5ef-104">Создание учетной записи устройства с помощью пользовательского интерфейса (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="2c5ef-104">Create a device account using UI (Surface Hub)</span></span>


<span data-ttu-id="2c5ef-105">Если вы предпочитаете использовать графический пользовательский интерфейс, вы можете создать учетную запись для устройства Microsoft Surface Hub в [Office 365](#create-device-acct-o365) или [Центре администрирования Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-105">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="2c5ef-106">Создание учетной записи устройства с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="2c5ef-106">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="2c5ef-107">[Создайте учетную запись в центре администрирования Microsoft 365](#create-device-acct-o365-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-107">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="2c5ef-108">[Создайте политику почтовых ящиков для мобильных устройств (ActiveSync) в Центре администрирования Microsoft Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-108">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="2c5ef-109">[Завершите создание учетной записи устройства с помощью PowerShell](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-109">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="2c5ef-110">[Настройте свойства учетной записи, касающиеся Exchange, с помощью PowerShell](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-110">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="2c5ef-111">[Активируйте учетную запись в Skype для бизнеса](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-111">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="2c5ef-112">Создание учетной записи в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="2c5ef-112">Create the account in the admin center</span></span>

1.  <span data-ttu-id="2c5ef-113">Вход в Office 365 путем посещенияhttps://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="2c5ef-113">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="2c5ef-114">Введите учетные данные администратора своего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-114">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="2c5ef-115">Это позволит вам перейти в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-115">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Центр администрирования Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="2c5ef-117">В центре администрирования перейдите к разделу **ресурсы** на левой панели, а затем щелкните **комнаты & оборудования**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-117">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Комната "комнаты & оборудования" в центре администрирования](images/room-equipment.png)

4. <span data-ttu-id="2c5ef-119">Нажмите кнопку **Добавить** для создания новой учетной записи помещения.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-119">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="2c5ef-120">Введите отображаемое и адрес электронной почты для учетной записи, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-120">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Окно создания новой учетной записи помещения](images/room-add.png)

5. <span data-ttu-id="2c5ef-122">Выберите созданную учетную запись помещения из списка "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="2c5ef-122">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="2c5ef-123">В правой панели отображаются свойства учетной записи и несколько дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-123">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="2c5ef-124">Нажмите кнопку **Сброс пароля**, чтобы изменить пароль, и снимите флажок **Обязать этого пользователя изменить пароль при первом входе**, так как изменить пароль при входе в систему на Surface Hub невозможно.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-124">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="2c5ef-125">Щелкните **Изменить** в разделе **Назначенная лицензия**, а затем щелкните стрелку раскрывающегося меню рядом с соответствующей лицензией, чтобы развернуть сведения.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-125">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="2c5ef-126">Выберите расположение пользователя, в списке лицензий включите **Skype для бизнеса Online (план 2)**, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-126">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="2c5ef-127">Лицензия может быть другая в зависимости от вашей организации (например, у вас может быть план 2 или план 3).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-127">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="2c5ef-128">Создание политики почтового ящика мобильного устройства (ActiveSync) в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="2c5ef-128">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="2c5ef-129">На левой панели центра администрирования нажмите кнопку **Администратор**и выберите пункт **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-129">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![Центр администрирования, в котором отображаются активные пользователи Exchange.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="2c5ef-131">В другой вкладке браузера откроется Центр администрирования Exchange, где вы можете создать и настроить почтовый ящик для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-131">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Центр администрирования Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="2c5ef-133">Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-133">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="2c5ef-134">Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-134">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="2c5ef-135">В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-135">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Центр администрирования Exchange — создание политики почтового ящика мобильного устройства.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="2c5ef-137">Чтобы создать новую политику почтового ящика мобильного устройства Surface Hub, нажмите кнопку **+** над списком политик.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-137">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="2c5ef-138">Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-138">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="2c5ef-139">Убедитесь, что политика не требует пароля для устройств, назначенных ей — флажок **Требовать пароль** должен быть снят. Затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-139">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Изображение, на котором указана новая политика мобильного устройства.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="2c5ef-141">После создания политики почтовых ящиков для мобильных устройств вернитесь в **Центр администрирования Exchange**, где вы увидите новую политику.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-141">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="2c5ef-143">Использование Windows PowerShell для завершения создания учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="2c5ef-143">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="2c5ef-144">Здесь необходимо завершить процесс создания учетной записи с помощью PowerShell, настроив некоторые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-144">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="2c5ef-145">Чтобы выполнить командлеты, используемые этими сценариями PowerShell, необходимы следующие компоненты из консоли PowerShell с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-145">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="2c5ef-146">Помощник по входу в Microsoft Online Services для ИТ-специалистов RTW</span><span class="sxs-lookup"><span data-stu-id="2c5ef-146">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="2c5ef-147">модуль Microsoft Azure Active Directory для Windows PowerShell;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-147">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="2c5ef-148">Skype для бизнеса Online, модуль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-148">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="2c5ef-149">Установка следующего модуля в PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c5ef-149">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="2c5ef-150">Подключение к мобильным службам</span><span class="sxs-lookup"><span data-stu-id="2c5ef-150">Connecting to online services</span></span>

1.  <span data-ttu-id="2c5ef-151">Запустите Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-151">Run Windows PowerShell as Administrator.</span></span>

    ![Изображение запуска Windows PowerShell от имени администратора.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="2c5ef-153">Создайте объект учетных данных, затем создайте сеанс, который подключается к Skype для бизнеса Online, введите данные глобальной учетной записи администратора клиента, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-153">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Изображение запроса учетных данных для Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="2c5ef-155">Для подключения к Microsoft Online Services выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-155">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="2c5ef-157">Теперь для подключения к Skype для бизнеса Online выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-157">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="2c5ef-159">Наконец, для подключения к службам Exchange Online выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-159">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="2c5ef-161">Теперь необходимо импортировать созданные сеансы Skype для бизнеса Online и Exchange Online, чтобы импортировать команды для Exchange и Skype и использовать их локально.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-161">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="2c5ef-162">Обратите внимание, что это может занять какое-то время.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-162">Note that this could take a while to complete.</span></span>

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="2c5ef-164">После подключения к веб-службам необходимо выполнить дополнительные командлеты, чтобы настроить эту учетную запись как учетную запись устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-164">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="2c5ef-165">Использование PowerShell для настройки свойства учетной записи Exchange</span><span class="sxs-lookup"><span data-stu-id="2c5ef-165">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="2c5ef-166">После подключения к веб-службам можно завершить настройку учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-166">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="2c5ef-167">Вы используете электронный адрес учетной записи устройства для:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-167">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="2c5ef-168">изменения типа почтового ящика с обычного на почтовый ящик помещения;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-168">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="2c5ef-169">установки пароля и включения учетной записи почтового ящика помещения;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-169">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="2c5ef-170">изменения различных свойств Exchange;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-170">Change various Exchange properties</span></span>
-   <span data-ttu-id="2c5ef-171">отключения срока действия пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-171">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="2c5ef-172">Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-172">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="2c5ef-173">Для сохранения значения получите его из почтового ящика:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-173">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="2c5ef-174">Отобразите значение:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-174">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="2c5ef-175">Вы увидите правильный электронный адрес.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-175">You will see the correct email address.</span></span>

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="2c5ef-177">Запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-177">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="2c5ef-178">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-178">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="2c5ef-179">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-179">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="2c5ef-181">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-181">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="2c5ef-182">См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-182">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="2c5ef-183">Включение учетной записи Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2c5ef-183">Enable the account with Skype for Business</span></span>

<span data-ttu-id="2c5ef-184">Включите учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-184">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="2c5ef-185">Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-185">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="2c5ef-186">Вам потребуется установить автономный план 2 или более позднюю версию Skype для бизнеса Online в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-186">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="2c5ef-187">план должен поддерживать возможности проведения конференций;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-187">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="2c5ef-188">Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для Surface Hub, вам понадобится Skype для бизнеса Online автономный план 3.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-188">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="2c5ef-189">у пользователей клиента должны быть почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-189">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="2c5ef-190">Для вашей учетной записи Surface Hub требуется лицензия на автономный план 2 для Skype для бизнеса Online либо отдельная версия Skype для бизнеса Online, но для нее не требуется лицензия на Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-190">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="2c5ef-191">Начните с создания удаленного сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-191">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="2c5ef-192">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-192">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="2c5ef-193">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-193">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="2c5ef-194">Создание учетной записи устройства с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="2c5ef-194">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="2c5ef-195">Этот метод будет работать только в том случае, если вы синхронизируются из локальной службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-195">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="2c5ef-196">Вы можете создать учетную запись устройство с помощью Центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-196">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="2c5ef-197">[Создайте учетную запись и почтовый ящик в Центре администрирования Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-197">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="2c5ef-198">[Создайте политику почтовых ящиков для мобильных устройств в Центре администрирования Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-198">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="2c5ef-199">[Настройте учетную запись с помощью PowerShell](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-199">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="2c5ef-200">[Активируйте учетную запись в Skype для бизнеса](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-200">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="2c5ef-201">Создание учетной записи и почтового ящика в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="2c5ef-201">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="2c5ef-202">Войдите в Центр администрирования Exchange, используя учетные данные администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-202">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="2c5ef-203">Перейдите в раздел **Получатели** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-203">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Изображения почтовых ящиков в Центре администрирования Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="2c5ef-205">Нажмите кнопку **+** над списком почтовых ящиков, чтобы создать новый, заполните поля **Отображаемое имя**, **Имя**, **Имя пользователя для входа** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-205">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Изображение создания почтового ящика.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="2c5ef-207">Создание политики почтовых ящиков для мобильных устройств в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="2c5ef-207">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="2c5ef-208">Если вы хотите создать и назначить политику для созданной учетной записи и используете Exchange 2010, найдите соответствующие сведения о создании политики и назначении политики при использовании EMC (консоль управления Exchange).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-208">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="2c5ef-209">Откройте Центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-209">Go to the Exchange Admin Center.</span></span>

    ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="2c5ef-211">Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-211">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="2c5ef-212">Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-212">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="2c5ef-213">В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-213">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Изображение использования Центра администрирования Exchange для создания политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="2c5ef-215">Чтобы создать новую политику почтового ящика учетной записи мобильного устройства, нажмите кнопку **+** над списком политик.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-215">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="2c5ef-216">Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-216">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="2c5ef-217">Политика не должна быть защищена паролем, поэтому убедитесь, что флажок **Требовать пароль** снят, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-217">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Изображение новой политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="2c5ef-219">После создания политики почтовых ящиков для мобильных устройств вернитесь в Центр администрирования Exchange, где вы увидите новую политику.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-219">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="2c5ef-221">Чтобы применить политику ActiveSync без PowerShell, можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-221">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="2c5ef-222">В Центре администрирования Exchange выберите элементы **Получатели** &gt; **Почтовые ящики**, а затем — почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-222">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="2c5ef-224">В области **сведений** прокрутите содержимое окна до раздела **Функции телефона и голосовой почты** и выберите команду **Просмотреть сведения**, чтобы открыть экран **Сведения о мобильном устройстве**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-224">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Изображение, на котором показаны сведения о почтовом ящике.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="2c5ef-226">Появится политика почтовых ящиков для мобильных устройств, которая назначена в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-226">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="2c5ef-227">Чтобы изменить эту политику, нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-227">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Изображение, на котором указана назначенная политика почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="2c5ef-229">Выберите нужную политику из списка, последовательно нажмите кнопки **ОК** и **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-229">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Изображение, на котором показан список политик почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="2c5ef-231">Настройка учетной записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c5ef-231">Use PowerShell to configure the account</span></span>

<span data-ttu-id="2c5ef-232">После подключения к веб-службам можно завершить настройку учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-232">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="2c5ef-233">Вы используете электронный адрес учетной записи устройства для:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-233">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="2c5ef-234">изменения типа почтового ящика с обычного на почтовый ящик помещения;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-234">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="2c5ef-235">изменения различных свойств Exchange;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-235">Change various Exchange properties</span></span>
-   <span data-ttu-id="2c5ef-236">отключения срока действия пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-236">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="2c5ef-237">Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-237">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="2c5ef-238">Для сохранения значения получите его из почтового ящика:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-238">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="2c5ef-239">Покажите значение, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-239">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="2c5ef-240">Вы увидите правильный электронный адрес.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-240">You will see the correct email address.</span></span>

2.  <span data-ttu-id="2c5ef-241">Вам нужно преобразовать учетную запись в почтовый ящик комнаты, поэтому выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-241">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="2c5ef-242">Чтобы учетная запись устройства прошла проверку подлинности на Surface Hub, нужно включить учетную запись почтового ящика помещения и задать пароль. Тогда устройство сможет использовать учетную запись для получения данных собрания с помощью ActiveSync и входа в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-242">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="2c5ef-243">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-243">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="2c5ef-244">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-244">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="2c5ef-245">Теперь мы должны настроить некоторые свойства в AD.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-245">Now we have to set some properties in AD.</span></span> <span data-ttu-id="2c5ef-246">Для этого нужен псевдоним учетной записи (это часть имени участника-пользователя до "@").</span><span class="sxs-lookup"><span data-stu-id="2c5ef-246">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="2c5ef-247">Пользователь должен быть включен в AD для проверки подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-247">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="2c5ef-248">Запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-248">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="2c5ef-249">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-249">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="2c5ef-250">См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2c5ef-250">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="2c5ef-251">Включение учетной записи Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2c5ef-251">Enable the account with Skype for Business</span></span>

<span data-ttu-id="2c5ef-252">Включите учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-252">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="2c5ef-253">Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-253">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="2c5ef-254">Вам потребуется установить автономный план 2 или более позднюю версию Skype для бизнеса Online в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-254">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="2c5ef-255">план должен поддерживать возможности проведения конференций;</span><span class="sxs-lookup"><span data-stu-id="2c5ef-255">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="2c5ef-256">Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для Surface Hub, вам понадобится Skype для бизнеса Online автономный план 3.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-256">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="2c5ef-257">у пользователей клиента должны быть почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-257">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="2c5ef-258">Для вашей учетной записи Surface Hub требуется лицензия на автономный план 2 для Skype для бизнеса Online либо отдельная версия Skype для бизнеса Online, но для нее не требуется лицензия на Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-258">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="2c5ef-259">Начните с создания удаленного сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2c5ef-259">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="2c5ef-260">Получение пула регистратора учетных записей Surface HUB</span><span class="sxs-lookup"><span data-stu-id="2c5ef-260">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="2c5ef-261">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-261">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. <span data-ttu-id="2c5ef-262">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="2c5ef-262">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





