---
title: Создание учетной записи устройства с помощью пользовательского интерфейса (Surface Hub 1)
description: Если вы предпочитаете использовать графический пользовательский интерфейс, вы можете создать учетную запись для устройства Microsoft Surface Hub в Office 365 или Центре администрирования Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: создание учетной записи устройства, пользовательский интерфейс Office 365, Центр администрирования Exchange, Центр администрирования Microsoft 365, Skype для бизнеса, политика почтовых ящиков мобильных устройств
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314472"
---
# <span data-ttu-id="7c3cb-104">Создание учетной записи устройства с помощью пользовательского интерфейса (Surface Hub 1)</span><span class="sxs-lookup"><span data-stu-id="7c3cb-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="7c3cb-105">На этой странице содержатся сведения об исходном Surface Hub (версия 1).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="7c3cb-106">Для Surface Hub 2S см. создание [учетной записи устройства Surface Hub 2S.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="7c3cb-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="7c3cb-107">Если вы предпочитаете использовать графический пользовательский интерфейс, вы можете создать учетную запись для устройства Microsoft Surface Hub в [Office 365](#create-device-acct-o365) или [Центре администрирования Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="7c3cb-108">Создание учетной записи устройства с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="7c3cb-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="7c3cb-109">[Создайте учетную запись в Центре администрирования Microsoft 365.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="7c3cb-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="7c3cb-110">[Создайте политику почтовых ящиков для мобильных устройств (ActiveSync) в Центре администрирования Microsoft Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="7c3cb-111">[Завершите создание учетной записи устройства с помощью PowerShell](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="7c3cb-112">[Настройте свойства учетной записи, касающиеся Exchange, с помощью PowerShell](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="7c3cb-113">[Активируйте учетную запись в Skype для бизнеса](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="7c3cb-114">Создание учетной записи в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="7c3cb-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="7c3cb-115">Во sign in to Office 365 by visiting https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="7c3cb-115">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="7c3cb-116">Введите учетные данные администратора своего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="7c3cb-117">После этого вы будете перенаться в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Центр администрирования Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="7c3cb-119">В Центре администрирования \*\*\*\* перейдите в "Ресурсы" на левой панели, а затем щелкните "Комнаты **& оборудование".**</span><span class="sxs-lookup"><span data-stu-id="7c3cb-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Параметр & помещения в Центре администрирования](images/room-equipment.png)

4. <span data-ttu-id="7c3cb-121">Нажмите кнопку **Добавить** для создания новой учетной записи помещения.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="7c3cb-122">Введите отображаемое и адрес электронной почты для учетной записи, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Окно создания новой учетной записи помещения](images/room-add.png)

