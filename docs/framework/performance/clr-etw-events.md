---
title: Eventi ETW di CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6b18f736743f1057641c20c7ef2bc544272f94f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616655"
---
# <a name="clr-etw-events"></a><span data-ttu-id="778bf-102">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="778bf-102">CLR ETW Events</span></span>
<span data-ttu-id="778bf-103">Gli argomenti presenti in questa sezione descrivono gli eventi ETW (Event Tracing for Windows).</span><span class="sxs-lookup"><span data-stu-id="778bf-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="778bf-104">A ogni evento sono associati una parola chiave e un livello, come descritto nell'argomento [Parole chiave e livelli ETW di CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="778bf-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="778bf-105">CLR dispone di due provider per gli eventi:</span><span class="sxs-lookup"><span data-stu-id="778bf-105">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="778bf-106">Il provider di runtime, che genera eventi in base alle parole chiave (categorie di eventi) abilitate.</span><span class="sxs-lookup"><span data-stu-id="778bf-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="778bf-107">Il GUID del provider di runtime di CLR è e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="778bf-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="778bf-108">Il provider di rundown, che viene usato per scopi specifici.</span><span class="sxs-lookup"><span data-stu-id="778bf-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="778bf-109">Il GUID del provider di rundown di CLR è a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="778bf-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="778bf-110">Per altre informazioni, vedere [Provider ETW di CLR](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="778bf-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="778bf-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="778bf-111">In This Section</span></span>  
 [<span data-ttu-id="778bf-112">Eventi di informazione di runtime</span><span class="sxs-lookup"><span data-stu-id="778bf-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="778bf-113">Acquisisce informazioni sul runtime, inclusi la SKU, il numero di versione, la modalità di attivazione del runtime, i parametri della riga di comando con i quali è stato avviato, il GUID (se applicabile) e altre informazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="778bf-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="778bf-114">Evento di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="778bf-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="778bf-115">Acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="778bf-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="778bf-116">Eventi di conflitto</span><span class="sxs-lookup"><span data-stu-id="778bf-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="778bf-117">Acquisisce informazioni sui conflitti per i blocchi di monitoraggio o nativi usati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="778bf-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="778bf-118">Eventi del pool di thread</span><span class="sxs-lookup"><span data-stu-id="778bf-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="778bf-119">Acquisisce informazioni sui pool dei thread di lavoro e di I/O.</span><span class="sxs-lookup"><span data-stu-id="778bf-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="778bf-120">Eventi del caricatore</span><span class="sxs-lookup"><span data-stu-id="778bf-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="778bf-121">Acquisisce informazioni sul caricamento e sullo scaricamento di moduli, assembly e domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="778bf-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="778bf-122">Eventi dei metodi</span><span class="sxs-lookup"><span data-stu-id="778bf-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="778bf-123">Acquisisce informazioni sui metodi di CLR per la risoluzione dei simboli.</span><span class="sxs-lookup"><span data-stu-id="778bf-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="778bf-124">Eventi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="778bf-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="778bf-125">Acquisisce informazioni che riguardano la procedura di Garbage Collection, utili nella diagnostica e nel debug.</span><span class="sxs-lookup"><span data-stu-id="778bf-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="778bf-126">Eventi di traccia JIT</span><span class="sxs-lookup"><span data-stu-id="778bf-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="778bf-127">Acquisisce informazioni sull'incorporamento Just-In-Time (JIT) e sulle chiamate tail.</span><span class="sxs-lookup"><span data-stu-id="778bf-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="778bf-128">Eventi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="778bf-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="778bf-129">Acquisisce informazioni sulla memorizzazione nella cache e sulla generazione di stub Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="778bf-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="778bf-130">Eventi ARM</span><span class="sxs-lookup"><span data-stu-id="778bf-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="778bf-131">Acquisisce informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="778bf-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="778bf-132">Eventi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="778bf-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="778bf-133">Acquisisce informazioni sulla verifica tramite nome sicuro e Authenticode.</span><span class="sxs-lookup"><span data-stu-id="778bf-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="778bf-134">Evento di stack</span><span class="sxs-lookup"><span data-stu-id="778bf-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="778bf-135">Acquisisce informazioni che vengono usate con altri eventi per generare le analisi dello stack in seguito alla generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="778bf-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778bf-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="778bf-136">See also</span></span>

- [<span data-ttu-id="778bf-137">Migliorare il debug e ottimizzazione delle prestazioni con ETW</span><span class="sxs-lookup"><span data-stu-id="778bf-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="778bf-138">Blog sulle prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="778bf-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="778bf-139">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="778bf-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)
- [<span data-ttu-id="778bf-140">Provider ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="778bf-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)
- [<span data-ttu-id="778bf-141">Parole chiave e livelli ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="778bf-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="778bf-142">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="778bf-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
