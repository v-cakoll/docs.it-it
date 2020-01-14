---
title: Eventi ETW in Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937863"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="aa373-102">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="aa373-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="aa373-103">Common Language Runtime (CLR) fornisce utili informazioni di diagnostica ETW (Event Tracing for Windows) tramite svariati eventi di debug e profilatura.</span><span class="sxs-lookup"><span data-stu-id="aa373-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="aa373-104">Gli eventi ETW di CLR sfruttano il sistema di traccia Windows ETW per migliorare il supporto esistente per la profilatura e il debug offerto da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="aa373-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="aa373-105">Altre informazioni su ETW sono disponibili nell'articolo [migliorare il debug e l'ottimizzazione delle prestazioni con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="aa373-105">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="aa373-106">Per informazioni su Xperf, vedere la voce [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) (Xperf di Windows Performance Toolkit) nel blog NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="aa373-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="aa373-107">Il .NET Framework 4 o versione successiva è necessario per tutti gli eventi descritti negli argomenti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="aa373-107">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="aa373-108">Il sistema operativo Windows Vista è il client minimo supportato e Windows Server 2008 è il server minimo supportato.</span><span class="sxs-lookup"><span data-stu-id="aa373-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa373-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="aa373-109">In This Section</span></span>  
 [<span data-ttu-id="aa373-110">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa373-110">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="aa373-111">Descrive gli strumenti e i comandi per acquisire e visualizzare gli eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="aa373-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="aa373-112">Provider ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="aa373-112">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="aa373-113">Fornisce informazioni sui provider di runtime e rundown e su come usarli per la raccolta di dati ETW.</span><span class="sxs-lookup"><span data-stu-id="aa373-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="aa373-114">Parole chiave e livelli ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="aa373-114">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="aa373-115">Descrive la parole chiave per i provider di runtime e rundown che consentono di filtrare gli eventi per categoria.</span><span class="sxs-lookup"><span data-stu-id="aa373-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="aa373-116">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="aa373-116">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="aa373-117">Contiene informazioni dettagliate sugli eventi ETW di CLR e su parole chiave, livelli e dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="aa373-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa373-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa373-118">See also</span></span>

- [<span data-ttu-id="aa373-119">Eventi ETW in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa373-119">ETW Events in the .NET Framework</span></span>](etw-events.md)
