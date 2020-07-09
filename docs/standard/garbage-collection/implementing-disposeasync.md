---
title: Implementare un metodo DisposeAsync
description: ''
author: IEvangelist
ms.author: dapine
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 31c4cc9136862551e02fae030e38ebd6c2916a38
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100925"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="585ef-102">Implementare un metodo DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="585ef-102">Implement a DisposeAsync method</span></span>

<span data-ttu-id="585ef-103">L' <xref:System.IAsyncDisposable?displayProperty=nameWithType> interfaccia è stata introdotta come parte di C# 8,0.</span><span class="sxs-lookup"><span data-stu-id="585ef-103">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="585ef-104">Il metodo viene implementato <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> quando è necessario eseguire la pulizia delle risorse, esattamente come si farebbe quando si [implementa un metodo Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="585ef-104">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="585ef-105">Una delle differenze principali, tuttavia, è che questa implementazione consente operazioni di pulizia asincrona.</span><span class="sxs-lookup"><span data-stu-id="585ef-105">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="585ef-106"><xref:System.IAsyncDisposable.DisposeAsync>Restituisce un oggetto <xref:System.Threading.Tasks.ValueTask> che rappresenta l'operazione di eliminazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="585ef-106">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="585ef-107">Generalmente, quando si implementa l' <xref:System.IAsyncDisposable> interfaccia, le classi implementano anche l' <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="585ef-107">It is typical that when implementing the <xref:System.IAsyncDisposable> interface, classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="585ef-108">Un modello di implementazione valido dell' <xref:System.IAsyncDisposable> interfaccia deve essere preparato per l'eliminazione sincrona o asincrona.</span><span class="sxs-lookup"><span data-stu-id="585ef-108">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="585ef-109">Tutte le linee guida per l'implementazione del modello Dispose si applicano all'implementazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="585ef-109">All of the guidance for implementing the dispose pattern applies to the asynchronous implementation.</span></span> <span data-ttu-id="585ef-110">Questo articolo presuppone che si abbia già familiarità con l' [implementazione di un metodo Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="585ef-110">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="585ef-111">DisposeAsync () e DisposeAsyncCore ()</span><span class="sxs-lookup"><span data-stu-id="585ef-111">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="585ef-112">L' <xref:System.IAsyncDisposable> interfaccia dichiara un singolo metodo senza parametri, <xref:System.IAsyncDisposable.DisposeAsync> .</span><span class="sxs-lookup"><span data-stu-id="585ef-112">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="585ef-113">Qualsiasi classe non sealed deve avere un `DisposeAsyncCore()` metodo aggiuntivo che restituisca anche un <xref:System.Threading.Tasks.ValueTask> .</span><span class="sxs-lookup"><span data-stu-id="585ef-113">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="585ef-114">`public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> Implementazione senza parametri.</span><span class="sxs-lookup"><span data-stu-id="585ef-114">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="585ef-115">Un `protected virtual ValueTask DisposeAsyncCore()` Metodo la cui firma è:</span><span class="sxs-lookup"><span data-stu-id="585ef-115">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

<span data-ttu-id="585ef-116">Il `DisposeAsyncCore()` metodo è `virtual` in modo che le classi derivate possano definire una pulizia aggiuntiva nelle rispettive sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="585ef-116">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

### <a name="the-disposeasync-method"></a><span data-ttu-id="585ef-117">Metodo DisposeAsync ()</span><span class="sxs-lookup"><span data-stu-id="585ef-117">The DisposeAsync() method</span></span>

<span data-ttu-id="585ef-118">Il `public` `DisposeAsync()` metodo senza parametri viene chiamato in modo implicito in un' `await using` istruzione e il suo scopo è liberare le risorse non gestite, eseguire operazioni di pulizia generali e indicare che il finalizzatore, se presente, non è necessario eseguire.</span><span class="sxs-lookup"><span data-stu-id="585ef-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, needn't run.</span></span> <span data-ttu-id="585ef-119">Liberare la memoria associata a un oggetto gestito è sempre il dominio del [Garbage Collector](index.md).</span><span class="sxs-lookup"><span data-stu-id="585ef-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="585ef-120">Per questo motivo il metodo ha un'implementazione standard:</span><span class="sxs-lookup"><span data-stu-id="585ef-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="585ef-121">Una differenza principale nel modello Dispose asincrono rispetto al modello Dispose è che la chiamata da <xref:System.IAsyncDisposable.DisposeAsync> al metodo di `Dispose(bool)` Overload viene fornita `false` come argomento.</span><span class="sxs-lookup"><span data-stu-id="585ef-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="585ef-122">Quando si implementa il <xref:System.IDisposable.Dispose?displayProperty=nameWithType> metodo, tuttavia, `true` viene passato.</span><span class="sxs-lookup"><span data-stu-id="585ef-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="585ef-123">Ciò consente di garantire l'equivalenza funzionale con il modello Dispose sincrono e garantisce inoltre che vengano richiamati i percorsi di codice del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="585ef-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="585ef-124">In altre parole, il `DisposeAsyncCore()` metodo eliminerà le risorse gestite in modo asincrono, pertanto non è opportuno eliminarle anche in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="585ef-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="585ef-125">Quindi, chiamare `Dispose(false)` anziché `Dispose(true)` .</span><span class="sxs-lookup"><span data-stu-id="585ef-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="585ef-126">Implementare il modello Dispose asincrono</span><span class="sxs-lookup"><span data-stu-id="585ef-126">Implement the async dispose pattern</span></span>

<span data-ttu-id="585ef-127">Tutte le classi non sealed devono essere considerate come una classe di base potenziale, perché potrebbero essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="585ef-127">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="585ef-128">Se si implementa il modello di Dispose asincrono per qualsiasi classe di base potenziale, è necessario fornire il `protected virtual ValueTask DisposeAsyncCore()` metodo.</span><span class="sxs-lookup"><span data-stu-id="585ef-128">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="585ef-129">Di seguito è riportato un esempio di implementazione del modello Dispose asincrono che usa un oggetto <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="585ef-129">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="585ef-130">Nell'esempio precedente è stato utilizzato <xref:System.Text.Json.Utf8JsonWriter> . per ulteriori informazioni su, vedere la pagina relativa `System.Text.Json` [alla migrazione da Newtonsoft.Json a System.Text.Js](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="585ef-130">The previous example used the <xref:System.Text.Json.Utf8JsonWriter>, for more information on `System.Text.Json`, see, [migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="585ef-131">Uso della funzionalità eliminabile asincrona</span><span class="sxs-lookup"><span data-stu-id="585ef-131">Using async disposable</span></span>

<span data-ttu-id="585ef-132">Per utilizzare correttamente un oggetto che implementa l' <xref:System.IAsyncDisposable> interfaccia, è possibile utilizzare le parole chiave [await](../../csharp/language-reference/operators/await.md)e [using](../../csharp/language-reference/keywords/using.md) insieme.</span><span class="sxs-lookup"><span data-stu-id="585ef-132">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using.md) keywords together.</span></span> <span data-ttu-id="585ef-133">Si consideri l'esempio seguente, `ExampleAsyncDisposable` in cui viene creata un'istanza della classe e quindi ne viene eseguito il wrapper in un' `await using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="585ef-133">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated, then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="585ef-134">Usare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> metodo di estensione dell' <xref:System.IAsyncDisposable> interfaccia per configurare il modo in cui viene eseguito il marshalling della continuazione dell'attività nel contesto o nell'utilità di pianificazione originale.</span><span class="sxs-lookup"><span data-stu-id="585ef-134">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="585ef-135">Per altre informazioni su `ConfigureAwait` , vedere [domande frequenti su ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="585ef-135">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="585ef-136">Per le situazioni in cui l'utilizzo di `ConfigureAwait` non è necessario, l' `await using` istruzione può essere semplificata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="585ef-136">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="585ef-137">Inoltre, può essere scritto per utilizzare l'ambito implicito di una [dichiarazione using](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="585ef-137">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="585ef-138">Using in pila</span><span class="sxs-lookup"><span data-stu-id="585ef-138">Stacked usings</span></span>

<span data-ttu-id="585ef-139">Nelle situazioni in cui si creano e si usano più oggetti che implementano <xref:System.IAsyncDisposable> , è possibile che `using` le istruzioni di sovrapposizione in condizioni errate possano impedire chiamate a <xref:System.IAsyncDisposable.DisposeAsync> .</span><span class="sxs-lookup"><span data-stu-id="585ef-139">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="585ef-140">Per evitare potenziali problemi, è consigliabile evitare lo stacking e seguire invece questo modello di esempio:</span><span class="sxs-lookup"><span data-stu-id="585ef-140">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="585ef-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="585ef-141">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
