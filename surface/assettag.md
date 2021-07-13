---
title: Средство тегов surface Asset
description: В этом разделе объясняется, как использовать средство тегов Surface Asset.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643835"
---
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="5a293-103">Средство тегов surface Asset</span><span class="sxs-lookup"><span data-stu-id="5a293-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="5a293-104">Surface Asset Tag — это утилита интерфейса командной строки (CLI), которая позволяет просматривать, назначать и изменять назначенное значение тега активов для устройств Surface.</span><span class="sxs-lookup"><span data-stu-id="5a293-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="5a293-105">Он работает на Surface Pro 3 и на всех более новых устройствах Surface.</span><span class="sxs-lookup"><span data-stu-id="5a293-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="5a293-106">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="5a293-106">System requirements</span></span>

- <span data-ttu-id="5a293-107">Surface Pro 3 или более поздней</span><span class="sxs-lookup"><span data-stu-id="5a293-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="5a293-108">Прошивка UEFI версии 3.9.150.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="5a293-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="5a293-109">Использование тега Surface Asset</span><span class="sxs-lookup"><span data-stu-id="5a293-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="5a293-110">Для запуска тега Surface Asset:</span><span class="sxs-lookup"><span data-stu-id="5a293-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="5a293-111">На устройстве Surface скачайте **surface Asset Tag.zip** центра загрузки Майкрософт, извлеките почтовый файл и сохраните AssetTag.exe в нужной папке (в этом примере C:\\assets). [](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="5a293-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a293-112">Для Surface Pro X используйте приложение с именем **AssetTag_x86** в файле ZIP.</span><span class="sxs-lookup"><span data-stu-id="5a293-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="5a293-113">Откройте консоль команды в качестве администратора и запустите AssetTag.exe, введите полный путь к инструменту.</span><span class="sxs-lookup"><span data-stu-id="5a293-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="5a293-114">Перезапустите Surface.</span><span class="sxs-lookup"><span data-stu-id="5a293-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a293-115">После настройки тега актива требуется вторая перезагрузка, прежде чем он появится в WMI.</span><span class="sxs-lookup"><span data-stu-id="5a293-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="5a293-116">Команды средств тегов активов</span><span class="sxs-lookup"><span data-stu-id="5a293-116">Asset Tag tool commands</span></span>

<span data-ttu-id="5a293-117">В следующих примерах AssetTag.exe в каталоге локального компьютера (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="5a293-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="5a293-118">Чтобы получить предложенный тег активов, **запустите AssetTag -g:**</span><span class="sxs-lookup"><span data-stu-id="5a293-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="5a293-119">Чтобы очистить предложенный тег активов, **запустите AssetTag -s:**</span><span class="sxs-lookup"><span data-stu-id="5a293-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="5a293-120">Чтобы установить предложенный тег активов, **запустите AssetTag -s testassettag12:**</span><span class="sxs-lookup"><span data-stu-id="5a293-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="5a293-121">Значение тега актива должно содержать от 1 до 36 символов.</span><span class="sxs-lookup"><span data-stu-id="5a293-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="5a293-122">Допустимые символы включают A-Z, a-z, 0-9, period (.) и hyphen (-).</span><span class="sxs-lookup"><span data-stu-id="5a293-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="5a293-123">Управление тегами активов</span><span class="sxs-lookup"><span data-stu-id="5a293-123">Managing asset tags</span></span>

<span data-ttu-id="5a293-124">Вы можете просмотреть существующий тег актива в параметрах UEFI в статье Сведения об устройстве (панель управления >**восстановления > advanced startup > перезапуска**сейчас.)</span><span class="sxs-lookup"><span data-stu-id="5a293-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="5a293-125">На рисунке ниже показаны результаты запуска средства тегов активов в Surface Go.</span><span class="sxs-lookup"><span data-stu-id="5a293-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![Результаты запуска средства Теги surface Asset на Surface Go.](images/assettag-fig1.png)

> **<span data-ttu-id="5a293-127&quot;>Рисунок 1.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5a293-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;5a293-128&quot;>Результаты запуска средства тегов surface Asset на Surface Go</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5a293-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;5a293-129&quot;>Поочередно можно использовать WMI для запроса существующего тега активов на устройстве:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5a293-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;5a293-130&quot;>(Get-WmiObject -query &quot;Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="5a293-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="5a293-131">Пример</span><span class="sxs-lookup"><span data-stu-id="5a293-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="5a293-132">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a293-132">Using PowerShell</span></span>

<span data-ttu-id="5a293-133">Сценарий ниже можно использовать для получения предлагаемого значения и интерпретации ошибок.</span><span class="sxs-lookup"><span data-stu-id="5a293-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```
