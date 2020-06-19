---
title: Finalizzatori - Guida per programmatori C#
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 62fc531a8064a8a5cb144a89aa9975b3199db976
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990121"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="48a03-102">Finalizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="48a03-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="48a03-103">I finalizzatori (detti anche **distruttori**) vengono usati per eseguire operazioni di pulizia finale eventualmente necessarie quando un'istanza di classe viene raccolta da Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="48a03-103">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48a03-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48a03-104">Remarks</span></span>  
  
- <span data-ttu-id="48a03-105">I finalizzatori non possono essere definiti negli struct.</span><span class="sxs-lookup"><span data-stu-id="48a03-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="48a03-106">Vengono usati solo con le classi.</span><span class="sxs-lookup"><span data-stu-id="48a03-106">They are only used with classes.</span></span>  
  
- <span data-ttu-id="48a03-107">Una classe può avere un solo finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="48a03-107">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="48a03-108">I finalizzatori non possono essere ereditati e non è possibile eseguirne l'overload.</span><span class="sxs-lookup"><span data-stu-id="48a03-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="48a03-109">I finalizzatori non possono essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="48a03-109">Finalizers cannot be called.</span></span> <span data-ttu-id="48a03-110">Vengono richiamati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="48a03-110">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="48a03-111">Un finalizzatore non accetta modificatori e non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="48a03-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="48a03-112">Ad esempio, di seguito è riportata la dichiarazione di un finalizzatore per la classe `Car`.</span><span class="sxs-lookup"><span data-stu-id="48a03-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="48a03-113">Un finalizzatore può anche essere implementato come definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="48a03-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="48a03-114">Il finalizzatore chiama implicitamente <xref:System.Object.Finalize%2A> per la classe di base dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48a03-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="48a03-115">Di conseguenza, una chiamata a un finalizzatore viene convertita implicitamente nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="48a03-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="48a03-116">Questo progetto significa che il `Finalize` metodo viene chiamato in modo ricorsivo per tutte le istanze nella catena di ereditarietà, dal più derivato al meno derivato.</span><span class="sxs-lookup"><span data-stu-id="48a03-116">This design means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48a03-117">I finalizzatori vuoti non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="48a03-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="48a03-118">Quando una classe contiene un finalizzatore, viene creata una voce nella coda `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="48a03-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="48a03-119">Quando si chiama il finalizzatore, viene richiamato Garbage Collector per elaborare la coda.</span><span class="sxs-lookup"><span data-stu-id="48a03-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="48a03-120">Se il finalizzatore è vuoto, si verifica semplicemente un calo di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="48a03-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="48a03-121">Il programmatore non ha alcun controllo sul momento in cui viene chiamato il finalizzatore; il Garbage Collector decide quando chiamarlo.</span><span class="sxs-lookup"><span data-stu-id="48a03-121">The programmer has no control over when the finalizer is called; the garbage collector decides when to call it.</span></span> <span data-ttu-id="48a03-122">Il Garbage Collector controlla gli oggetti che non vengono più usati dall'applicazione e,</span><span class="sxs-lookup"><span data-stu-id="48a03-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="48a03-123">se considera un oggetto idoneo per la finalizzazione, chiama il finalizzatore (se presente) e recupera la memoria usata per archiviare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48a03-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span>

 <span data-ttu-id="48a03-124">Nelle applicazioni .NET Framework (ma non nelle applicazioni .NET Core) i finalizzatori vengono chiamati anche alla chiusura del programma.</span><span class="sxs-lookup"><span data-stu-id="48a03-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span>
  
 <span data-ttu-id="48a03-125">È possibile forzare la Garbage Collection chiamando <xref:System.GC.Collect%2A> , ma nella maggior parte dei casi, questa chiamata deve essere evitata perché potrebbe creare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="48a03-125">It's possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this call should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="48a03-126">Uso di finalizzatori per liberare risorse</span><span class="sxs-lookup"><span data-stu-id="48a03-126">Using finalizers to release resources</span></span>  
 <span data-ttu-id="48a03-127">In generale, in C# non è richiesto il maggior livello di gestione della memoria da parte dello sviluppatore come linguaggi che non hanno come destinazione un runtime con Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="48a03-127">In general, C# does not require as much memory management on the part of the developer as languages that don't target a runtime with garbage collection.</span></span> <span data-ttu-id="48a03-128">Ciò è dovuto al fatto che .NET Garbage Collector gestisce in modo implicito l'allocazione e il rilascio di memoria per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="48a03-128">This is because the .NET garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="48a03-129">Tuttavia, quando l'applicazione incapsula risorse non gestite, ad esempio Windows, file e connessioni di rete, è necessario usare i finalizzatori per liberare tali risorse.</span><span class="sxs-lookup"><span data-stu-id="48a03-129">However, when your application encapsulates unmanaged resources, such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="48a03-130">Quando l'oggetto è idoneo per la finalizzazione, il Garbage Collector esegue il metodo `Finalize` dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48a03-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="48a03-131">Rilascio esplicito di risorse</span><span class="sxs-lookup"><span data-stu-id="48a03-131">Explicit release of resources</span></span>  
 <span data-ttu-id="48a03-132">Se l'applicazione usa una risorsa esterna che consuma molta memoria, è consigliabile specificare un modo per rilasciare la risorsa in modo esplicito prima che il Garbage Collector renda disponibile l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48a03-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="48a03-133">Per rilasciare la risorsa, implementare un `Dispose` metodo dall' <xref:System.IDisposable> interfaccia che esegue la pulizia necessaria per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48a03-133">To release the resource, implement a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="48a03-134">Questo consente di migliorare notevolmente le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48a03-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="48a03-135">Anche con questo controllo esplicito sulle risorse, il finalizzatore diventa una protezione per la pulizia delle risorse se la chiamata al `Dispose` metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="48a03-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method fails.</span></span>  
  
 <span data-ttu-id="48a03-136">Per ulteriori informazioni sulla pulizia delle risorse, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="48a03-136">For more information about cleaning up resources, see the following articles:</span></span>  
  
- [<span data-ttu-id="48a03-137">Pulizia delle risorse non gestite</span><span class="sxs-lookup"><span data-stu-id="48a03-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="48a03-138">Implementazione di un metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="48a03-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="48a03-139">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="48a03-139">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="48a03-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="48a03-140">Example</span></span>  
 <span data-ttu-id="48a03-141">L'esempio seguente crea tre classi che costituiscono una catena di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="48a03-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="48a03-142">La classe `First` è la classe base, `Second` è derivata da `First` e `Third` è derivata da `Second`.</span><span class="sxs-lookup"><span data-stu-id="48a03-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="48a03-143">Tutte e tre hanno finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="48a03-143">All three have finalizers.</span></span> <span data-ttu-id="48a03-144">In `Main` viene creata un'istanza della classe più derivata.</span><span class="sxs-lookup"><span data-stu-id="48a03-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="48a03-145">Durante l'esecuzione del programma, si noti che i finalizzatori delle tre classi vengono chiamati automaticamente e in ordine, dalla classe più derivata alla meno derivata.</span><span class="sxs-lookup"><span data-stu-id="48a03-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="48a03-146">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="48a03-146">C# language specification</span></span>  

<span data-ttu-id="48a03-147">Per altre informazioni, vedere la sezione [Distruttori](~/_csharplang/spec/classes.md#destructors) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="48a03-147">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48a03-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48a03-148">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="48a03-149">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="48a03-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="48a03-150">Costruttori</span><span class="sxs-lookup"><span data-stu-id="48a03-150">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="48a03-151">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="48a03-151">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
