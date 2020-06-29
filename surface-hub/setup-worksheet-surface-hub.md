---
title: Рабочий план настройки (Surface Hub)
description: Когда вы закончите предварительную настройку и будете готовы к первому запуску Microsoft Surface Hub, убедитесь, что у вас есть все сведения, указанные в этом разделе.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Рабочий план настройки, предварительная настройка, первая настройка
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836448"
---
# <span data-ttu-id="b53a4-104">Рабочий план настройки (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b53a4-104">Setup worksheet (Surface Hub)</span></span>


<span data-ttu-id="b53a4-105">Когда вы закончите предварительную настройку и будете готовы к первому запуску Microsoft Surface Hub, убедитесь, что у вас есть все сведения, указанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b53a4-105">When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.</span></span>

<span data-ttu-id="b53a4-106">Заполните один список для каждого устройства Surface Hub, который необходимо настроить, хотя некоторые сведения можно использовать на всех Surface Hub, например данные прокси-сервера или учетные данные домена.</span><span class="sxs-lookup"><span data-stu-id="b53a4-106">You should fill out one list for each Surface Hub you need to configure, although some information can be used on all Surface Hubs, like the proxy information or domain credentials.</span></span> <span data-ttu-id="b53a4-107">Часть данных может не потребоваться в зависимости от того, как вы решили настроить устройство, или в зависимости от конфигурации среды для инфраструктуры вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b53a4-107">Some of this information may not be needed, depending on how you've decided to configure your device, or depending on how the environment is configured for your organization's infrastructure.</span></span>

