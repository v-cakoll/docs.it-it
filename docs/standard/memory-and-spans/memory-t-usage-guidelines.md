---
title: Linee guida per l'utilizzo di Memory<T> e Span<T>
description: Questo articolo descrive la memoria <T> e l'intervallo <T> , ovvero buffer di dati strutturati in .NET Core che possono essere usati nelle pipeline.
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: b9405d746c141308c7d984dac9da0d65d1048d1e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380019"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="18149-103">Linee guida per l'utilizzo di Memory\<T> e Span\<T></span><span class="sxs-lookup"><span data-stu-id="18149-103">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="18149-104">.NET Core include vari tipi che rappresentano una regione contigua arbitraria della memoria.</span><span class="sxs-lookup"><span data-stu-id="18149-104">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="18149-105">In .NET Core 2.0 sono stati introdotti <xref:System.Span%601> e <xref:System.ReadOnlySpan%601>, ovvero buffer di memoria leggeri che possono essere supportati da memoria gestita o non gestita.</span><span class="sxs-lookup"><span data-stu-id="18149-105">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="18149-106">Dato che questi tipi possono solo essere archiviati nello stack, non sono adatti per vari scenari, incluse le chiamate di metodi asincrone.</span><span class="sxs-lookup"><span data-stu-id="18149-106">Because these types can only be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="18149-107">.NET Core 2.1 introduce alcuni tipi aggiuntivi, tra cui <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> e <xref:System.Buffers.MemoryPool%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-107">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="18149-108">Come <xref:System.Span%601>, <xref:System.Memory%601> e i tipi correlati possono essere supportati da memoria gestita e non gestita.</span><span class="sxs-lookup"><span data-stu-id="18149-108">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="18149-109">Diversamente da <xref:System.Span%601>, <xref:System.Memory%601> supporta l'archiviazione nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="18149-109">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can be stored on the managed heap.</span></span>

<span data-ttu-id="18149-110">Sia <xref:System.Span%601> che <xref:System.Memory%601> sono buffer di dati strutturati che possono essere usati nelle pipeline.</span><span class="sxs-lookup"><span data-stu-id="18149-110">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="18149-111">Questo significa che sono progettati in modo che alcuni o tutti i dati possano essere passati in modo efficiente ai componenti nella pipeline, che possono elaborarli e facoltativamente modificare il buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-111">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="18149-112">Dato che <xref:System.Memory%601> e i tipi correlati sono accessibili da più componenti o da più thread, è importante che gli sviluppatori seguano alcune linee guida sull'utilizzo standard in modo da produrre codice solido.</span><span class="sxs-lookup"><span data-stu-id="18149-112">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="18149-113">Proprietari, consumer e gestione della durata</span><span class="sxs-lookup"><span data-stu-id="18149-113">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="18149-114">Poiché i buffer possono essere passati tra le API e dato che i buffer sono in alcuni casi accessibili da più thread, è importante prendere in considerazione la gestione della durata.</span><span class="sxs-lookup"><span data-stu-id="18149-114">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="18149-115">Esistono tre concetti principali:</span><span class="sxs-lookup"><span data-stu-id="18149-115">There are three core concepts:</span></span>

