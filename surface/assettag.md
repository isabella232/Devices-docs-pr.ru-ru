---
title: Инструмент тега актива Surface
description: В этой статье объясняется, как использовать инструмент тега актива Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834747"
---
# <span data-ttu-id="da2d7-103">Инструмент тега актива Surface</span><span class="sxs-lookup"><span data-stu-id="da2d7-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="da2d7-104">Тег актива Surface — это служебная программа интерфейса командной строки (CLI), позволяющая просматривать, назначать и изменять назначенные значения тегов ресурсов для устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="da2d7-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="da2d7-105">Она работает на Surface Pro 3 и всех современных устройствах Surface.</span><span class="sxs-lookup"><span data-stu-id="da2d7-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="da2d7-106">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="da2d7-106">System requirements</span></span>

- <span data-ttu-id="da2d7-107">Surface Pro 3 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="da2d7-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="da2d7-108">Встроенное по UEFI версии 3.9.150.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="da2d7-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="da2d7-109">Использование тега актива Surface</span><span class="sxs-lookup"><span data-stu-id="da2d7-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="da2d7-110">Чтобы запустить тег актива Surface, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="da2d7-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="da2d7-111">На устройстве Surface Скачайте **ресурс surface Tag.zip** из [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=46703), извлеките zip-файл и AssetTag.exe сохраните его в нужной папке (в этом примере — C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="da2d7-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="da2d7-112">Для Surface Pro X используйте приложение с именем **AssetTag_x86** в ZIP-файле.</span><span class="sxs-lookup"><span data-stu-id="da2d7-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="da2d7-113">Откройте командную консоль от имени администратора и запустите AssetTag.exe, указав полный путь к инструменту.</span><span class="sxs-lookup"><span data-stu-id="da2d7-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="da2d7-114">Перезапустите Surface.</span><span class="sxs-lookup"><span data-stu-id="da2d7-114">Restart Surface.</span></span>

### <span data-ttu-id="da2d7-115">Команды инструмента «тег актива»</span><span class="sxs-lookup"><span data-stu-id="da2d7-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="da2d7-116">В приведенных ниже примерах AssetTag.exe сохраняется в каталоге на локальном компьютере (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="da2d7-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="da2d7-117">Чтобы получить нужный тег актива, выполните AssetTag-g.</span><span class="sxs-lookup"><span data-stu-id="da2d7-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="da2d7-118">Пример.</span><span class="sxs-lookup"><span data-stu-id="da2d7-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="da2d7-119">Чтобы очистить предложенный тег актива, выполните AssetTag-s.</span><span class="sxs-lookup"><span data-stu-id="da2d7-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="da2d7-120">Пример.</span><span class="sxs-lookup"><span data-stu-id="da2d7-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="da2d7-121">Чтобы установить предложенный тег актива, выполните AssetTag-s testassettag12.</span><span class="sxs-lookup"><span data-stu-id="da2d7-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="da2d7-122">Пример.</span><span class="sxs-lookup"><span data-stu-id="da2d7-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="da2d7-123">Значение тега актива должно содержать от 1 до 36 символов.</span><span class="sxs-lookup"><span data-stu-id="da2d7-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="da2d7-124">Допустимые символы включают A-Z, a-z, 0-9, точки (.) и дефис (-).</span><span class="sxs-lookup"><span data-stu-id="da2d7-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="da2d7-125">Управление тегами ресурсов</span><span class="sxs-lookup"><span data-stu-id="da2d7-125">Managing asset tags</span></span>

<span data-ttu-id="da2d7-126">Вы можете просмотреть существующий тег актива в параметрах UEFI в разделе сведения об устройстве (**Панель управления > восстановление > Расширенная загрузка > перезапустить прямо сейчас**.)</span><span class="sxs-lookup"><span data-stu-id="da2d7-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="da2d7-127">На рисунке ниже показаны результаты выполнения инструмента "тег актива" на Surface go.</span><span class="sxs-lookup"><span data-stu-id="da2d7-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="da2d7-128">Результаты выполнения инструмента тега актива Surface на Surface go.</span><span class="sxs-lookup"><span data-stu-id="da2d7-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="da2d7-129">Рисунок 1.</span><span class="sxs-lookup"><span data-stu-id="da2d7-129">Figure 1.</span></span>** <span data-ttu-id="da2d7-130">Результаты выполнения инструмента тега актива Surface на Surface Go</span><span class="sxs-lookup"><span data-stu-id="da2d7-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="da2d7-131">Кроме того, с помощью WMI можно запросить существующий тег актива на устройстве.</span><span class="sxs-lookup"><span data-stu-id="da2d7-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="da2d7-132">(Get-WmiObject-запрос "SELECT \* FROM Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="da2d7-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="da2d7-133">Пример.</span><span class="sxs-lookup"><span data-stu-id="da2d7-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="da2d7-134">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="da2d7-134">Using PowerShell</span></span>

<span data-ttu-id="da2d7-135">Ниже приведен сценарий, который можно использовать для того, чтобы вычислить предлагаемое значение и интерпретировать все ошибки.</span><span class="sxs-lookup"><span data-stu-id="da2d7-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
