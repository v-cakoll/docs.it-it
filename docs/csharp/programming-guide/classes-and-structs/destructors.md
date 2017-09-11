---
title: Finalizzatori (Guida per programmatori C#)
ms.date: 2017-05-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 43bb7e6488da5eda863e7ad70b25c9bf55bebb52
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="6eae4-102">Finalizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6eae4-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="6eae4-103">I finalizzatori sono usati per finalizzare istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="6eae4-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eae4-104">Note</span><span class="sxs-lookup"><span data-stu-id="6eae4-104">Remarks</span></span>  
  
-   <span data-ttu-id="6eae4-105">I finalizzatori non possono essere definiti negli struct.</span><span class="sxs-lookup"><span data-stu-id="6eae4-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="6eae4-106">Vengono usati solo con le classi.</span><span class="sxs-lookup"><span data-stu-id="6eae4-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="6eae4-107">Una classe può avere un solo finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="6eae4-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="6eae4-108">I finalizzatori non possono essere ereditati e non è possibile eseguirne l'overload.</span><span class="sxs-lookup"><span data-stu-id="6eae4-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="6eae4-109">I finalizzatori non possono essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="6eae4-109">Finalizers cannot be called.</span></span> <span data-ttu-id="6eae4-110">Vengono richiamati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6eae4-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="6eae4-111">Un finalizzatore non accetta modificatori e non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="6eae4-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="6eae4-112">Ad esempio, di seguito è riportata la dichiarazione di un finalizzatore per la classe `Car`.</span><span class="sxs-lookup"><span data-stu-id="6eae4-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 <span data-ttu-id="6eae4-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6eae4-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span></span>  

<span data-ttu-id="6eae4-114">Un finalizzatore può anche essere implementato come definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6eae4-114">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

<span data-ttu-id="6eae4-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="6eae4-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span></span>  
  
 <span data-ttu-id="6eae4-116">Il finalizzatore chiama implicitamente <xref:System.Object.Finalize%2A> per la classe di base dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6eae4-116">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="6eae4-117">Di conseguenza, una chiamata a un finalizzatore viene convertita implicitamente nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6eae4-117">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="6eae4-118">In questo modo, il metodo `Finalize` viene chiamato in modo ricorsivo per tutte le istanze nella catena di ereditarietà, dalla più derivata alla meno derivata.</span><span class="sxs-lookup"><span data-stu-id="6eae4-118">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6eae4-119">I finalizzatori vuoti non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="6eae4-119">Empty finalizers should not be used.</span></span> <span data-ttu-id="6eae4-120">Quando una classe contiene un finalizzatore, viene creata una voce nella coda `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="6eae4-120">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="6eae4-121">Quando si chiama il finalizzatore, viene richiamato Garbage Collector per elaborare la coda.</span><span class="sxs-lookup"><span data-stu-id="6eae4-121">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="6eae4-122">Se il finalizzatore è vuoto, si verifica semplicemente un calo di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6eae4-122">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="6eae4-123">Il programmatore non ha alcun controllo sul momento in cui viene chiamato il finalizzatore, poiché il momento è determinato dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="6eae4-123">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="6eae4-124">Il Garbage Collector controlla gli oggetti che non vengono più usati dall'applicazione e,</span><span class="sxs-lookup"><span data-stu-id="6eae4-124">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="6eae4-125">se considera un oggetto idoneo per la finalizzazione, chiama il finalizzatore (se presente) e recupera la memoria usata per archiviare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6eae4-125">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> <span data-ttu-id="6eae4-126">I finalizzatori vengono chiamati anche quando si esce dal programma.</span><span class="sxs-lookup"><span data-stu-id="6eae4-126">Finalizers are also called when the program exits.</span></span>  
  
 <span data-ttu-id="6eae4-127">Sebbene sia possibile forzare l'esecuzione di Garbage Collection chiamando <xref:System.GC.Collect%2A>, nella maggior parte dei casi è preferibile non effettuare questa operazione per evitare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6eae4-127">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="6eae4-128">Uso di finalizzatori per liberare risorse</span><span class="sxs-lookup"><span data-stu-id="6eae4-128">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="6eae4-129">In generale C# non richiede una gestione della memoria come quella necessaria quando si sviluppa con un linguaggio che non ha come destinazione un runtime con Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6eae4-129">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="6eae4-130">Il Garbage Collector di .NET Framework, infatti, gestisce in modo implicito l'allocazione e il rilascio di memoria per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6eae4-130">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="6eae4-131">Tuttavia, quando l'applicazione incapsula risorse non gestite come finestre, file e connessioni di rete, è necessario usare i finalizzatori per rendere disponibili tali risorse.</span><span class="sxs-lookup"><span data-stu-id="6eae4-131">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="6eae4-132">Quando l'oggetto è idoneo per la finalizzazione, il Garbage Collector esegue il metodo `Finalize` dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6eae4-132">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="6eae4-133">Rilascio esplicito di risorse</span><span class="sxs-lookup"><span data-stu-id="6eae4-133">Explicit Release of Resources</span></span>  
 <span data-ttu-id="6eae4-134">Se l'applicazione usa una risorsa esterna che consuma molta memoria, è consigliabile specificare un modo per rilasciare la risorsa in modo esplicito prima che il Garbage Collector renda disponibile l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6eae4-134">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="6eae4-135">A questo scopo, è possibile implementare un metodo `Dispose` dall'interfaccia <xref:System.IDisposable> che esegua la pulitura necessaria per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6eae4-135">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="6eae4-136">Questo consente di migliorare notevolmente le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6eae4-136">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="6eae4-137">Nonostante questo controllo esplicito sulle risorse, il finalizzatore consente di salvaguardare la pulitura delle risorse nei casi in cui la chiamata al metodo `Dispose` non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="6eae4-137">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="6eae4-138">Per informazioni dettagliate sulla pulitura delle risorse, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6eae4-138">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="6eae4-139">Pulizia delle risorse non gestite</span><span class="sxs-lookup"><span data-stu-id="6eae4-139">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="6eae4-140">Implementazione di un metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="6eae4-140">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="6eae4-141">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="6eae4-141">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="6eae4-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="6eae4-142">Example</span></span>  
 <span data-ttu-id="6eae4-143">L'esempio seguente crea tre classi che costituiscono una catena di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="6eae4-143">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="6eae4-144">La classe `First` è la classe base, `Second` è derivata da `First` e `Third` è derivata da `Second`.</span><span class="sxs-lookup"><span data-stu-id="6eae4-144">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="6eae4-145">Tutte e tre hanno finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="6eae4-145">All three have finalizers.</span></span> <span data-ttu-id="6eae4-146">In `Main` viene creata un'istanza della classe più derivata.</span><span class="sxs-lookup"><span data-stu-id="6eae4-146">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="6eae4-147">Durante l'esecuzione del programma, si noti che i finalizzatori delle tre classi vengono chiamati automaticamente e in ordine, dalla classe più derivata alla meno derivata.</span><span class="sxs-lookup"><span data-stu-id="6eae4-147">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 <span data-ttu-id="6eae4-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6eae4-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6eae4-149">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6eae4-149">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6eae4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eae4-150">See Also</span></span>  
 <span data-ttu-id="6eae4-151"><xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="6eae4-151"><xref:System.IDisposable></span></span>   
 <span data-ttu-id="6eae4-152">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6eae4-152">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6eae4-153">[Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="6eae4-153">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="6eae4-154">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6eae4-154">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