- <span data-ttu-id="18149-116">**Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18149-116">**Ownership**.</span></span> <span data-ttu-id="18149-117">Il proprietario di un'istanza del buffer è responsabile della gestione della durata, inclusa l'eliminazione definitiva del buffer quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="18149-117">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="18149-118">Tutti i buffer hanno un solo proprietario.</span><span class="sxs-lookup"><span data-stu-id="18149-118">All buffers have a single owner.</span></span> <span data-ttu-id="18149-119">Il proprietario è in genere il componente che ha creato il buffer o che ha ricevuto il buffer da una factory.</span><span class="sxs-lookup"><span data-stu-id="18149-119">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="18149-120">La proprietà può anche essere trasferita. Il **componente A** può cedere il controllo del buffer al **componente-B** e a quel punto il **componente A** non può più usare il buffer e il \*\*componente B \*\* diventa responsabile dell'eliminazione definitiva del buffer quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="18149-120">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="18149-121">A **consumo**.</span><span class="sxs-lookup"><span data-stu-id="18149-121">**Consumption**.</span></span> <span data-ttu-id="18149-122">Il consumer di un'istanza del buffer è autorizzato a usare l'istanza del buffer leggendo da tale istanza e forse anche scrivendo in tale istanza.</span><span class="sxs-lookup"><span data-stu-id="18149-122">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="18149-123">I buffer possono avere un solo consumer alla volta, a meno che non venga fornito un meccanismo di sincronizzazione esterno.</span><span class="sxs-lookup"><span data-stu-id="18149-123">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="18149-124">Il consumer attivo di un buffer non è necessariamente il proprietario del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-124">The active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="18149-125">**Lease**.</span><span class="sxs-lookup"><span data-stu-id="18149-125">**Lease**.</span></span> <span data-ttu-id="18149-126">Il lease è il periodo di tempo per cui un particolare componente è autorizzato a essere il consumer del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-126">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="18149-127">L'esempio di pseudocodice seguente illustra questi tre concetti.</span><span class="sxs-lookup"><span data-stu-id="18149-127">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="18149-128">Include un metodo `Main` che crea un'istanza di un buffer <xref:System.Memory%601> di tipo <xref:System.Char>, chiama il metodo `WriteInt32ToBuffer` per scrivere la rappresentazione stringa di un intero nel buffer e quindi chiama il metodo `DisplayBufferToConsole` per visualizzare il valore del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-128">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

