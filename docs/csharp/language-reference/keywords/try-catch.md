---
title: try-catch - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 3d4315a09869b77b4ae8cbb43646f9a96280b678
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173471"
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="e9c1f-102">try-catch (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e9c1f-102">try-catch (C# Reference)</span></span>

<span data-ttu-id="e9c1f-103">L'istruzione try-catch è costituita da un blocco `try` seguito da una o più clausole `catch`, che specificano i gestori per eccezioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>

<span data-ttu-id="e9c1f-104">Quando viene generata un'eccezione, Common Language Runtime(CLR) cerca l'istruzione `catch` che gestisce questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-104">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="e9c1f-105">Se il metodo attualmente in esecuzione non contiene tale blocco `catch`, CLR analizza il metodo che ha chiamato il metodo corrente e così via fino allo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-105">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="e9c1f-106">Se non viene trovato alcun blocco `catch`, CLR visualizza un messaggio di eccezione non gestita per l'utente e interrompe l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-106">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>

<span data-ttu-id="e9c1f-107">Il blocco `try` contiene il codice protetto che potrebbe generare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-107">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="e9c1f-108">Il blocco viene eseguito fino a quando non viene generata un'eccezione o viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-108">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="e9c1f-109">Ad esempio, il seguente tentativo di eseguire il cast di un oggetto `null` genera l'eccezione <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="e9c1f-109">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

<span data-ttu-id="e9c1f-110">Anche se la clausola `catch` può essere usata senza argomenti per intercettare qualsiasi tipo di eccezione, questo utilizzo non è consigliato.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-110">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="e9c1f-111">In generale, è consigliabile intercettare solo le eccezioni di cui si sa come eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-111">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="e9c1f-112">È quindi opportuno specificare sempre argomento di oggetto derivato da <xref:System.Exception?displayProperty=nameWithType>, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9c1f-112">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>

```csharp
catch (InvalidCastException e)
{
}
```

<span data-ttu-id="e9c1f-113">È possibile usare più clausole `catch` specifiche nella stessa istruzione try-catch.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-113">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="e9c1f-114">In questo caso, l'ordine delle clausole `catch` è importante perché le clausole `catch` vengono esaminate nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-114">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="e9c1f-115">Intercettare le eccezioni più specifiche prima di quelle meno specifiche.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-115">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="e9c1f-116">Il compilatore provoca un errore se si ordinano i blocchi catch in modo che un blocco successivo non possa mai essere raggiunto.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-116">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>

<span data-ttu-id="e9c1f-117">Usando gli argomenti `catch`, è possibile filtrare le eccezioni che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-117">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="e9c1f-118">È anche possibile usare un filtro eccezioni per esaminare ulteriormente l'eccezione e decidere se gestirla.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-118">You can also use an exception filter that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="e9c1f-119">Se il filtro eccezioni restituisce false, la ricerca di un gestore prosegue.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-119">If the exception filter returns false, then the search for a handler continues.</span></span>

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

<span data-ttu-id="e9c1f-120">I filtri eccezioni sono preferibili per l'intercettazione e la rigenerazione (come illustrato di seguito) perché lasciano intatto lo stack.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-120">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="e9c1f-121">Se un gestore successivo esegue il dump dello stack, è possibile visualizzare l'origine dell'eccezione, anziché solo l'ultima posizione in cui è stata rigenerata.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-121">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="e9c1f-122">Un uso comune delle espressioni di filtro eccezioni è la registrazione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-122">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="e9c1f-123">È possibile creare un filtro che restituisca sempre false da visualizzare anche in un log. È possibile registrare le eccezioni mentre si verificano senza doverle gestire e rigenerare.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-123">You can create a filter that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>

<span data-ttu-id="e9c1f-124">Un'istruzione [throw](throw.md) può essere usata in un blocco `catch` per rigenerare l'eccezione intercettata dall'istruzione `catch`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-124">A [throw](throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="e9c1f-125">Il seguente esempio estrae le informazioni di origine da un'eccezione <xref:System.IO.IOException> e quindi genera l'eccezione per il metodo padre.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-125">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

<span data-ttu-id="e9c1f-126">È possibile intercettare un'eccezione e generarne un'altra.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-126">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="e9c1f-127">In questo caso, specificare l'eccezione intercettata come eccezione interna, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-127">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

<span data-ttu-id="e9c1f-128">È anche possibile generare nuovamente un'eccezione quando una determinata condizione è true, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-128">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> <span data-ttu-id="e9c1f-129">È anche possibile usare un filtro eccezioni per ottenere un risultato simile in un modo spesso più pulito, che in più non modifichi lo stack, come descritto in precedenza in questo documento.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-129">It is also possible to use an exception filter to get a similar result in an often cleaner fashion (as well as not modifying the stack, as explained earlier in this document).</span></span> <span data-ttu-id="e9c1f-130">L'esempio seguente presenta un comportamento simile al precedente per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-130">The following example has a similar behavior for callers as the previous example.</span></span> <span data-ttu-id="e9c1f-131">La funzione restituisce `InvalidCastException` al chiamante quando `e.Data` è `null`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-131">The function throws the `InvalidCastException` back to the caller when `e.Data` is `null`.</span></span>
>
> ```csharp
> catch (InvalidCastException e) when (e.Data != null)
> {
>     // Take some action.
> }
> ```

<span data-ttu-id="e9c1f-132">Da un blocco `try` inizializzare solo le variabili dichiarate al suo interno.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-132">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="e9c1f-133">In caso contrario, è possibile che si verifichi un'eccezione prima del completamento dell'esecuzione del blocco.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-133">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="e9c1f-134">Nel seguente esempio di codice, la variabile `n` viene inizializzata nel blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-134">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="e9c1f-135">Un tentativo di usare questa variabile al di fuori del blocco `try` nell'istruzione `Write(n)` genererà un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-135">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>

```csharp
static void Main()
{
    int n;
    try
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

<span data-ttu-id="e9c1f-136">Per altre informazioni su catch, vedere [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-136">For more information about catch, see [try-catch-finally](try-catch-finally.md).</span></span>

## <a name="exceptions-in-async-methods"></a><span data-ttu-id="e9c1f-137">Eccezioni nei metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="e9c1f-137">Exceptions in async methods</span></span>

<span data-ttu-id="e9c1f-138">Un metodo asincrono viene contrassegnato da un modificatore [async](async.md) e in genere contiene una o più espressioni o istruzioni await.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-138">An async method is marked  by an  [async](async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="e9c1f-139">Un'espressione await applica l'operatore [await](../operators/await.md) a un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-139">An await expression applies the [await](../operators/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="e9c1f-140">Quando il controllo raggiunge un oggetto `await` nel metodo asincrono, l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-140">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="e9c1f-141">Una volta completata l'attività, l'esecuzione del metodo può riprendere.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-141">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="e9c1f-142">Per altre informazioni, vedere [Programmazione asincrona con Async e Await](../../programming-guide/concepts/async/index.md) e [Flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-142">For more information, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>

<span data-ttu-id="e9c1f-143">L'attività completata a cui viene applicato `await` può essere in uno stato di errore a causa di un'eccezione non gestita nel metodo che restituisce l'attività.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-143">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="e9c1f-144">L'attesa dell'attività genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-144">Awaiting the task throws an exception.</span></span> <span data-ttu-id="e9c1f-145">Un'attività può inoltre terminare con uno stato di annullamento se viene annullato il processo asincrono che la restituisce.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-145">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="e9c1f-146">L'attesa di un'attività annullata genera un'eccezione `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-146">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="e9c1f-147">Per altre informazioni su come annullare un processo asincrono, vedere [Ottimizzazione dell'applicazione Async](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-147">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="e9c1f-148">Per intercettare l'eccezione, attendere l'attività in un blocco `try` e intercettare l'eccezione nel blocco `catch` associato.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-148">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="e9c1f-149">Per un esempio, vedere la sezione [Esempio di metodo asincrono](#async-method-example).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-149">For an example, see the [Async method example](#async-method-example) section.</span></span>

<span data-ttu-id="e9c1f-150">Un'attività può essere in uno stato di errore perché si sono verificate più eccezioni nel metodo asincrono atteso.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-150">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="e9c1f-151">Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-151">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9c1f-152">Quando si attende tale attività, solo una delle eccezioni viene intercettata, ma non è possibile prevedere quale.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-152">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="e9c1f-153">Per un esempio, vedere la sezione [Esempio di Task.WhenAll](#taskwhenall-example).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-153">For an example, see the [Task.WhenAll example](#taskwhenall-example) section.</span></span>

## <a name="example"></a><span data-ttu-id="e9c1f-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9c1f-154">Example</span></span>

<span data-ttu-id="e9c1f-155">Nel seguente esempio, il blocco `try` contiene una chiamata al metodo `ProcessString` che potrebbe causare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-155">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="e9c1f-156">La clausola `catch` contiene il gestore di eccezioni che visualizza solo un messaggio sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-156">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="e9c1f-157">Quando l'istruzione `throw` viene chiamata da `MyMethod`, il sistema cerca l'istruzione `catch` e visualizza il messaggio `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-157">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a><span data-ttu-id="e9c1f-158">Esempio di due blocchi catch</span><span class="sxs-lookup"><span data-stu-id="e9c1f-158">Two catch blocks example</span></span>

<span data-ttu-id="e9c1f-159">Nell'esempio seguente, vengono usati due blocchi catch e viene intercettata l'eccezione più specifica, che è la prima.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-159">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>

<span data-ttu-id="e9c1f-160">Per intercettare l'eccezione meno specifica, è possibile sostituire l'istruzione throw in `ProcessString` con l'istruzione seguente: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-160">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>

<span data-ttu-id="e9c1f-161">Se nell'esempio si inserisce per primo il blocco catch meno specifico, viene visualizzato il messaggio di errore seguente: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-161">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a><span data-ttu-id="e9c1f-162">Esempio di metodo asincrono</span><span class="sxs-lookup"><span data-stu-id="e9c1f-162">Async method example</span></span>

<span data-ttu-id="e9c1f-163">L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="e9c1f-164">Per intercettare un'eccezione generata da un'attività asincrona, inserire l'espressione `await` in un blocco `try` e intercettare l'eccezione in un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>

<span data-ttu-id="e9c1f-165">Rimuovere il commento dalla riga `throw new Exception` nell'esempio per illustrare la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="e9c1f-166">La proprietà `IsFaulted` dell'attività viene impostata su `True`, la proprietà `Exception.InnerException` dell'attività viene impostata sull'eccezione e l'eccezione viene intercettata nel blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>

<span data-ttu-id="e9c1f-167">Rimuovere il commento dalla riga `throw new OperationCanceledException` per illustrare cosa accade quando si annulla un processo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-167">Uncomment the `throw new OperationCanceledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="e9c1f-168">La proprietà `IsCanceled` dell'attività viene impostata su `true` e l'eccezione viene intercettata nel blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="e9c1f-169">In alcune condizioni che non si applicano a questo esempio, la proprietà `IsFaulted` dell'attività viene impostata su `true` e `IsCanceled` viene impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a><span data-ttu-id="e9c1f-170">Esempio di Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="e9c1f-170">Task.WhenAll example</span></span>

<span data-ttu-id="e9c1f-171">Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-171">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="e9c1f-172">Il blocco `try` attende l'attività restituita da una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-172">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9c1f-173">L'attività viene completata quando vengono completate le tre attività a cui si applica WhenAll.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-173">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>

<span data-ttu-id="e9c1f-174">Ognuna delle tre attività genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-174">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="e9c1f-175">Il blocco `catch` scorre le eccezioni presenti nella proprietà `Exception.InnerExceptions` dell'attività restituita da <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9c1f-175">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="e9c1f-176">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e9c1f-176">C# language specification</span></span>

<span data-ttu-id="e9c1f-177">Per altre informazioni, vedere la sezione [Istruzione try](~/_csharplang/spec/statements.md#the-try-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e9c1f-177">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9c1f-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9c1f-178">See also</span></span>

- [<span data-ttu-id="e9c1f-179">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e9c1f-179">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e9c1f-180">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e9c1f-180">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e9c1f-181">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e9c1f-181">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e9c1f-182">Istruzioni try, throw e catch (C++)</span><span class="sxs-lookup"><span data-stu-id="e9c1f-182">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="e9c1f-183">generazione</span><span class="sxs-lookup"><span data-stu-id="e9c1f-183">throw</span></span>](throw.md)
- [<span data-ttu-id="e9c1f-184">try...finally</span><span class="sxs-lookup"><span data-stu-id="e9c1f-184">try-finally</span></span>](try-finally.md)
- [<span data-ttu-id="e9c1f-185">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="e9c1f-185">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
