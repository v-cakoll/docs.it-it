---
title: Eventi ETW in Common Language Runtime
description: Leggere un riepilogo e visualizzare i collegamenti relativi agli eventi ETW (Event Tracing for Windows) nel Common Language Runtime (CLR).
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: aa422dcb7efbc0f6f7f09e09a6c9e44b40ada86b
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309482"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="3ac9d-103">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3ac9d-103">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="3ac9d-104">Common Language Runtime (CLR) fornisce utili informazioni di diagnostica ETW (Event Tracing for Windows) tramite svariati eventi di debug e profilatura.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-104">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="3ac9d-105">Gli eventi ETW di CLR sfruttano il sistema di traccia Windows ETW per migliorare il supporto esistente per la profilatura e il debug offerto da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-105">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="3ac9d-106">Altre informazioni su ETW sono disponibili nell'articolo [migliorare il debug e l'ottimizzazione delle prestazioni con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="3ac9d-106">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="3ac9d-107">Per informazioni su Xperf, vedere la voce [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) (Xperf di Windows Performance Toolkit) nel blog NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-107">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="3ac9d-108">Il .NET Framework 4 o versione successiva è necessario per tutti gli eventi descritti negli argomenti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-108">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="3ac9d-109">Il sistema operativo Windows Vista è il client minimo supportato e Windows Server 2008 è il server minimo supportato.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-109">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ac9d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3ac9d-110">In This Section</span></span>  
 [<span data-ttu-id="3ac9d-111">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3ac9d-111">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="3ac9d-112">Descrive gli strumenti e i comandi per acquisire e visualizzare gli eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-112">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="3ac9d-113">Provider ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="3ac9d-113">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="3ac9d-114">Fornisce informazioni sui provider di runtime e rundown e su come usarli per la raccolta di dati ETW.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-114">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="3ac9d-115">Parole chiave e livelli ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="3ac9d-115">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="3ac9d-116">Descrive la parole chiave per i provider di runtime e rundown che consentono di filtrare gli eventi per categoria.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-116">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="3ac9d-117">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="3ac9d-117">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="3ac9d-118">Contiene informazioni dettagliate sugli eventi ETW di CLR e su parole chiave, livelli e dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="3ac9d-118">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac9d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac9d-119">See also</span></span>

- [<span data-ttu-id="3ac9d-120">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3ac9d-120">ETW Events in the .NET Framework</span></span>](etw-events.md)