<span data-ttu-id="18149-129">Il metodo `Main` crea il buffer (in questo caso un'istanza di <xref:System.Span%601>) e pertanto ne è il proprietario.</span><span class="sxs-lookup"><span data-stu-id="18149-129">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="18149-130">`Main` è quindi responsabile dell'eliminazione definitiva del buffer quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="18149-130">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="18149-131">Questa operazione viene eseguita chiamando il metodo <xref:System.Span%601.Clear?displayProperty=nameWithType> del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-131">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="18149-132">(Il metodo <xref:System.Span%601.Clear> in questo caso cancella effettivamente la memoria del buffer. La struttura <xref:System.Span%601> non ha in effetti un metodo per l'eliminazione definitiva del buffer.)</span><span class="sxs-lookup"><span data-stu-id="18149-132">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="18149-133">Il buffer ha due consumer, `WriteInt32ToBuffer` e `DisplayBufferToConsole`.</span><span class="sxs-lookup"><span data-stu-id="18149-133">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="18149-134">Esiste un solo consumer alla volta (prima `WriteInt32ToBuffer` e poi `DisplayBufferToConsole`), e nessuno dei consumer è proprietario del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-134">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="18149-135">Si noti anche che il concetto di "consumer" in questo contesto non implica una visualizzazione di sola lettura del buffer. I consumer possono modificare il contenuto del buffer, come nel caso di `WriteInt32ToBuffer`, se ricevono una vista in lettura/scrittura del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-135">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="18149-136">Il metodo `WriteInt32ToBuffer` ha un lease per il buffer (può utilizzarlo) dall'inizio della chiamata al metodo fino al momento in cui il metodo restituisce il controllo.</span><span class="sxs-lookup"><span data-stu-id="18149-136">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="18149-137">Analogamente, `DisplayBufferToConsole` ha un lease per il buffer mentre è in esecuzione e il lease viene rilasciato quando viene rimosso il metodo.</span><span class="sxs-lookup"><span data-stu-id="18149-137">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="18149-138">(Non è disponibile alcuna API per la gestione del lease. Un "lease" è una questione concettuale.)</span><span class="sxs-lookup"><span data-stu-id="18149-138">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="18149-139">Memory\<T> e il modello proprietario/consumer</span><span class="sxs-lookup"><span data-stu-id="18149-139">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="18149-140">Come indicato nella sezione [Proprietari, consumer e gestione della durata](#owners-consumers-and-lifetime-management), un buffer ha sempre un proprietario.</span><span class="sxs-lookup"><span data-stu-id="18149-140">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="18149-141">.NET Core supporta due modelli di proprietà:</span><span class="sxs-lookup"><span data-stu-id="18149-141">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="18149-142">Un modello che supporta la proprietà singola.</span><span class="sxs-lookup"><span data-stu-id="18149-142">A model that supports single ownership.</span></span> <span data-ttu-id="18149-143">Un buffer ha un solo proprietario per tutta la sua durata.</span><span class="sxs-lookup"><span data-stu-id="18149-143">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="18149-144">Un modello che supporta il trasferimento della proprietà.</span><span class="sxs-lookup"><span data-stu-id="18149-144">A model that supports ownership transfer.</span></span> <span data-ttu-id="18149-145">La proprietà di un buffer può essere trasferita dal relativo proprietario (autore) originale a un altro componente, che quindi diventa responsabile della gestione della durata del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-145">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="18149-146">Tale proprietario può a sua volta trasferire la proprietà a un altro componente e così via.</span><span class="sxs-lookup"><span data-stu-id="18149-146">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="18149-147">Per gestire in modo esplicito la proprietà di un buffer si usa l'interfaccia <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18149-147">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="18149-148"><xref:System.Buffers.IMemoryOwner%601> supporta entrambi i modelli di proprietà.</span><span class="sxs-lookup"><span data-stu-id="18149-148"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="18149-149">Il componente con un riferimento a <xref:System.Buffers.IMemoryOwner%601> è proprietario del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-149">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="18149-150">L'esempio seguente usa un'istanza di <xref:System.Buffers.IMemoryOwner%601?> per riflettere la proprietà di un buffer <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-150">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of an <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="18149-151">È anche possibile scrivere questo esempio con [`using`](../../csharp/language-reference/keywords/using-statement.md) :</span><span class="sxs-lookup"><span data-stu-id="18149-151">We can also write this example with the [`using`](../../csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="18149-152">In questo codice:</span><span class="sxs-lookup"><span data-stu-id="18149-152">In this code:</span></span>

- <span data-ttu-id="18149-153">Il metodo `Main` mantiene il riferimento all'istanza di <xref:System.Buffers.IMemoryOwner%601>, quindi il metodo `Main` è il proprietario del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-153">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="18149-154">I metodi `WriteInt32ToBuffer` e `DisplayBufferToConsole` accettano <xref:System.Memory%601> come API pubblica.</span><span class="sxs-lookup"><span data-stu-id="18149-154">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept <xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="18149-155">Sono pertanto consumer del buffer</span><span class="sxs-lookup"><span data-stu-id="18149-155">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="18149-156">e lo utilizzano uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="18149-156">And they only consume it one at a time.</span></span>

<span data-ttu-id="18149-157">Anche se il metodo `WriteInt32ToBuffer` è progettato per scrivere un valore nel buffer, il metodo `DisplayBufferToConsole` non lo è.</span><span class="sxs-lookup"><span data-stu-id="18149-157">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="18149-158">Di conseguenza, potrebbe avere accettato un argomento di tipo <xref:System.ReadOnlyMemory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-158">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="18149-159">Per altre informazioni su <xref:System.ReadOnlyMemory%601> , vedere [regola #2: usare ReadOnlySpan \< t> o ReadOnlyMemory \< t> se il buffer deve essere](#rule-2)di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="18149-159">For more information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="18149-160">Istanza di Memory\<T> "senza proprietario"</span><span class="sxs-lookup"><span data-stu-id="18149-160">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="18149-161">È possibile creare un'istanza di <xref:System.Memory%601> senza usare <xref:System.Buffers.IMemoryOwner%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-161">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="18149-162">In questo caso, la proprietà del buffer è implicita anziché esplicita ed è supportato solo il modello con proprietario singolo.</span><span class="sxs-lookup"><span data-stu-id="18149-162">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="18149-163">A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="18149-163">You can do this by:</span></span>

- <span data-ttu-id="18149-164">Chiamare direttamente uno dei costruttori <xref:System.Memory%601> passando un `T[]`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="18149-164">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="18149-165">Chiamare il metodo di estensione [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) per produrre un'istanza di `ReadOnlyMemory<char>`.</span><span class="sxs-lookup"><span data-stu-id="18149-165">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="18149-166">Il metodo che crea inizialmente l'istanza di <xref:System.Memory%601> è il proprietario implicito del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-166">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="18149-167">Non è possibile trasferire la proprietà a qualsiasi altro componente perché non esiste alcuna istanza di <xref:System.Buffers.IMemoryOwner%601> per facilitare il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="18149-167">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="18149-168">(In alternativa, è anche possibile immaginare che il Garbage Collector del runtime sia il proprietario del buffer e che i metodi utilizzino semplicemente il buffer.)</span><span class="sxs-lookup"><span data-stu-id="18149-168">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="18149-169">Linee guida per l'utilizzo</span><span class="sxs-lookup"><span data-stu-id="18149-169">Usage guidelines</span></span>

<span data-ttu-id="18149-170">Dato che un blocco di memoria ha un proprietario, ma è destinato a essere passato a più componenti, alcuni dei quali potrebbero operare simultaneamente su un blocco di memoria specifico, è importante definire delle linee guida per l'uso sia di <xref:System.Memory%601> che di <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-170">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="18149-171">Le linee guida sono necessarie per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="18149-171">Guidelines are necessary because:</span></span>

- <span data-ttu-id="18149-172">Un componente può mantenere un riferimento a un blocco di memoria dopo il rilascio da parte del proprietario.</span><span class="sxs-lookup"><span data-stu-id="18149-172">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="18149-173">È possibile che un componente operi su un buffer in contemporanea con un altro componente, con un processo che danneggia i dati nel buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-173">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="18149-174">Anche se il funzionamento basato sull'allocazione dello stack di <xref:System.Span%601> consente di ottimizzare le prestazioni e rende <xref:System.Span%601> il tipo preferito per operare su un blocco di memoria, <xref:System.Span%601> diventa soggetto ad alcune restrizioni significative.</span><span class="sxs-lookup"><span data-stu-id="18149-174">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions.</span></span> <span data-ttu-id="18149-175">È importante sapere quando usare <xref:System.Span%601> e quando usare <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-175">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="18149-176">Di seguito sono riportati alcuni consigli per usare correttamente <xref:System.Memory%601> e i tipi correlati.</span><span class="sxs-lookup"><span data-stu-id="18149-176">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="18149-177">Il materiale sussidiario applicabile a e <xref:System.Memory%601> <xref:System.Span%601> si applica anche a <xref:System.ReadOnlyMemory%601> e, a <xref:System.ReadOnlySpan%601> meno che non si noti esplicitamente diversamente.</span><span class="sxs-lookup"><span data-stu-id="18149-177">Guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="18149-178">**#1 di regole: per un'API sincrona, utilizzare Span \< t> anziché Memory \< t> come parametro, se possibile.**</span><span class="sxs-lookup"><span data-stu-id="18149-178">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="18149-179"><xref:System.Span%601> è più versatile di <xref:System.Memory%601> e può rappresentare una più ampia gamma di buffer di memoria contigui.</span><span class="sxs-lookup"><span data-stu-id="18149-179"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="18149-180"><xref:System.Span%601> offre anche prestazioni migliori di <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-180"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>.</span></span> <span data-ttu-id="18149-181">Infine, è possibile usare la proprietà <xref:System.Memory%601.Span?displayProperty=nameWithType> per convertire un'istanza di <xref:System.Memory%601> in <xref:System.Span%601>, anche se la conversione da Span\<T> a Memory\<T> non è possibile.</span><span class="sxs-lookup"><span data-stu-id="18149-181">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="18149-182">Nel caso i chiamanti abbiano un'istanza di <xref:System.Memory%601>, pertanto, potranno chiamare comunque i metodi con i parametri <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-182">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="18149-183">L'uso di un parametro di tipo <xref:System.Span%601> anziché di tipo <xref:System.Memory%601> consente anche di scrivere un'implementazione corretta del metodo consumer.</span><span class="sxs-lookup"><span data-stu-id="18149-183">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="18149-184">Si otterranno automaticamente controlli in fase di compilazione per assicurarsi che non si stia tentando di accedere al buffer dopo la scadenza del lease del metodo (più avanti sono disponibili altre informazioni su questo argomento).</span><span class="sxs-lookup"><span data-stu-id="18149-184">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="18149-185">Sarà a volte necessario usare un parametro <xref:System.Memory%601> invece di un parametro<xref:System.Span%601>, anche in caso di sincronia completa.</span><span class="sxs-lookup"><span data-stu-id="18149-185">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="18149-186">È possibile che un'API da cui si dipende accetti solo argomenti <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-186">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="18149-187">Non è un problema, ma tenere presenti i compromessi che implica l'uso sincrono di <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-187">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2" />

<span data-ttu-id="18149-188">**#2 della regola: usare ReadOnlySpan \< t> o ReadOnlyMemory \< t> se il buffer deve essere di sola lettura.**</span><span class="sxs-lookup"><span data-stu-id="18149-188">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="18149-189">Negli esempi precedenti il metodo `DisplayBufferToConsole` legge solo dal buffer e non modifica il contenuto del buffer.</span><span class="sxs-lookup"><span data-stu-id="18149-189">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="18149-190">La firma del metodo deve essere modificata come segue.</span><span class="sxs-lookup"><span data-stu-id="18149-190">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="18149-191">In effetti, se si combinano questa regola e la regola 1, è possibile migliorare ancora e riscrivere la firma del metodo come segue:</span><span class="sxs-lookup"><span data-stu-id="18149-191">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="18149-192">Il metodo `DisplayBufferToConsole` ora funziona praticamente con qualsiasi tipo di buffer immaginabile: `T[]`, archiviazione allocata con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) e così via.</span><span class="sxs-lookup"><span data-stu-id="18149-192">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), and so on.</span></span> <span data-ttu-id="18149-193">È anche possibile passare direttamente una <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="18149-193">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="18149-194">**#3 della regola: se il metodo accetta \< la memoria t> e restituisce `void` , non è necessario usare l' \< istanza Memory t> dopo che il metodo restituisce un risultato.**</span><span class="sxs-lookup"><span data-stu-id="18149-194">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="18149-195">Questo aspetto è correlato al concetto di "lease" menzionato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="18149-195">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="18149-196">Il lease di un metodo che restituisce void per l'istanza di <xref:System.Memory%601> inizia con l'accesso al metodo e termina quando il metodo viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="18149-196">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="18149-197">Si consideri l'esempio seguente, che chiama `Log` in un ciclo in base all'input dalla console.</span><span class="sxs-lookup"><span data-stu-id="18149-197">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="18149-198">Se `Log` è un metodo completamente sincrono, questo codice si comporterà come previsto poiché non esiste un solo consumer attivo dell'istanza di memoria in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="18149-198">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="18149-199">Si immagini, invece, che `Log` abbia questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="18149-199">But imagine instead that `Log` has this implementation.</span></span>

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

<span data-ttu-id="18149-200">In questa implementazione `Log` viola il lease perché tenta ancora di usare l'istanza di <xref:System.Memory%601> in background dopo l'uscita dal metodo originale.</span><span class="sxs-lookup"><span data-stu-id="18149-200">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="18149-201">Il metodo `Main` potrebbe modificare il buffer mentre `Log` tenta una lettura, con potenziale danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="18149-201">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="18149-202">Esistono diversi modi per risolvere questo problema:</span><span class="sxs-lookup"><span data-stu-id="18149-202">There are several ways to resolve this:</span></span>

- <span data-ttu-id="18149-203">Il metodo `Log` può restituire un <xref:System.Threading.Tasks.Task> invece di `void`, come l'implementazione seguente del metodo `Log`.</span><span class="sxs-lookup"><span data-stu-id="18149-203">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="18149-204">`Log` può invece essere implementato come segue:</span><span class="sxs-lookup"><span data-stu-id="18149-204">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="18149-205">**#4 della regola: se il metodo accetta una memoria \< t> e restituisce un'attività, non è necessario usare l' \< istanza memory t> dopo che l'attività passa allo stato terminale.**</span><span class="sxs-lookup"><span data-stu-id="18149-205">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="18149-206">Si tratta semplicemente della variante asincrona della regola 3.</span><span class="sxs-lookup"><span data-stu-id="18149-206">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="18149-207">Il metodo `Log` dall'esempio precedente può essere scritto come segue per la conformità a questa regola:</span><span class="sxs-lookup"><span data-stu-id="18149-207">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="18149-208">In questo caso, "stato terminale" significa che l'attività passa a uno stato completato, di errore o annullato.</span><span class="sxs-lookup"><span data-stu-id="18149-208">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="18149-209">In altre parole, "stato terminale" significa "tutto ciò che potrebbe causare la generazione di await o la continuazione dell'esecuzione".</span><span class="sxs-lookup"><span data-stu-id="18149-209">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="18149-210">Queste linee guida si applicano ai metodi che restituiscono <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> o qualsiasi tipo simile.</span><span class="sxs-lookup"><span data-stu-id="18149-210">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="18149-211">**#5 della regola: se il costruttore accetta la memoria \< t> come parametro, si presuppone che i metodi di istanza nell'oggetto costruito siano utenti dell' \< istanza di memoria t>.**</span><span class="sxs-lookup"><span data-stu-id="18149-211">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="18149-212">Prendere in considerazione gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="18149-212">Consider the following example:</span></span>

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

<span data-ttu-id="18149-213">In questo caso, il costruttore `OddValueExtractor` accetta un `ReadOnlyMemory<int>` come parametro costruttore, pertanto il costruttore stesso è un consumer dell'istanza di `ReadOnlyMemory<int>` e tutti i metodi di istanza per il valore restituito sono anche consumer dell'istanza di `ReadOnlyMemory<int>` originale.</span><span class="sxs-lookup"><span data-stu-id="18149-213">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="18149-214">Questo significa che `TryReadNextOddValue` utilizza l'istanza di `ReadOnlyMemory<int>`, anche se non viene passata direttamente al metodo `TryReadNextOddValue`.</span><span class="sxs-lookup"><span data-stu-id="18149-214">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="18149-215">**#6 della regola: se nel tipo è presente una proprietà della memoria impostabile \< t>-tipizzata (o un metodo di istanza equivalente), si presuppone che i metodi di istanza su tale oggetto siano consumer della memoria \< t> istanza.**</span><span class="sxs-lookup"><span data-stu-id="18149-215">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="18149-216">Si tratta semplicemente di una variante della regola 5.</span><span class="sxs-lookup"><span data-stu-id="18149-216">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="18149-217">Questa regola esiste perché si presuppone che i setter delle proprietà o i metodi equivalenti acquisiscano gli input e li salvino in modo permanente, in modo che i metodi di istanza per lo stesso oggetto possano utilizzare lo stato acquisito.</span><span class="sxs-lookup"><span data-stu-id="18149-217">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="18149-218">L'esempio seguente attiva questa regola:</span><span class="sxs-lookup"><span data-stu-id="18149-218">The following example triggers this rule:</span></span>

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

<span data-ttu-id="18149-219">**#7 di regole: se si dispone \< di un riferimento a IMemoryOwner T>, è necessario a un certo punto eliminarlo o trasferirne la proprietà (ma non entrambi).**</span><span class="sxs-lookup"><span data-stu-id="18149-219">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="18149-220">Dato che un'istanza di <xref:System.Memory%601> potrebbe essere supportata da memoria gestita o non gestita, il proprietario deve chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> al termine delle operazioni eseguite sull'istanza di <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="18149-220">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="18149-221">In alternativa, il proprietario potrebbe trasferire la proprietà dell'istanza di <xref:System.Buffers.IMemoryOwner%601> a un altro componente e a quel punto il componente di destinazione diventa responsabile di chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> al momento appropriato (più avanti sono disponibili altre informazioni su questo argomento).</span><span class="sxs-lookup"><span data-stu-id="18149-221">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="18149-222">Se non viene chiamato il metodo <xref:System.Buffers.MemoryPool%601.Dispose%2A>, potrebbero verificarsi perdite della memoria non gestita o altre forme di riduzione del livello delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="18149-222">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="18149-223">Questa regola si applica anche al codice che chiama i metodi factory, ad esempio <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18149-223">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="18149-224">Il chiamante diventa il proprietario dell'oggetto restituito <xref:System.Buffers.IMemoryOwner%601> ed è responsabile dell'eliminazione dell'istanza al termine.</span><span class="sxs-lookup"><span data-stu-id="18149-224">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="18149-225">**#8 di regole: se si dispone di un \< parametro IMemoryOwner T> nella superficie dell'API, si accetta la proprietà di tale istanza.**</span><span class="sxs-lookup"><span data-stu-id="18149-225">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="18149-226">L'accettazione di un'istanza di questo tipo segnala che il componente intende acquisire la proprietà di questa istanza.</span><span class="sxs-lookup"><span data-stu-id="18149-226">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="18149-227">Il componente diventa responsabile della corretta eliminazione in base alla regola 7.</span><span class="sxs-lookup"><span data-stu-id="18149-227">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="18149-228">Qualsiasi componente che trasferisce la proprietà dell'istanza di <xref:System.Buffers.IMemoryOwner%601> a un altro componente non deve più usare tale istanza dopo il completamento della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="18149-228">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18149-229">Se il costruttore accetta <xref:System.Buffers.IMemoryOwner%601> come parametro, il tipo deve implementare <xref:System.IDisposable> e il metodo <xref:System.IDisposable.Dispose%2A> deve chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18149-229">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="18149-230">**#9 di regole: se si esegue il wrapping di un metodo p/Invoke sincrono, l'API deve accettare span \< T> come parametro.**</span><span class="sxs-lookup"><span data-stu-id="18149-230">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="18149-231">In base alla regola 1, <xref:System.Span%601> è in genere il tipo corretto da usare per le API sincrone.</span><span class="sxs-lookup"><span data-stu-id="18149-231">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="18149-232">È possibile aggiungere <xref:System.Span%601> istanze tramite la [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) parola chiave, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="18149-232">You can pin <xref:System.Span%601> instances via the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="18149-233">Nell'esempio precedente, `pbData` può essere Null se, ad esempio, l'intervallo di input è vuoto.</span><span class="sxs-lookup"><span data-stu-id="18149-233">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="18149-234">Se il metodo esportato richiede assolutamente che `pbData` non sia Null, anche se `cbData` è 0, il metodo può essere implementato come segue:</span><span class="sxs-lookup"><span data-stu-id="18149-234">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="18149-235">**#10 di regole: se si esegue il wrapping di un metodo p/invoke asincrono, l'API deve accettare la memoria \< T> come parametro.**</span><span class="sxs-lookup"><span data-stu-id="18149-235">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="18149-236">Poiché non è possibile utilizzare la [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) parola chiave tra le operazioni asincrone, è possibile utilizzare il <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> metodo per aggiungere <xref:System.Memory%601> istanze, indipendentemente dal tipo di memoria contigua rappresentata dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="18149-236">Since you cannot use the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="18149-237">Nell'esempio seguente viene illustrato come usare questa API per eseguire una chiamata P/Invoke asincrona.</span><span class="sxs-lookup"><span data-stu-id="18149-237">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)(handle.Target);
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a><span data-ttu-id="18149-238">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18149-238">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
