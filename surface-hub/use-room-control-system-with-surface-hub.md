---
title: Использование системы управления помещением (Surface Hub)
description: С устройством Microsoft Surface Hub можно использовать системы управления помещением.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: система управления помещением, Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834848"
---
# <span data-ttu-id="94929-104">Использование системы управления помещением (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="94929-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="94929-105">С устройством Microsoft Surface Hub можно использовать системы управления помещением.</span><span class="sxs-lookup"><span data-stu-id="94929-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="94929-106">Для этого необходимо подключить оборудование системы управления к Surface Hub, обычно через последовательный порт RJ11 в нижней части Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="94929-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <span data-ttu-id="94929-107">Параметры терминала</span><span class="sxs-lookup"><span data-stu-id="94929-107">Terminal settings</span></span>

<span data-ttu-id="94929-108">Для подключения к панели системы управления помещением не нужно настраивать параметры терминала.</span><span class="sxs-lookup"><span data-stu-id="94929-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="94929-109">Если вы хотите подключить ПК или ноутбук к Surface Hub и отправлять последовательные команды из Surface Hub, вы можете использовать программу эмулятора терминала, например Tera Term или PuTTY.</span><span class="sxs-lookup"><span data-stu-id="94929-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="94929-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="94929-110">Setting</span></span> | <span data-ttu-id="94929-111">Значение</span><span class="sxs-lookup"><span data-stu-id="94929-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="94929-112">Скорость (бит/с)</span><span class="sxs-lookup"><span data-stu-id="94929-112">Baud rate</span></span> | <span data-ttu-id="94929-113">115200</span><span class="sxs-lookup"><span data-stu-id="94929-113">115200</span></span> |
| <span data-ttu-id="94929-114">Биты данных</span><span class="sxs-lookup"><span data-stu-id="94929-114">Data bits</span></span> | <span data-ttu-id="94929-115">No8</span><span class="sxs-lookup"><span data-stu-id="94929-115">8</span></span> | 
| <span data-ttu-id="94929-116">Стоп-биты</span><span class="sxs-lookup"><span data-stu-id="94929-116">Stop bits</span></span> | <span data-ttu-id="94929-117">1,1</span><span class="sxs-lookup"><span data-stu-id="94929-117">1</span></span> |
| <span data-ttu-id="94929-118">Четность</span><span class="sxs-lookup"><span data-stu-id="94929-118">Parity</span></span> | <span data-ttu-id="94929-119">нет</span><span class="sxs-lookup"><span data-stu-id="94929-119">none</span></span> |
| <span data-ttu-id="94929-120">Управление потоком</span><span class="sxs-lookup"><span data-stu-id="94929-120">Flow control</span></span> | <span data-ttu-id="94929-121">нет</span><span class="sxs-lookup"><span data-stu-id="94929-121">none</span></span> |
| <span data-ttu-id="94929-122">Перевод строки</span><span class="sxs-lookup"><span data-stu-id="94929-122">Line feed</span></span> | <span data-ttu-id="94929-123">каждый возврат каретки</span><span class="sxs-lookup"><span data-stu-id="94929-123">every carriage return</span></span> |
 

## <span data-ttu-id="94929-124">Схема подключения</span><span class="sxs-lookup"><span data-stu-id="94929-124">Wiring diagram</span></span>

<span data-ttu-id="94929-125">Вы можете использовать стандартный разъем RJ-11 (6P6C) для подключения последовательного порта Surface Hub к системе управления помещением.</span><span class="sxs-lookup"><span data-stu-id="94929-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="94929-126">Это рекомендуемый метод.</span><span class="sxs-lookup"><span data-stu-id="94929-126">This is the recommended method.</span></span> <span data-ttu-id="94929-127">Вы также можете использовать 4-жильный кабель RJ-11, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="94929-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="94929-128">На этой схеме показана правильная распайка для кабеля от RJ-11 (6P6C) к DB9.</span><span class="sxs-lookup"><span data-stu-id="94929-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![Изображение монтажной схемы.](images/room-control-wiring-diagram.png)

## <span data-ttu-id="94929-130">Наборы команд</span><span class="sxs-lookup"><span data-stu-id="94929-130">Command sets</span></span>

