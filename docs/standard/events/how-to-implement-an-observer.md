---
title: 'Procedura: Implementare un elemento Observer'
description: Implementare un Observer in .NET. Il modello di progettazione Observer richiede una divisione tra un Observer, che registra per le notifiche e un provider.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
ms.openlocfilehash: 43236ead15be0777f4284ba553a2f2f5e09d0a73
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768995"
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="b201b-104">Procedura: Implementare un elemento Observer</span><span class="sxs-lookup"><span data-stu-id="b201b-104">How to: Implement an Observer</span></span>
<span data-ttu-id="b201b-105">Lo schema progettuale degli observer richiede una divisione tra un observer, che si registra per le notifiche, e un provider, che monitora i dati e invia notifiche a uno o più observer.</span><span class="sxs-lookup"><span data-stu-id="b201b-105">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="b201b-106">Questo argomento descrive come creare un observer.</span><span class="sxs-lookup"><span data-stu-id="b201b-106">This topic discusses how to create an observer.</span></span> <span data-ttu-id="b201b-107">Un argomento correlato, [Procedura: Implementare un provider](how-to-implement-a-provider.md), descrive come creare un provider.</span><span class="sxs-lookup"><span data-stu-id="b201b-107">A related topic, [How to: Implement a Provider](how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="b201b-108">Per creare un observer</span><span class="sxs-lookup"><span data-stu-id="b201b-108">To create an observer</span></span>  
  
1. <span data-ttu-id="b201b-109">Definire l'observer, che è un tipo che implementa l'interfaccia <xref:System.IObserver%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b201b-109">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="b201b-110">Ad esempio, il codice seguente definisce un tipo denominato `TemperatureReporter` che rappresenta un'implementazione costruita <xref:System.IObserver%601?displayProperty=nameWithType> con un argomento di tipo generico `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="b201b-110">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2. <span data-ttu-id="b201b-111">Se l'observer può smettere di ricevere notifiche prima che il provider chiami la relativa implementazione <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, definire una variabile privata che conterrà l'implementazione <xref:System.IDisposable> restituita dal metodo <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> del provider.</span><span class="sxs-lookup"><span data-stu-id="b201b-111">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b201b-112">È anche necessario definire un metodo di sottoscrizione che chiama il metodo <xref:System.IObservable%601.Subscribe%2A> del provider e archivia l'oggetto <xref:System.IDisposable> restituito.</span><span class="sxs-lookup"><span data-stu-id="b201b-112">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="b201b-113">Ad esempio, il codice seguente definisce una variabile privata denominata `unsubscriber` e un metodo `Subscribe` che chiama il metodo <xref:System.IObservable%601.Subscribe%2A> del provider e assegna l'oggetto restituito alla variabile `unsubscriber`.</span><span class="sxs-lookup"><span data-stu-id="b201b-113">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3. <span data-ttu-id="b201b-114">Definire un metodo che consente all'observer di smettere di ricevere interrompere notifiche prima che il provider chiami la relativa implementazione <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, se questa funzionalità è necessaria.</span><span class="sxs-lookup"><span data-stu-id="b201b-114">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="b201b-115">L'esempio seguente definisce un metodo `Unsubscribe`.</span><span class="sxs-lookup"><span data-stu-id="b201b-115">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4. <span data-ttu-id="b201b-116">Fornire le implementazioni dei tre metodi definiti dall'interfaccia <xref:System.IObserver%601>: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b201b-116">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b201b-117">A seconda del provider e delle esigenze dell'applicazione, i metodi <xref:System.IObserver%601.OnError%2A> e <xref:System.IObserver%601.OnCompleted%2A> possono essere implementazioni dello stub.</span><span class="sxs-lookup"><span data-stu-id="b201b-117">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="b201b-118">Si noti che il metodo <xref:System.IObserver%601.OnError%2A> non deve gestire l'oggetto <xref:System.Exception> passato come eccezione e che il metodo <xref:System.IObserver%601.OnCompleted%2A> è libero di chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> del provider.</span><span class="sxs-lookup"><span data-stu-id="b201b-118">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="b201b-119">L'esempio seguente mostra l'implementazione <xref:System.IObserver%601> della classe `TemperatureReporter`.</span><span class="sxs-lookup"><span data-stu-id="b201b-119">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="b201b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b201b-120">Example</span></span>  
 <span data-ttu-id="b201b-121">L'esempio seguente contiene il codice sorgente completo per la classe `TemperatureReporter`, che fornisce l'implementazione <xref:System.IObserver%601> per un'applicazione di monitoraggio della temperatura.</span><span class="sxs-lookup"><span data-stu-id="b201b-121">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="b201b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b201b-122">See also</span></span>

- <xref:System.IObserver%601>
- [<span data-ttu-id="b201b-123">Modello di progettazione Observer</span><span class="sxs-lookup"><span data-stu-id="b201b-123">Observer Design Pattern</span></span>](observer-design-pattern.md)
- [<span data-ttu-id="b201b-124">Procedura: implementare un provider</span><span class="sxs-lookup"><span data-stu-id="b201b-124">How to: Implement a Provider</span></span>](how-to-implement-a-provider.md)
- [<span data-ttu-id="b201b-125">Procedure consigliate per un modello di progettazione observer</span><span class="sxs-lookup"><span data-stu-id="b201b-125">Observer Design Pattern Best Practices</span></span>](observer-design-pattern-best-practices.md)
