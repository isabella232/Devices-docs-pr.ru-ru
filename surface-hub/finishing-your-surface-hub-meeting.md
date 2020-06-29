---
title: Завершить сеанс— завершение собрания Surface Hub
description: Чтобы завершить собрание Surface Hub, коснитесь "Завершить сеанс". Surface Hub очищает состояние приложения, состояние операционной системы и пользовательский интерфейс, чтобы подготовиться к следующему собранию.
keywords: Готово, закончить собрание Surface Hub, завершить собрание Surface Hub, очистить собрание Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836235"
---
# <span data-ttu-id="83ecb-105">Завершение собрания Surface Hub с помощью кнопки "Завершить сеанс"</span><span class="sxs-lookup"><span data-stu-id="83ecb-105">End a Surface Hub meeting with End session</span></span>
<span data-ttu-id="83ecb-106">Surface Hub— это устройство для совместной работы разных групп людей в местах для собраний.</span><span class="sxs-lookup"><span data-stu-id="83ecb-106">Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.</span></span> <span data-ttu-id="83ecb-107">В конце собрания пользователи могут коснуться кнопки **Завершить сеанс**, чтобы удалить конфиденциальные данные и подготовить устройство к следующему собранию.</span><span class="sxs-lookup"><span data-stu-id="83ecb-107">At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.</span></span> <span data-ttu-id="83ecb-108">Surface Hub очистит или сбросит следующие состояния:</span><span class="sxs-lookup"><span data-stu-id="83ecb-108">Surface Hub will clean up, or reset, the following states:</span></span>
- <span data-ttu-id="83ecb-109">Приложения</span><span class="sxs-lookup"><span data-stu-id="83ecb-109">Applications</span></span>
- <span data-ttu-id="83ecb-110">Операционная система</span><span class="sxs-lookup"><span data-stu-id="83ecb-110">Operating system</span></span>
- <span data-ttu-id="83ecb-111">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="83ecb-111">User interface</span></span>

<span data-ttu-id="83ecb-112">В этом разделе объясняется, что именно сбрасывается для каждого из этих состояний при нажатии кнопки **Завершить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="83ecb-112">This topic explains what **End session** resets for each of these states.</span></span>

## <span data-ttu-id="83ecb-113">Приложения</span><span class="sxs-lookup"><span data-stu-id="83ecb-113">Applications</span></span>
<span data-ttu-id="83ecb-114">При запуске приложений на Surface Hub они сохраняются в памяти, а данные хранятся на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="83ecb-114">When you start apps on Surface Hub, they are stored in memory and data is stored at the application level.</span></span> <span data-ttu-id="83ecb-115">Данные будут доступны для всех пользователей во время этого сеанса (или собрания) до удаления или перезаписи даты.</span><span class="sxs-lookup"><span data-stu-id="83ecb-115">Data is available to all users during that session (or meeting) until date is removed or overwritten.</span></span> <span data-ttu-id="83ecb-116">При нажатии кнопки **Завершить сеанс** состояние приложения Surface Hub очищается при закрытии приложения, удалении журнала браузера, сбросе приложений и удалении журналов Skype.</span><span class="sxs-lookup"><span data-stu-id="83ecb-116">When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.</span></span>

### <span data-ttu-id="83ecb-117">Закрытие приложений</span><span class="sxs-lookup"><span data-stu-id="83ecb-117">Close applications</span></span>
<span data-ttu-id="83ecb-118">Surface Hub закрывает все видимые окна, включая приложения Win32 и приложения универсальной платформы Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="83ecb-118">Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications.</span></span> <span data-ttu-id="83ecb-119">При закрытии приложение использует многозадачное представление и запрашивает видимые окна.</span><span class="sxs-lookup"><span data-stu-id="83ecb-119">The application close stage uses the multitasking view to query the visible windows.</span></span> <span data-ttu-id="83ecb-120">Окна Win32, которые не закроются за определенное время, будут закрыты с помощью **TerminateProcess**.</span><span class="sxs-lookup"><span data-stu-id="83ecb-120">Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.</span></span> 
   
