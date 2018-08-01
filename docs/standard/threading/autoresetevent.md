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
ms.openlocfilehash: c1785ce223f0dcd4da7ea6ef9fa3a3e897a39dca
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143518"
---
# <a name="autoresetevent"></a><span data-ttu-id="f6a1c-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="f6a1c-102">AutoResetEvent</span></span>
<span data-ttu-id="f6a1c-103">La classe <xref:System.Threading.AutoResetEvent> rappresenta un evento di handle di attesa locale che viene reimpostato automaticamente quando viene segnalato, dopo il rilascio di un singolo thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="f6a1c-104">Questa classe rappresenta un caso speciale della relativa classe di base, <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="f6a1c-105">Vedere la documentazione concettuale [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) per l'uso e le caratteristiche degli eventi di ripristino automatici.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="f6a1c-106">Un oggetto <xref:System.Threading.AutoResetEvent> viene reimpostato automaticamente su non segnalato dal sistema dopo il rilascio di un singolo thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="f6a1c-107">Se non c'è alcun thread in attesa, lo stato dell'oggetto evento resta segnalato.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="f6a1c-108"><xref:System.Threading.AutoResetEvent> corrisponde a una chiamata Win32 a `CreateEvent`, che specifica `false` per l'argomento `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="f6a1c-109">Per un esempio che usa <xref:System.Threading.AutoResetEvent>, vedere <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="f6a1c-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a1c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6a1c-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="f6a1c-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="f6a1c-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="f6a1c-112">Threading</span><span class="sxs-lookup"><span data-stu-id="f6a1c-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="f6a1c-113">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="f6a1c-113">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>  
 [<span data-ttu-id="f6a1c-114">Handle di attesa</span><span class="sxs-lookup"><span data-stu-id="f6a1c-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
