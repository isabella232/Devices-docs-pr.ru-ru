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
# <span data-ttu-id="2e12f-104">Гибридное развертывание (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="2e12f-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="2e12f-105">Гибридное развертывание требует специальной обработки для настройки учетной записи устройства Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="2e12f-106">Если вы используете гибридное развертывание с различными службами, часть из которых размещена в локальной среде, а часть — в Интернете, конфигурация будет зависеть от того, где размещена каждая служба.</span><span class="sxs-lookup"><span data-stu-id="2e12f-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="2e12f-107">В этом разделе рассматриваются гибридные развертывания для [Exchange с локальным размещением](#exchange-on-premises), [Exchange с внешним размещением](#exchange-online), Skype для бизнеса с локальным размещением, Skype для бизнеса Online и Skype для бизнеса гибридный.</span><span class="sxs-lookup"><span data-stu-id="2e12f-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="2e12f-108">Так как существует множество вариантов такого типа развертывания, невозможно представить подробные инструкции для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="2e12f-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="2e12f-109">Следующий процесс подойдет для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="2e12f-109">The following process will work for many configurations.</span></span> <span data-ttu-id="2e12f-110">Если данный процесс вам не подходит, рекомендуем использовать PowerShell (см. [Приложение относительно PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)), чтобы добиться тех же результатов для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="2e12f-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="2e12f-111">Затем следует использовать предоставленный сценарий PowerShell для проверки настроек Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="2e12f-112">(См. статью [Сценарий проверки учетной записи](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span><span class="sxs-lookup"><span data-stu-id="2e12f-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-113">В гибридной среде Exchange выполните инструкции для [локального сервера Exchange](#exchange-on-premises).</span><span class="sxs-lookup"><span data-stu-id="2e12f-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="2e12f-114">Чтобы переместить объекты Exchange в Office 365, используйте командлет [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="2e12f-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="2e12f-115">Локальное развертывание Exchange</span><span class="sxs-lookup"><span data-stu-id="2e12f-115">Exchange on-premises</span></span>

<span data-ttu-id="2e12f-116">Следуйте этой процедуре, если вы используете локальное решение Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e12f-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="2e12f-117">В ходе данной процедуры необходимо использовать средства администратора AD, чтобы добавить адрес электронной почты для локальной учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="2e12f-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="2e12f-118">Она будет синхронизироваться с Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="2e12f-119">В средстве **Active Directory — пользователи и компьютеры** щелкните правой кнопкой мыши папку или подразделение, где будут созданы учетные записи Surface Hub, и щелкните **Создать**&gt; **Пользователь**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="2e12f-120">Введите отображаемое имя из предыдущего командлета в поле **Полное имя** , а псевдоним — в поле **Имя входа пользователя** .</span><span class="sxs-lookup"><span data-stu-id="2e12f-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="2e12f-121">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-121">Click **Next**.</span></span><p>