### <span data-ttu-id="83ecb-121">Удаление журнала браузера</span><span class="sxs-lookup"><span data-stu-id="83ecb-121">Delete browser history</span></span>
<span data-ttu-id="83ecb-122">Surface Hub использует функцию удаления журнала браузера (DBH) в Edge, чтобы очистить журнал и кэшированные данные Edge.</span><span class="sxs-lookup"><span data-stu-id="83ecb-122">Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data.</span></span> <span data-ttu-id="83ecb-123">Точно так же пользователь может очистить журнал браузера вручную, но функция **Завершить сеанс**, кроме этого, обеспечивает удаление информации о состояниях приложения и данных до начала следующего сеанса или собрания.</span><span class="sxs-lookup"><span data-stu-id="83ecb-123">This is similar to how a user can clear out their browser history manually, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.</span></span> 
 
### <span data-ttu-id="83ecb-124">Сброс приложений</span><span class="sxs-lookup"><span data-stu-id="83ecb-124">Reset applications</span></span>
<span data-ttu-id="83ecb-125">Функция **Завершить сеанс** сбрасывает состояние каждого приложения, установленного на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="83ecb-125">**End session** resets the state of each application that is installed on the Surface Hub.</span></span> <span data-ttu-id="83ecb-126">Сброс приложения очищает все фоновые задачи, данные приложения, уведомления и диалоговые окна согласия пользователя.</span><span class="sxs-lookup"><span data-stu-id="83ecb-126">Resetting an application clears all background tasks, application data, notifications, and user consent dialogs.</span></span> <span data-ttu-id="83ecb-127">Приложения возвращаются в состояние первого запуска для следующих людей, которые будут использовать Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="83ecb-127">Applications are returned to their first-run state for the next people that use Surface Hub.</span></span>  
 
### <span data-ttu-id="83ecb-128">Удаление журналов Skype</span><span class="sxs-lookup"><span data-stu-id="83ecb-128">Remove Skype logs</span></span>
<span data-ttu-id="83ecb-129">Skype не хранит персональные данные на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="83ecb-129">Skype does not store personally-identifiable information on Surface Hub.</span></span> <span data-ttu-id="83ecb-130">Информация хранится в службе Skype в соответствии с существующими рекомендациями по Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="83ecb-130">Information is stored in the Skype service to meet existing Skype for Business guidance.</span></span> <span data-ttu-id="83ecb-131">При нажатии кнопки **Завершить сеанс** удаляются только локальные данные журнала Skype.</span><span class="sxs-lookup"><span data-stu-id="83ecb-131">Local Skype logging information is the only data removed when **End session** is selected.</span></span> <span data-ttu-id="83ecb-132">Это также относится к журналам платформы Unified Communications Client Platform (UCCP) и журналам мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="83ecb-132">This includes Unified Communications Client Platform (UCCP) logs and media logs.</span></span>   

## <span data-ttu-id="83ecb-133">Операционная система</span><span class="sxs-lookup"><span data-stu-id="83ecb-133">Operating System</span></span>
<span data-ttu-id="83ecb-134">Операционная система содержит различные сведения о состоянии сеансов, которые необходимо очищать после каждого собрания Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="83ecb-134">The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.</span></span> 

### <span data-ttu-id="83ecb-135">Файловая система</span><span class="sxs-lookup"><span data-stu-id="83ecb-135">File System</span></span>
<span data-ttu-id="83ecb-136">Участники собрания получают доступ к ограниченному набору каталогов на Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="83ecb-136">Meeting attendees have access to a limited set of directories on the Surface Hub.</span></span> <span data-ttu-id="83ecb-137">При нажатии кнопки **Завершить сеанс** Surface Hub очищает эти каталоги:</span><span class="sxs-lookup"><span data-stu-id="83ecb-137">When **End session** is selected, Surface Hub clears these directories:</span></span><br>
- <span data-ttu-id="83ecb-138">Музыка</span><span class="sxs-lookup"><span data-stu-id="83ecb-138">Music</span></span>
- <span data-ttu-id="83ecb-139">Видео</span><span class="sxs-lookup"><span data-stu-id="83ecb-139">Videos</span></span>
- <span data-ttu-id="83ecb-140">Документы</span><span class="sxs-lookup"><span data-stu-id="83ecb-140">Documents</span></span>
- <span data-ttu-id="83ecb-141">Изображения</span><span class="sxs-lookup"><span data-stu-id="83ecb-141">Pictures</span></span>
- <span data-ttu-id="83ecb-142">Загрузки</span><span class="sxs-lookup"><span data-stu-id="83ecb-142">Downloads</span></span>

