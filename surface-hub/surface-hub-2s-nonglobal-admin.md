---
title: Настройка учетных записей неглобальных администраторов на Surface Hub 2S
description: В этой статье описано, как настроить учетные записи неглобальных администраторов для управления Surface Hub 2.
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
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196828"
---
# <span data-ttu-id="cfaa7-104">Настройка учетных записей неглобальных администраторов на Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="cfaa7-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="cfaa7-105">Когда вы присоединяете Surface Hub 2S к домену Azure AD, вы можете настроить учетные записи неглобальных администраторов, которые ограничивают разрешения на управление приложением "Параметры" на Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="cfaa7-106">Это позволяет вам получать разрешения администратора только для Surface Hub только в том случае, если вы не можете получить потенциально нежелательного администратора для всего домена Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="cfaa7-107">Прежде чем начать, убедитесь в том, что Surface Hub 2 входит в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="cfaa7-108">В противном случае вам потребуется сбросить Surface Hub 2 и выполнить начальную программу установки (OOBE), выбрав параметр для присоединения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="cfaa7-109">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cfaa7-109">Summary</span></span> 

<span data-ttu-id="cfaa7-110">Процесс создания учетных записей, не являющихся глобальными администраторами, состоит из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="cfaa7-111">В Microsoft Intune создайте группу безопасности, в которой находятся администраторы, назначенные для управления Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="cfaa7-112">Получение SID группы Azure AD с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="cfaa7-113">Создание XML-файла, содержащего SID группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="cfaa7-114">Создайте группу безопасности с устройствами Surface Hub 2S, которые будут управляться группой безопасности неглобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="cfaa7-115">Создание настраиваемого профиля конфигурации, предназначенного для группы безопасности, содержащей устройства Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="cfaa7-116">Создание групп безопасности Azure AD</span><span class="sxs-lookup"><span data-stu-id="cfaa7-116">Create Azure AD security groups</span></span>

<span data-ttu-id="cfaa7-117">Сначала создайте группу безопасности с учетными записями администратора.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="cfaa7-118">Затем создайте другую группу безопасности для устройств Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="cfaa7-119">Создание группы безопасности для учетных записей администраторов</span><span class="sxs-lookup"><span data-stu-id="cfaa7-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="cfaa7-120">Войдите в Intune через [центр администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), выберите **группы**  >  **создать группу** > и в разделе Тип группы выберите пункт **безопасность.**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="cfaa7-121">Введите имя группы (например, **"Surface Hub Local Администраторы"** ) и нажмите кнопку "создать" **.**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Создание группы безопасности для администраторов центра администрирования](images/sh-create-sec-group.png)

3. <span data-ttu-id="cfaa7-123">Откройте группу, выберите пункт **Участники**и нажмите кнопку **Добавить участников** , чтобы ввести учетные записи администраторов, которые вы хотите назначить в качестве неглобальных администраторов Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="cfaa7-124">Чтобы узнать больше о создании групп в Intune, ознакомьтесь со статьей  [Добавление групп для упорядочения пользователей и устройств](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="cfaa7-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="cfaa7-125">Создание группы безопасности для устройств Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="cfaa7-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="cfaa7-126">Повторите описанные выше действия, чтобы создать отдельную группу безопасности для устройств-концентраторов. Например, **Surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Создание группы безопасности для устройств-концентраторов](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="cfaa7-128">Получение SID группы Azure AD с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfaa7-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="cfaa7-129">Запустите PowerShell с правами повышенной учетной записи (**Запуск от имени администратора**) и убедитесь, что ваша система настроена для выполнения сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="cfaa7-130">Дополнительные сведения можно найти в разделе [о политиках выполнения](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="cfaa7-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="cfaa7-131">[Установите модуль Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="cfaa7-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="cfaa7-132">Войдите в свою учетную запись клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="cfaa7-133">Войдя в свой клиент, выполните указанные ниже unifiedgroup.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="cfaa7-134">Вам будет предложено "введите идентификатор объекта группы Azure AD".</span><span class="sxs-lookup"><span data-stu-id="cfaa7-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="cfaa7-135">В Intune выберите созданную ранее группу и скопируйте идентификатор объекта, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Копирование идентификатора объекта группы безопасности](images/sh-objectid.png)

6. <span data-ttu-id="cfaa7-137">Чтобы получить SID группы безопасности, выполните следующие unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="cfaa7-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="cfaa7-138">Вставьте идентификатор объекта в unifiedgroup PowerShell, нажмите клавишу **Ввод**, а затем скопируйте **SID группы Azure AD** в текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="cfaa7-139">Создание XML-файла, содержащего SID группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="cfaa7-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="cfaa7-140">Скопируйте следующий текст в текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="cfaa7-141">Замените заполнитель SID (начиная с S-1-12-1) на **ИД безопасности группы Azure AD** , а затем сохраните его в формате XML. Например, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="cfaa7-142">Создание настраиваемого профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="cfaa7-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="cfaa7-143">В диспетчере конечных точек **Devices**щелкните  >  **профили конфигурации**устройств, чтобы  >  **создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="cfaa7-144">В разделе Platform (платформа) выберите **Windows 10 или более поздней версии.**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="cfaa7-145">В разделе Профиль выберите пункт **Настраиваемая**и нажмите кнопку **создать.**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="cfaa7-146">Добавьте имя и описание, а затем нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="cfaa7-147">В разделе **Параметры конфигурации**  >  **OMA-URI**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="cfaa7-148">В области добавить строку добавьте имя и в разделе     **OMA-URI**добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="cfaa7-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="cfaa7-149">В разделе Тип данных выберите пункт **строковый XML** и перейдите к файлу XML, созданному на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Загрузка XML-файла конфигурации локального администратора](images/sh-local-admin-config.png)

7. <span data-ttu-id="cfaa7-151">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-151">Click **Save**.</span></span>
8. <span data-ttu-id="cfaa7-152">Щелкните **выбрать группы, чтобы включить** , и выберите [группу безопасности, созданную ранее](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub Devices**).</span><span class="sxs-lookup"><span data-stu-id="cfaa7-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="cfaa7-153">Нажмите кнопку **Далее**</span><span class="sxs-lookup"><span data-stu-id="cfaa7-153">Click **Next.**</span></span>
9. <span data-ttu-id="cfaa7-154">В разделе правила применимости при необходимости добавьте правило.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="cfaa7-155">В противном случае нажмите кнопку **Далее** , а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="cfaa7-156">Дополнительные сведения о настраиваемых профилях конфигурации с помощью строк OMA-URI см. [в статье Использование настраиваемых параметров для устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="cfaa7-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="cfaa7-157">Неглобальные администраторы, управляющие Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="cfaa7-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="cfaa7-158">Участники группы безопасности **"Локальные администраторы Surface Hub** " теперь могут войти в приложение "Параметры" на Surface Hub 2S и управлять параметрами.</span><span class="sxs-lookup"><span data-stu-id="cfaa7-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