![Поле "Новый объект" для создания пользователя в Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="2e12f-123">Введите пароль этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-123">Type the password for this account.</span></span> <span data-ttu-id="2e12f-124">Затем введите подтверждение пароля.</span><span class="sxs-lookup"><span data-stu-id="2e12f-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="2e12f-125">Убедитесь, что установлен только флажок **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="2e12f-126">**Важно!** Обязательно установите флажок **Срок действия пароля не ограничен** для Skype для бизнеса на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="2e12f-127">Правила домена могут запрещать применение паролей без срока действия.</span><span class="sxs-lookup"><span data-stu-id="2e12f-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="2e12f-128">В этом случае необходимо создать исключение для каждой учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Изображение диалогового окна ввода пароля.](images/hybriddeployment-02a.png)

-   <span data-ttu-id="2e12f-130">Нажмите кнопку **Готово** , чтобы создать учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2e12f-130">Click **Finish** to create the account.</span></span>

![Изображение с именем учетной записи, именем входа и паролем для нового пользователя.](images/hybriddeployment-03a.png)

2. <span data-ttu-id="2e12f-132">Включите удаленный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="2e12f-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="2e12f-133">Откройте локальную командную консоль Exchange с правами администратора и запустите этот командлет.</span><span class="sxs-lookup"><span data-stu-id="2e12f-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="2e12f-134">Если у вас нет локальной среды Exchange для выполнения этого командлета, можно внести те же изменения непосредственно в объекте Active Directory для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="2e12f-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="2e12f-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="2e12f-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="2e12f-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="2e12f-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="2e12f-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="2e12f-138">После создания учетной записи выполните синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="2e12f-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="2e12f-139">По завершении перейдите на страницу пользователи в центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная в предыдущих шагах, объединена в Интернет.</span><span class="sxs-lookup"><span data-stu-id="2e12f-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="2e12f-140">Подключитесь к Microsoft Exchange Online и установите некоторые свойства для учетной записи в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="2e12f-141">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e12f-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="2e12f-142">Убедитесь, что у вас есть права для запуска соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="2e12f-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="2e12f-143">Дальнейшие действия будут выполняться в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="2e12f-144">Создайте политику Exchange ActiveSync или используйте совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="2e12f-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="2e12f-145">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="2e12f-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="2e12f-146">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="2e12f-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="2e12f-147">В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.</span><span class="sxs-lookup"><span data-stu-id="2e12f-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="2e12f-148">Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="2e12f-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="2e12f-149">После ее создания вы можете применить ту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="2e12f-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="2e12f-150">После того как у вас есть совместимая политика, необходимо применить ее к учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2e12f-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="2e12f-151">Настройте свойства Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e12f-151">Set Exchange properties.</span></span>

<span data-ttu-id="2e12f-152">Настройте свойства Exchange в учетной записи устройства для улучшения возможностей собраний.</span><span class="sxs-lookup"><span data-stu-id="2e12f-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="2e12f-153">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2e12f-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="2e12f-154">Подключитесь к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2e12f-154">Connect to Azure AD.</span></span>

<span data-ttu-id="2e12f-155">Сначала необходимо установить модуль Azure AD для PowerShell версии 2.</span><span class="sxs-lookup"><span data-stu-id="2e12f-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="2e12f-156">В приглашении PowerShell с повышенными привилегиями выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2e12f-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="2e12f-157">Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="2e12f-158">Для этого можно запустить следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="2e12f-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="2e12f-159">Назначьте лицензию Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="2e12f-160">У учетной записи устройства должна быть действительная лицензия Office 365 (O365), чтобы Exchange и Skype для бизнеса работали.</span><span class="sxs-lookup"><span data-stu-id="2e12f-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="2e12f-161">Если у вас есть лицензия, назначьте расположение использования учетной записи устройства — это определяет, какие продукты будут доступны учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="2e12f-162">Вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="2e12f-163">После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="2e12f-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="2e12f-164">Затем включите учетную запись устройства в [Skype для бизнеса Online](#skype-for-business-online), [Skype для бизнеса с локальным размещением](#skype-for-business-on-premises) или [Skype для бизнеса гибридный](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="2e12f-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="2e12f-165">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2e12f-165">Skype for Business Online</span></span>

<span data-ttu-id="2e12f-166">У пользователей клиента должны быть почтовые ящики Exchange (по крайней мере один почтовый ящик Exchange в клиенте является обязательным).</span><span class="sxs-lookup"><span data-stu-id="2e12f-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="2e12f-167">В следующей таблице поясняется, какие планы или дополнительных услуги вам необходимы.</span><span class="sxs-lookup"><span data-stu-id="2e12f-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="2e12f-168">Сценарий системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="2e12f-168">Skype room system scenario</span></span> | <span data-ttu-id="2e12f-169">Если у вас есть Office 365 Premium, Microsoft 365 для предприятий или автономный план 2 Skype для бизнеса, вам понадобятся:</span><span class="sxs-lookup"><span data-stu-id="2e12f-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="2e12f-170">Если у вас есть план для предприятий, вам необходимо:</span><span class="sxs-lookup"><span data-stu-id="2e12f-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="2e12f-171">Если у вас есть Skype для бизнеса Server 2015 (локальный или гибридный), вам понадобятся:</span><span class="sxs-lookup"><span data-stu-id="2e12f-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="2e12f-172">Присоединение к запланированному собранию</span><span class="sxs-lookup"><span data-stu-id="2e12f-172">Join a scheduled meeting</span></span> | <span data-ttu-id="2e12f-173">Автономный план 1 для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e12f-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="2e12f-174">E1, 3, 4, или 5</span><span class="sxs-lookup"><span data-stu-id="2e12f-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="2e12f-175">Стандартная клиентская лицензия Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e12f-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="2e12f-176">Запуск нерегламентированного собрания</span><span class="sxs-lookup"><span data-stu-id="2e12f-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="2e12f-177">Автономный план 2 для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e12f-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="2e12f-178">E1, 3, 4 или 5</span><span class="sxs-lookup"><span data-stu-id="2e12f-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="2e12f-179">Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия для предприятий</span><span class="sxs-lookup"><span data-stu-id="2e12f-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="2e12f-180">Запуск нерегламентированного собрания и исходящие звонки на телефонные номера</span><span class="sxs-lookup"><span data-stu-id="2e12f-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="2e12f-181">Автономный план 2 Skype для бизнеса с голосовой Конференцией</span><span class="sxs-lookup"><span data-stu-id="2e12f-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="2e12f-182">**Примечание.** Выставление счетов за использование ТСОП является необязательным</span><span class="sxs-lookup"><span data-stu-id="2e12f-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="2e12f-183">E1 или E3 с помощью голосовой конференции или</span><span class="sxs-lookup"><span data-stu-id="2e12f-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="2e12f-184">Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия для предприятий</span><span class="sxs-lookup"><span data-stu-id="2e12f-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="2e12f-185">Присвоение комнате номера телефона и совершение или прием вызовов в комнате либо участие в конференции посредством подключения по номеру телефона</span><span class="sxs-lookup"><span data-stu-id="2e12f-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="2e12f-186">Самостоятельный план 2 Skype для бизнеса с телефонной системой и планом голосовой связи PSTN</span><span class="sxs-lookup"><span data-stu-id="2e12f-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="2e12f-187">E1 или E3 с телефонной системой и планом голосовой связи PSTN</span><span class="sxs-lookup"><span data-stu-id="2e12f-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="2e12f-188">Стандартная клиентская лицензия Skype для бизнеса Server или клиентская лицензия Plus</span><span class="sxs-lookup"><span data-stu-id="2e12f-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="2e12f-189">В следующей таблице перечислены планы Office 365 и варианты Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2e12f-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="2e12f-190">План O365</span><span class="sxs-lookup"><span data-stu-id="2e12f-190">O365 Plan</span></span> | <span data-ttu-id="2e12f-191">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e12f-191">Skype for Business</span></span> | <span data-ttu-id="2e12f-192">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="2e12f-192">Phone System</span></span> | <span data-ttu-id="2e12f-193">Голосовые конференции</span><span class="sxs-lookup"><span data-stu-id="2e12f-193">Audio Conferencing</span></span> | <span data-ttu-id="2e12f-194">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="2e12f-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="2e12f-195">O365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="2e12f-195">O365 Business Essentials</span></span> | <span data-ttu-id="2e12f-196">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-196">Included</span></span> |  |  |  |
| <span data-ttu-id="2e12f-197">O365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="2e12f-197">O365 Business Premium</span></span> | <span data-ttu-id="2e12f-198">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-198">Included</span></span> |  |  |  |
| <span data-ttu-id="2e12f-199">E1</span><span class="sxs-lookup"><span data-stu-id="2e12f-199">E1</span></span> | <span data-ttu-id="2e12f-200">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-200">Included</span></span> | <span data-ttu-id="2e12f-201">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e12f-201">Add-on</span></span> | <span data-ttu-id="2e12f-202">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e12f-202">Add-on</span></span> | <span data-ttu-id="2e12f-203">Надстройка (требуется надстройка для телефонной системы)</span><span class="sxs-lookup"><span data-stu-id="2e12f-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="2e12f-204">E3</span><span class="sxs-lookup"><span data-stu-id="2e12f-204">E3</span></span> | <span data-ttu-id="2e12f-205">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-205">Included</span></span> | <span data-ttu-id="2e12f-206">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e12f-206">Add-on</span></span> | <span data-ttu-id="2e12f-207">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e12f-207">Add-on</span></span> | <span data-ttu-id="2e12f-208">Надстройка (требуется надстройка для телефонной системы)</span><span class="sxs-lookup"><span data-stu-id="2e12f-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="2e12f-209">E5</span><span class="sxs-lookup"><span data-stu-id="2e12f-209">E5</span></span> | <span data-ttu-id="2e12f-210">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-210">Included</span></span> | <span data-ttu-id="2e12f-211">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-211">Included</span></span> | <span data-ttu-id="2e12f-212">Включено</span><span class="sxs-lookup"><span data-stu-id="2e12f-212">Included</span></span> | <span data-ttu-id="2e12f-213">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e12f-213">Add-on</span></span>  |

1. <span data-ttu-id="2e12f-214">Для начала создайте удаленную сессию PowerShell с ПК в среде Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2e12f-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="2e12f-215">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="2e12f-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="2e12f-216">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="2e12f-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="2e12f-217">Назначьте лицензии Skype для бизнеса учетной записи Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="2e12f-218">После выполнения предыдущих действий для включений учетной записи Surface Hub в Skype для бизнеса Online вам необходимо назначить лицензию устройству Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="2e12f-219">С помощью административного портала Office 365 вы можете назначить на устройство лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="2e12f-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="2e12f-220">Войдите в систему как администратор клиента, откройте портал администрирования O365 и щелкните приложение администратора.</span><span class="sxs-lookup"><span data-stu-id="2e12f-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="2e12f-221">Выберите **Пользователи и группы** и щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="2e12f-222">Щелкните учетную запись Surface Hub, а затем щелкните значок пера, чтобы изменить данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="2e12f-223">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-223">Click **Licenses**.</span></span>

- <span data-ttu-id="2e12f-224">В окне **Назначение лицензий**выберите Skype для бизнеса (план 1) или Skype для бизнеса (план 2), в зависимости от ваших требований лицензирования и голосовой связи в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="2e12f-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="2e12f-225">Если вы хотите использовать корпоративную голосовую почту на Surface Hub, вам придется использовать лицензию на план 2.</span><span class="sxs-lookup"><span data-stu-id="2e12f-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="2e12f-226">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-227">Также можно воспользоваться модулем Microsoft Azure Active Directory для Windows PowerShell, чтобы выполнить командлеты, необходимые для назначения одной из этих лицензий, но в настоящей статье это не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="2e12f-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="2e12f-228">Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т. д.) и попробуйте войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2e12f-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="2e12f-229">Skype для бизнеса с локальным размещением</span><span class="sxs-lookup"><span data-stu-id="2e12f-229">Skype for Business on-premises</span></span>

<span data-ttu-id="2e12f-230">Для выполнения этого командлета необходимо подключиться к одному из клиентов Skype.</span><span class="sxs-lookup"><span data-stu-id="2e12f-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="2e12f-231">Откройте Skype PowerShell и запустите:</span><span class="sxs-lookup"><span data-stu-id="2e12f-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="2e12f-232">Skype для бизнеса гибридный</span><span class="sxs-lookup"><span data-stu-id="2e12f-232">Skype for Business hybrid</span></span>

<span data-ttu-id="2e12f-233">Если ваша организация настроила [гибридное подключение между Skype для бизнеса Server и Skype для бизнеса Online](https://technet.microsoft.com/library/jj205403.aspx), рекомендации по созданию учетных записей отличаются от стандартного развертывания Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="2e12f-234">Surface Hub требуется учетная запись Skype типа `meetingroom`, тогда как обычный пользователь будет использовать в Skype учетную запись пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="2e12f-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="2e12f-235">Если сервер Skype настроен для гибридного режима, в котором могут работать как пользователи локального сервера Skype, так и пользователи, размещенные в Office 365, при попытке создания учетной записи Surface Hub может возникнуть ряд проблем.</span><span class="sxs-lookup"><span data-stu-id="2e12f-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="2e12f-236">В гибридной среде Skype для бизнеса Server 2015 любой пользователь, который вы хотите использовать в Skype для бизнеса Online, необходимо сначала создать в локальном развертывании, чтобы создать учетную запись пользователя в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e12f-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2e12f-237">Затем вы можете переместить пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2e12f-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="2e12f-238">Перемещение учетной записи пользователя из локальной сети в сеть осуществляется с помощью командлета [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2e12f-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="2e12f-239">Чтобы переместить объект Csmeetingroom, используйте командлет [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="2e12f-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-240">Для использования командлета Move-CsMeetingRoom необходимо установить [накопительный пакет обновления 2017 для 6.0.9319.281 для Skype для бизнеса server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) или [накопительный пакет обновления за Июль 2017 г. 5.0.8308.992 для Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="2e12f-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="2e12f-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2e12f-241">Exchange online</span></span>

<span data-ttu-id="2e12f-242">Следуйте этой процедуре, если вы используете Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2e12f-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="2e12f-243">Создайте учетную запись почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="2e12f-244">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e12f-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="2e12f-245">Убедитесь, что у вас есть права для запуска соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="2e12f-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="2e12f-246">Настройка почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="2e12f-246">Set up a mailbox.</span></span>

<span data-ttu-id="2e12f-247">После запуска сеанса вы создадите новый почтовый ящик и добавите его как учетную запись почтового ящика помещения или поменяете параметры существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="2e12f-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="2e12f-248">Это позволит учетной записи пройти проверку подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="2e12f-249">При изменении существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="2e12f-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="2e12f-250">При создании нового почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="2e12f-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="2e12f-251">Создайте политику Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="2e12f-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="2e12f-252">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="2e12f-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="2e12f-253">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="2e12f-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="2e12f-254">Если это значение задано неправильно, службы Exchange на Surface Hub (почту, календарь и присоединение к собраниям) не будут включены.</span><span class="sxs-lookup"><span data-stu-id="2e12f-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="2e12f-255">Если вы еще не создали совместимую политику, используйте указанный ниже командлет — он создаст политику Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="2e12f-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="2e12f-256">После ее создания вы можете применить ту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="2e12f-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="2e12f-257">После того как у вас есть совместимая политика, необходимо применить ее к учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="2e12f-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="2e12f-258">Однако политики можно применять только к учетным записям пользователей, но не почтовым ящикам ресурса.</span><span class="sxs-lookup"><span data-stu-id="2e12f-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="2e12f-259">Необходимо преобразовать почтовый ящик в пользовательский тип, применить политику, а затем преобразовать его обратно в почтовый ящик. Возможно, вам также придется повторно включить его и установить пароль.</span><span class="sxs-lookup"><span data-stu-id="2e12f-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="2e12f-260">Настройте свойства Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e12f-260">Set Exchange properties.</span></span>

<span data-ttu-id="2e12f-261">В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="2e12f-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="2e12f-262">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2e12f-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="2e12f-263">Добавьте адрес электронной почты для учетной записи локального домена.</span><span class="sxs-lookup"><span data-stu-id="2e12f-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="2e12f-264">В ходе данной процедуры необходимо использовать средства администратора AD, чтобы добавить адрес электронной почты для локальной учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="2e12f-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="2e12f-265">В средстве **Active Directory — пользователи и компьютеры** щелкните правой кнопкой мыши папку или подразделение, где будут созданы учетные записи Surface Hub, и щелкните **Создать**&gt; **Пользователь**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="2e12f-266">Введите отображаемое имя из предыдущего командлета в поле **Полное имя** , а псевдоним — в поле **Имя входа пользователя** .</span><span class="sxs-lookup"><span data-stu-id="2e12f-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="2e12f-267">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-267">Click **Next**.</span></span>

![Поле "Новый объект" для создания пользователя в Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="2e12f-269">Введите пароль этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-269">Type the password for this account.</span></span> <span data-ttu-id="2e12f-270">Затем введите подтверждение пароля.</span><span class="sxs-lookup"><span data-stu-id="2e12f-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="2e12f-271">Убедитесь, что установлен только флажок **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e12f-272">Выбор **срока действия пароля неограничен** для Skype для бизнеса на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="2e12f-273">Правила домена могут запрещать применение паролей без срока действия.</span><span class="sxs-lookup"><span data-stu-id="2e12f-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="2e12f-274">В этом случае необходимо создать исключение для каждой учетной записи устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Изображение диалогового окна ввода пароля.](images/hybriddeployment-02a.png)

- <span data-ttu-id="2e12f-276">Нажмите кнопку **Готово** , чтобы создать учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2e12f-276">Click **Finish** to create the account.</span></span>

![Изображение с именем учетной записи, именем входа и паролем для нового пользователя.](images/hybriddeployment-03a.png)

6. <span data-ttu-id="2e12f-278">Выполните синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="2e12f-278">Run directory synchronization.</span></span>

<span data-ttu-id="2e12f-279">После создания учетной записи выполните синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="2e12f-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="2e12f-280">После завершения перейдите на страницу пользователей и убедитесь, что две учетные записи, созданные ранее, объединились.</span><span class="sxs-lookup"><span data-stu-id="2e12f-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="2e12f-281">Подключитесь к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2e12f-281">Connect to Azure AD.</span></span>

<span data-ttu-id="2e12f-282">Сначала необходимо установить модуль Azure AD для PowerShell версии 2.</span><span class="sxs-lookup"><span data-stu-id="2e12f-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="2e12f-283">В приглашении PowerShell с повышенными привилегиями выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2e12f-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="2e12f-284">Вам необходимо подключиться к Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="2e12f-285">Вы можете выполнить этот командлет для подключения:</span><span class="sxs-lookup"><span data-stu-id="2e12f-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="2e12f-286">Назначьте лицензию Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="2e12f-287">У учетной записи устройства должна быть действительная лицензия Office 365 (O365), чтобы Exchange и Skype для бизнеса работали.</span><span class="sxs-lookup"><span data-stu-id="2e12f-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="2e12f-288">Если у вас есть лицензия, назначьте расположение использования учетной записи устройства — это определяет, какие продукты будут доступны учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="2e12f-289">Затем вы можете использовать `Get-AzureADSubscribedSku` , чтобы получить список доступных продуктов для вашего клиента O365.</span><span class="sxs-lookup"><span data-stu-id="2e12f-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="2e12f-290">После этого укажите SKU-коды, которые необходимо назначить SkuId, переменной `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="2e12f-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="2e12f-291">Затем включите учетную запись устройства в [Skype для бизнеса Online](#skype-for-business-online), [Skype для бизнеса с локальным размещением](#skype-for-business-on-premises) или [Skype для бизнеса гибридный](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="2e12f-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="2e12f-292">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2e12f-292">Skype for Business Online</span></span>

<span data-ttu-id="2e12f-293">Для включения Skype для бизнеса ваша среда должна соответствовать [необходимым требованиям для Skype для бизнеса Online](#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="2e12f-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="2e12f-294">Для начала создайте удаленную сессию PowerShell с ПК в среде Skype для бизнеса Online с ПК.</span><span class="sxs-lookup"><span data-stu-id="2e12f-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="2e12f-295">Чтобы включить учетную запись Surface Hub в Skype для бизнеса Server, выполните этот командлет:</span><span class="sxs-lookup"><span data-stu-id="2e12f-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="2e12f-296">Если вы не знаете, какое значение использовать для параметра `RegistrarPool` в вашей среде, можно получить значение от существующего пользователя Skype для бизнеса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="2e12f-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="2e12f-297">Назначение лицензии Skype для бизнеса учетной записи Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2e12f-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="2e12f-298">После выполнения предыдущих действий для включений учетной записи Surface Hub в Skype для бизнеса Online вам необходимо назначить лицензию устройству Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="2e12f-299">С помощью административного портала Office 365 вы можете назначить на устройство лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="2e12f-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="2e12f-300">Войдите в систему как администратор клиента, откройте портал администрирования O365 и щелкните приложение администратора.</span><span class="sxs-lookup"><span data-stu-id="2e12f-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="2e12f-301">Выберите **Пользователи и группы** и щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="2e12f-302">Щелкните учетную запись Surface Hub, а затем щелкните значок пера, чтобы изменить данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="2e12f-303">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-303">Click **Licenses**.</span></span>

- <span data-ttu-id="2e12f-304">В окне **Назначение лицензий**выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3) в зависимости от вашей лицензии и требований к корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2e12f-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="2e12f-305">Необходимо выбрать лицензию с планом 3, если вы хотите использовать корпоративную голосовую связь на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="2e12f-306">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2e12f-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-307">Также можно воспользоваться модулем Microsoft Azure Active Directory для Windows PowerShell, чтобы выполнить командлеты, необходимые для назначения одной из этих лицензий, но в настоящей статье это не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="2e12f-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="2e12f-308">Для проверки запустите клиент Skype для бизнеса (для ПК, Android и т. д.) и попробуйте войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2e12f-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="2e12f-309">Skype для бизнеса с локальным размещением</span><span class="sxs-lookup"><span data-stu-id="2e12f-309">Skype for Business on-premises</span></span>

<span data-ttu-id="2e12f-310">Для выполнения этого командлета необходимо подключиться к одному из клиентов Skype.</span><span class="sxs-lookup"><span data-stu-id="2e12f-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="2e12f-311">Откройте Skype PowerShell и запустите:</span><span class="sxs-lookup"><span data-stu-id="2e12f-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="2e12f-312">Skype для бизнеса гибридный</span><span class="sxs-lookup"><span data-stu-id="2e12f-312">Skype for Business hybrid</span></span>

<span data-ttu-id="2e12f-313">Если ваша организация настроила [гибридное подключение между Skype для бизнеса Server и Skype для бизнеса Online](https://technet.microsoft.com/library/jj205403.aspx), рекомендации по созданию учетных записей отличаются от стандартного развертывания Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2e12f-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="2e12f-314">Surface Hub требуется учетная запись Skype типа *конференц-зал*, тогда как обычный пользователь будет использовать в Skype учетную запись *пользовательского* типа.</span><span class="sxs-lookup"><span data-stu-id="2e12f-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="2e12f-315">Если сервер Skype настроен для гибридного режима, в котором могут работать как пользователи локального сервера Skype, так и пользователи, размещенные в Office 365, при попытке создания учетной записи Surface Hub может возникнуть ряд проблем.</span><span class="sxs-lookup"><span data-stu-id="2e12f-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="2e12f-316">В гибридной среде Skype для бизнеса Server 2015 любой пользователь, который вы хотите использовать в Skype для бизнеса Online, необходимо сначала создать в локальном развертывании, чтобы создать учетную запись пользователя в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e12f-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2e12f-317">Затем вы можете переместить пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2e12f-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="2e12f-318">Перемещение учетной записи пользователя из локальной сети в сеть осуществляется с помощью командлета [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2e12f-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="2e12f-319">Чтобы переместить объект Csmeetingroom, используйте командлет [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="2e12f-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-320">Для использования командлета Move-CsMeetingRoom необходимо установить [накопительный пакет обновления 2017 для 6.0.9319.281 для Skype для бизнеса server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) или [накопительный пакет обновления за Июль 2017 г. 5.0.8308.992 для Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="2e12f-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
