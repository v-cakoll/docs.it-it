---
title: Modello asincrono basato su eventi (EAP)
description: Vedere collegamenti ad articoli relativi al modello asincrono basato su eventi (EAP) in .NET, ad esempio implementazione, procedure consigliate, implementazione di un client EAP e altro ancora.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768872"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="5f60e-103">Modello asincrono basato su eventi (EAP)</span><span class="sxs-lookup"><span data-stu-id="5f60e-103">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="5f60e-104">È possibile esporre funzionalità asincrone al codice client in molti modi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-104">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="5f60e-105">Il modello asincrono basato su eventi determina l'unico modo per la presentazione del comportamento asincrono da parte delle classi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-105">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f60e-106">A partire da .NET Framework 4, Task Parallel Library fornisce un nuovo modello di programmazione asincrona e parallela.</span><span class="sxs-lookup"><span data-stu-id="5f60e-106">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="5f60e-107">Per altre informazioni, vedere [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) e [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="5f60e-107">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5f60e-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5f60e-108">In This Section</span></span>

 [<span data-ttu-id="5f60e-109">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-109">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="5f60e-110">Descrive il modo in cui il modello asincrono basato su eventi rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi correlati alla progettazione multithread.</span><span class="sxs-lookup"><span data-stu-id="5f60e-110">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="5f60e-111">Implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-111">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-112">Descrive il modo standardizzato di creare un pacchetto di una classe con funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="5f60e-112">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="5f60e-113">Suggerimenti per l'implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-113">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-114">Descrive i requisiti per l'esposizione di funzionalità asincrone in base al modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-114">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="5f60e-115">Quando implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-115">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-116">Descrive come stabilire quando occorre scegliere di implementare il modello asincrono basato su eventi anziché il modello <xref:System.IAsyncResult> rappresentato dal [modello di programmazione asincrona (APM)](asynchronous-programming-model-apm.md)</span><span class="sxs-lookup"><span data-stu-id="5f60e-116">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="5f60e-117">Procedura: implementare un componente che supporta il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-117">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-118">Spiega come creare un componente che implementa un modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-118">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="5f60e-119">L'implementazione è eseguita mediante classi di helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, in modo da assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f60e-119">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="5f60e-120">Procedura: implementare un client del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-120">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-121">Spiega come creare un client che usa un componente che implementa un modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-121">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="5f60e-122">Procedura: usare componenti che supportano il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5f60e-122">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5f60e-123">Descrive come usare un componente che supporta il modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="5f60e-123">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5f60e-124">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="5f60e-124">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="5f60e-125">Descrive la classe <xref:System.ComponentModel.AsyncOperation> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f60e-125">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="5f60e-126">Descrive la classe <xref:System.ComponentModel.AsyncOperationManager> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f60e-126">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="5f60e-127">Descrive il componente <xref:System.ComponentModel.BackgroundWorker> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f60e-127">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f60e-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5f60e-128">Related Sections</span></span>

 [<span data-ttu-id="5f60e-129">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="5f60e-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="5f60e-130">Descrive un modello di programmazione delle operazioni asincrone e parallele.</span><span class="sxs-lookup"><span data-stu-id="5f60e-130">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="5f60e-131">Threading</span><span class="sxs-lookup"><span data-stu-id="5f60e-131">Threading</span></span>](../threading/index.md)  
 <span data-ttu-id="5f60e-132">Descrive le funzionalità di multithreading in .NET.</span><span class="sxs-lookup"><span data-stu-id="5f60e-132">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f60e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f60e-133">See also</span></span>

- [<span data-ttu-id="5f60e-134">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="5f60e-134">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="5f60e-135">Events</span><span class="sxs-lookup"><span data-stu-id="5f60e-135">Events</span></span>](../events/index.md)
- [<span data-ttu-id="5f60e-136">Modelli di programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="5f60e-136">Asynchronous Programming Design Patterns</span></span>](index.md)