<span data-ttu-id="83ecb-143">Кроме того, Surface Hub очищает следующие каталоги, так как многие приложения часто записывают в них данные:</span><span class="sxs-lookup"><span data-stu-id="83ecb-143">Surface Hub also clears these directories, since many applications often write to them:</span></span>
- <span data-ttu-id="83ecb-144">Рабочий стол</span><span class="sxs-lookup"><span data-stu-id="83ecb-144">Desktop</span></span>
- <span data-ttu-id="83ecb-145">Избранное</span><span class="sxs-lookup"><span data-stu-id="83ecb-145">Favorites</span></span>
- <span data-ttu-id="83ecb-146">Недавние документы</span><span class="sxs-lookup"><span data-stu-id="83ecb-146">Recent</span></span>
- <span data-ttu-id="83ecb-147">Общие документы</span><span class="sxs-lookup"><span data-stu-id="83ecb-147">Public Documents</span></span>
- <span data-ttu-id="83ecb-148">Общая музыка</span><span class="sxs-lookup"><span data-stu-id="83ecb-148">Public Music</span></span>
- <span data-ttu-id="83ecb-149">Общие видео</span><span class="sxs-lookup"><span data-stu-id="83ecb-149">Public Videos</span></span>
- <span data-ttu-id="83ecb-150">Общие загрузки</span><span class="sxs-lookup"><span data-stu-id="83ecb-150">Public Downloads</span></span>

### <span data-ttu-id="83ecb-151">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="83ecb-151">Credentials</span></span>
<span data-ttu-id="83ecb-152">Учетные данные пользователей, которые хранятся в **TokenBroker**, **PasswordVault** или **диспетчере учетных данных**, удаляются при нажатии кнопки **Завершить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="83ecb-152">User credentials that are stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.</span></span>

## <span data-ttu-id="83ecb-153">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="83ecb-153">User interface</span></span>
<span data-ttu-id="83ecb-154">При нажатии кнопки **Завершить сеанс** параметры пользовательского интерфейса возвращаются к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83ecb-154">User interface (UI) settings are returned to their default values when **End session** is selected.</span></span> 

### <span data-ttu-id="83ecb-155">Элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="83ecb-155">UI items</span></span>
- <span data-ttu-id="83ecb-156">Сброс быстрых действий до состояния по умолчанию</span><span class="sxs-lookup"><span data-stu-id="83ecb-156">Reset Quick Actions to default state</span></span>
- <span data-ttu-id="83ecb-157">Очистка всплывающих уведомлений</span><span class="sxs-lookup"><span data-stu-id="83ecb-157">Clear Toast notifications</span></span>
- <span data-ttu-id="83ecb-158">Сброс уровней громкости</span><span class="sxs-lookup"><span data-stu-id="83ecb-158">Reset volume levels</span></span>
- <span data-ttu-id="83ecb-159">Сброс ширины боковой панели</span><span class="sxs-lookup"><span data-stu-id="83ecb-159">Reset sidebar width</span></span>
- <span data-ttu-id="83ecb-160">Сброс макета режима планшета</span><span class="sxs-lookup"><span data-stu-id="83ecb-160">Reset tablet mode layout</span></span>
- <span data-ttu-id="83ecb-161">Выход пользователя из собрания Office 365 и файлов</span><span class="sxs-lookup"><span data-stu-id="83ecb-161">Sign user out of Office 365 meetings and files</span></span>

### <span data-ttu-id="83ecb-162">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="83ecb-162">Accessibility</span></span>
<span data-ttu-id="83ecb-163">При нажатии кнопки **Завершить сеанс** функции и приложения специальных возможностей возвращаются к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83ecb-163">Accessibility features and apps are returned to default settings when **End session** is selected.</span></span>
- <span data-ttu-id="83ecb-164">Клавиши фильтра</span><span class="sxs-lookup"><span data-stu-id="83ecb-164">Filter keys</span></span>
- <span data-ttu-id="83ecb-165">Высокая контрастность</span><span class="sxs-lookup"><span data-stu-id="83ecb-165">High contrast</span></span>
- <span data-ttu-id="83ecb-166">Залипание клавиш</span><span class="sxs-lookup"><span data-stu-id="83ecb-166">Sticky keys</span></span>
- <span data-ttu-id="83ecb-167">Клавиши-переключатели</span><span class="sxs-lookup"><span data-stu-id="83ecb-167">Toggle keys</span></span>
- <span data-ttu-id="83ecb-168">Клавиши управления курсором мыши</span><span class="sxs-lookup"><span data-stu-id="83ecb-168">Mouse keys</span></span>
- <span data-ttu-id="83ecb-169">Экранная лупа</span><span class="sxs-lookup"><span data-stu-id="83ecb-169">Magnifier</span></span>
- <span data-ttu-id="83ecb-170">Экранный диктор</span><span class="sxs-lookup"><span data-stu-id="83ecb-170">Narrator</span></span>

