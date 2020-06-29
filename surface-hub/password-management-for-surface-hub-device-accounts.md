---
title: Управление паролями (Surface Hub)
description: Для каждой учетной записи устройства Microsoft Surface Hub требуется указать пароль для проверки подлинности и работы некоторых функций устройства.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: пароль, управление паролями, чередование паролей, учетная запись устройства
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836680"
---
# <span data-ttu-id="18a38-104">Управление паролями (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="18a38-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="18a38-105">Для каждой учетной записи устройства Microsoft Surface Hub требуется указать пароль для проверки подлинности и работы некоторых функций устройства.</span><span class="sxs-lookup"><span data-stu-id="18a38-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="18a38-106">Из соображений безопасности следует регулярно менять этот пароль (что также называют "чередованием").</span><span class="sxs-lookup"><span data-stu-id="18a38-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="18a38-107">Но если пароль учетной записи устройства изменится, пароль, ранее сохраненный в Surface Hub, станет недоступным, а все функции, которые зависят от учетной записи устройства, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="18a38-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="18a38-108">Вам потребуется изменить пароль учетной записи устройства на Surface Hub в приложении "Параметры", чтобы восстановить эти возможности.</span><span class="sxs-lookup"><span data-stu-id="18a38-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="18a38-109">Чтобы упростить управление паролями для учетных записей устройств Surface Hub, можно воспользоваться одним из следующих двух способов:</span><span class="sxs-lookup"><span data-stu-id="18a38-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="18a38-110">отключить истечение срока действия пароля для учетной записи устройства;</span><span class="sxs-lookup"><span data-stu-id="18a38-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="18a38-111">предоставить Surface Hub разрешение на автоматическую смену пароля учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="18a38-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="18a38-112">Отключение ротации паролей для учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="18a38-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="18a38-113">Задайте для свойства **PasswordNeverExpires** значение True.</span><span class="sxs-lookup"><span data-stu-id="18a38-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="18a38-114">Следует проверить, соответствует ли это требованиям безопасности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="18a38-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="18a38-115">Предоставление Surface Hub разрешения на автоматическую смену пароля учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="18a38-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="18a38-116">Surface Hub может управлять паролем учетной записи устройства, часто изменяя его. При этом вам не требуется обновлять сведения об учетной записи устройства вручную.</span><span class="sxs-lookup"><span data-stu-id="18a38-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="18a38-117">Вы можете включить эту функцию в приложении **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="18a38-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="18a38-118">После включения этой функции пароль учетной записи устройства будет изменяться еженедельно в часы обслуживания.</span><span class="sxs-lookup"><span data-stu-id="18a38-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="18a38-119">Обратите внимание, что при изменении пароля учетной записи устройства вы не увидите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="18a38-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="18a38-120">Если вам нужно войти в учетную запись или ввести пароль снова (например, чтобы изменить параметры учетной записи устройства на Surface Hub), вам потребуется использовать Active Directory или портал администрирования Office 365, чтобы сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="18a38-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18a38-121">Если ваша организация использует гибридную топологию (некоторые службы размещены локально, другие— в Интернете с помощью Office 365), необходимо настроить учетную запись устройства в формате **домен\имя_пользователя**.</span><span class="sxs-lookup"><span data-stu-id="18a38-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="18a38-122">В противном случае ротация паролей не заработает.</span><span class="sxs-lookup"><span data-stu-id="18a38-122">Otherwise, password rotation will not work.</span></span>
