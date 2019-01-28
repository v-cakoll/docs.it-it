---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70af739bdb90a70a1319354b4964c261e432912b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729957"
---
# <a name="autoresetevent"></a><span data-ttu-id="c9ad1-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="c9ad1-102">AutoResetEvent</span></span>
<span data-ttu-id="c9ad1-103">La classe <xref:System.Threading.AutoResetEvent> rappresenta un evento di handle di attesa locale che viene reimpostato automaticamente quando viene segnalato, dopo il rilascio di un singolo thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="c9ad1-104">Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="c9ad1-105">Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di ripristino automatici.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="c9ad1-106">Un oggetto <xref:System.Threading.AutoResetEvent> viene reimpostato automaticamente su non segnalato dal sistema dopo il rilascio di un singolo thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="c9ad1-107">Se non c'è alcun thread in attesa, lo stato dell'oggetto evento resta segnalato.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-107">If no threads are waiting, the event object's state remains signaled.</span></span>
  
 <span data-ttu-id="c9ad1-108">Per un esempio che usa <xref:System.Threading.AutoResetEvent>, vedere <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="c9ad1-108">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ad1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9ad1-109">See also</span></span>

- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="c9ad1-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="c9ad1-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [<span data-ttu-id="c9ad1-111">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="c9ad1-111">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="c9ad1-112">Threading</span><span class="sxs-lookup"><span data-stu-id="c9ad1-112">Threading</span></span>](index.md)
