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
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a><span data-ttu-id="1a710-104">Настройка учетных записей администраторов, не являющихся глобальными, на Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="1a710-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="1a710-105">При подстройке Surface Hub 2S к домену Azure AD можно настроить учетные записи не глобального администратора, ограничивающие разрешения на управление приложением "Параметры" на Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="1a710-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="1a710-106">Это позволяет использовать разрешения администратора только для Surface Hub 2S и предотвращать потенциально нежелательный доступ администратора во всем домене Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a710-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="1a710-107">Перед началом работы убедитесь, что surface Hub 2S присоединяется к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a710-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="1a710-108">Если нет, вам потребуется сбросить Surface Hub 2S и выполнить первую, из коробки (OOBE) программу установки, выбрав вариант присоединиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a710-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="1a710-109">Сводка</span><span class="sxs-lookup"><span data-stu-id="1a710-109">Summary</span></span> 

<span data-ttu-id="1a710-110">Процесс создания учетных записей не глобального администратора включает в себя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1a710-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="1a710-111">В Microsoft Intune создайте группу безопасности, содержащую администраторов, назначенных для управления Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="1a710-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="1a710-112">Получение SID группы Azure AD с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a710-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="1a710-113">Создание XML-файла, содержащего SID группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a710-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="1a710-114">Создайте группу безопасности, содержащую устройства Surface Hub 2S, которые будут управляться группой безопасности не глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="1a710-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="1a710-115">Создайте настраиваемый профиль конфигурации, нацеленный на группу безопасности, которая содержит устройства Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="1a710-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="1a710-116">Создание групп безопасности Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a710-116">Create Azure AD security groups</span></span>

<span data-ttu-id="1a710-117">Сначала создайте группу безопасности, содержащую учетные записи администратора.</span><span class="sxs-lookup"><span data-stu-id="1a710-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="1a710-118">Затем создайте другую группу безопасности для устройств Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1a710-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="1a710-119">Создание группы безопасности для учетных записей администратора</span><span class="sxs-lookup"><span data-stu-id="1a710-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="1a710-120">Во входе в Intune с помощью \*\*\*\* центра администрирования [microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)выберите группу New Group > и в соответствии с типом группы  >  \*\*\*\* выберите **Security.**</span><span class="sxs-lookup"><span data-stu-id="1a710-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="1a710-121">Введите имя группы ( например, локальные администраторы **Surface Hub)** и выберите **Create.**</span><span class="sxs-lookup"><span data-stu-id="1a710-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Создание группы безопасности для администраторов концентраторов](images/sh-create-sec-group.png)

3. <span data-ttu-id="1a710-123">Откройте группу, выберите **Членов,** а затем выберите Добавить участников для ввода учетных записей администратора, которые вы хотите назначить не глобальными администраторами в Surface Hub 2S. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1a710-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="1a710-124">Дополнительные информацию о создании групп в Intune см. в добавлении [групп для организации пользователей и устройств.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="1a710-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-2s-devices"></a><span data-ttu-id="1a710-125">Создание группы безопасности для устройств Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="1a710-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="1a710-126">Повторите предыдущую процедуру, чтобы создать отдельную группу безопасности для устройств Hub; например, **устройства Surface Hub.**</span><span class="sxs-lookup"><span data-stu-id="1a710-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Создание группы безопасности для устройств Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="1a710-128">Получение SID группы Azure AD с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a710-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="1a710-129">Запустите PowerShell с повышенными привилегиями учетной записи **(Запустите**в качестве администратора) и убедитесь, что ваша система настроена для запуска сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a710-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="1a710-130">Чтобы узнать больше, обратитесь [к политике выполнения](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="1a710-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="1a710-131">[Установка модуля Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="1a710-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="1a710-132">Вопишитесь в клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a710-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="1a710-133">При подписании в клиенте запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1a710-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="1a710-134">В нем будет предложено ввести "Введите ID объекта вашей группы Azure AD".</span><span class="sxs-lookup"><span data-stu-id="1a710-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="1a710-135">В Intune выберите группу, созданную ранее, и скопируйте объект id, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="1a710-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Скопируйте id объекта группы безопасности](images/sh-objectid.png)

6. <span data-ttu-id="1a710-137">Запустите следующий командлет, чтобы получить SID группы безопасности:</span><span class="sxs-lookup"><span data-stu-id="1a710-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="1a710-138">Введите id объекта в командлет PowerShell, нажмите **кнопку Ввод,** а затем скопируйте SID **Группы Azure AD в** текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="1a710-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="1a710-139">Создание XML-файла, содержащего SID группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a710-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="1a710-140">Скопируйте следующее в текстовый редактор:</span><span class="sxs-lookup"><span data-stu-id="1a710-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="1a710-141">Замените SID-держателя (начиная с S-1-12-1) на sid **azure AD Group,** а затем сохраните файл в качестве XML; например, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="1a710-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="1a710-142">Создание настраиваемой конфигурации профиля</span><span class="sxs-lookup"><span data-stu-id="1a710-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="1a710-143">В Endpoint Manager выберите **профили**  >  **конфигурации устройств**  >  **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="1a710-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="1a710-144">Под платформой выберите **Windows 10 и более поздний.**</span><span class="sxs-lookup"><span data-stu-id="1a710-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="1a710-145">В профиле выберите **Настраиваемый,** а затем выберите **Создать.**</span><span class="sxs-lookup"><span data-stu-id="1a710-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="1a710-146">Добавьте имя и описание, а затем выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="1a710-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="1a710-147">В **параметрах Конфигурация**  >  **OMA-URI Параметры**выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1a710-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="1a710-148">В области Добавить строку добавьте имя и в     **OMA-URI**добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="1a710-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="1a710-149">В соответствии с типом Data выберите **Строку XML** и откройте XML-файл, созданный на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="1a710-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![отправка локального файла конфигурии администратора xml](images/sh-local-admin-config.png)

7. <span data-ttu-id="1a710-151">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a710-151">Click **Save**.</span></span>
8. <span data-ttu-id="1a710-152">Щелкните **Выберите группы, чтобы** включить и выбрать группу [безопасности,](#create-security-group-for-surface-hub-2s-devices) созданную ранее **(устройства Surface Hub).**</span><span class="sxs-lookup"><span data-stu-id="1a710-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="1a710-153">Нажмите кнопку **Далее**</span><span class="sxs-lookup"><span data-stu-id="1a710-153">Click **Next.**</span></span>
9. <span data-ttu-id="1a710-154">В соответствии с правилами применимости при желании добавьте правило.</span><span class="sxs-lookup"><span data-stu-id="1a710-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="1a710-155">В противном случае **выберите Далее,** а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1a710-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="1a710-156">Дополнительные данные о пользовательских профилях конфигурации с помощью строк OMA-URI см. в странице Использование настраиваемой настройки для [устройств Windows 10 в Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="1a710-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub-2s"></a><span data-ttu-id="1a710-157">Не глобальные администраторы, управляющие Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="1a710-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="1a710-158">Теперь члены группы **безопасности локальных** администраторов Surface Hub могут войти в приложение Параметры на Surface Hub 2S и управлять настройками.</span><span class="sxs-lookup"><span data-stu-id="1a710-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
