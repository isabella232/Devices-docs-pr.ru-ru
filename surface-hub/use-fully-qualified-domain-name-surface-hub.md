---
title: Использование полного доменного имени в Surface Hub
description: Узнайте, как устранять распространенные проблемы, в том числе проблемы с установкой, и ошибки Exchange ActiveSync.
keywords:
- Устранение распространенных проблем
- проблемы с настройкой
- Ошибки Exchange ActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834851"
---
# <span data-ttu-id="ba363-106">Настройка доменного имени Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ba363-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="ba363-107">В некоторых сценариях вам может потребоваться указать доменное имя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ba363-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="ba363-108">**Несколько суффиксов DNS**— если в вашей инфраструктуре Skype для бизнеса есть разделенные пространства имен, например когда у одного или нескольких серверов есть суффикс DNS, не совпадающий с суффиксом адреса для входа (SIP) в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ba363-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="ba363-109">**Суффиксы Skype для бизнеса и Exchange отличаются**— если суффикс адреса для входа в Skype для бизнеса отличается от суффикса адреса Exchange, используемого для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="ba363-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="ba363-110">**Работа с сертификатами** : в крупных организациях с локальными серверами Skype для бизнеса обычно используются сертификаты с собственными корневыми центрами сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="ba363-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="ba363-111">Домен ЦС часто отличается от домена сервера Skype для бизнеса, в результате чего сертификат оказывается недоверенным и возникает ошибка входа.</span><span class="sxs-lookup"><span data-stu-id="ba363-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="ba363-112">Приложению Skype необходимо знать доменное имя сертификата, чтобы настроить отношение доверия.</span><span class="sxs-lookup"><span data-stu-id="ba363-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="ba363-113">Как правило, в предприятиях используются групповые политики для отправки полных доменных имен клиенту Skype, но групповые политики не поддерживаются в Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ba363-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="ba363-114">Настройка доменного имени Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ba363-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="ba363-115">На Surface Hub откройте приложение **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="ba363-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="ba363-116">Нажмите кнопку **Surface Hub**, а затем нажмите кнопку **Вызовы и звук**.</span><span class="sxs-lookup"><span data-stu-id="ba363-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="ba363-117">В разделе **Конфигурация Skype для бизнеса** нажмите кнопку **Настроить доменное имя**.</span><span class="sxs-lookup"><span data-stu-id="ba363-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="ba363-118">Введите имя домена Skype для бизнеса Server и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ba363-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="ba363-119">Можно ввести несколько доменных имен, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="ba363-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="ba363-120">Пример: lync.com, outlook.com, lync.glbdns.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ba363-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![Добавление полного доменного имени Skype для бизнеса в параметры](images/system-settings-add-fqdn.png)
