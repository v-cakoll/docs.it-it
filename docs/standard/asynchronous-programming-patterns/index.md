---
title: Modelli di programmazione asincrona
description: Informazioni sul modello asincrono basato su attività (TAP), il modello asincrono basato su eventi (EAP), & il modello di programmazione asincrona (APM) in .NET.
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: bd4d44d8de8a64be82e9ce6af593a86719b59fcf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84583505"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="04de4-103">Modelli di programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="04de4-103">Asynchronous programming patterns</span></span>

<span data-ttu-id="04de4-104">In .NET sono disponibili tre modelli per l'esecuzione di operazioni asincrone:</span><span class="sxs-lookup"><span data-stu-id="04de4-104">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="04de4-105">**Modello asincrono basato su attività (TAP)**, che usa un unico metodo per rappresentare l'inizio e il completamento di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="04de4-105">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="04de4-106">Il modello TAP è stato introdotto in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="04de4-106">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="04de4-107">**È l'approccio consigliato per la programmazione asincrona in .NET.**</span><span class="sxs-lookup"><span data-stu-id="04de4-107">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="04de4-108">Le parole chiave [async](../../csharp/language-reference/keywords/async.md) e [await](../../csharp/language-reference/operators/await.md) in C# e gli operatori [Async](../../visual-basic/language-reference/modifiers/async.md) e [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic aggiungono il supporto del linguaggio per TAP.</span><span class="sxs-lookup"><span data-stu-id="04de4-108">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="04de4-109">Per altre informazioni, vedere [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività, TAP).</span><span class="sxs-lookup"><span data-stu-id="04de4-109">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="04de4-110">**Modello asincrono basato su eventi (EAP)**, ovvero il modello legacy basato su eventi per fornire il comportamento asincrono.</span><span class="sxs-lookup"><span data-stu-id="04de4-110">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="04de4-111">Richiede un metodo con il suffisso `Async` e uno o più eventi, i tipi delegati del gestore eventi e i tipi derivati da `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="04de4-111">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="04de4-112">EAP è stato introdotto in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="04de4-112">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="04de4-113">Questo modello non è più consigliato per i nuovi progetti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="04de4-113">It's no longer recommended for new development.</span></span> <span data-ttu-id="04de4-114">Per ulteriori informazioni, vedere [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP).</span><span class="sxs-lookup"><span data-stu-id="04de4-114">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="04de4-115">Il **modello di programmazione asincrona (APM)** (chiamato anche modello <xref:System.IAsyncResult>) è il modello legacy che usa l'interfaccia <xref:System.IAsyncResult> per fornire il comportamento asincrono.</span><span class="sxs-lookup"><span data-stu-id="04de4-115">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="04de4-116">In questo modello, le operazioni sincrone richiedono i metodi `Begin` e `End` (ad esempio `BeginWrite` e `EndWrite` per implementare un'operazione di scrittura asincrona).</span><span class="sxs-lookup"><span data-stu-id="04de4-116">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="04de4-117">Questo modello non è più consigliato per i nuovi sviluppi.</span><span class="sxs-lookup"><span data-stu-id="04de4-117">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="04de4-118">Per altre informazioni, vedere [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM).</span><span class="sxs-lookup"><span data-stu-id="04de4-118">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="04de4-119">Confronto dei modelli</span><span class="sxs-lookup"><span data-stu-id="04de4-119">Comparison of patterns</span></span>

<span data-ttu-id="04de4-120">Per un rapido confronto tra le procedure delle operazioni asincrone dei tre modelli, considerare un metodo `Read` che legga una specifica quantità di rati in un determinato buffer, iniziando da uno specifico offset:</span><span class="sxs-lookup"><span data-stu-id="04de4-120">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="04de4-121">La controparte TAP di questo metodo espone il seguente metodo `ReadAsync` singolo:</span><span class="sxs-lookup"><span data-stu-id="04de4-121">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="04de4-122">La controparte EAP esporrà il seguente set di tipi e membri:</span><span class="sxs-lookup"><span data-stu-id="04de4-122">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="04de4-123">La controparte APM espone i metodi `BeginRead` e `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="04de4-123">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="04de4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04de4-124">See also</span></span>

- [<span data-ttu-id="04de4-125">La programmazione asincrona in dettaglio</span><span class="sxs-lookup"><span data-stu-id="04de4-125">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="04de4-126">Programmazione asincrona in C#</span><span class="sxs-lookup"><span data-stu-id="04de4-126">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="04de4-127">Programmazione asincrona in F#</span><span class="sxs-lookup"><span data-stu-id="04de4-127">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="04de4-128">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04de4-128">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
