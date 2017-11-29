---
title: Programmazione multithreading con il modello asincrono basato su eventi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a26f6750f68609b40e6917fc5b257e43d95c3c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="c3f53-102">Programmazione multithreading con il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="c3f53-103">È possibile esporre funzionalità asincrone al codice client in molti modi.</span><span class="sxs-lookup"><span data-stu-id="c3f53-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="c3f53-104">Il modello asincrono basato su eventi determina il modo consigliato per la presentazione del comportamento asincrono da parte delle classi.</span><span class="sxs-lookup"><span data-stu-id="c3f53-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3f53-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c3f53-105">In This Section</span></span>  
 [<span data-ttu-id="c3f53-106">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="c3f53-107">Descrive il modo in cui il modello asincrono basato su eventi rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi correlati alla progettazione multithread.</span><span class="sxs-lookup"><span data-stu-id="c3f53-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="c3f53-108">Implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="c3f53-109">Descrive il modo standardizzato di creare un pacchetto di una classe con funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="c3f53-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="c3f53-110">Suggerimenti per l'implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="c3f53-111">Descrive i requisiti per l'esposizione di funzionalità asincrone in base al modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="c3f53-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="c3f53-112">Quando implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="c3f53-113">Descrive come determinare quando occorre scegliere di implementare il modello asincrono basato su eventi invece del modello <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="c3f53-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="c3f53-114">Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="c3f53-115">Illustra come creare un componente che implementa un modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="c3f53-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="c3f53-116">L'implementazione è eseguita mediante classi di helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, in modo da assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f53-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="c3f53-117">Procedura: Usare componenti che supportano il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="c3f53-118">Descrive come usare un componente che supporta il modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="c3f53-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c3f53-119">Riferimento</span><span class="sxs-lookup"><span data-stu-id="c3f53-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="c3f53-120">Descrive la classe <xref:System.ComponentModel.AsyncOperation> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c3f53-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="c3f53-121">Descrive la classe <xref:System.ComponentModel.AsyncOperationManager> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c3f53-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="c3f53-122">Descrive il componente <xref:System.ComponentModel.BackgroundWorker> e include collegamenti a tutti i membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c3f53-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f53-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3f53-123">See Also</span></span>  
 [<span data-ttu-id="c3f53-124">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="c3f53-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="c3f53-125">Eventi</span><span class="sxs-lookup"><span data-stu-id="c3f53-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="c3f53-126">Multithreading nei componenti</span><span class="sxs-lookup"><span data-stu-id="c3f53-126">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 <span data-ttu-id="c3f53-127">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="c3f53-127">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>
