---
title: Modello asincrono basato su eventi (EAP)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7811113244d8c5f7d79a55ebb01f04e99e9bd2a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567806"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="18ca4-102">Modello asincrono basato su eventi (EAP)</span><span class="sxs-lookup"><span data-stu-id="18ca4-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="18ca4-103">È possibile esporre funzionalità asincrone al codice client in molti modi.</span><span class="sxs-lookup"><span data-stu-id="18ca4-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="18ca4-104">Il modello asincrono basato su eventi determina l'unico modo per la presentazione del comportamento asincrono da parte delle classi.</span><span class="sxs-lookup"><span data-stu-id="18ca4-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18ca4-105">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Task Parallel Library fornisce un nuovo modello di programmazione asincrona e parallela.</span><span class="sxs-lookup"><span data-stu-id="18ca4-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="18ca4-106">Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="18ca4-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18ca4-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="18ca4-107">In This Section</span></span>  
 [<span data-ttu-id="18ca4-108">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="18ca4-109">Descrive il modo in cui il modello asincrono basato su eventi rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi correlati alla progettazione multithread.</span><span class="sxs-lookup"><span data-stu-id="18ca4-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="18ca4-110">Implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="18ca4-111">Descrive il modo standardizzato di creare un pacchetto di una classe con funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="18ca4-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="18ca4-112">Suggerimenti per l'implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="18ca4-113">Descrive i requisiti per l'esposizione di funzionalità asincrone in base al modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="18ca4-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="18ca4-114">Quando implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="18ca4-115">Descrive come determinare quando occorre scegliere di implementare il modello asincrono basato su eventi invece del modello <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="18ca4-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="18ca4-116">Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="18ca4-117">Illustra come creare un componente che implementa un modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="18ca4-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="18ca4-118">L'implementazione è eseguita mediante classi di helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, in modo da assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="18ca4-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="18ca4-119">Procedura: Usare componenti che supportano il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="18ca4-120">Descrive come usare un componente che supporta il modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="18ca4-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="18ca4-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="18ca4-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="18ca4-122">Descrive la classe <xref:System.ComponentModel.AsyncOperation> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="18ca4-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="18ca4-123">Descrive la classe <xref:System.ComponentModel.AsyncOperationManager> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="18ca4-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="18ca4-124">Descrive il componente <xref:System.ComponentModel.BackgroundWorker> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="18ca4-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="18ca4-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="18ca4-125">Related Sections</span></span>  
 [<span data-ttu-id="18ca4-126">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="18ca4-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="18ca4-127">Descrive un modello di programmazione delle operazioni asincrone e parallele.</span><span class="sxs-lookup"><span data-stu-id="18ca4-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="18ca4-128">Threading</span><span class="sxs-lookup"><span data-stu-id="18ca4-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="18ca4-129">Descrive le funzionalità di multithreading nel.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18ca4-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="18ca4-130">Threading</span><span class="sxs-lookup"><span data-stu-id="18ca4-130">Threading</span></span>](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="18ca4-131">Descrive le funzionalità di multithreading nei linguaggi C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18ca4-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ca4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ca4-132">See Also</span></span>  
 [<span data-ttu-id="18ca4-133">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="18ca4-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="18ca4-134">Eventi</span><span class="sxs-lookup"><span data-stu-id="18ca4-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="18ca4-135">Multithreading nei componenti</span><span class="sxs-lookup"><span data-stu-id="18ca4-135">Multithreading in Components</span></span>](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="18ca4-136">Modelli di programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="18ca4-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
