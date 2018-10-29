---
title: ManualResetEvent e ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85d0c5c291743c6daac549e15d479fcf332235c
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452823"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="440c3-102">ManualResetEvent e ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="440c3-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="440c3-103">La classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> rappresenta un evento di handle di attesa locale che deve essere reimpostato manualmente dopo essere stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="440c3-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="440c3-104">Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="440c3-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="440c3-105">Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di impostazione del manuale.</span><span class="sxs-lookup"><span data-stu-id="440c3-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="440c3-106">Un oggetto <xref:System.Threading.ManualResetEvent> rimane segnalato finché non viene chiamato il metodo <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="440c3-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="440c3-107">Qualsiasi numero di thread in attesa, o di thread che attende l'evento dopo che è stato segnalato, può essere rilasciato mentre viene segnalato lo stato dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="440c3-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="440c3-108">In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] è possibile usare la classe <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> per ottenere prestazioni migliori quando si prevedono tempi di attesa molto brevi e quando l'evento non supera un limite di processo.</span><span class="sxs-lookup"><span data-stu-id="440c3-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="440c3-109"><xref:System.Threading.ManualResetEventSlim> usa una rotazione per un breve periodo di tempo mentre si attende che l'evento venga segnalato.</span><span class="sxs-lookup"><span data-stu-id="440c3-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="440c3-110">Quando i tempi di attesa sono brevi, la rotazione può essere molto meno costosa rispetto all'attesa tramite handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="440c3-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="440c3-111">Se tuttavia l'evento non viene segnalato entro un determinato periodo di tempo, <xref:System.Threading.ManualResetEventSlim> ricorre a una normale attesa di handle dell'evento.</span><span class="sxs-lookup"><span data-stu-id="440c3-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="440c3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="440c3-112">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="440c3-113">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="440c3-113">AutoResetEvent</span></span>](autoresetevent.md)  
- [<span data-ttu-id="440c3-114">SpinWait</span><span class="sxs-lookup"><span data-stu-id="440c3-114">SpinWait</span></span>](spinwait.md)  
- [<span data-ttu-id="440c3-115">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="440c3-115">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)
- [<span data-ttu-id="440c3-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="440c3-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="440c3-117">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="440c3-117">Threading objects and features</span></span>](threading-objects-and-features.md)  
- [<span data-ttu-id="440c3-118">Threading</span><span class="sxs-lookup"><span data-stu-id="440c3-118">Threading</span></span>](index.md)  