5. <span data-ttu-id="7c3cb-124">Выберите созданную учетную запись помещения из списка "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="7c3cb-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="7c3cb-125">В правой панели отображаются свойства учетной записи и несколько дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="7c3cb-126">Нажмите кнопку **Сброс пароля**, чтобы изменить пароль, и снимите флажок **Обязать этого пользователя изменить пароль при первом входе**, так как изменить пароль при входе в систему на Surface Hub невозможно.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="7c3cb-127">Щелкните **Изменить** в разделе **Назначенная лицензия**, а затем щелкните стрелку раскрывающегося меню рядом с соответствующей лицензией, чтобы развернуть сведения.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="7c3cb-128">Выберите расположение пользователя, в списке лицензий включите **Skype для бизнеса Online (план 2)**, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="7c3cb-129">Лицензия может быть другая в зависимости от вашей организации (например, у вас может быть план 2 или план 3).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="7c3cb-130">Создание политики почтового ящика мобильного устройства (ActiveSync) в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="7c3cb-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="7c3cb-131">На левой панели Центра администрирования щелкните **"АДМИНИСТРАТОР",** а затем щелкните **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="7c3cb-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![Центр администрирования, где показаны активные пользователи Exchange.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="7c3cb-133">В другой вкладке браузера откроется Центр администрирования Exchange, где вы можете создать и настроить почтовый ящик для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Центр администрирования Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="7c3cb-135">Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="7c3cb-136">Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="7c3cb-137">В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Центр администрирования Exchange — создание политики почтового ящика мобильного устройства.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="7c3cb-139">Чтобы создать новую политику почтового ящика мобильного устройства Surface Hub, нажмите кнопку **+** над списком политик.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="7c3cb-140">Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="7c3cb-141">Убедитесь, что политика не требует пароля для устройств, назначенных ей — флажок **Требовать пароль** должен быть снят. Затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Изображение, на котором указана новая политика мобильного устройства.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="7c3cb-143">После создания политики почтовых ящиков для мобильных устройств вернитесь в **Центр администрирования Exchange**, где вы увидите новую политику.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="7c3cb-145">Использование Windows PowerShell для завершения создания учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="7c3cb-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="7c3cb-146">Здесь необходимо завершить процесс создания учетной записи с помощью PowerShell, настроив некоторые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="7c3cb-147">Чтобы выполнить командлеты, используемые этими сценариями PowerShell, необходимы следующие компоненты из консоли PowerShell с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="7c3cb-148">Microsoft Online Services Sign-In RTW для ИТ-специалистов</span><span class="sxs-lookup"><span data-stu-id="7c3cb-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="7c3cb-149">модуль Microsoft Azure Active Directory для Windows PowerShell;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="7c3cb-150">Skype для бизнеса Online, модуль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="7c3cb-151">Установка следующего модуля в Powershell</span><span class="sxs-lookup"><span data-stu-id="7c3cb-151">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="7c3cb-152">Подключение к мобильным службам</span><span class="sxs-lookup"><span data-stu-id="7c3cb-152">Connecting to online services</span></span>

1.  <span data-ttu-id="7c3cb-153">Запустите Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-153">Run Windows PowerShell as Administrator.</span></span>

    ![Изображение запуска Windows PowerShell от имени администратора.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="7c3cb-155">Создайте объект учетных данных, затем создайте сеанс, который подключается к Skype для бизнеса Online, введите данные глобальной учетной записи администратора клиента, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Изображение запроса учетных данных для Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="7c3cb-157">Для подключения к Microsoft Online Services выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-157">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="7c3cb-159">Теперь для подключения к Skype для бизнеса Online выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="7c3cb-161">Наконец, для подключения к службам Exchange Online выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="7c3cb-163">Теперь необходимо импортировать созданные сеансы Skype для бизнеса Online и Exchange Online, чтобы импортировать команды для Exchange и Skype и использовать их локально.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="7c3cb-164">Обратите внимание, что это может занять какое-то время.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-164">Note that this could take a while to complete.</span></span>

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="7c3cb-166">После подключения к веб-службам необходимо выполнить дополнительные командлеты, чтобы настроить эту учетную запись как учетную запись устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="7c3cb-167">Использование PowerShell для настройки свойства учетной записи Exchange</span><span class="sxs-lookup"><span data-stu-id="7c3cb-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="7c3cb-168">После подключения к веб-службам можно завершить настройку учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="7c3cb-169">Вы используете электронный адрес учетной записи устройства для:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="7c3cb-170">изменения типа почтового ящика с обычного на почтовый ящик помещения;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="7c3cb-171">установки пароля и включения учетной записи почтового ящика помещения;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="7c3cb-172">изменения различных свойств Exchange;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="7c3cb-173">отключения срока действия пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="7c3cb-174">Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="7c3cb-175">Для сохранения значения получите его из почтового ящика:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="7c3cb-176">Отобразите значение:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="7c3cb-177">Вы увидите правильный электронный адрес.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-177">You will see the correct email address.</span></span>

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="7c3cb-179">Запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="7c3cb-180">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7c3cb-181">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Изображение командлета PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="7c3cb-183">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="7c3cb-184">См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="7c3cb-185">Включение учетной записи Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c3cb-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="7c3cb-186">Включите учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="7c3cb-187">Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="7c3cb-188">В плане O365 вам потребуется автономный план 2 или более высокий план Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="7c3cb-189">план должен поддерживать возможности проведения конференций;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="7c3cb-190">Если вам Корпоративная голосовая связь (телефонии PSTN) с использованием поставщиков услуг телефонии для Surface Hub, вам потребуется автономный план 3 для Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="7c3cb-191">у пользователей клиента должны быть почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="7c3cb-192">Для учетной записи Surface Hub требуется лицензия на автономный план 2 или автономный план 3 для Skype для бизнеса Online, но лицензия Exchange Online не требуется.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="7c3cb-193">Начните с создания удаленного сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="7c3cb-194">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="7c3cb-195">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="7c3cb-196">Создание учетной записи устройства с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="7c3cb-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="7c3cb-197">Этот метод будет работать только при синхронизации из локальной службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="7c3cb-198">Вы можете создать учетную запись устройство с помощью Центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="7c3cb-199">[Создайте учетную запись и почтовый ящик в Центре администрирования Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="7c3cb-200">[Создайте политику почтовых ящиков для мобильных устройств в Центре администрирования Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="7c3cb-201">[Настройте учетную запись с помощью PowerShell](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="7c3cb-202">[Активируйте учетную запись в Skype для бизнеса](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="7c3cb-203">Создание учетной записи и почтового ящика в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="7c3cb-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="7c3cb-204">Войдите в Центр администрирования Exchange, используя учетные данные администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="7c3cb-205">Перейдите в раздел **Получатели** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Изображения почтовых ящиков в Центре администрирования Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="7c3cb-207">Нажмите кнопку **+** над списком почтовых ящиков, чтобы создать новый, заполните поля **Отображаемое имя**, **Имя**, **Имя пользователя для входа** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Изображение создания почтового ящика.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="7c3cb-209">Создание политики почтовых ящиков для мобильных устройств в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="7c3cb-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="7c3cb-210">Если вы хотите создать и назначить политику созданной учетной записи и используете Exchange 2010, наберите соответствующую информацию о создании политики и назначении политики при использовании консоли управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="7c3cb-211">Откройте Центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-211">Go to the Exchange Admin Center.</span></span>

    ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="7c3cb-213">Для создания политики почтового ящика мобильного устройства щелкните **Мобильный** на панели слева, а затем щелкните **Политики почтового ящика мобильного устройства**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="7c3cb-214">Для устройств Surface Hub необходима учетная запись с политикой почтового ящика мобильного устройства, которая не требует пароля, поэтому если у вас уже есть политика, соответствующая этому требованию, вы можете применить эту политику к данной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="7c3cb-215">В противном случае выполните следующие действия, чтобы создать новую политику, которая будет использоваться только для учетных записей устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Изображение использования Центра администрирования Exchange для создания политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="7c3cb-217">Чтобы создать новую политику почтового ящика учетной записи мобильного устройства, нажмите кнопку **+** над списком политик.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="7c3cb-218">Введите имя, которое поможет отличить эту политику от других учетных записей устройства (например, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="7c3cb-219">Политика не должна быть защищена паролем, поэтому убедитесь, что флажок **Требовать пароль** снят, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Изображение новой политики почтового ящика мобильного устройства.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="7c3cb-221">После создания политики почтовых ящиков для мобильных устройств вернитесь в Центр администрирования Exchange, где вы увидите новую политику.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Изображение с новой политикой почтового ящика мобильного устройства в Центре администрирования Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="7c3cb-223">Чтобы применить политику ActiveSync без PowerShell, можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="7c3cb-224">В Центре администрирования Exchange выберите элементы **Получатели** &gt; **Почтовые ящики**, а затем — почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Изображение Центра администрирования Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="7c3cb-226">В области **сведений** прокрутите содержимое окна до раздела **Функции телефона и голосовой почты** и выберите команду **Просмотреть сведения**, чтобы открыть экран **Сведения о мобильном устройстве**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Изображение, на котором показаны сведения о почтовом ящике.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="7c3cb-228">Появится политика почтовых ящиков для мобильных устройств, которая назначена в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="7c3cb-229">Чтобы изменить эту политику, нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Изображение, на котором указана назначенная политика почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="7c3cb-231">Выберите нужную политику из списка, последовательно нажмите кнопки **ОК** и **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Изображение, на котором показан список политик почтовых ящиков для мобильных устройств.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="7c3cb-233">Настройка учетной записи с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c3cb-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="7c3cb-234">После подключения к веб-службам можно завершить настройку учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="7c3cb-235">Вы используете электронный адрес учетной записи устройства для:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="7c3cb-236">изменения типа почтового ящика с обычного на почтовый ящик помещения;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="7c3cb-237">изменения различных свойств Exchange;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="7c3cb-238">отключения срока действия пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="7c3cb-239">Вам потребуется ввести электронный адрес учетной записи и создать переменную с этим значением:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="7c3cb-240">Для сохранения значения получите его из почтового ящика:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-240">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="7c3cb-241">Покажите значение, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-241">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="7c3cb-242">Вы увидите правильный электронный адрес.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="7c3cb-243">Необходимо преобразовать учетную запись в почтовый ящик помещения, поэтому запустите 3:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-243">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="7c3cb-244">Чтобы учетная запись устройства прошла проверку подлинности на Surface Hub, нужно включить учетную запись почтового ящика помещения и задать пароль. Тогда устройство сможет использовать учетную запись для получения данных собрания с помощью ActiveSync и входа в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="7c3cb-245">В учетной записи устройство можно настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7c3cb-246">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="7c3cb-247">Теперь мы должны настроить некоторые свойства в AD.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="7c3cb-248">Для этого нужен псевдоним учетной записи (это часть имени участника-пользователя до "@").</span><span class="sxs-lookup"><span data-stu-id="7c3cb-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="7c3cb-249">Пользователь должен быть включен в AD для проверки подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="7c3cb-250">Запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-250">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="7c3cb-251">Если вы хотите, чтобы срок действия пароля не истекал, это также можно сделать с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="7c3cb-252">См. раздел [Управление паролями](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7c3cb-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="7c3cb-253">Включение учетной записи Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c3cb-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="7c3cb-254">Включите учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="7c3cb-255">Для включения Skype для бизнеса ваша среда должна соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="7c3cb-256">В плане O365 вам потребуется автономный план 2 или более высокий план Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="7c3cb-257">план должен поддерживать возможности проведения конференций;</span><span class="sxs-lookup"><span data-stu-id="7c3cb-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="7c3cb-258">Если вам Корпоративная голосовая связь (телефонии PSTN) с помощью поставщиков услуг телефонии для Surface Hub, вам потребуется автономный план 3 для Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="7c3cb-259">у пользователей клиента должны быть почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="7c3cb-260">Для учетной записи Surface Hub требуется лицензия на автономный план 2 или автономный план 3 для Skype для бизнеса Online, но лицензия Exchange Online не требуется.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="7c3cb-261">Начните с создания удаленного сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="7c3cb-262">Извлечение пула регистратора учетных записей Surface Hub</span><span class="sxs-lookup"><span data-stu-id="7c3cb-262">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="7c3cb-263">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. <span data-ttu-id="7c3cb-264">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```