---
title: Threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: c5ca102dc98e50067d39d2f0c51a6ff75e342e9f
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588661"
---
# <a name="managed-threading"></a><span data-ttu-id="0a497-102">Threading gestito</span><span class="sxs-lookup"><span data-stu-id="0a497-102">Managed Threading</span></span>
<span data-ttu-id="0a497-103">Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività.</span><span class="sxs-lookup"><span data-stu-id="0a497-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="0a497-104">L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi.</span><span class="sxs-lookup"><span data-stu-id="0a497-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="0a497-105">Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.</span><span class="sxs-lookup"><span data-stu-id="0a497-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a497-106">A partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread.</span><span class="sxs-lookup"><span data-stu-id="0a497-106">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="0a497-107">Per ulteriori informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="0a497-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a497-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0a497-108">In This Section</span></span>  
 [<span data-ttu-id="0a497-109">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="0a497-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="0a497-110">Fornisce una panoramica del threading gestito e illustra quando usare più thread.</span><span class="sxs-lookup"><span data-stu-id="0a497-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="0a497-111">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="0a497-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="0a497-112">Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.</span><span class="sxs-lookup"><span data-stu-id="0a497-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="0a497-113">Procedure consigliate per il threading gestitoManaged Threading Best Practices</span><span class="sxs-lookup"><span data-stu-id="0a497-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="0a497-114">Illustra i livelli di sincronizzazione, come evitare deadlock e race condition e altri problemi di threading.</span><span class="sxs-lookup"><span data-stu-id="0a497-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="0a497-115">Funzionalità e oggetti di threading</span><span class="sxs-lookup"><span data-stu-id="0a497-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="0a497-116">Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.</span><span class="sxs-lookup"><span data-stu-id="0a497-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a497-117">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="0a497-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="0a497-118">Contiene classi per l'uso e la sincronizzazione dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="0a497-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="0a497-119">Contiene le classi di raccolta che sono sicure per l'uso con più thread.</span><span class="sxs-lookup"><span data-stu-id="0a497-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="0a497-120">Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.</span><span class="sxs-lookup"><span data-stu-id="0a497-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a497-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0a497-121">Related Sections</span></span>  
 [<span data-ttu-id="0a497-122">Domini applicazione</span><span class="sxs-lookup"><span data-stu-id="0a497-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="0a497-123">Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0a497-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="0a497-124">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="0a497-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="0a497-125">Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0a497-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="0a497-126">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="0a497-126">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 <span data-ttu-id="0a497-127">Offre una panoramica del modello consigliato per la programmazione asincrona in .NET.</span><span class="sxs-lookup"><span data-stu-id="0a497-127">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="0a497-128">Chiamata di metodi sincroni in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="0a497-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="0a497-129">Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.</span><span class="sxs-lookup"><span data-stu-id="0a497-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="0a497-130">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="0a497-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="0a497-131">Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0a497-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="0a497-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="0a497-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="0a497-133">Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.</span><span class="sxs-lookup"><span data-stu-id="0a497-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
