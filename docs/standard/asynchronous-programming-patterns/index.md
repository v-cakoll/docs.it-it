---
title: Modelli di programmazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249036"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="b5b5b-102">Modelli di programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="b5b5b-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="b5b5b-103">In .NET Framework sono disponibili tre modelli per l'esecuzione di operazioni asincrone:</span><span class="sxs-lookup"><span data-stu-id="b5b5b-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="b5b5b-104">**Modello di programmazione asincrona (APM)** (detto anche modello <xref:System.IAsyncResult>), dove le operazioni asincrone richiedono i metodi `Begin` e `End` (ad esempio, `BeginWrite` e `EndWrite` per le operazioni di scrittura asincrona).</span><span class="sxs-lookup"><span data-stu-id="b5b5b-104">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="b5b5b-105">Questo modello non è più consigliato per i nuovi sviluppi.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="b5b5b-106">Per altre informazioni, vedere [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM).</span><span class="sxs-lookup"><span data-stu-id="b5b5b-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="b5b5b-107">**Modello asincrono basato su eventi (EAP)**, che richiede un metodo con suffisso `Async` oltre a uno o più eventi, tipi delegati di gestore eventi e tipi derivati da `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-107">**Event-based Asynchronous Pattern (EAP)**, which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="b5b5b-108">EAP è stato introdotto in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="b5b5b-109">Non è consigliabile per i nuovi sviluppi.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="b5b5b-110">Per ulteriori informazioni, vedere [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP).</span><span class="sxs-lookup"><span data-stu-id="b5b5b-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="b5b5b-111">**Modello asincrono basato su attività (TAP)**, che usa un unico metodo per rappresentare l'inizio e il completamento di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-111">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="b5b5b-112">TAP è stato introdotto in.NET Framework 4 ed è l'approccio consigliato per la programmazione asincrona in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="b5b5b-113">Le parole chiave [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) in C# e gli operatori [Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) nel linguaggio Visual Basic aggiungono supporto del linguaggio per TAP.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="b5b5b-114">Per altre informazioni, vedere [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività, TAP).</span><span class="sxs-lookup"><span data-stu-id="b5b5b-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="b5b5b-115">Confronto tra modelli</span><span class="sxs-lookup"><span data-stu-id="b5b5b-115">Comparing Patterns</span></span>  

<span data-ttu-id="b5b5b-116">Per un rapido confronto tra le procedure delle operazioni asincrone dei tre modelli, considerare un metodo `Read` che legga una specifica quantità di rati in un determinato buffer, iniziando da uno specifico offset:</span><span class="sxs-lookup"><span data-stu-id="b5b5b-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="b5b5b-117">La controparte APM di questo metodo esporrà i metodi `BeginRead` e `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="b5b5b-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="b5b5b-118">La controparte EAP esporrà il seguente set di tipi e membri:</span><span class="sxs-lookup"><span data-stu-id="b5b5b-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="b5b5b-119">La controparte TAP esporrà il seguente metodo `ReadAsync` singolo:</span><span class="sxs-lookup"><span data-stu-id="b5b5b-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="b5b5b-120">Per una trattazione completa di TAP, APM ed EAP, vedere i collegamenti disponibili nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="b5b5b-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b5b5b-121">Related topics</span></span>

| <span data-ttu-id="b5b5b-122">Titolo</span><span class="sxs-lookup"><span data-stu-id="b5b5b-122">Title</span></span> | <span data-ttu-id="b5b5b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5b5b-123">Description</span></span> |
| ----- | ----------- |
| <span data-ttu-id="b5b5b-124">[Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM)</span><span class="sxs-lookup"><span data-stu-id="b5b5b-124">[Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)</span></span> | <span data-ttu-id="b5b5b-125">Viene descritto il modello legacy che usa l'interfaccia <xref:System.IAsyncResult> per ottenere un comportamento asincrono.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="b5b5b-126">Questo modello non è consigliabile per i nuovi sviluppi.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-126">This model is no longer recommended for new development.</span></span> |
| <span data-ttu-id="b5b5b-127">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="b5b5b-127">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span> | <span data-ttu-id="b5b5b-128">Viene descritto il modello legacy per fornire il comportamento asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="b5b5b-129">Questo modello non è consigliabile per i nuovi sviluppi.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="b5b5b-130">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="b5b5b-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="b5b5b-131">Viene descritto il nuovo modello asincrono basato sullo spazio dei nomi <xref:System.Threading.Tasks>.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="b5b5b-132">Questo modello è l'approccio consigliato per la programmazione asincrona in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b5b5b-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b5b5b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5b5b-133">See also</span></span>

- [<span data-ttu-id="b5b5b-134">Programmazione asincrona in C#</span><span class="sxs-lookup"><span data-stu-id="b5b5b-134">Asynchronous programming in C#</span></span>](~/docs/csharp/async.md)   
- [<span data-ttu-id="b5b5b-135">Programmazione asincrona in F#</span><span class="sxs-lookup"><span data-stu-id="b5b5b-135">Async Programming in F#</span></span>](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [<span data-ttu-id="b5b5b-136">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5b5b-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
