---
title: Настройка рабочего профиля Android Enterprise для Surface Duo
description: В этой статье рассказывается о том, как настроить профиль работы в Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911204"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>Настройка рабочего профиля Android Enterprise для Surface Duo

Для развертывания BYOD профили работы предоставляют отдельное пространство для приложений и данных Duo, предоставляя организациям полный контроль над своими данными, приложениями и политиками безопасности, не мешая сотрудникам использовать свое устройство для личных приложений и данных.

### <a name="set-up-android-enterprise-work-profile"></a>Настройка профиля Enterprise Android

Используйте профили работы для управления корпоративными данными и приложениями на устройствах Android, которые принадлежат пользователям. По умолчанию включена регистрация устройств личного профиля работы, которая не требует дополнительной конфигурации администратора.  

**Чтобы включить Enterprise профиль:**

- В Endpoint Manager выберите **регистрацию Устройств**на Android  >  **Android,** а затем выберите персональные  >  **** устройства **с профилем работы.**
<br><br>
 ![В Enterprise рабочий профиль.](images/enroll-start.png)

 
**Вход в Surface Duo с профилем Enterprise Android**

1. Установите приложение Корпоративный портал в магазине Google Play и вопишитесь в свою учетную запись Microsoft work или school.<br><br>
![Вход в Surface Duo.](images/duo-wp-1.png)
 
2. На странице Настройка доступа выберите **Начало**.<br><br>
![Начните.](images/duo-wp-2.png)

3. Просмотрите сведения на странице конфиденциальности и выберите **Продолжить**.<br><br>
 ![Продолжить.](images/duo-wp-3.png)
<br><br>
 ![Выберите продолжить.](images/duo-wp-4.png)
 
4. После завершения установки профиля работы выберите **Продолжить** активацию и зарегистрировать устройство.<br><br>
 ![Выберите продолжить активацию и регистрацию устройства.](images/duo-wp-5.png)

5. Выберите пункт **Продолжить**.<br><br>
 ![Выберите продолжить снова.](images/duo-wp-6.png)

6. При активации профиля работы выберите **Продолжить** обновление параметров устройства. В этом примере рабочий профиль применяет параметр MDM, чтобы потребовать более надежный 6-значный альфанумерный пароль. <br><br>

     ![Пример альфа-числимый пароль.](images/duo-wp-7.png)<br><br>
7. Выберите **Разрешить,** чтобы ввести необходимую проверку подлинности, а затем выберите **Продолжить** завершение настройки профиля работы. <br><br>
     ![Выберите продолжить настройку.](images/duo-wp-8.png)<br><br>
     ![полная настройка.](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>Подробнее

- [Настройка регистрации устройств профилей Enterprise Android](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

