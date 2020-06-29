---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator — это простое средство развертывания, с помощью которого организации могут быстро пересоздавать образы устройств Surface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: развертывание, установка, средство
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834392"
---
# <span data-ttu-id="5df75-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="5df75-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="5df75-105">Ускоритель развертывания Microsoft Surface (SDA) автоматизирует создание и настройку рекомендуемого опыта развертывания Майкрософт с помощью бесплатных средств развертывания Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5df75-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="5df75-106">В апреле 2020 для упрощения и автоматизации развертывания изображений Surface в корпоративной среде средство SDA позволяет создавать "Заводский" образ Windows, который можно настроить для организационных требований.</span><span class="sxs-lookup"><span data-stu-id="5df75-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="5df75-107">Открытый источник, управляемый сценарием SDA использует комплект средств оценки и развертывания Windows (ADK) для Windows 10, который упрощает создание образов Windows (WIM) в тестовых и рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="5df75-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="5df75-108">Если последнее приложение ADK еще не установлено, оно будет загружено и установлено при запуске средства SDA.</span><span class="sxs-lookup"><span data-stu-id="5df75-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="5df75-109">Полученное изображение точно соответствует конфигурации изображений восстановления исходного состояния системы (BMR), без предустановленных приложений, таких как Microsoft Office или приложение UWP Surface.</span><span class="sxs-lookup"><span data-stu-id="5df75-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="5df75-110">Чтобы запустить SDA, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5df75-110">To run SDA:</span></span>**

1. <span data-ttu-id="5df75-111">Перейдите на [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="5df75-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="5df75-112">Выберите команду **Копировать или скачать** и ознакомьтесь с файлом readme.</span><span class="sxs-lookup"><span data-stu-id="5df75-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="5df75-113">Внесите в сценарий необходимые переменные для вашей среды, как описано в файле readme и рецензирование перед запуском в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="5df75-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Запуск средства акселератора для развертывания Surface](images/surface-deployment-accelerator.png)

## <span data-ttu-id="5df75-115">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="5df75-115">Related links</span></span>

 - [<span data-ttu-id="5df75-116">Средство развертывания исходного образа, выпущенное в GitHub</span><span class="sxs-lookup"><span data-stu-id="5df75-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="5df75-117">Скачивание и установка Windows ADK</span><span class="sxs-lookup"><span data-stu-id="5df75-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