<span data-ttu-id="94929-131">Системы управления помещением используют общие сценарии конференц-зала для команд.</span><span class="sxs-lookup"><span data-stu-id="94929-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="94929-132">Команды передаются из системы управления по последовательному подключению на устройство Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="94929-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="94929-133">Команды основаны на ASCII, при этом Surface Hub уведомляет пользователя при изменении состояния.</span><span class="sxs-lookup"><span data-stu-id="94929-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="94929-134">Доступны следующие модификаторы команд.</span><span class="sxs-lookup"><span data-stu-id="94929-134">The following command modifiers are available.</span></span> <span data-ttu-id="94929-135">Команды заканчивают символом новой строки (/n).</span><span class="sxs-lookup"><span data-stu-id="94929-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="94929-136">Ответы могут поступать в любое время после изменения состояния, не вызванного непосредственно командой управления портом.</span><span class="sxs-lookup"><span data-stu-id="94929-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="94929-137">Модификатор</span><span class="sxs-lookup"><span data-stu-id="94929-137">Modifier</span></span> | <span data-ttu-id="94929-138">Результат</span><span class="sxs-lookup"><span data-stu-id="94929-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="94929-139">Увеличить значение</span><span class="sxs-lookup"><span data-stu-id="94929-139">Increment a value</span></span> |
| - | <span data-ttu-id="94929-140">Уменьшить значение</span><span class="sxs-lookup"><span data-stu-id="94929-140">Decrease a value</span></span> |
| = | <span data-ttu-id="94929-141">Задать конкретное значение</span><span class="sxs-lookup"><span data-stu-id="94929-141">Set a discrete value</span></span> |
| <span data-ttu-id="94929-142">?</span><span class="sxs-lookup"><span data-stu-id="94929-142">?</span></span> | <span data-ttu-id="94929-143">Запросы текущего значения</span><span class="sxs-lookup"><span data-stu-id="94929-143">Queries for a current value</span></span> |
 

## <span data-ttu-id="94929-144">Питание</span><span class="sxs-lookup"><span data-stu-id="94929-144">Power</span></span>

<span data-ttu-id="94929-145">Surface Hub может находиться в одном из следующих состояний питания.</span><span class="sxs-lookup"><span data-stu-id="94929-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="94929-146">Состояние</span><span class="sxs-lookup"><span data-stu-id="94929-146">State</span></span> | <span data-ttu-id="94929-147">Состояние Energy Star</span><span class="sxs-lookup"><span data-stu-id="94929-147">Energy Star state</span></span>| <span data-ttu-id="94929-148">Описание</span><span class="sxs-lookup"><span data-stu-id="94929-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-149">до</span><span class="sxs-lookup"><span data-stu-id="94929-149">0</span></span> | <span data-ttu-id="94929-150">S5</span><span class="sxs-lookup"><span data-stu-id="94929-150">S5</span></span> | <span data-ttu-id="94929-151">Отключено</span><span class="sxs-lookup"><span data-stu-id="94929-151">Off</span></span> |
| <span data-ttu-id="94929-152">1,1</span><span class="sxs-lookup"><span data-stu-id="94929-152">1</span></span> | - | <span data-ttu-id="94929-153">Питание включено (не определено)</span><span class="sxs-lookup"><span data-stu-id="94929-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="94929-154">2</span><span class="sxs-lookup"><span data-stu-id="94929-154">2</span></span> | <span data-ttu-id="94929-155">S3</span><span class="sxs-lookup"><span data-stu-id="94929-155">S3</span></span> | <span data-ttu-id="94929-156">Спящий режим</span><span class="sxs-lookup"><span data-stu-id="94929-156">Sleep</span></span> |
| <span data-ttu-id="94929-157">5</span><span class="sxs-lookup"><span data-stu-id="94929-157">5</span></span> | <span data-ttu-id="94929-158">S0</span><span class="sxs-lookup"><span data-stu-id="94929-158">S0</span></span> | <span data-ttu-id="94929-159">Готово</span><span class="sxs-lookup"><span data-stu-id="94929-159">Ready</span></span> |


<span data-ttu-id="94929-160">В режиме замены компьютера доступны только состояния питания "Готово" и "Отключено", а меняется только экран.</span><span class="sxs-lookup"><span data-stu-id="94929-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="94929-161">Порт управления невозможно использовать для включения компьютера для замены.</span><span class="sxs-lookup"><span data-stu-id="94929-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="94929-162">Состояние</span><span class="sxs-lookup"><span data-stu-id="94929-162">State</span></span> | <span data-ttu-id="94929-163">Состояние Energy Star</span><span class="sxs-lookup"><span data-stu-id="94929-163">Energy Star state</span></span>| <span data-ttu-id="94929-164">Описание</span><span class="sxs-lookup"><span data-stu-id="94929-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-165">до</span><span class="sxs-lookup"><span data-stu-id="94929-165">0</span></span> | <span data-ttu-id="94929-166">S5</span><span class="sxs-lookup"><span data-stu-id="94929-166">S5</span></span> | <span data-ttu-id="94929-167">Отключено</span><span class="sxs-lookup"><span data-stu-id="94929-167">Off</span></span> |
| <span data-ttu-id="94929-168">5</span><span class="sxs-lookup"><span data-stu-id="94929-168">5</span></span> | <span data-ttu-id="94929-169">S0</span><span class="sxs-lookup"><span data-stu-id="94929-169">S0</span></span> | <span data-ttu-id="94929-170">Готово</span><span class="sxs-lookup"><span data-stu-id="94929-170">Ready</span></span> |

