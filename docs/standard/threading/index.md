---
title: Threading gestito
description: Vedere i collegamenti agli articoli relativi al threading gestito in .NET che illustra le nozioni di base, le procedure consigliate, gli oggetti Threading & funzionalità, le pagine di riferimento & altro ancora.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: 570db45138c85c4252967404da4404d434660d69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599750"
---
# <a name="managed-threading"></a><span data-ttu-id="b2d87-103">Threading gestito</span><span class="sxs-lookup"><span data-stu-id="b2d87-103">Managed Threading</span></span>
<span data-ttu-id="b2d87-104">Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività.</span><span class="sxs-lookup"><span data-stu-id="b2d87-104">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="b2d87-105">L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi.</span><span class="sxs-lookup"><span data-stu-id="b2d87-105">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="b2d87-106">Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.</span><span class="sxs-lookup"><span data-stu-id="b2d87-106">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2d87-107">A partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread.</span><span class="sxs-lookup"><span data-stu-id="b2d87-107">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="b2d87-108">Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2d87-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2d87-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b2d87-109">In This Section</span></span>  
 [<span data-ttu-id="b2d87-110">Nozioni fondamentali sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="b2d87-110">Managed Threading Basics</span></span>](managed-threading-basics.md)  
 <span data-ttu-id="b2d87-111">Fornisce una panoramica del threading gestito e illustra quando usare più thread.</span><span class="sxs-lookup"><span data-stu-id="b2d87-111">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="b2d87-112">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="b2d87-112">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
 <span data-ttu-id="b2d87-113">Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.</span><span class="sxs-lookup"><span data-stu-id="b2d87-113">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="b2d87-114">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="b2d87-114">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="b2d87-115">Illustra i livelli di sincronizzazione, come evitare deadlock e race condition e altri problemi di threading.</span><span class="sxs-lookup"><span data-stu-id="b2d87-115">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="b2d87-116">Oggetti e funzionalità di threading</span><span class="sxs-lookup"><span data-stu-id="b2d87-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)  
 <span data-ttu-id="b2d87-117">Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.</span><span class="sxs-lookup"><span data-stu-id="b2d87-117">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b2d87-118">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="b2d87-118">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="b2d87-119">Contiene classi per l'uso e la sincronizzazione dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="b2d87-119">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="b2d87-120">Contiene le classi di raccolta che sono sicure per l'uso con più thread.</span><span class="sxs-lookup"><span data-stu-id="b2d87-120">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="b2d87-121">Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.</span><span class="sxs-lookup"><span data-stu-id="b2d87-121">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b2d87-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b2d87-122">Related Sections</span></span>  
 [<span data-ttu-id="b2d87-123">Domini applicazione</span><span class="sxs-lookup"><span data-stu-id="b2d87-123">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
 <span data-ttu-id="b2d87-124">Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b2d87-124">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="b2d87-125">I/O file asincrono</span><span class="sxs-lookup"><span data-stu-id="b2d87-125">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)  
 <span data-ttu-id="b2d87-126">Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b2d87-126">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="b2d87-127">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="b2d87-127">Task-based Asynchronous Pattern (TAP)</span></span>](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 <span data-ttu-id="b2d87-128">Offre una panoramica del modello consigliato per la programmazione asincrona in .NET.</span><span class="sxs-lookup"><span data-stu-id="b2d87-128">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="b2d87-129">Chiamata di metodi sincroni in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="b2d87-129">Calling Synchronous Methods Asynchronously</span></span>](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="b2d87-130">Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.</span><span class="sxs-lookup"><span data-stu-id="b2d87-130">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="b2d87-131">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="b2d87-131">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="b2d87-132">Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b2d87-132">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="b2d87-133">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="b2d87-133">Parallel LINQ (PLINQ)</span></span>](../parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="b2d87-134">Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.</span><span class="sxs-lookup"><span data-stu-id="b2d87-134">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
