---
title: Удаление SSD на совместимых устройствах Surface
description: В этой статье, предназначенной для квалифицированных ИТ-специалистов, описываются рекомендуемые рекомендации по удалению и замене SSD в Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X и Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop Studio
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
- Windows 10
- Windows 11
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: fbc1e2bee35874328637b23e66d148a4924030db
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449272"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>Лучшие практики для удаления SSD с совместимых устройств Surface

> [!IMPORTANT]
> Эта статья предназначена только для использования квалифицированными ИТ-специалистами в организации предприятия. В нем описываются рекомендуемые рекомендации для использования квалифицированными ИТ-специалистами при удалении и замене SSD в следующих совместимых устройствах Surface:

- Surface Laptop Studio
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> Открытие устройств и замена компонентов устройств могут представлять угрозы для электрошока, повреждения устройства, пожара и личных повреждений, а также другие опасности.  Всегда используйте осторожность, когда вы проводите такие действия. Соблюдайте меры предосторожности и процедуры, которые определены в [руководстве по удалению rSSD](https://www.microsoft.com/download/100440) для Enterprise. Мы рекомендуем вам получить профессиональную помощь, если вы не можете соблюдать меры предосторожности и процедуры, указанные в "руководстве по удалению rSSD для Enterprise".

## <a name="prerequisites"></a>Что вам понадобится

> [!IMPORTANT]
> В этой статье предполагается, что вы понимаете общие политики и процедуры, описанные в "руководстве по удалению rSSD для Enterprise".

## <a name="prepare-for-ssd-removal"></a>Подготовка к удалению SSD

### <a name="install-the-latest-updates"></a>Установка последних обновлений

Перед началом работы убедитесь, что в Windows версии Windows установлены последние обновления:

1. Перейдите **к Параметры** > **** >  **Update & безопасности** и выберите **Проверьте обновления**.
2. Установка всех доступных обновлений.
3. Проверка всех паролей, необходимых для доступа к устройству.  

## <a name="manage-bitlocker"></a>"Управление BitLocker"

> [!NOTE]
> В этом разделе содержатся рекомендации для организаций, которые включили шифрование BitLocker для жестких дисков. Дополнительные сведения см. в  [руководстве по восстановлению BitLocker](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>Если шифрование BitLocker отключено во время удаления и замены SSD

Если устройство можно расшифровать до удаления и замены SSD, выполните следующие действия, чтобы отключить BitLocker:

1. В **Параметры** введите **BitLocker** и выберите **Управление BitLocker**.
2. Выберите **отключение BitLocker**.
3. Питание устройства.

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>Если шифрование BitLocker включено во время удаления и замены SSD

Если устройство зашифровано до удаления и замены SSD, выполните следующие действия, чтобы создать ключ восстановления BitLocker и сохранить его в хранилище USB:

1. В **Параметры** введите **BitLocker**.
2. Выберите **клавишу Управления bitLockerGenerate** > **BitLockerer.**
2. Вставьте USB-накопитель.
4. Сохраните ключ восстановления в хранилище USB.  
5. Удалите USB-накопитель.  
6. Питание устройства.

## <a name="remove-and-replace-ssd"></a>Удаление и замена SSD

1. Удалите SSD с помощью соответствующих инструкций для устройства, включенных в [руководство по удалению rSSD для Enterprise](https://www.microsoft.com/download/100440).
2. Поместите исходный SSD в новое устройство и подключите новое устройство к подключению к интернету с проводной связью.
3. Питание на новом устройстве. Устройство может проходить обновление прошивки во время запуска.  

## <a name="after-ssd-removal-and-replacement"></a>После удаления и замены SSD

### <a name="manage-unencrypted-ssds"></a>Управление незашифрованными SSD

Если SSD не расшифрована во время передачи, выполните следующие действия:

1. Перейдите **в параметры Sign-In** **OptionsPassword** >  (представленный значком ключа слева).  
2. Введите пароль и войдите в ожидании завершения двух факторов проверки подлинности (если это применимо).
3. После полного подписания перейдите в **StartAccountSign** > **** > .****  
4. Во входе с помощью пароля и Windows Hello пин-кода при запросе.
    - Если устройство было отключено bitLocker для облегчения удаления и замены SSD, а после замены необходимо включить BitLocker, перейдите в **BitLockerManage** >  **BitLockerResume** >  **BitLockume BitLocker**.  
6. Запустите [службу диагностики поверхности Майкрософт набор средств для бизнеса](surface-diagnostic-toolkit-for-business-intro.md) (SDT), чтобы проверить полную функциональность устройства.  
7. Проверьте, Windows ли активация, перенавигав **Параметры** >  **Activation**.  Если вы видите сообщения об ошибках, выберите **устранение неполадок**.
8. Проверьте учетную запись Office, **открыв приложение Office**, перейдите в **FileAccount** **** >  и проверьте сообщения об ошибках.  

### <a name="managing-encrypted-ssds"></a>Управление зашифрованными SSD-кодами

> [!NOTE]
> Для чтения ключа Восстановления BitLocker, сохраненного на USB-диске, необходимо иметь второе устройство.

Если SSD зашифрован во время передачи, выполните следующие действия:

1. Вставьте USB-накопитель, содержащий ключ восстановления BitLocker во втором устройстве.
2. Откройте файл .txt, содержащий ключ восстановления Bitlocker.
3. Вручную введите ключ восстановления BitLocker на новом устройстве, которое содержит исходный SSD.  
4. После успешного вступив в клавишу восстановления BitLocker, перейдите в **Sign-In** **OptionsPassword** >  (представленный значком ключа слева).  
5. Введите пароль и войдите, пока не будет завершена двух-факторная проверка подлинности (если это применимо).
6. После полного подписания перейдите в **StartAccountSign** > **** > .****  
7. Впишитесь, используя пароль, а затем Windows Hello и добавьте ПИН-код.
8. Если устройство было отключено с помощью BitLocker для облегчения удаления и замены SSD, и если вы хотите включить BitLocker после замены, **** >  перейдите к Параметры **BitLockerManage** >  **BitLockerResume** >  **BitLockume BitLocker**.  
9. **[Запустите SDT,](surface-diagnostic-toolkit-for-business-intro.md)** чтобы проверить полную функциональность устройства.  
10. Чтобы проверить Windows активацию, **выберите Параметры** >  **Activation**.  Если вы видите сообщения об ошибках, выберите **устранение неполадок**.
11. Чтобы проверить состояние учетной записи Office, откройте приложение **Office**, а затем перейдите в **FileAccount****** > , чтобы проверить сообщения об ошибках.

## <a name="learn-more"></a>Подробнее

- [руководство по удалению rSSD для Enterprise](https://www.microsoft.com/download/100440)
- [Руководство по восстановлению BitLocker](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Все еще нужна помощь? Перейдите в [Microsoft Community](https://answers.microsoft.com/).
