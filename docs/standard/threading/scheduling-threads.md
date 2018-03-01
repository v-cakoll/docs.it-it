---
title: Pianificazione di thread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6bb715c11cc0d9b07e4ea8805ace7680ca92097c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="scheduling-threads"></a><span data-ttu-id="94ec1-102">Pianificazione di thread</span><span class="sxs-lookup"><span data-stu-id="94ec1-102">Scheduling Threads</span></span>
<span data-ttu-id="94ec1-103">A ogni thread è assegnata una priorità specifica.</span><span class="sxs-lookup"><span data-stu-id="94ec1-103">Every thread has a thread priority assigned to it.</span></span> <span data-ttu-id="94ec1-104">Ai thread creati all'interno di Common Language Runtime viene inizialmente assegnata la priorità **ThreadPriority.Normal**.</span><span class="sxs-lookup"><span data-stu-id="94ec1-104">Threads created within the common language runtime are initially assigned the priority of **ThreadPriority.Normal**.</span></span> <span data-ttu-id="94ec1-105">I thread creati esternamente al runtime conservano la priorità che avevano prima di entrare nell'ambiente gestito.</span><span class="sxs-lookup"><span data-stu-id="94ec1-105">Threads created outside the runtime retain the priority they had before they entered the managed environment.</span></span> <span data-ttu-id="94ec1-106">È possibile ottenere o impostare la priorità di un thread con la proprietà **Thread.Priority**.</span><span class="sxs-lookup"><span data-stu-id="94ec1-106">You can get or set the priority of any thread with the **Thread.Priority** property.</span></span>  
  
 <span data-ttu-id="94ec1-107">L'esecuzione dei thread viene pianificata in base alla relativa priorità.</span><span class="sxs-lookup"><span data-stu-id="94ec1-107">Threads are scheduled for execution based on their priority.</span></span> <span data-ttu-id="94ec1-108">Anche se i thread vengono eseguiti all'interno del runtime, a tutti i thread vengono assegnati intervalli di tempo del processore dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="94ec1-108">Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.</span></span> <span data-ttu-id="94ec1-109">I dettagli dell'algoritmo di pianificazione usato per determinare l'ordine in cui vengono eseguiti i thread varia in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="94ec1-109">The details of the scheduling algorithm used to determine the order in which threads are executed varies with each operating system.</span></span> <span data-ttu-id="94ec1-110">In alcuni sistemi operativi, il thread con la priorità più alta (tra quelli eseguibili) è sempre pianificato per essere eseguito per primo.</span><span class="sxs-lookup"><span data-stu-id="94ec1-110">Under some operating systems, the thread with the highest priority (of those threads that can be executed) is always scheduled to run first.</span></span> <span data-ttu-id="94ec1-111">Se sono disponibili più thread con la stessa priorità, l'utilità di pianificazione scorre tali thread assegnando a ciascuno di essi un intervallo di tempo fisso per la loro esecuzione.</span><span class="sxs-lookup"><span data-stu-id="94ec1-111">If multiple threads with the same priority are all available, the scheduler cycles through the threads at that priority, giving each thread a fixed time slice in which to execute.</span></span> <span data-ttu-id="94ec1-112">Finché un thread con una priorità più alta è disponibile per l'esecuzione, i thread con priorità inferiore non verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="94ec1-112">As long as a thread with a higher priority is available to run, lower priority threads do not get to execute.</span></span> <span data-ttu-id="94ec1-113">Quando non sono più presenti thread eseguibili con una priorità specifica, l'utilità di pianificazione passa alla successiva priorità più bassa e pianifica l'esecuzione dei thread associati a tale priorità.</span><span class="sxs-lookup"><span data-stu-id="94ec1-113">When there are no more runnable threads at a given priority, the scheduler moves to the next lower priority and schedules the threads at that priority for execution.</span></span> <span data-ttu-id="94ec1-114">Se un thread con priorità maggiore diventa eseguibile, il thread con priorità inferiore viene interrotto e viene di nuovo consentita l'esecuzione del thread con priorità superiore.</span><span class="sxs-lookup"><span data-stu-id="94ec1-114">If a higher priority thread becomes runnable, the lower priority thread is preempted and the higher priority thread is allowed to execute once again.</span></span> <span data-ttu-id="94ec1-115">Oltre a quanto precedentemente detto, il sistema operativo può anche regolare le priorità dei thread in modo dinamico quando l'interfaccia utente di un'applicazione viene spostata in background dal primo piano.</span><span class="sxs-lookup"><span data-stu-id="94ec1-115">On top of all that, the operating system can also adjust thread priorities dynamically as an application's user interface is moved between foreground and background.</span></span> <span data-ttu-id="94ec1-116">Altri sistemi operativi potrebbero scegliere di usare un algoritmo di pianificazione diverso.</span><span class="sxs-lookup"><span data-stu-id="94ec1-116">Other operating systems might choose to use a different scheduling algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ec1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ec1-117">See Also</span></span>  
 [<span data-ttu-id="94ec1-118">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="94ec1-118">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="94ec1-119">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="94ec1-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
