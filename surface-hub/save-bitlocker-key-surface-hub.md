---
title: Сохранение ключа BitLocker (Surface Hub)
description: На каждом устройстве Microsoft Surface Hub автоматически устанавливается программное обеспечение для шифрования дисков BitLocker. Корпорация Майкрософт настоятельно рекомендует создавать резервные копии ключей восстановления BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, ключи восстановления Bitlocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836464"
---
# <span data-ttu-id="69bdc-105">Сохранение ключа BitLocker (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="69bdc-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="69bdc-106">На каждом устройстве Microsoft Surface Hub автоматически устанавливается программное обеспечение для шифрования дисков BitLocker.</span><span class="sxs-lookup"><span data-stu-id="69bdc-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="69bdc-107">Корпорация Майкрософт настоятельно рекомендует создавать резервные копии ключей восстановления BitLocker.</span><span class="sxs-lookup"><span data-stu-id="69bdc-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="69bdc-108">Существует несколько способов управления ключом BitLocker на устройстве Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="69bdc-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="69bdc-109">Если вы присоединили Surface Hub к домену, устройство будет создавать резервную копию ключа в домене и хранить его в объекте компьютера.</span><span class="sxs-lookup"><span data-stu-id="69bdc-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="69bdc-110">Если вы не можете найти ключ BitLocker после присоединения к домену, возможно, ваше схема Active Directory не поддерживает резервное копирование ключа BitLocker.</span><span class="sxs-lookup"><span data-stu-id="69bdc-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="69bdc-111">Если вы не хотите изменить схему, вы можете сохранить ключ BitLocker, открыв приложение «Параметры», и использовать процедуру для учетной записи локального администратора, которая описана далее.</span><span class="sxs-lookup"><span data-stu-id="69bdc-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="69bdc-112">Если вы присоединили Surface Hub к Azure Active Directory (Azure AD), ключ BitLocker будет храниться в учетной записи, которая использовалась для присоединения устройства.</span><span class="sxs-lookup"><span data-stu-id="69bdc-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="69bdc-113">Если вы используете локальную учетную запись администратора для управления устройством, вы можете сохранить ключ BitLocker, перейдя в приложение " **Параметры** " и перейдя к **обновлению &** &gt; **восстановления**безопасности.</span><span class="sxs-lookup"><span data-stu-id="69bdc-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="69bdc-114">Вставьте USB-накопитель и выберите параметр сохранения ключа BitLocker.</span><span class="sxs-lookup"><span data-stu-id="69bdc-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="69bdc-115">Ключ будет сохранен в текстовый файл на USB-накопителе.</span><span class="sxs-lookup"><span data-stu-id="69bdc-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="69bdc-116">Еще по теме</span><span class="sxs-lookup"><span data-stu-id="69bdc-116">Related topics</span></span>

[<span data-ttu-id="69bdc-117">Управление Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="69bdc-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="69bdc-118">Руководство администратора Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="69bdc-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





