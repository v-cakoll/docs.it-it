---
title: Threading gestito
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f2a8792818e837f019403aa84c2c2e98db0b2b89
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="managed-threading"></a><span data-ttu-id="0e532-102">Threading gestito</span><span class="sxs-lookup"><span data-stu-id="0e532-102">Managed Threading</span></span>
<span data-ttu-id="0e532-103">Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività.</span><span class="sxs-lookup"><span data-stu-id="0e532-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="0e532-104">L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi.</span><span class="sxs-lookup"><span data-stu-id="0e532-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="0e532-105">Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.</span><span class="sxs-lookup"><span data-stu-id="0e532-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e532-106">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> e <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=fullName> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread.</span><span class="sxs-lookup"><span data-stu-id="0e532-106">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> and <xref:System.Threading.Tasks.Task?displayProperty=fullName> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=fullName> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="0e532-107">Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e532-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e532-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0e532-108">In This Section</span></span>  
 [<span data-ttu-id="0e532-109">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="0e532-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="0e532-110">Fornisce una panoramica del threading gestito e illustra quando usare più thread.</span><span class="sxs-lookup"><span data-stu-id="0e532-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="0e532-111">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="0e532-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="0e532-112">Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.</span><span class="sxs-lookup"><span data-stu-id="0e532-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="0e532-113">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="0e532-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="0e532-114">Illustra i livelli di sincronizzazione, come evitare deadlock e race condition, computer a processore singolo e multiprocessore e altri problemi di threading.</span><span class="sxs-lookup"><span data-stu-id="0e532-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, single-processor and multiprocessor computers, and other threading issues.</span></span>  
  
 <span data-ttu-id="0e532-115">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="0e532-115">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>  
 <span data-ttu-id="0e532-116">Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.</span><span class="sxs-lookup"><span data-stu-id="0e532-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0e532-117">Riferimento</span><span class="sxs-lookup"><span data-stu-id="0e532-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="0e532-118">Contiene classi per l'uso e la sincronizzazione dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e532-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="0e532-119">Contiene le classi di raccolta che sono sicure per l'uso con più thread.</span><span class="sxs-lookup"><span data-stu-id="0e532-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="0e532-120">Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.</span><span class="sxs-lookup"><span data-stu-id="0e532-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0e532-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0e532-121">Related Sections</span></span>  
 [<span data-ttu-id="0e532-122">Domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0e532-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="0e532-123">Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0e532-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="0e532-124">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="0e532-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="0e532-125">Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0e532-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 <span data-ttu-id="0e532-126">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="0e532-126">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 <span data-ttu-id="0e532-127">Fornisce una descrizione generale della programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="0e532-127">Provides an overview of asynchronous programming.</span></span>  
  
 [<span data-ttu-id="0e532-128">Chiamata sincrona dei metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="0e532-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="0e532-129">Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.</span><span class="sxs-lookup"><span data-stu-id="0e532-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="0e532-130">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="0e532-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="0e532-131">Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0e532-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="0e532-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="0e532-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 <span data-ttu-id="0e532-133">Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.</span><span class="sxs-lookup"><span data-stu-id="0e532-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>

