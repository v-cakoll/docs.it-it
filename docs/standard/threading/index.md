---
title: Threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: e4c19b664e8fc040fdc4a284b30f6104d676088d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279154"
---
# <a name="managed-threading"></a><span data-ttu-id="6de65-102">Threading gestito</span><span class="sxs-lookup"><span data-stu-id="6de65-102">Managed Threading</span></span>
<span data-ttu-id="6de65-103">Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività.</span><span class="sxs-lookup"><span data-stu-id="6de65-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="6de65-104">L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi.</span><span class="sxs-lookup"><span data-stu-id="6de65-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="6de65-105">Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.</span><span class="sxs-lookup"><span data-stu-id="6de65-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6de65-106">A partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread.</span><span class="sxs-lookup"><span data-stu-id="6de65-106">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="6de65-107">Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="6de65-107">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6de65-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6de65-108">In This Section</span></span>  
 [<span data-ttu-id="6de65-109">Nozioni fondamentali sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="6de65-109">Managed Threading Basics</span></span>](managed-threading-basics.md)  
 <span data-ttu-id="6de65-110">Fornisce una panoramica del threading gestito e illustra quando usare più thread.</span><span class="sxs-lookup"><span data-stu-id="6de65-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="6de65-111">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="6de65-111">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
 <span data-ttu-id="6de65-112">Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.</span><span class="sxs-lookup"><span data-stu-id="6de65-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="6de65-113">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="6de65-113">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="6de65-114">Illustra i livelli di sincronizzazione, come evitare deadlock e race condition e altri problemi di threading.</span><span class="sxs-lookup"><span data-stu-id="6de65-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="6de65-115">Oggetti e funzionalità di threading</span><span class="sxs-lookup"><span data-stu-id="6de65-115">Threading Objects and Features</span></span>](threading-objects-and-features.md)  
 <span data-ttu-id="6de65-116">Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.</span><span class="sxs-lookup"><span data-stu-id="6de65-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6de65-117">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="6de65-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="6de65-118">Contiene classi per l'uso e la sincronizzazione dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="6de65-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="6de65-119">Contiene le classi di raccolta che sono sicure per l'uso con più thread.</span><span class="sxs-lookup"><span data-stu-id="6de65-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="6de65-120">Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.</span><span class="sxs-lookup"><span data-stu-id="6de65-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6de65-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6de65-121">Related Sections</span></span>  
 [<span data-ttu-id="6de65-122">Domini applicazione</span><span class="sxs-lookup"><span data-stu-id="6de65-122">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
 <span data-ttu-id="6de65-123">Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6de65-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="6de65-124">I/O file asincrono</span><span class="sxs-lookup"><span data-stu-id="6de65-124">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)  
 <span data-ttu-id="6de65-125">Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6de65-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="6de65-126">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="6de65-126">Task-based Asynchronous Pattern (TAP)</span></span>](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 <span data-ttu-id="6de65-127">Offre una panoramica del modello consigliato per la programmazione asincrona in .NET.</span><span class="sxs-lookup"><span data-stu-id="6de65-127">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="6de65-128">Chiamata di metodi sincroni in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="6de65-128">Calling Synchronous Methods Asynchronously</span></span>](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="6de65-129">Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.</span><span class="sxs-lookup"><span data-stu-id="6de65-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="6de65-130">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="6de65-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="6de65-131">Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6de65-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="6de65-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="6de65-132">Parallel LINQ (PLINQ)</span></span>](../parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="6de65-133">Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.</span><span class="sxs-lookup"><span data-stu-id="6de65-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
