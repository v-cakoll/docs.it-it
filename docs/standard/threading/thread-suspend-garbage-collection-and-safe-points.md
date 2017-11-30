---
title: Thread.Suspend, operazioni di Garbage Collection e punti sicuri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="a2c31-102">Thread.Suspend, operazioni di Garbage Collection e punti sicuri</span><span class="sxs-lookup"><span data-stu-id="a2c31-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="a2c31-103">Quando si chiama <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> su un thread, il sistema rileva che una sospensione di thread è stato richiesto e consente l'esecuzione fino a quando non è stato raggiunto un punto sicuro prima di sospendere effettivamente il thread del thread.</span><span class="sxs-lookup"><span data-stu-id="a2c31-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="a2c31-104">Un punto sicuro per un thread è un punto nell'esecuzione delle Garbage collection può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="a2c31-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="a2c31-105">Quando viene raggiunto un punto sicuro, il runtime garantisce che il thread sospeso non effettuerà ulteriori progressi nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a2c31-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="a2c31-106">Un thread in esecuzione all'esterno di codice gestito è sempre sicuro per l'operazione di garbage collection e l'esecuzione continua fino a quando non tenta di riprendere l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a2c31-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2c31-107">Per eseguire un'operazione di garbage collection, il runtime deve sospendere tutti i thread eccetto quello che esegue la raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2c31-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="a2c31-108">Ogni thread deve essere portato a un punto sicuro prima di poter essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="a2c31-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c31-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2c31-109">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [<span data-ttu-id="a2c31-110">Threading</span><span class="sxs-lookup"><span data-stu-id="a2c31-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="a2c31-111">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="a2c31-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
