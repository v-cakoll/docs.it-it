---
title: Eventi ETW di CLR
description: 'Vedere gli articoli sugli eventi ETW (Event Tracing for Windows) di Common Language Runtime (CLR). Sono disponibili due provider di eventi: provider di runtime e provider di rundown.'
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
ms.openlocfilehash: 22a2f027462d67d5a933972a7420c5f0e38353e5
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309833"
---
# <a name="clr-etw-events"></a><span data-ttu-id="2c5de-104">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="2c5de-104">CLR ETW Events</span></span>
<span data-ttu-id="2c5de-105">Gli argomenti presenti in questa sezione descrivono gli eventi ETW (Event Tracing for Windows).</span><span class="sxs-lookup"><span data-stu-id="2c5de-105">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="2c5de-106">A ogni evento sono associati una parola chiave e un livello, come descritto nell'argomento [Parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2c5de-106">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="2c5de-107">CLR dispone di due provider per gli eventi:</span><span class="sxs-lookup"><span data-stu-id="2c5de-107">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="2c5de-108">Il provider di runtime, che genera eventi in base alle parole chiave (categorie di eventi) abilitate.</span><span class="sxs-lookup"><span data-stu-id="2c5de-108">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="2c5de-109">Il GUID del provider di runtime di CLR è e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="2c5de-109">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="2c5de-110">Il provider di rundown, che viene usato per scopi specifici.</span><span class="sxs-lookup"><span data-stu-id="2c5de-110">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="2c5de-111">Il GUID del provider di rundown di CLR è a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="2c5de-111">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="2c5de-112">Per altre informazioni, vedere [Provider ETW di CLR](clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="2c5de-112">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c5de-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2c5de-113">In This Section</span></span>  
 [<span data-ttu-id="2c5de-114">Eventi di informazione di runtime</span><span class="sxs-lookup"><span data-stu-id="2c5de-114">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="2c5de-115">Acquisisce informazioni sul runtime, inclusi la SKU, il numero di versione, la modalità di attivazione del runtime, i parametri della riga di comando con i quali è stato avviato, il GUID (se applicabile) e altre informazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="2c5de-115">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="2c5de-116">Evento di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="2c5de-116">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="2c5de-117">Acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="2c5de-117">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="2c5de-118">Eventi di conflitto</span><span class="sxs-lookup"><span data-stu-id="2c5de-118">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="2c5de-119">Acquisisce informazioni sui conflitti per i blocchi di monitoraggio o nativi usati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="2c5de-119">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="2c5de-120">Eventi del pool di thread</span><span class="sxs-lookup"><span data-stu-id="2c5de-120">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="2c5de-121">Acquisisce informazioni sui pool dei thread di lavoro e di I/O.</span><span class="sxs-lookup"><span data-stu-id="2c5de-121">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="2c5de-122">Eventi del caricatore</span><span class="sxs-lookup"><span data-stu-id="2c5de-122">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="2c5de-123">Acquisisce informazioni sul caricamento e sullo scaricamento di moduli, assembly e domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c5de-123">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="2c5de-124">Eventi dei metodi</span><span class="sxs-lookup"><span data-stu-id="2c5de-124">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="2c5de-125">Acquisisce informazioni sui metodi di CLR per la risoluzione dei simboli.</span><span class="sxs-lookup"><span data-stu-id="2c5de-125">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="2c5de-126">Eventi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="2c5de-126">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="2c5de-127">Acquisisce informazioni che riguardano la procedura di Garbage Collection, utili nella diagnostica e nel debug.</span><span class="sxs-lookup"><span data-stu-id="2c5de-127">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="2c5de-128">Eventi di traccia JIT</span><span class="sxs-lookup"><span data-stu-id="2c5de-128">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="2c5de-129">Acquisisce informazioni sull'incorporamento Just-In-Time (JIT) e sulle chiamate tail.</span><span class="sxs-lookup"><span data-stu-id="2c5de-129">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="2c5de-130">Eventi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="2c5de-130">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="2c5de-131">Acquisisce informazioni sulla memorizzazione nella cache e sulla generazione di stub Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="2c5de-131">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="2c5de-132">Eventi ARM</span><span class="sxs-lookup"><span data-stu-id="2c5de-132">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="2c5de-133">Acquisisce informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c5de-133">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="2c5de-134">Eventi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2c5de-134">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="2c5de-135">Acquisisce informazioni sulla verifica tramite nome sicuro e Authenticode.</span><span class="sxs-lookup"><span data-stu-id="2c5de-135">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="2c5de-136">Evento di stack</span><span class="sxs-lookup"><span data-stu-id="2c5de-136">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="2c5de-137">Acquisisce informazioni che vengono usate con altri eventi per generare le analisi dello stack in seguito alla generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="2c5de-137">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5de-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c5de-138">See also</span></span>

- [<span data-ttu-id="2c5de-139">Migliorare il debug e la regolazione delle prestazioni con ETW</span><span class="sxs-lookup"><span data-stu-id="2c5de-139">Improve Debugging And Performance Tuning With ETW</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [<span data-ttu-id="2c5de-140">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2c5de-140">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="2c5de-141">Provider ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="2c5de-141">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="2c5de-142">Parole chiave e livelli ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="2c5de-142">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="2c5de-143">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2c5de-143">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
