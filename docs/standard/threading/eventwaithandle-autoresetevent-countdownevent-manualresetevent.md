---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583152"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="928fb-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="928fb-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>

<span data-ttu-id="928fb-103">Gli handle di attesa degli eventi consentono di sincronizzare le attività segnalandosi reciprocamente e attendendo segnali degli altri thread.</span><span class="sxs-lookup"><span data-stu-id="928fb-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="928fb-104">Questi eventi di sincronizzazione sono basati sugli handle di attesa del sistema operativo e possono essere suddivisi in due tipi: quelli che vengono reimpostati automaticamente quando vengono segnalati e quelli che devono essere reimpostati manualmente.</span><span class="sxs-lookup"><span data-stu-id="928fb-104">These synchronization events are based on operating system wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
<span data-ttu-id="928fb-105">Gli handle di attesa degli eventi sono utili in molti degli scenari di sincronizzazione della classe <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="928fb-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="928fb-106">Gli handle di attesa degli eventi sono spesso più facili da usare dei metodi <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> e offrono un controllo maggiore sulla segnalazione.</span><span class="sxs-lookup"><span data-stu-id="928fb-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="928fb-107">Gli handle di attesa dell'evento denominato possono inoltre essere usati per sincronizzare le attività nei domini delle applicazioni e nei processi, mentre i monitor sono locali rispetto a un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="928fb-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="928fb-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="928fb-108">In this section</span></span>

 [<span data-ttu-id="928fb-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="928fb-109">EventWaitHandle</span></span>](eventwaithandle.md)  
 <span data-ttu-id="928fb-110">La classe <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> può rappresentare sia gli eventi di reimpostazione automatici che quelli manuali, nonché gli eventi locali o gli eventi del sistema denominato.</span><span class="sxs-lookup"><span data-stu-id="928fb-110">The <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="928fb-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="928fb-111">AutoResetEvent</span></span>](autoresetevent.md)  
 <span data-ttu-id="928fb-112">La classe <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che viene reimpostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="928fb-112">The <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="928fb-113">ManualResetEvent e ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="928fb-113">ManualResetEvent and ManualResetEventSlim</span></span>](manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="928fb-114">La classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> deriva da <xref:System.Threading.EventWaitHandle> e rappresenta un evento locale che deve essere reimpostato manualmente.</span><span class="sxs-lookup"><span data-stu-id="928fb-114">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="928fb-115">La classe <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> è una versione leggera e più veloce che può essere usata per gli eventi all'interno del processo stesso.</span><span class="sxs-lookup"><span data-stu-id="928fb-115">The <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="928fb-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="928fb-116">CountdownEvent</span></span>](countdownevent.md)  
 <span data-ttu-id="928fb-117">La classe <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> fornisce un metodo semplificato per implementare modelli di parallelismo fork/join nel codice che sfrutta gli handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="928fb-117">The <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  

## <a name="see-also"></a><span data-ttu-id="928fb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="928fb-118">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [<span data-ttu-id="928fb-119">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="928fb-119">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="928fb-120">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="928fb-120">Managed threading basics</span></span>](managed-threading-basics.md)