<span data-ttu-id="94929-171">Для устройства управления любое состояние кроме "5 / Готово" считается отключенным.</span><span class="sxs-lookup"><span data-stu-id="94929-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="94929-172">Каждая команда PowerOn приводит к двум изменениям состояния и ответам.</span><span class="sxs-lookup"><span data-stu-id="94929-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="94929-173">Команда</span><span class="sxs-lookup"><span data-stu-id="94929-173">Command</span></span> | <span data-ttu-id="94929-174">Изменение состояния</span><span class="sxs-lookup"><span data-stu-id="94929-174">State change</span></span>| <span data-ttu-id="94929-175">Ответ</span><span class="sxs-lookup"><span data-stu-id="94929-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="94929-176">PowerOn</span></span> | <span data-ttu-id="94929-177">Устройство включается (дисплей и компьютер).</span><span class="sxs-lookup"><span data-stu-id="94929-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="94929-178">Служба на ПК уведомляет SMC о том, что компьютер готов.</span><span class="sxs-lookup"><span data-stu-id="94929-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="94929-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="94929-179">Power=0</span></span></br></br><span data-ttu-id="94929-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="94929-180">Power=5</span></span> |
| <span data-ttu-id="94929-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="94929-181">PowerOff</span></span> | <span data-ttu-id="94929-182">Переход устройства в состояние "эмбиент" (компьютер включен, экран затемняется).</span><span class="sxs-lookup"><span data-stu-id="94929-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="94929-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="94929-183">Power=0</span></span> |
| <span data-ttu-id="94929-184">Power?</span><span class="sxs-lookup"><span data-stu-id="94929-184">Power?</span></span> |  <span data-ttu-id="94929-185">SMC сообщает последнее известное состояние питания.</span><span class="sxs-lookup"><span data-stu-id="94929-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="94929-186">Питание=<#></span><span class="sxs-lookup"><span data-stu-id="94929-186">Power=<#></span></span> |



## <span data-ttu-id="94929-187">Яркость</span><span class="sxs-lookup"><span data-stu-id="94929-187">Brightness</span></span>

<span data-ttu-id="94929-188">Текущий уровень яркости находится в диапазоне от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="94929-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="94929-189">Изменение уровня яркости может инициироваться системой управления помещением или другой системой.</span><span class="sxs-lookup"><span data-stu-id="94929-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="94929-190">Команда</span><span class="sxs-lookup"><span data-stu-id="94929-190">Command</span></span> | <span data-ttu-id="94929-191">Изменение состояния</span><span class="sxs-lookup"><span data-stu-id="94929-191">State change</span></span> |<span data-ttu-id="94929-192">Ответ</span><span class="sxs-lookup"><span data-stu-id="94929-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="94929-193">Brightness+</span></span> | <span data-ttu-id="94929-194">Контроллер управления системой (SMC) отправляет команду увеличения яркости.</span><span class="sxs-lookup"><span data-stu-id="94929-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="94929-195">Служба ПК в системе управления уведомляет SMC о новом уровне яркости.</span><span class="sxs-lookup"><span data-stu-id="94929-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="94929-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="94929-196">Brightness = 51</span></span> |
| <span data-ttu-id="94929-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="94929-197">Brightness-</span></span> |  <span data-ttu-id="94929-198">SMC отправляет команду уменьшения яркости.</span><span class="sxs-lookup"><span data-stu-id="94929-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="94929-199">Служба на ПК уведомляет SMC о новом уровне яркости.</span><span class="sxs-lookup"><span data-stu-id="94929-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="94929-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="94929-200">Brightness = 50</span></span> |

## <span data-ttu-id="94929-201">Volume</span><span class="sxs-lookup"><span data-stu-id="94929-201">Volume</span></span>

