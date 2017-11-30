---
title: ManualResetEvent e ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="f5ae1-102">ManualResetEvent e ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="f5ae1-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="f5ae1-103">La <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> classe rappresenta un evento di handle di attesa locale che deve essere reimpostato manualmente dopo essere stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="f5ae1-104">Questa classe rappresenta un caso speciale della relativa classe base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5ae1-105">Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di impostazione del manuale.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="f5ae1-106">Oggetto <xref:System.Threading.ManualResetEvent> oggetto rimane segnalato fino a quando il relativo <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="f5ae1-107">Qualsiasi numero di thread in attesa, o di thread che attende l'evento dopo che è stato segnalato, può essere rilasciato mentre viene segnalato lo stato dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="f5ae1-108"><xref:System.Threading.ManualResetEvent>corrisponde a un Win32 `CreateEvent` chiama, specificando `true` per il `bManualReset` argomento.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="f5ae1-109">Nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare la <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> classe per ottenere prestazioni migliori quando si prevedono tempi di attesa molto brevi e quando l'evento non supera un limite di processo.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="f5ae1-110"><xref:System.Threading.ManualResetEventSlim>utilizza spin per un breve periodo di tempo durante l'attesa per l'evento venga segnalato.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="f5ae1-111">Quando i tempi di attesa sono brevi, la rotazione può essere molto meno costosa rispetto all'attesa tramite handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="f5ae1-112">Tuttavia, se l'evento non viene segnalato all'interno di un determinato periodo di tempo, <xref:System.Threading.ManualResetEventSlim> ricorre a un periodo di attesa di handle di evento regolare.</span><span class="sxs-lookup"><span data-stu-id="f5ae1-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ae1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ae1-113">See Also</span></span>  
 [<span data-ttu-id="f5ae1-114">Threading</span><span class="sxs-lookup"><span data-stu-id="f5ae1-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="f5ae1-115">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="f5ae1-115">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>  
 [<span data-ttu-id="f5ae1-116">Handle di attesa</span><span class="sxs-lookup"><span data-stu-id="f5ae1-116">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [<span data-ttu-id="f5ae1-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="f5ae1-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="f5ae1-118">SpinWait</span><span class="sxs-lookup"><span data-stu-id="f5ae1-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="f5ae1-119">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="f5ae1-119">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
