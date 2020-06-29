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
# Управление ротацией пароля учетной записи устройства

Вы можете настроить Surface Hub 2S для автоматического изменения пароля учетной записи устройства, не требуя вручную обновлять сведения об учетной записи устройства.

Если включить функцию поворота пароля, Surface Hub 2 изменяет пароль каждые 7 дней. Автоматически создаваемые пароли содержат 15-32 символов, включая сочетание прописных и строчных букв, цифр и специальных символов.

Пароли не изменяются во время собрания. Если параметр Surface Hub 2 выключен, пароль будет пытаться изменить его немедленно при включенном или каждые 10 минут, пока вы не завершите работу.