<span data-ttu-id="94929-202">Текущий уровень громкости находится в диапазоне от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="94929-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="94929-203">Изменение уровня громкости может инициироваться системой управления помещением или другой системой.</span><span class="sxs-lookup"><span data-stu-id="94929-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="94929-204">Команда "Volume" управляет только громкостью для режима встроенного компьютера или компьютера на замену, а не из [источников "Guest"](connect-and-display-with-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="94929-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="94929-205">Команда</span><span class="sxs-lookup"><span data-stu-id="94929-205">Command</span></span> | <span data-ttu-id="94929-206">Изменение состояния</span><span class="sxs-lookup"><span data-stu-id="94929-206">State change</span></span> | <span data-ttu-id="94929-207">Ответ</span><span class="sxs-lookup"><span data-stu-id="94929-207">Response</span></span></br><span data-ttu-id="94929-208">(Включено в [режиме компьютера на замену](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="94929-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="94929-209">Volume+</span></span> |  <span data-ttu-id="94929-210">SMC отправляет команду увеличения громкости.</span><span class="sxs-lookup"><span data-stu-id="94929-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="94929-211">Служба на ПК уведомляет SMC о новом уровне громкости.</span><span class="sxs-lookup"><span data-stu-id="94929-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="94929-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="94929-212">Volume = 51</span></span> |
| <span data-ttu-id="94929-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="94929-213">Volume-</span></span> |  <span data-ttu-id="94929-214">SMC отправляет команду уменьшения громкости.</span><span class="sxs-lookup"><span data-stu-id="94929-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="94929-215">Служба на ПК уведомляет SMC о новом уровне громкости.</span><span class="sxs-lookup"><span data-stu-id="94929-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="94929-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="94929-216">Volume = 50</span></span> |


 

## <span data-ttu-id="94929-217">Отключение звука</span><span class="sxs-lookup"><span data-stu-id="94929-217">Mute for audio</span></span>

<span data-ttu-id="94929-218">Звук можно отключить.</span><span class="sxs-lookup"><span data-stu-id="94929-218">Audio can be muted.</span></span>

| <span data-ttu-id="94929-219">Команда</span><span class="sxs-lookup"><span data-stu-id="94929-219">Command</span></span> | <span data-ttu-id="94929-220">Изменение состояния</span><span class="sxs-lookup"><span data-stu-id="94929-220">State change</span></span> | <span data-ttu-id="94929-221">Ответ</span><span class="sxs-lookup"><span data-stu-id="94929-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="94929-222">AudioMute+</span></span> |  <span data-ttu-id="94929-223">SMC отправляет команду отключения звука.</span><span class="sxs-lookup"><span data-stu-id="94929-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="94929-224">Служба на ПК уведомляет SMC о том, что звук отключен.</span><span class="sxs-lookup"><span data-stu-id="94929-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="94929-225">нет</span><span class="sxs-lookup"><span data-stu-id="94929-225">none</span></span> |


 

## <span data-ttu-id="94929-226">Источник видео</span><span class="sxs-lookup"><span data-stu-id="94929-226">Video source</span></span>

<span data-ttu-id="94929-227">Вы можете использовать несколько источников изображения.</span><span class="sxs-lookup"><span data-stu-id="94929-227">Several display sources can be used.</span></span>

| <span data-ttu-id="94929-228">Состояние</span><span class="sxs-lookup"><span data-stu-id="94929-228">State</span></span> | <span data-ttu-id="94929-229">Описание</span><span class="sxs-lookup"><span data-stu-id="94929-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="94929-230">до</span><span class="sxs-lookup"><span data-stu-id="94929-230">0</span></span> |  <span data-ttu-id="94929-231">Бортовой ПК</span><span class="sxs-lookup"><span data-stu-id="94929-231">Onboard PC</span></span> |
| <span data-ttu-id="94929-232">1,1</span><span class="sxs-lookup"><span data-stu-id="94929-232">1</span></span> |  <span data-ttu-id="94929-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="94929-233">DisplayPort</span></span> |
| <span data-ttu-id="94929-234">2</span><span class="sxs-lookup"><span data-stu-id="94929-234">2</span></span> |  <span data-ttu-id="94929-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="94929-235">HDMI</span></span> |
| <span data-ttu-id="94929-236">Трехконтактный</span><span class="sxs-lookup"><span data-stu-id="94929-236">3</span></span> |  <span data-ttu-id="94929-237">VGA</span><span class="sxs-lookup"><span data-stu-id="94929-237">VGA</span></span> |


 

<span data-ttu-id="94929-238">Изменение источника отображения может быть запрошено системой управления помещением или другой системой.</span><span class="sxs-lookup"><span data-stu-id="94929-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="94929-239">Команда</span><span class="sxs-lookup"><span data-stu-id="94929-239">Command</span></span> | <span data-ttu-id="94929-240">Изменение состояния</span><span class="sxs-lookup"><span data-stu-id="94929-240">State change</span></span> | <span data-ttu-id="94929-241">Ответ</span><span class="sxs-lookup"><span data-stu-id="94929-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="94929-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="94929-242">Source=#</span></span> |  <span data-ttu-id="94929-243">SMC изменяет источник.</span><span class="sxs-lookup"><span data-stu-id="94929-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="94929-244">Служба на ПК уведомляет SMC об изменении источника изображения.</span><span class="sxs-lookup"><span data-stu-id="94929-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="94929-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="94929-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="94929-246">Source+</span><span class="sxs-lookup"><span data-stu-id="94929-246">Source+</span></span> |  <span data-ttu-id="94929-247">SMC переходит к следующему активному источнику входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="94929-248">Служба на ПК уведомляет SMC о текущем источнике входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="94929-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="94929-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="94929-250">Source-</span><span class="sxs-lookup"><span data-stu-id="94929-250">Source-</span></span> | <span data-ttu-id="94929-251">SMC переходит к предыдущему активному источнику входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="94929-252">Служба на ПК уведомляет SMC о текущем источнике входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="94929-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="94929-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="94929-254">Source?</span><span class="sxs-lookup"><span data-stu-id="94929-254">Source?</span></span> |  <span data-ttu-id="94929-255">SMC запрашивает у службы на ПК активный источник входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="94929-256">Служба на ПК уведомляет SMC о текущем источнике входных данных.</span><span class="sxs-lookup"><span data-stu-id="94929-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="94929-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="94929-257">Source=&lt;#&gt;</span></span> |

## <span data-ttu-id="94929-258">Ошибки</span><span class="sxs-lookup"><span data-stu-id="94929-258">Errors</span></span>

<span data-ttu-id="94929-259">Ошибки возвращаются в формате, описанном в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="94929-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="94929-260">Ошибка</span><span class="sxs-lookup"><span data-stu-id="94929-260">Error</span></span> | <span data-ttu-id="94929-261">Примечания</span><span class="sxs-lookup"><span data-stu-id="94929-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="94929-262">Ошибка: неизвестная команда &lt;input&gt;.</span><span class="sxs-lookup"><span data-stu-id="94929-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="94929-263">Инструкция содержит неизвестную начальную команду.</span><span class="sxs-lookup"><span data-stu-id="94929-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="94929-264">Например, &quot;VOL+&quot; — это недопустимая команда, которая возвращает сообщение &quot;Ошибка: неизвестная команда VOL&quot;.</span><span class="sxs-lookup"><span data-stu-id="94929-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="94929-265">Ошибка: неизвестный оператор &lt;input&gt;.</span><span class="sxs-lookup"><span data-stu-id="94929-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="94929-266">Инструкция содержит неизвестный оператор.</span><span class="sxs-lookup"><span data-stu-id="94929-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="94929-267">Например, &quot;Volume!&quot; — неверная команда, которая возвращает сообщение &quot; Ошибка: неизвестный оператор '!'&quot;.</span><span class="sxs-lookup"><span data-stu-id="94929-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="94929-268">Ошибка: неизвестный параметр &lt;input&gt;.</span><span class="sxs-lookup"><span data-stu-id="94929-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="94929-269">Инструкция содержит неизвестный параметр.</span><span class="sxs-lookup"><span data-stu-id="94929-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="94929-270">Например, &quot;Volume=abc&quot; — неправильная команда, которая возвращает сообщение &quot;Ошибка: неизвестный параметр abc&quot;.</span><span class="sxs-lookup"><span data-stu-id="94929-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="94929-271">Ошибка: команда недоступна, если &lt;input&gt; выключен.</span><span class="sxs-lookup"><span data-stu-id="94929-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="94929-272">Если устройство Surface Hub выключено, все команды, кроме команд питания, возвращают данную ошибку.</span><span class="sxs-lookup"><span data-stu-id="94929-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="94929-273">Например, &quot;Volume+&quot; — неверная команда, которая возвращает сообщение &quot;Ошибка: команда недоступна, если громкость выключена&quot;.</span><span class="sxs-lookup"><span data-stu-id="94929-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <span data-ttu-id="94929-274">Еще по теме</span><span class="sxs-lookup"><span data-stu-id="94929-274">Related topics</span></span>


[<span data-ttu-id="94929-275">Управление Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="94929-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="94929-276">Руководство администратора Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="94929-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





