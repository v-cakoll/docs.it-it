---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="66e71-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="66e71-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="66e71-103">Gli handle di attesa degli eventi consentono di sincronizzare le attività segnalandosi reciprocamente e attendendo segnali degli altri thread.</span><span class="sxs-lookup"><span data-stu-id="66e71-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="66e71-104">Questi eventi di sincronizzazione sono basati sugli handle di attesa Win32 e possono essere suddivisi in due tipi: quelli che vengono reimpostati automaticamente quando vengono segnalati e quelli che devono essere reimpostati manualmente.</span><span class="sxs-lookup"><span data-stu-id="66e71-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="66e71-105">Handle di attesa eventi sono utili in molti degli stessi scenari di sincronizzazione di <xref:System.Threading.Monitor> classe.</span><span class="sxs-lookup"><span data-stu-id="66e71-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="66e71-106">Handle di attesa eventi sono spesso più facili da utilizzare rispetto di <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> metodi e forniscono un controllo più efficiente della segnalazione.</span><span class="sxs-lookup"><span data-stu-id="66e71-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="66e71-107">Gli handle di attesa dell'evento denominato possono inoltre essere usati per sincronizzare le attività nei domini delle applicazioni e nei processi, mentre i monitor sono locali rispetto a un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66e71-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66e71-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="66e71-108">In This Section</span></span>  
 [<span data-ttu-id="66e71-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="66e71-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="66e71-110">La <xref:System.Threading.EventWaitHandle> classe può rappresentare un automatico o manuale Reimposta nonché eventi locali o eventi di sistema denominato.</span><span class="sxs-lookup"><span data-stu-id="66e71-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="66e71-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="66e71-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="66e71-112">Il <xref:System.Threading.AutoResetEvent> deriva dalla classe <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale viene reimpostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="66e71-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="66e71-113">ManualResetEvent e ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="66e71-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="66e71-114">Il <xref:System.Threading.ManualResetEvent> deriva dalla classe <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che deve essere reimpostato manualmente.</span><span class="sxs-lookup"><span data-stu-id="66e71-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="66e71-115">La <xref:System.Threading.ManualResetEventSlim> classe è una versione più veloce e semplice che può essere utilizzata per gli eventi all'interno del processo stesso.</span><span class="sxs-lookup"><span data-stu-id="66e71-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="66e71-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="66e71-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="66e71-117">La <xref:System.Threading.CountdownEvent> classe fornisce un metodo semplificato per implementare modelli di parallelismo di divisione e unione nel codice che usa handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="66e71-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66e71-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="66e71-118">Related Sections</span></span>  
 [<span data-ttu-id="66e71-119">Handle di attesa</span><span class="sxs-lookup"><span data-stu-id="66e71-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="66e71-120">Il <xref:System.Threading.WaitHandle> classe è la classe base per il <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, e <xref:System.Threading.Mutex> classi.</span><span class="sxs-lookup"><span data-stu-id="66e71-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="66e71-121">Contiene metodi statici, ad esempio <xref:System.Threading.WaitHandle.SignalAndWait%2A> e <xref:System.Threading.WaitHandle.WaitAll%2A> che sono utili quando si lavora con tutti i tipi di handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="66e71-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e71-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e71-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 <span data-ttu-id="66e71-123">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="66e71-123">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>  
 [<span data-ttu-id="66e71-124">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="66e71-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