### <span data-ttu-id="83ecb-171">Буфер обмена</span><span class="sxs-lookup"><span data-stu-id="83ecb-171">Clipboard</span></span>
<span data-ttu-id="83ecb-172">Буфер обмена очищается, чтобы удалить данные, которые копировались в него во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="83ecb-172">The clipboard is cleared to remove data that was copied to the clipboard during the session.</span></span> 

## <span data-ttu-id="83ecb-173">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="83ecb-173">Frequently asked questions</span></span>
**<span data-ttu-id="83ecb-174">Что произойдет, если я забуду нажать кнопку "Завершить сеанс" в конце собрания и устройством Surface Hub воспользуется другой пользователь?</span><span class="sxs-lookup"><span data-stu-id="83ecb-174">What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?</span></span>**<br>
<span data-ttu-id="83ecb-175">Surface Hub очищает содержимое собрания, только когда пользователи касаются кнопки **Завершить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="83ecb-175">Surface Hub only cleans up meeting content when users tap **End session**.</span></span> <span data-ttu-id="83ecb-176">Если покинуть собрание, не касаясь кнопки **Завершить сеанс**, на устройстве через некоторое время снова отобразится экран приветствия.</span><span class="sxs-lookup"><span data-stu-id="83ecb-176">If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time.</span></span> <span data-ttu-id="83ecb-177">На экране приветствия пользователи имеют возможность продолжить предыдущий сеанс или начать новый.</span><span class="sxs-lookup"><span data-stu-id="83ecb-177">From the welcome screen, users have the option to resume the previous session or start a new one.</span></span> <span data-ttu-id="83ecb-178">Вы также можете отключить возможность возобновлять сеанс, если кнопка **Завершить сеанс** не нажата.</span><span class="sxs-lookup"><span data-stu-id="83ecb-178">You can also disable the ability to resume a session if **End session** is not pressed.</span></span>

**<span data-ttu-id="83ecb-179">Можно ли восстановить документы?</span><span class="sxs-lookup"><span data-stu-id="83ecb-179">Are documents recoverable?</span></span>**<br> <span data-ttu-id="83ecb-180">Удаление файлов с жесткого диска при нажатии кнопки **Завершить сеанс** происходит точно так же, как и в любом другом случае.</span><span class="sxs-lookup"><span data-stu-id="83ecb-180">Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive.</span></span> <span data-ttu-id="83ecb-181">Возможно, стороннее программное обеспечение сможет восстановить данные на жестком диске, но Surface Hub не поддерживает функцию восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="83ecb-181">Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub.</span></span> <span data-ttu-id="83ecb-182">Чтобы предотвратить потерю данных, всегда сохраняйте нужные данные, прежде чем покинуть собрание.</span><span class="sxs-lookup"><span data-stu-id="83ecb-182">To prevent data loss, always save the data you need before leaving a meeting.</span></span>

**<span data-ttu-id="83ecb-183">Соответствуют ли действия по очистке данных с помощью кнопки "Завершить сеанс" стандарту Министерства обороны США по очистке и уничтожению данных DoD 5220.22-M?</span><span class="sxs-lookup"><span data-stu-id="83ecb-183">Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?</span></span>**<br>
<span data-ttu-id="83ecb-184">Нет.</span><span class="sxs-lookup"><span data-stu-id="83ecb-184">No.</span></span> <span data-ttu-id="83ecb-185">Сейчас действия по очистке с помощью кнопки **Завершить сеанс** не соответствуют этому стандарту.</span><span class="sxs-lookup"><span data-stu-id="83ecb-185">Currently, the clean-up actions from **End session** do not comply with this standard.</span></span>  
  
