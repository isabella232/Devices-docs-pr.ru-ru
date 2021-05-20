---
title: Создание пакетов подготовки для Surface Hub 2S
description: На этой странице описывается развертывание Surface Hub 2S с помощью пакетов предварительного обеспечения и других средств.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576869"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>Создание пакетов подготовки для Surface Hub 2S

Вы можете использовать Windows (WCD) для создания пакетов подготовка для автоматизации развертывания Surface Hub 2S. Используйте пакеты подготовка для добавления сертификатов, настройки прокси, настройки администраторов устройств и учетных записей устройств. Вы также можете использовать пакеты подготовка вместе с файлом конфигурации для развертывания нескольких концентраторов Surface с одним usb-накопителем.

### <a name="install-windows-configuration-designer"></a>Установка конструктора конфигураций Windows

Установите Windows конструктор конфигурации из набора Windows и развертывания (ADK) для Windows 10. Скачайте и установите [ADK для Windows 10 версии 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Дополнительные сведения см. в разделе [Скачивание и установка Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### <a name="add-certificates"></a>Добавление сертификатов

Вы можете импортировать сертификаты Authority в Surface Hub 2S.
Чтобы добавить сертификаты Surface Hub 2S, вам потребуется копия каждого сертификата в формате X.509 в формате .cer. Невозможно импортировать .crt, .pfx или другие форматы контейнера. Сертификаты должны импортироваться в Windows configuration Designer и организовываться по иерархии:

> [!div class="mx-imgBorder"]
> ![Добавление сертификатов](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>Настройка прокси во время OOBE

В Windows Конструктор конфигурации перейдите на вкладку Настройка параметров прокси и введите соответствующие параметры, как показано ниже.

> [!div class="mx-imgBorder"]
> ![настроить параметры прокси-сервера;](images/sh2-proxy.png) 

> [!NOTE]
> При настройке параметров прокси-сервера автоматически отключите параметры, если вы собираетесь использовать сценарий установки или прокси-сервер. **** Вы можете использовать сценарий установки *или* прокси-сервер, а не оба.

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>Партнерская Surface Hub 2S с Azure Active Directory

Вы можете аффилировать Surface Hub 2S с Azure Active Directory с помощью пакета подготовка: в качестве глобального администратора Azure Active Directory вы можете присоединиться к большому числу новых устройств Windows для Azure Active Directory и Intune с помощью маркера массы.

Чтобы создать основной маркер, назовите ему дружеское имя, настройте дату истечения срока действия (максимум 30 дней) и используйте учетные данные администратора для приобретения маркера, как показано ниже:

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Настройка администраторов устройств пример 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>Подготовка нескольких устройств (.csv файла)

В дополнение к пакету подготовка можно использовать файл Surface Hub конфигурации, чтобы упростить настройку устройств. Файл Surface Hub конфигурации содержит список учетных записей устройств и дружественные имена для беспроводной проекции. Во время первого запуска вы получаете возможность выбрать учетную запись устройства и удобное имя из файла конфигурации.

### <a name="to-create-a-surface-hub-configuration-file"></a>Создание файла Surface Hub конфигурации

1. С Microsoft Excel или другого редактора CSV создайте CSV-файл с именем: **SurfaceHubConfiguration.csv**

2. Введите список учетных записей устройств и дружественных имен в этом формате:

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. Сохраните файл в корневом диске USB, где вы скопировали файл PPKG.

    > [!div class="mx-imgBorder"]
    > ![Пример файла конфигурации](images/sh2-config-file.png)
