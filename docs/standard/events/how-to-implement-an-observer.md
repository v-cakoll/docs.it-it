---
title: 'Procedura: Implementare un elemento Observer'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="54f30-102">Procedura: Implementare un elemento Observer</span><span class="sxs-lookup"><span data-stu-id="54f30-102">How to: Implement an Observer</span></span>
<span data-ttu-id="54f30-103">Il modello di progettazione osservatore richiede una divisione tra un osservatore, che registra per le notifiche, e un provider, che esegue il monitoraggio dei dati e inviare notifiche agli osservatori di uno o più.</span><span class="sxs-lookup"><span data-stu-id="54f30-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="54f30-104">In questo argomento viene illustrato come creare un osservatore.</span><span class="sxs-lookup"><span data-stu-id="54f30-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="54f30-105">Un argomento correlato, [procedura: implementare un Provider](../../../docs/standard/events/how-to-implement-a-provider.md), viene illustrato come creare un provider.</span><span class="sxs-lookup"><span data-stu-id="54f30-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="54f30-106">Per creare un elemento observer</span><span class="sxs-lookup"><span data-stu-id="54f30-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="54f30-107">Definire l'osservatore, che è un tipo che implementa il <xref:System.IObserver%601?displayProperty=nameWithType> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="54f30-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="54f30-108">Ad esempio, il codice seguente definisce un tipo denominato `TemperatureReporter` che rappresenta un elemento costruito <xref:System.IObserver%601?displayProperty=nameWithType> implementazione con un argomento di tipo generico di `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="54f30-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="54f30-109">Se l'osservatore può interrompere la ricezione di notifiche prima che il provider chiama il relativo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementazione, definire una variabile privata che conterrà il <xref:System.IDisposable> implementazione il provider ha restituito <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="54f30-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="54f30-110">È inoltre necessario definire un metodo di sottoscrizione che chiama il provider <xref:System.IObservable%601.Subscribe%2A> (metodo) e archivia l'oggetto restituito <xref:System.IDisposable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="54f30-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="54f30-111">Ad esempio, il codice seguente definisce una variabile privata denominata `unsubscriber` e definisce un `Subscribe` metodo che chiama il provider <xref:System.IObservable%601.Subscribe%2A> metodo e assegna l'oggetto restituito per il `unsubscriber` variabile.</span><span class="sxs-lookup"><span data-stu-id="54f30-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="54f30-112">Definire un metodo che consente l'osservatore interrompere la ricezione di notifiche prima che il provider chiama il relativo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementazione, se questa funzionalità è necessaria.</span><span class="sxs-lookup"><span data-stu-id="54f30-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="54f30-113">L'esempio seguente definisce un `Unsubscribe` metodo.</span><span class="sxs-lookup"><span data-stu-id="54f30-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="54f30-114">Fornire le implementazioni dei tre metodi definiti dal <xref:System.IObserver%601> interfaccia: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="54f30-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="54f30-115">A seconda di provider e le esigenze dell'applicazione, il <xref:System.IObserver%601.OnError%2A> e <xref:System.IObserver%601.OnCompleted%2A> metodi possono essere implementazioni dello stub.</span><span class="sxs-lookup"><span data-stu-id="54f30-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="54f30-116">Si noti che il <xref:System.IObserver%601.OnError%2A> metodo non deve gestire l'oggetto passato <xref:System.Exception> oggetto come un'eccezione e <xref:System.IObserver%601.OnCompleted%2A> metodo è libero di chiamare il provider <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementazione.</span><span class="sxs-lookup"><span data-stu-id="54f30-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="54f30-117">Nell'esempio seguente il <xref:System.IObserver%601> implementazione del `TemperatureReporter` classe.</span><span class="sxs-lookup"><span data-stu-id="54f30-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="54f30-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="54f30-118">Example</span></span>  
 <span data-ttu-id="54f30-119">Nell'esempio seguente contiene il codice sorgente completo per il `TemperatureReporter` (classe), che fornisce il <xref:System.IObserver%601> implementazione per un'applicazione di monitoraggio della temperatura.</span><span class="sxs-lookup"><span data-stu-id="54f30-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="54f30-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f30-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="54f30-121">Modello di progettazione observer</span><span class="sxs-lookup"><span data-stu-id="54f30-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="54f30-122">Procedura: Implementare un provider</span><span class="sxs-lookup"><span data-stu-id="54f30-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="54f30-123">Procedure consigliate per un modello di progettazione observer</span><span class="sxs-lookup"><span data-stu-id="54f30-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
