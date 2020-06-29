---
title: Управление ротацией пароля учетной записи устройства
description: Сведения о том, как настроить Surface Hub 2S локальные учетные записи с помощью PowerShell
keywords: Разделяйте значения запятыми
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836640"
---
# <span data-ttu-id="d2803-104">Управление ротацией пароля учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="d2803-104">Manage device account password rotation</span></span>

<span data-ttu-id="d2803-105">Вы можете настроить Surface Hub 2S для автоматического изменения пароля учетной записи устройства, не требуя вручную обновлять сведения об учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="d2803-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="d2803-106">Если включить функцию поворота пароля, Surface Hub 2 изменяет пароль каждые 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d2803-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="d2803-107">Автоматически создаваемые пароли содержат 15-32 символов, включая сочетание прописных и строчных букв, цифр и специальных символов.</span><span class="sxs-lookup"><span data-stu-id="d2803-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="d2803-108">Пароли не изменяются во время собрания.</span><span class="sxs-lookup"><span data-stu-id="d2803-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="d2803-109">Если параметр Surface Hub 2 выключен, пароль будет пытаться изменить его немедленно при включенном или каждые 10 минут, пока вы не завершите работу.</span><span class="sxs-lookup"><span data-stu-id="d2803-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>
