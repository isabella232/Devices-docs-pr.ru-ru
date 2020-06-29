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
# <span data-ttu-id="e90c2-104">Развертывание в сети или гибридное развертывание с помощью среды гибридной голосовой связи Skype (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="e90c2-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="e90c2-105">В данном разделе описано, как включить облачную УАТС Skype для бизнеса с локальной связью с телефонной сетью общего пользования (ТСОП) с помощью Cloud Connector Edition или пула Skype для бизнеса2015.</span><span class="sxs-lookup"><span data-stu-id="e90c2-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="e90c2-106">В этом случае</span><span class="sxs-lookup"><span data-stu-id="e90c2-106">In this option.</span></span> <span data-ttu-id="e90c2-107">домашние пулы Skype для бизнеса и серверы Exchange располагаются в облаке, а связь устанавливается с помощью ТСОП через локальный пул со Skype для бизнеса2015 или Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e90c2-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="e90c2-108">[Дополнительные сведения о различных вариантах использования облачной УАТС](https://technet.microsoft.com/library/mt612869.aspx).</span><span class="sxs-lookup"><span data-stu-id="e90c2-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="e90c2-109">Если у вас развернута облачная УАТС Skype для бизнеса с одним из вариантов гибридной голосовой связи, выполните описанные ниже действия, чтобы включить учетную запись помещения для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e90c2-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="e90c2-110">Важно сначала создать обычную учетную запись, назначить все параметры гибридной голосовой связи и телефонные номера, а затем преобразовать эту учетную запись в учетную запись помещения.</span><span class="sxs-lookup"><span data-stu-id="e90c2-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="e90c2-111">В противном случае вы не сможете назначить гибридный телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="e90c2-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="e90c2-112">Если создать учетную запись до настройки гибридной голосовой связи (выполнив команду Enable-CSMeetingRoom), вы не сможете настроить необходимые параметры гибридной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e90c2-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="e90c2-113">Чтобы настроить параметры гибридной голосовой связи для настроенной ранее учетной записи или изменить телефонный номер, удалите дополнительную лицензию E5 или E3 + облачная УАТС, а затем выполните описанные ниже действия, начиная с шага 3.</span><span class="sxs-lookup"><span data-stu-id="e90c2-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="e90c2-114">Создайте новую учетной запись пользователя для Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e90c2-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="e90c2-115">В этом примере используется <strong> surfacehub2@adatum.com </strong> .</span><span class="sxs-lookup"><span data-stu-id="e90c2-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="e90c2-116">Учетная запись может быть создана в локальной службе каталогов Active Directory и синхронизирована с облаком, а также создана непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="e90c2-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![Новый объект— пользователь](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="e90c2-118">Установите флажок **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="e90c2-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="e90c2-119">Это важно для устройств Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e90c2-119">This is important for a Surface Hub device.</span></span>

   ![Срок действия пароля не ограничен](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="e90c2-121">В Office365 добавьте лицензию **E5** или дополнительную лицензию **E3 и облачная УАТС** в учетной записи пользователя, созданной для помещения.</span><span class="sxs-lookup"><span data-stu-id="e90c2-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="e90c2-122">Это необходимо для работы гибридной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e90c2-122">This is required for Hybrid Voice to work.</span></span>

   ![Добавление лицензии продукта](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="e90c2-124">Подождите около 15 минут, пока учетная запись пользователя для помещения не появится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e90c2-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="e90c2-125">После создания учетной записи пользователя для помещения в Skype для бизнеса Online включите ее для использования гибридной голосовой связи в удаленной оболочке PowerShell Skype для бизнеса, выполнив такой командлет:</span><span class="sxs-lookup"><span data-stu-id="e90c2-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="e90c2-126">Проверьте поток вызовов гибридной голосовой связи, сделав пробные телефонные вызовы с устройства Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e90c2-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="e90c2-127">Откройте удаленный сеанс PowerShell на компьютере и подключитесь к Exchange, выполнив указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="e90c2-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="e90c2-128">После запуска сеанса измените учетную запись пользователя для помещения, чтобы добавить ее как **RoomMailboxAccount**, выполнив командлеты ниже.</span><span class="sxs-lookup"><span data-stu-id="e90c2-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="e90c2-129">Это поможет учетной записи пройти проверку подлинности на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e90c2-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="e90c2-130">После настройки почтового ящика необходимо создать новую политику Exchange ActiveSync или использовать совместимую существующую политику.</span><span class="sxs-lookup"><span data-stu-id="e90c2-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="e90c2-131">Устройства Surface Hub совместимы только с учетными записями устройств, для свойства **PasswordEnabled** которых в политике ActiveSync установлено значение **False**.</span><span class="sxs-lookup"><span data-stu-id="e90c2-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="e90c2-132">В противном случае службы Exchange (почта, календарь и собрания) на устройстве Surface Hub будут отключены.</span><span class="sxs-lookup"><span data-stu-id="e90c2-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="e90c2-133">Если вы еще не создали совместимую политику, используйте указанный ниже командлет (он создаст политику под названием Surface Hubs).</span><span class="sxs-lookup"><span data-stu-id="e90c2-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="e90c2-134">После ее создания вы сможете применить эту же политику к другим учетным записям устройств.</span><span class="sxs-lookup"><span data-stu-id="e90c2-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="e90c2-135">Имея совместимую политику, нужно применить ее к учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="e90c2-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="e90c2-136">Однако политики можно применять только к учетным записям пользователей, но не почтовых ящиков ресурса.</span><span class="sxs-lookup"><span data-stu-id="e90c2-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="e90c2-137">Выполните приведенные ниже командлеты, чтобы преобразовать учетную запись почтового ящика в пользовательскую, применить политику, а затем преобразовать ее обратно в учетную запись почтового ящика. Возможно, вам также понадобится повторно включить учетную запись и установить пароль.</span><span class="sxs-lookup"><span data-stu-id="e90c2-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="e90c2-138">В учетной записи устройства необходимо настроить различные свойства Exchange, чтобы расширить возможности собрания.</span><span class="sxs-lookup"><span data-stu-id="e90c2-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="e90c2-139">Свойства, которые можно настроить, см. в разделе [Свойства Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="e90c2-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="e90c2-140">Ниже приведены командлеты, демонстрирующие пример настройки свойств Exchange.</span><span class="sxs-lookup"><span data-stu-id="e90c2-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="e90c2-141">Добавьте почтовый ящик в качестве устройства для собраний в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e90c2-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="e90c2-142">Запустите следующий командлет, который включает учетную запись в качестве устройства для собрания.</span><span class="sxs-lookup"><span data-stu-id="e90c2-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="e90c2-143">В результате выполнения этого командлета у пользователей будет отображаться вопрос, находятся ли они в конференц-зале (как показано на изображении ниже).</span><span class="sxs-lookup"><span data-stu-id="e90c2-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="e90c2-144">При выборе варианта **Да** отключаются микрофон и динамик.</span><span class="sxs-lookup"><span data-stu-id="e90c2-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="e90c2-145">Теперь учетная запись помещения полностью настроена, включая гибридную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="e90c2-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="e90c2-146">Если вы используете локальную версию Skype, то дополнительные атрибуты (такие как описание, расположение и т. д.) можно настроить локально.</span><span class="sxs-lookup"><span data-stu-id="e90c2-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="e90c2-147">При создании комнаты в Skype Online эти параметры можно настроить в сети.</span><span class="sxs-lookup"><span data-stu-id="e90c2-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="e90c2-148">Изображение ниже показывает, как это устройство отображается у пользователей.</span><span class="sxs-lookup"><span data-stu-id="e90c2-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