<table>
<tr>
<th><span data-ttu-id="b53a4-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="b53a4-108">Property</span></span></th>
<th><span data-ttu-id="b53a4-109">Назначение свойства</span><span class="sxs-lookup"><span data-stu-id="b53a4-109">What this is used for</span></span></th>
<th><span data-ttu-id="b53a4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b53a4-110">Example</span></span></th>
<th><span data-ttu-id="b53a4-111">Фактическое значение</span><span class="sxs-lookup"><span data-stu-id="b53a4-111">Actual value</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-112">Сведения о прокси-сервере</span><span class="sxs-lookup"><span data-stu-id="b53a4-112">Proxy information</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-113">Если в вашей организации для доступа к сети или Интернету используется прокси-сервер, необходимо предоставить сценарий или указать имя и порт сервера.</span><span class="sxs-lookup"><span data-stu-id="b53a4-113">If your network uses a proxy for network and/or Internet access, you must provide a script or server/port information.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-114">Сценарий прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="b53a4-114">Proxy script:</span></span> <code>http://contoso/proxy.pa</code> </br>
- <span data-ttu-id="b53a4-115">ИЛИ -</span><span class="sxs-lookup"><span data-stu-id="b53a4-115">OR -</span></span> </br>
<span data-ttu-id="b53a4-116">Информация о сервере и порте: 10.10.10.100, порт 80</span><span class="sxs-lookup"><span data-stu-id="b53a4-116">Server and port info: 10.10.10.100, port 80</span></span>
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-117">Учетные данные беспроводной сети (имя пользователя и пароль)</span><span class="sxs-lookup"><span data-stu-id="b53a4-117">Wireless network credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-118">Необходимо, если вы хотите подключить устройство к беспроводной сети Wi-Fi, которая требует ввода учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="b53a4-118">If you decide to connect your device to Wi-Fi, and your wireless network requires user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-119">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="b53a4-119">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-120">Имя участника-пользователя учетной записи устройства или домен\имя_пользователя и пароль учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="b53a4-120">Device account UPN or Domain\username and device account password</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-121">Это имя участника-пользователя (UPN) или домен\имя_пользователя и пароль учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-121">This is the User Principal Name (UPN) or the domain\username, and the password of the device account.</span></span> <span data-ttu-id="b53a4-122">Почта, календарь и Skype для бизнеса зависят от совместимой учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-122">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span></p>
</td>
<td>
<p> <span data-ttu-id="b53a4-123">Имя участника-пользователя: ConfRoom15@contoso.com, #Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="b53a4-123">UPN: ConfRoom15@contoso.com, #Passw0rd1</span></span> </br>
- <span data-ttu-id="b53a4-124">ИЛИ -</span><span class="sxs-lookup"><span data-stu-id="b53a4-124">OR -</span></span> <br> 
<span data-ttu-id="b53a4-125">Домен и имя пользователя: CONTOSO\ConfRoom15, #Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="b53a4-125">Domain and username: CONTOSO\ConfRoom15, #Passw0rd1</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-126">Microsoft Exchange Server учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="b53a4-126">Device account Microsoft Exchange server</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-127">Это сервер Exchange Server учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-127">This is the device account's Exchange server.</span></span>
<span data-ttu-id="b53a4-128">Почта, календарь и Skype для бизнеса зависят от совместимой учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-128">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="b53a4-129">Для работы почты и календаря в учетной записи устройства должен быть задан действительный сервер Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b53a4-129">For mail and calendar to work, the device account must have a valid Exchange server.</span></span> <span data-ttu-id="b53a4-130">Устройство попытается найти его автоматически.</span><span class="sxs-lookup"><span data-stu-id="b53a4-130">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-131">outlook.office365.com</span><span class="sxs-lookup"><span data-stu-id="b53a4-131">outlook.office365.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-132">SIP-адрес учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="b53a4-132">Device account Session Initiation Protocol (SIP) address</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-133">Это SIP-адрес Skype для бизнеса учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-133">This is the device account's Skype for Business SIP address.</span></span>
<span data-ttu-id="b53a4-134">Почта, календарь и Skype для бизнеса зависят от совместимой учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-134">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="b53a4-135">Для поддержки Skype для бизнеса в учетной записи устройства должен быть указан допустимый SIP-адрес.</span><span class="sxs-lookup"><span data-stu-id="b53a4-135">For Skype for Business to work, the device account must have a valid SIP address.</span></span> <span data-ttu-id="b53a4-136">Устройство попытается найти его автоматически.</span><span class="sxs-lookup"><span data-stu-id="b53a4-136">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-137">sip: ConfRoom15@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b53a4-137">sip: ConfRoom15@contoso.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-138">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="b53a4-138">Friendly name</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-139">Понятное имя устройства — это отображаемое имя, которое пользователи увидят при попытке подключения к Surface Hub по беспроводной сети.</span><span class="sxs-lookup"><span data-stu-id="b53a4-139">The friendly name of the device is the broadcast name that people will see when they try to wirelessly connect to the Surface Hub.</span></span> <span data-ttu-id="b53a4-140">Это имя отображается на экране Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b53a4-140">This name will be displayed prominently on the Surface Hub's screen.</span></span>
<span data-ttu-id="b53a4-141">Мы рекомендуем выбрать такое понятное имя, чтобы пользователи легко могли отличить одно устройство Surface Hub от других при попытке подключения.</span><span class="sxs-lookup"><span data-stu-id="b53a4-141">We suggest that the friendly name you choose is recognizable and unique so that people can distinguish one Surface Hub from another when trying to connect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-142">Конференц-зал 15</span><span class="sxs-lookup"><span data-stu-id="b53a4-142">Conference Room 15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-143">Имя устройства</span><span class="sxs-lookup"><span data-stu-id="b53a4-143">Device name</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-144">Имя устройства — это имя, которое будет использоваться для присоединения к домену. Это удостоверение, которое вы увидите в решении MDM, если устройство зарегистрировано в нем.</span><span class="sxs-lookup"><span data-stu-id="b53a4-144">The device name is the name that will be used for domain join, and is the identity you will see in your MDM provider if the device is enrolled into MDM.</span></span>
<span data-ttu-id="b53a4-145">Имя устройства не должно совпадать с именами других устройств в домене Active Directory пользователя (если вы решили присоединить устройство к домену).</span><span class="sxs-lookup"><span data-stu-id="b53a4-145">The device name you choose must not be the same name as any other device on the user’s Active Directory domain (if you decide to domain join the device).</span></span> <span data-ttu-id="b53a4-146">Устройство не может быть присоединено к домену, если его имя не уникально.</span><span class="sxs-lookup"><span data-stu-id="b53a4-146">The device cannot join the domain if its name is not unique.</span></span>
</p>
</td>
<td>
<p><span data-ttu-id="b53a4-147">confroom15</span><span class="sxs-lookup"><span data-stu-id="b53a4-147">confroom15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="b53a4-148">ПРИ ПРИСОЕДИНЕНИИ К AZURE AD</span><span class="sxs-lookup"><span data-stu-id="b53a4-148">IF YOU'RE JOINING AZURE AD</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-149">Учетные данные пользователя клиента Azure AD (имя пользователя и пароль)</span><span class="sxs-lookup"><span data-stu-id="b53a4-149">Azure AD tenant user credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-150">Если вы решили сделать пользователей организации Azure Active Directory (Azure AD) администраторами устройства, вам необходимо присоединиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b53a4-150">If you decide to have people in your Azure Active Directory (Azure AD) organization become admins on the device, then you'll need to join Azure AD.</span></span>
<span data-ttu-id="b53a4-151">Для присоединения к Azure AD требуются действительные учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="b53a4-151">To join Azure AD, you will need valid user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-152">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="b53a4-152">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="b53a4-153">ПРИ ПРИСОЕДИНЕНИИ К ДОМЕНУ</span><span class="sxs-lookup"><span data-stu-id="b53a4-153">IF YOU'RE JOINING A DOMAIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-154">Домен, к которому присоединяется домен</span><span class="sxs-lookup"><span data-stu-id="b53a4-154">Domain to join</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-155">Это домен, к которому необходимо присоединиться, чтобы участники выбранной группы безопасности стали администраторами для устройства.</span><span class="sxs-lookup"><span data-stu-id="b53a4-155">This is the domain you will need to join so that a security group of your choice can be admins for the device.</span></span>
<span data-ttu-id="b53a4-156">Вам может потребоваться полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b53a4-156">You may need the fully qualified domain name (FQDN).</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-157">contoso (короткое имя) ИЛИ contoso.corp.com (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="b53a4-157">contoso (short name) OR contoso.corp.com (FQDN)</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-158">Учетные данные учетной записи домена (имя пользователя и пароль)</span><span class="sxs-lookup"><span data-stu-id="b53a4-158">Domain account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-159">К домену невозможно присоединиться, если вы не сможете предоставить необходимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b53a4-159">A domain can't be joined unless you provide sufficient account credentials to join the domain.</span></span> <span data-ttu-id="b53a4-160">После указания домена и учетных данных для присоединения к домену, участники выбранной группы безопасности смогут изменять параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b53a4-160">Once you provide a domain to join and credentials to join the domain, then a security group of your choice can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-161">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="b53a4-161">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-162">Псевдоним группы безопасности администраторов</span><span class="sxs-lookup"><span data-stu-id="b53a4-162">Admin security group alias</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-163">Это группа безопасности в службе Active Directory (AD). Все ее участники могут изменять параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b53a4-163">This is a security group in your Active Directory (AD); any members of this security group can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-164">SurfaceHubAdmins</span><span class="sxs-lookup"><span data-stu-id="b53a4-164">SurfaceHubAdmins</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="b53a4-165">ПРИ ИСПОЛЬЗОВАНИИ ЛОКАЛЬНОГО АДМИНИСТРАТОРА</span><span class="sxs-lookup"><span data-stu-id="b53a4-165">IF YOU'RE USING A LOCAL ADMIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-166">Учетные данные локального администратора (имя пользователя и пароль)</span><span class="sxs-lookup"><span data-stu-id="b53a4-166">Local admin account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-167">Если вы решили не присоединяться к домену AD или Azure AD, вы можете создать на устройстве учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="b53a4-167">If you decide not to join an AD domain or Azure AD, you can create a local admin account on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-168">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="b53a4-168">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="b53a4-169">ЕСЛИ ТРЕБУЕТСЯ УСТАНОВИТЬ СЕРТИФИКАТЫ ИЛИ ПРИЛОЖЕНИЯ</span><span class="sxs-lookup"><span data-stu-id="b53a4-169">IF YOU NEED TO INSTALL CERTIFICATES OR APPS</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="b53a4-170">USB-накопитель</span><span class="sxs-lookup"><span data-stu-id="b53a4-170">USB drive</span></span></p>
</td>
<td>
<p><span data-ttu-id="b53a4-171">Если перед первым запуском вам известно, что потребуется установить сертификаты или универсальные приложения, выполните действия из раздела <a href="provisioning-packages-for-certificates-surface-hub.md">Создание пакетов подготовки</a>.</span><span class="sxs-lookup"><span data-stu-id="b53a4-171">If you know before first run that you want to install certificates or universal apps, follow the steps in <a href="provisioning-packages-for-certificates-surface-hub.md">Create provisioning packages</a>.</span></span> <span data-ttu-id="b53a4-172">Пакеты подготовки будут созданы на USB-накопителе.</span><span class="sxs-lookup"><span data-stu-id="b53a4-172">Your provisioning packages will be created on a USB drive.</span></span></p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





