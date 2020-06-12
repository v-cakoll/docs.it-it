---
title: Utilizzo del modello asincrono basato su attività
description: Informazioni su come utilizzare il modello asincrono basato su attività (TAP) quando si utilizzano operazioni asincrone.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: 960d328e156d66b0bdc7baf4d4e0f151fd4d543c
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717497"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a><span data-ttu-id="83392-103">Utilizzo del modello asincrono basato su attività</span><span class="sxs-lookup"><span data-stu-id="83392-103">Consuming the Task-based Asynchronous Pattern</span></span>

<span data-ttu-id="83392-104">Quando si usa il modello asincrono basato su attività (TAP, Task-based Asynchronous Pattern) per lavorare con operazioni asincrone, è possibile usare i callback per ottenere un'attesa non bloccante.</span><span class="sxs-lookup"><span data-stu-id="83392-104">When you use the Task-based Asynchronous Pattern (TAP) to work with asynchronous operations, you can use callbacks to achieve waiting without blocking.</span></span>  <span data-ttu-id="83392-105">Per le attività, è possibile ottenere questo risultato tramite metodi come <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83392-105">For tasks, this is achieved through methods such as <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="83392-106">Il supporto asincrono basato sul linguaggio nasconde i callback consentendo alle operazioni asincrone di essere in attesa all'interno di un normale flusso di controllo e il codice generato dal compilatore fornisce lo stesso livello di supporto delle API.</span><span class="sxs-lookup"><span data-stu-id="83392-106">Language-based asynchronous support hides callbacks by allowing asynchronous operations to be awaited within normal control flow, and compiler-generated code provides this same API-level support.</span></span>

## <a name="suspending-execution-with-await"></a><span data-ttu-id="83392-107">Sospendere l'esecuzione con Await</span><span class="sxs-lookup"><span data-stu-id="83392-107">Suspending Execution with Await</span></span>
 <span data-ttu-id="83392-108">A partire da .NET Framework 4.5 è possibile usare la parola chiave [await](../../csharp/language-reference/operators/await.md) in C# e l'[operatore Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic per attendere in modo asincrono gli oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="83392-108">Starting with the .NET Framework 4.5, you can use the [await](../../csharp/language-reference/operators/await.md) keyword in C# and the [Await Operator](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic to asynchronously await <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects.</span></span> <span data-ttu-id="83392-109">Quando si è in attesa di <xref:System.Threading.Tasks.Task>, l'espressione `await` è di tipo `void`.</span><span class="sxs-lookup"><span data-stu-id="83392-109">When you're awaiting a <xref:System.Threading.Tasks.Task>, the `await` expression is of type `void`.</span></span> <span data-ttu-id="83392-110">Quando si è in attesa di <xref:System.Threading.Tasks.Task%601>, l'espressione `await` è di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="83392-110">When you're awaiting a <xref:System.Threading.Tasks.Task%601>, the `await` expression is of type `TResult`.</span></span> <span data-ttu-id="83392-111">Un'espressione `await` deve essere presente nel corpo di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-111">An `await` expression must occur inside the body of an asynchronous method.</span></span> <span data-ttu-id="83392-112">Per altre informazioni sul supporto dei linguaggi C# e Visual Basic in .NET Framework 4.5, vedere le specifiche dei linguaggi C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83392-112">For more information about C# and Visual Basic language support in the .NET Framework 4.5, see the C# and Visual Basic language specifications.</span></span>

 <span data-ttu-id="83392-113">Dietro le quinte, la funzionalità await installa un callback per l'attività tramite una continuazione.</span><span class="sxs-lookup"><span data-stu-id="83392-113">Under the covers, the await functionality installs a callback on the task by using a continuation.</span></span>  <span data-ttu-id="83392-114">Questo callback riprende il metodo asincrono in corrispondenza del punto di sospensione.</span><span class="sxs-lookup"><span data-stu-id="83392-114">This callback resumes the asynchronous method at the point of suspension.</span></span> <span data-ttu-id="83392-115">Quando il metodo asincrono viene ripreso, se l'operazione attesa è stata completata correttamente ed era <xref:System.Threading.Tasks.Task%601>, viene restituito il corrispondente elemento `TResult`.</span><span class="sxs-lookup"><span data-stu-id="83392-115">When the asynchronous method is resumed, if the awaited operation completed successfully and was a <xref:System.Threading.Tasks.Task%601>, its `TResult` is returned.</span></span>  <span data-ttu-id="83392-116">Se l'elemento <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> atteso è terminato con lo stato <xref:System.Threading.Tasks.TaskStatus.Canceled>, viene generata un'eccezione <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="83392-116">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state, an <xref:System.OperationCanceledException> exception is thrown.</span></span>  <span data-ttu-id="83392-117">Se l'elemento <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> atteso è terminato con lo stato <xref:System.Threading.Tasks.TaskStatus.Faulted>, viene generata l'eccezione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="83392-117">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state, the exception that caused it to fault is thrown.</span></span> <span data-ttu-id="83392-118">Un `Task` può fallire a causa di più eccezioni, ma solo una di queste eccezioni viene propagata.</span><span class="sxs-lookup"><span data-stu-id="83392-118">A `Task` can fault as a result of multiple exceptions, but only one of these exceptions is propagated.</span></span> <span data-ttu-id="83392-119">La proprietà <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> restituisce tuttavia un'eccezione <xref:System.AggregateException> contenente tutti gli errori.</span><span class="sxs-lookup"><span data-stu-id="83392-119">However, the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property returns an <xref:System.AggregateException> exception that contains all the errors.</span></span>

 <span data-ttu-id="83392-120">Se un contesto di sincronizzazione (oggetto <xref:System.Threading.SynchronizationContext>) è associato al thread che stava eseguendo il metodo asincrono durante la sospensione (ad esempio, se la proprietà <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> non è `null`), il metodo asincrono riprende nello stesso contesto di sincronizzazione usando il metodo <xref:System.Threading.SynchronizationContext.Post%2A> del contesto.</span><span class="sxs-lookup"><span data-stu-id="83392-120">If a synchronization context (<xref:System.Threading.SynchronizationContext> object) is associated with the thread that was executing the asynchronous method at the time of suspension (for example, if the <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> property is not `null`), the asynchronous method resumes on that same synchronization context by using the context’s <xref:System.Threading.SynchronizationContext.Post%2A> method.</span></span> <span data-ttu-id="83392-121">In caso contrario, si basa sull'utilità di pianificazione (oggetto <xref:System.Threading.Tasks.TaskScheduler>) che è corrente al momento della sospensione.</span><span class="sxs-lookup"><span data-stu-id="83392-121">Otherwise, it relies on the task scheduler (<xref:System.Threading.Tasks.TaskScheduler> object) that was current at the time of suspension.</span></span> <span data-ttu-id="83392-122">Si tratta in genere dell'utilità di pianificazione predefinita (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), che specifica come destinazione il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="83392-122">Typically, this is the default task scheduler (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), which targets the thread pool.</span></span> <span data-ttu-id="83392-123">L'utilità di pianificazione determina se l'operazione asincrona in attesa deve riprendere al momento del completamento o se la ripresa deve essere pianificata.</span><span class="sxs-lookup"><span data-stu-id="83392-123">This task scheduler determines whether the awaited asynchronous operation should resume where it completed or whether the resumption should be scheduled.</span></span> <span data-ttu-id="83392-124">L'utilità di pianificazione predefinita consente in genere l'esecuzione della continuazione nel thread in cui l'operazione attesa è stata completata.</span><span class="sxs-lookup"><span data-stu-id="83392-124">The default scheduler typically allows the continuation to run on the thread that the awaited operation completed.</span></span>

 <span data-ttu-id="83392-125">Quando un metodo asincrono viene chiamato, esegue in modo sincrono il corpo della funzione fino alla prima espressione await su un'istanza awaitable che non è ancora terminata, a quel punto la chiamata restituisce il controllo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="83392-125">When an asynchronous method is called, it synchronously executes the body of the function up until the first await expression on an awaitable instance that has not yet completed, at which point the invocation returns to the caller.</span></span> <span data-ttu-id="83392-126">Se il metodo asincrono non restituisce `void`, viene restituito un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> per rappresentare il calcolo in corso.</span><span class="sxs-lookup"><span data-stu-id="83392-126">If the asynchronous method does not return `void`, a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object is returned to represent the ongoing computation.</span></span> <span data-ttu-id="83392-127">In un metodo asincrono non void, se viene rilevata un'istruzione return o viene raggiunta la fine del corpo del metodo, l'attività termina con lo stato finale <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>.</span><span class="sxs-lookup"><span data-stu-id="83392-127">In a non-void asynchronous method, if a return statement is encountered or the end of the method body is reached, the task is completed in the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> final state.</span></span> <span data-ttu-id="83392-128">Se un'eccezione non gestita fa in modo che il controllo lasci il corpo del metodo asincrono, l'attività termina con lo stato <xref:System.Threading.Tasks.TaskStatus.Faulted>.</span><span class="sxs-lookup"><span data-stu-id="83392-128">If an unhandled exception causes control to leave the body of the asynchronous method, the task ends in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state.</span></span> <span data-ttu-id="83392-129">Se tale eccezione è <xref:System.OperationCanceledException>, l'attività termina invece con lo stato <xref:System.Threading.Tasks.TaskStatus.Canceled>.</span><span class="sxs-lookup"><span data-stu-id="83392-129">If that exception is an <xref:System.OperationCanceledException>, the task instead ends in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state.</span></span> <span data-ttu-id="83392-130">Viene in questo modo pubblicato il risultato o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="83392-130">In this manner, the result or exception is eventually published.</span></span>

 <span data-ttu-id="83392-131">Vi sono diverse varianti importanti di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="83392-131">There are several important variations of this behavior.</span></span>  <span data-ttu-id="83392-132">Per motivi di prestazioni, se un processo viene completato prima che sia atteso, il controllo non viene prodotto e la funzione prosegue nell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83392-132">For performance reasons, if a task has already completed by the time the task is awaited, control is not yielded, and the function continues to execute.</span></span>  <span data-ttu-id="83392-133">Non è inoltre sempre desiderabile tornare al contesto originale e questo comportamento può essere modificato. La sezione seguente descrive questa situazione nei dettagli.</span><span class="sxs-lookup"><span data-stu-id="83392-133">Additionally, returning to the original context isn't always the desired behavior and can be changed; this is described in more detail in the next section.</span></span>

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a><span data-ttu-id="83392-134">Configurazione della sospensione e della ripresa con Yield e ConfigureAwait</span><span class="sxs-lookup"><span data-stu-id="83392-134">Configuring Suspension and Resumption with Yield and ConfigureAwait</span></span>
 <span data-ttu-id="83392-135">Esistono diversi metodi che forniscono maggiore controllo sull'esecuzione di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-135">Several methods provide more control over an asynchronous method’s execution.</span></span> <span data-ttu-id="83392-136">È ad esempio possibile usare il metodo <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> per introdurre un punto di sospensione nel metodo asincrono:</span><span class="sxs-lookup"><span data-stu-id="83392-136">For example, you can use the <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> method to introduce a yield point into the asynchronous method:</span></span>

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 <span data-ttu-id="83392-137">Questa operazione equivale a eseguire un postback asincrono o a ritornare in modo asincrono al contesto corrente tramite programmazione.</span><span class="sxs-lookup"><span data-stu-id="83392-137">This is equivalent to asynchronously posting or scheduling back to the current context.</span></span>

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 <span data-ttu-id="83392-138">È anche possibile usare il metodo <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> per controllare meglio la sospensione e la ripresa in un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-138">You can also use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method for better control over suspension and resumption in an asynchronous method.</span></span>  <span data-ttu-id="83392-139">Come accennato in precedenza, per impostazione predefinita il contesto corrente viene acquisito nel momento in cui un metodo asincrono viene sospeso e questo contesto acquisito viene utilizzato per richiamare la continuazione del metodo asincrono al momento della ripresa.</span><span class="sxs-lookup"><span data-stu-id="83392-139">As mentioned previously, by default, the current context is captured at the time an asynchronous  method is suspended, and that captured context is used to invoke the asynchronous  method’s continuation upon resumption.</span></span>  <span data-ttu-id="83392-140">In molti casi questo è il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="83392-140">In many cases, this is the exact behavior you want.</span></span>  <span data-ttu-id="83392-141">In altri casi non è necessario preoccuparsi del contesto di continuazione ed è possibile ottenere migliori prestazioni evitando tali postback al contesto originale.</span><span class="sxs-lookup"><span data-stu-id="83392-141">In other cases, you may not care about the continuation context, and you can achieve better performance by avoiding such posts back to the original context.</span></span>  <span data-ttu-id="83392-142">Usare a tale scopo il metodo <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> per indicare all'operazione await di non acquisire e riprendere il contesto, ma di continuare l'esecuzione quando l'operazione asincrona di cui si era in attesa viene completata:</span><span class="sxs-lookup"><span data-stu-id="83392-142">To enable this, use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method to inform the await operation not to capture and resume on the context, but to continue execution wherever the asynchronous operation that was being awaited completed:</span></span>

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a><span data-ttu-id="83392-143">Annullamento di un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="83392-143">Canceling an Asynchronous Operation</span></span>
 <span data-ttu-id="83392-144">A partire da .NET Framework 4, i metodi TAP che supportano l'annullamento forniscono almeno un overload che accetta un token di annullamento (oggetto <xref:System.Threading.CancellationToken>).</span><span class="sxs-lookup"><span data-stu-id="83392-144">Starting with the .NET Framework 4, TAP methods that support cancellation provide at least one overload that accepts a cancellation token (<xref:System.Threading.CancellationToken> object).</span></span>

 <span data-ttu-id="83392-145">Un token di annullamento viene creato tramite un'origine di token di annullamento (oggetto <xref:System.Threading.CancellationTokenSource>).</span><span class="sxs-lookup"><span data-stu-id="83392-145">A cancellation token is created through a cancellation token source (<xref:System.Threading.CancellationTokenSource> object).</span></span>  <span data-ttu-id="83392-146">La proprietà <xref:System.Threading.CancellationTokenSource.Token%2A> dell'origine restituisce il token di annullamento che verrà segnalato quando il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A> dell'origine verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="83392-146">The source’s <xref:System.Threading.CancellationTokenSource.Token%2A> property returns the cancellation token that will be signaled when the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method is called.</span></span>  <span data-ttu-id="83392-147">Ad esempio, per scaricare una singola pagina Web e poter annullare l'operazione, si crea un oggetto <xref:System.Threading.CancellationTokenSource>, si passa il token al metodo TAP e quindi, quando si è pronti per annullare l'operazione, si chiama il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A> dell'origine:</span><span class="sxs-lookup"><span data-stu-id="83392-147">For example, if you want to download a single webpage and you want to be able to cancel the operation, you create a <xref:System.Threading.CancellationTokenSource> object, pass its token to the TAP method, and then call the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method when you're ready to cancel the operation:</span></span>

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 <span data-ttu-id="83392-148">Per annullare più chiamate asincrone, è possibile passare lo stesso token per tutte le chiamate:</span><span class="sxs-lookup"><span data-stu-id="83392-148">To cancel multiple asynchronous invocations, you can pass the same token to all invocations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 <span data-ttu-id="83392-149">È in alternativa possibile passare lo stesso token a un sottoinsieme selettivo di operazioni:</span><span class="sxs-lookup"><span data-stu-id="83392-149">Or, you can pass the same token to a selective subset of operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 <span data-ttu-id="83392-150">Le richieste di annullamento possono essere avviate da qualsiasi thread.</span><span class="sxs-lookup"><span data-stu-id="83392-150">Cancellation requests may be initiated from any thread.</span></span>

 <span data-ttu-id="83392-151">È possibile passare il valore di <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> a ogni metodo che accetta un token di annullamento per indicare che non verrà mai richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="83392-151">You can pass the <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> value to any method that accepts a cancellation token to indicate that cancellation will never be requested.</span></span>  <span data-ttu-id="83392-152">In tal modo la proprietà <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> restituisce `false` e il metodo chiamato può essere ottimizzato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="83392-152">This causes the <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> property to return `false`, and the called method can optimize accordingly.</span></span>  <span data-ttu-id="83392-153">È possibile, a scopo di test, passare un token di annullamento già annullato di cui si è creata un'istanza usando il costruttore che accetta un valore booleano per indicare se il token deve essere avviato in uno stato already-canceled (già cancellato) o not-cancelable (non cancellabile).</span><span class="sxs-lookup"><span data-stu-id="83392-153">For testing purposes, you can also pass in a pre-canceled cancellation token that is instantiated by using the constructor that accepts a Boolean value to indicate whether the token should start in an already-canceled or not-cancelable state.</span></span>

 <span data-ttu-id="83392-154">Questo approccio all'annullamento presenta diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="83392-154">This approach to cancellation has several advantages:</span></span>

- <span data-ttu-id="83392-155">È possibile passare lo stesso token di annullamento a un numero qualsiasi di operazioni asincrone e sincrone.</span><span class="sxs-lookup"><span data-stu-id="83392-155">You can pass the same cancellation token to any number of asynchronous and synchronous operations.</span></span>

- <span data-ttu-id="83392-156">La stessa richiesta di annullamento può essere estesa a un numero qualsiasi di listener.</span><span class="sxs-lookup"><span data-stu-id="83392-156">The same cancellation request may be proliferated to any number of listeners.</span></span>

- <span data-ttu-id="83392-157">Lo sviluppatore dell'API asincrona ha il controllo totale sull'eventuale richiesta di annullamento e sull'eventuale esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83392-157">The developer of the asynchronous API is in complete control of whether cancellation may be requested and when it may take effect.</span></span>

- <span data-ttu-id="83392-158">Il codice che usa l'API può determinare in modo selettivo a quali chiamate asincrone verranno propagate le richieste di annullamento.</span><span class="sxs-lookup"><span data-stu-id="83392-158">The code that consumes the API may selectively determine the asynchronous invocations that cancellation requests will be propagated to.</span></span>

## <a name="monitoring-progress"></a><span data-ttu-id="83392-159">Monitoraggio dello stato</span><span class="sxs-lookup"><span data-stu-id="83392-159">Monitoring Progress</span></span>
 <span data-ttu-id="83392-160">Alcuni metodi asincroni espongono lo stato di avanzamento tramite un'interfaccia dello stato di avanzamento passata all'interno del metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-160">Some asynchronous methods expose progress through a progress interface passed into the asynchronous method.</span></span>  <span data-ttu-id="83392-161">Si consideri ad esempio una funzione che scarica in modo asincrono una stringa di testo e, durante il processo, genera gli aggiornamenti dello stato di avanzamento che include la percentuale di download completata fino a quel momento.</span><span class="sxs-lookup"><span data-stu-id="83392-161">For example, consider a function which asynchronously downloads a string of text, and along the way raises progress updates that include the percentage of the download that has completed thus far.</span></span>  <span data-ttu-id="83392-162">Tale metodo può essere usato in un'applicazione Windows Presentation Foundation (WPF) come segue:</span><span class="sxs-lookup"><span data-stu-id="83392-162">Such a method could be consumed in a Windows Presentation Foundation (WPF) application as follows:</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a><span data-ttu-id="83392-163">Utilizzo di combinatori incorporati basati su attività</span><span class="sxs-lookup"><span data-stu-id="83392-163">Using the Built-in Task-based Combinators</span></span>
 <span data-ttu-id="83392-164">Lo spazio dei nomi <xref:System.Threading.Tasks> include diversi metodi per la composizione e l'uso delle attività.</span><span class="sxs-lookup"><span data-stu-id="83392-164">The <xref:System.Threading.Tasks> namespace includes several methods for composing and working with tasks.</span></span>

### <a name="taskrun"></a><span data-ttu-id="83392-165">Task.Run</span><span class="sxs-lookup"><span data-stu-id="83392-165">Task.Run</span></span>
 <span data-ttu-id="83392-166">La classe <xref:System.Threading.Tasks.Task> include diversi metodi <xref:System.Threading.Tasks.Task.Run%2A> che consentono di eseguire facilmente l'offload del lavoro come <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> nel pool di thread, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-166">The <xref:System.Threading.Tasks.Task> class includes several <xref:System.Threading.Tasks.Task.Run%2A> methods that let you easily offload work as a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> to the thread pool, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 <span data-ttu-id="83392-167">Alcuni di questi metodi <xref:System.Threading.Tasks.Task.Run%2A>, ad esempio l'overload <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, esistono come abbreviazione per il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83392-167">Some of these <xref:System.Threading.Tasks.Task.Run%2A> methods, such as the <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> overload, exist as shorthand for the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="83392-168">Altri overload, come <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, consentono di usare await nel lavoro di cui è stato eseguito l'offload, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-168">Other overloads, such as <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, enable you to use await within the offloaded work, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 <span data-ttu-id="83392-169">Tali overload sono logicamente equivalenti all'uso del metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> insieme al metodo di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> in Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="83392-169">Such overloads are logically equivalent to using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method in conjunction with the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension method in the Task Parallel Library.</span></span>

### <a name="taskfromresult"></a><span data-ttu-id="83392-170">Task.FromResult</span><span class="sxs-lookup"><span data-stu-id="83392-170">Task.FromResult</span></span>
 <span data-ttu-id="83392-171">Usare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> negli scenari in cui i dati possono essere già disponibili e devono essere solo restituiti da un metodo che restituisce attività del tipo <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="83392-171">Use the <xref:System.Threading.Tasks.Task.FromResult%2A> method in scenarios where data may already be available and just needs to be returned from a task-returning method lifted into a <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a><span data-ttu-id="83392-172">Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="83392-172">Task.WhenAll</span></span>
 <span data-ttu-id="83392-173">Usare il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A> per attendere in modo asincrono più operazioni asincrone rappresentate come attività.</span><span class="sxs-lookup"><span data-stu-id="83392-173">Use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method to asynchronously wait on multiple asynchronous operations that are represented as tasks.</span></span>  <span data-ttu-id="83392-174">Il metodo dispone di più overload che supportano un set di attività non generiche o un set non uniforme di attività generiche (ad esempio attendere in modo asincrono più operazioni che restituiscono void, o attendere in modo asincrono più metodi che restituiscono dei valori, dove ogni valore può essere di tipo diverso) e supportano un set uniforme di attività generiche (ad esempio attendere in modo asincrono più metodi che restituiscono `TResult`).</span><span class="sxs-lookup"><span data-stu-id="83392-174">The method has multiple overloads that support a set of non-generic tasks or a non-uniform set of generic tasks (for example, asynchronously waiting for multiple void-returning operations, or asynchronously waiting for multiple value-returning methods where each value may have a different type) and to support a uniform set of generic tasks (such as asynchronously waiting for multiple `TResult`-returning methods).</span></span>

 <span data-ttu-id="83392-175">Si supponga di voler inviare messaggi di posta elettronica a numerosi clienti.</span><span class="sxs-lookup"><span data-stu-id="83392-175">Let's say you want to send email messages to several customers.</span></span> <span data-ttu-id="83392-176">È possibile sovrapporre l'invio dei messaggi in modo da non dover attendere che un messaggio termini prima di inviare il successivo.</span><span class="sxs-lookup"><span data-stu-id="83392-176">You can overlap sending the messages so you're not waiting for one message to complete before sending the next.</span></span> <span data-ttu-id="83392-177">È inoltre possibile scoprire quando le operazioni di invio sono state completate e se si sono verificati degli errori:</span><span class="sxs-lookup"><span data-stu-id="83392-177">You can also find out when the send operations have completed and whether any errors have occurred:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 <span data-ttu-id="83392-178">Questo codice non gestisce in modo esplicito le eccezioni che possono verificarsi, ma consente la propagazione delle eccezioni da `await` sull'attività risultante da <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="83392-178">This code doesn't explicitly handle exceptions that may occur, but lets exceptions propagate out of the `await` on the resulting task from <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span></span>  <span data-ttu-id="83392-179">Per gestire le eccezioni, è possibile usare codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="83392-179">To handle the exceptions, you can use code such as the following:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 <span data-ttu-id="83392-180">In questo caso, se un'operazione asincrona non riesce, tutte le eccezioni verranno consolidate in un'eccezione <xref:System.AggregateException>, archiviata nell'attività <xref:System.Threading.Tasks.Task> restituita dal metodo <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="83392-180">In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an <xref:System.AggregateException> exception, which is stored in the <xref:System.Threading.Tasks.Task> that is returned from the <xref:System.Threading.Tasks.Task.WhenAll%2A> method.</span></span>  <span data-ttu-id="83392-181">Solo una di queste eccezioni viene tuttavia propagata dalla parola chiave `await`.</span><span class="sxs-lookup"><span data-stu-id="83392-181">However, only one of those exceptions is propagated by the `await` keyword.</span></span>  <span data-ttu-id="83392-182">Se si desidera esaminare tutte le eccezioni, è possibile riscrivere il codice precedente come segue:</span><span class="sxs-lookup"><span data-stu-id="83392-182">If you want to examine all the exceptions, you can rewrite the previous code as follows:</span></span>

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 <span data-ttu-id="83392-183">Si consideri un esempio in cui si scaricano più file dal Web in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-183">Let's consider an example of downloading multiple files from the web asynchronously.</span></span>  <span data-ttu-id="83392-184">In questo caso tutte le operazioni asincrone hanno tipi di risultato omogenei ed è facile accedere ai risultati:</span><span class="sxs-lookup"><span data-stu-id="83392-184">In this case, all the asynchronous operations have homogeneous result types, and it's easy to access the results:</span></span>

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 <span data-ttu-id="83392-185">È possibile applicare le stesse tecniche di gestione delle eccezioni illustrate nello scenario di restituzione di void precedente:</span><span class="sxs-lookup"><span data-stu-id="83392-185">You can use the same exception-handling techniques we discussed in the previous void-returning scenario:</span></span>

```csharp
Task<string> [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a><span data-ttu-id="83392-186">Task.WhenAny</span><span class="sxs-lookup"><span data-stu-id="83392-186">Task.WhenAny</span></span>
 <span data-ttu-id="83392-187">È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per attendere in modo asincrono più operazioni asincrone rappresentate come attività da completare.</span><span class="sxs-lookup"><span data-stu-id="83392-187">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to asynchronously wait for just one of multiple asynchronous operations represented as tasks to complete.</span></span>  <span data-ttu-id="83392-188">Questo metodo viene usato principalmente in quattro casi:</span><span class="sxs-lookup"><span data-stu-id="83392-188">This method serves four primary use cases:</span></span>

- <span data-ttu-id="83392-189">Ridondanza: esecuzione ripetuta di un'operazione e selezione di quella che viene terminata per prima (ad esempio contatto di più servizi Web di quotazioni di borsa tramite cui verrà generato un solo risultato e selezione di quello che viene completato più velocemente).</span><span class="sxs-lookup"><span data-stu-id="83392-189">Redundancy:  Performing an operation multiple times and selecting the one that completes first (for example, contacting multiple stock quote web services that will produce a single result and selecting the one that completes the fastest).</span></span>

- <span data-ttu-id="83392-190">Interfoliazione: avvio di più operazioni e attesa del completamento di tutte, ma elaborazione al termine delle operazioni in questione.</span><span class="sxs-lookup"><span data-stu-id="83392-190">Interleaving:  Launching multiple operations and waiting for all of them to complete, but processing them as they complete.</span></span>

- <span data-ttu-id="83392-191">Limitazione: consentire l'avvio di operazioni aggiuntive al completamento delle altre.</span><span class="sxs-lookup"><span data-stu-id="83392-191">Throttling:  Allowing additional operations to begin as others complete.</span></span>  <span data-ttu-id="83392-192">Questa è un'estensione dello scenario di interfoliazione.</span><span class="sxs-lookup"><span data-stu-id="83392-192">This is an extension of the interleaving scenario.</span></span>

- <span data-ttu-id="83392-193">Bailout iniziale: ad esempio, un'operazione rappresentata dall'attività t1 può essere raggruppata in un'attività <xref:System.Threading.Tasks.Task.WhenAny%2A> con un'altra attività t2 ed è possibile attendere l'attività <xref:System.Threading.Tasks.Task.WhenAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="83392-193">Early bailout:  For example, an operation represented by task t1 can be grouped in a <xref:System.Threading.Tasks.Task.WhenAny%2A> task with another task t2, and you can wait on the <xref:System.Threading.Tasks.Task.WhenAny%2A> task.</span></span> <span data-ttu-id="83392-194">L'attività t2 potrebbe rappresentare un timeout, un annullamento o un altro segnale che fa sì che l'attività <xref:System.Threading.Tasks.Task.WhenAny%2A> termini prima di t1.</span><span class="sxs-lookup"><span data-stu-id="83392-194">Task t2 could represent a time-out, or cancellation, or some other signal that causes the <xref:System.Threading.Tasks.Task.WhenAny%2A> task to complete before t1 completes.</span></span>

#### <a name="redundancy"></a><span data-ttu-id="83392-195">Ridondanza</span><span class="sxs-lookup"><span data-stu-id="83392-195">Redundancy</span></span>
 <span data-ttu-id="83392-196">Si consideri il caso in cui si desidera decidere se comprare o meno dei titoli.</span><span class="sxs-lookup"><span data-stu-id="83392-196">Consider a case where you want to make a decision about whether to buy a stock.</span></span>  <span data-ttu-id="83392-197">Esistono numerosi servizi Web attendibili che consigliano su azioni, ma a seconda del traffico giornaliero, ogni servizio può risultare lento in determinati momenti.</span><span class="sxs-lookup"><span data-stu-id="83392-197">There are several stock recommendation web services that you trust, but depending on daily load, each service can end up being slow at different times.</span></span>  <span data-ttu-id="83392-198">È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per ricevere una notifica quando un'operazione termina:</span><span class="sxs-lookup"><span data-stu-id="83392-198">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to receive a notification when any operation completes:</span></span>

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 <span data-ttu-id="83392-199">Diversamente da <xref:System.Threading.Tasks.Task.WhenAll%2A>, che restituisce i risultati da cui è stato rimosso il wrapping di tutte le attività completate correttamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> restituisce l'attività completata.</span><span class="sxs-lookup"><span data-stu-id="83392-199">Unlike <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns the unwrapped results of all tasks that completed successfully, <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task that completed.</span></span> <span data-ttu-id="83392-200">Se un'attività ha esito negativo, è importante sottolineare che ha avuto esito negativo e se l'attività ha esito positivo, è importante sapere a quale attività è associato il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="83392-200">If a task fails, it’s important to know that it failed, and if a task succeeds, it’s important to know which task the return value is associated with.</span></span>  <span data-ttu-id="83392-201">Pertanto, è necessario accedere al risultato dell'attività restituita o attenderlo ulteriormente, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="83392-201">Therefore, you need to access the result of the returned task, or further await it, as  this example shows.</span></span>

 <span data-ttu-id="83392-202">Come per <xref:System.Threading.Tasks.Task.WhenAll%2A>, è necessario poter adattare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="83392-202">As with <xref:System.Threading.Tasks.Task.WhenAll%2A>, you have to be able to accommodate exceptions.</span></span>  <span data-ttu-id="83392-203">Poiché l'attività terminata viene restituita, è possibile attendere l'attività restituita per propagare gli errori ed eseguire `try/catch` in modo appropriato, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-203">Because you receive the completed task back, you can await the returned task to have errors propagated, and `try/catch` them appropriately; for example:</span></span>

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 <span data-ttu-id="83392-204">Anche se il primo processo viene completato correttamente, le attività successive possono dare esito negativo.</span><span class="sxs-lookup"><span data-stu-id="83392-204">Additionally, even if a first task completes successfully, subsequent tasks may fail.</span></span>  <span data-ttu-id="83392-205">A questo punto, sono disponibili diverse opzioni per la gestione delle eccezioni: è possibile attendere il completamento di tutte le attività avviate e, in questo caso, è possibile utilizzare il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A> oppure è possibile decidere che tutte le eccezioni sono importanti e devono essere registrate.</span><span class="sxs-lookup"><span data-stu-id="83392-205">At this point, you have several options for dealing with exceptions:  You can wait until all the launched tasks have completed, in which case you can use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method, or you can decide that all exceptions are important and must be logged.</span></span>  <span data-ttu-id="83392-206">È possibile a tale scopo usare le continuazioni per ricevere una notifica quando le attività terminano in modo asincrono:</span><span class="sxs-lookup"><span data-stu-id="83392-206">For this, you can use continuations to receive a notification when tasks have completed asynchronously:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 <span data-ttu-id="83392-207">oppure:</span><span class="sxs-lookup"><span data-stu-id="83392-207">or:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 <span data-ttu-id="83392-208">o anche:</span><span class="sxs-lookup"><span data-stu-id="83392-208">or even:</span></span>

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 <span data-ttu-id="83392-209">È possibile, infine, annullare tutte le operazioni rimanenti:</span><span class="sxs-lookup"><span data-stu-id="83392-209">Finally, you may want to cancel all the remaining operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a><span data-ttu-id="83392-210">Interfoliazione</span><span class="sxs-lookup"><span data-stu-id="83392-210">Interleaving</span></span>
 <span data-ttu-id="83392-211">Si consideri il caso in cui si scarichino delle immagini dal Web e ogni immagine venga elaborata, ad esempio aggiungendo l'immagine a un controllo dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="83392-211">Consider a case where you're downloading images from the web and processing each image (for example, adding the image to a UI control).</span></span>  <span data-ttu-id="83392-212">È necessario eseguire l'elaborazione sequenzialmente nell'interfaccia utente del thread, ma si desidera scaricare quante più immagini possibili contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="83392-212">You have to do the processing sequentially on the UI thread, but you want to download the images as concurrently as possible.</span></span> <span data-ttu-id="83392-213">Non si desidera, tra l'altro, aspettare che le immagini siano tutte scaricate prima di aggiungerle all'interfaccia utente, ma si desidera aggiungerle man mano che vengono scaricate:</span><span class="sxs-lookup"><span data-stu-id="83392-213">Also, you don’t want to hold up adding the images to the UI until they’re all downloaded—you want to add them as they complete:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 <span data-ttu-id="83392-214">È anche possibile applicare l'interfoliazione a uno scenario che include un'elaborazione complessa a livello di calcolo nella classe <xref:System.Threading.ThreadPool> delle immagini scaricate, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-214">You can also apply interleaving to a scenario that involves computationally intensive processing on the <xref:System.Threading.ThreadPool> of the downloaded images; for example:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a><span data-ttu-id="83392-215">Limitazione</span><span class="sxs-lookup"><span data-stu-id="83392-215">Throttling</span></span>
 <span data-ttu-id="83392-216">Si consideri l'esempio dell'interfoliazione, con la differenza che l'utente sta scaricando un numero così elevato di immagini che i download devono essere limitati. Si desidera, ad esempio, che solo uno specifico numero di download sia realizzato contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="83392-216">Consider the interleaving example, except that the user is downloading so many images that the downloads have to be throttled; for example, you want only a specific number of downloads to happen concurrently.</span></span> <span data-ttu-id="83392-217">È possibile a tale scopo avviare un sottoinsieme di operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="83392-217">To achieve this, you can start a subset of the asynchronous operations.</span></span>  <span data-ttu-id="83392-218">Mentre le operazioni terminano, è possibile avviare operazioni aggiuntive che prendano il loro posto:</span><span class="sxs-lookup"><span data-stu-id="83392-218">As operations complete, you can start additional operations to take their place:</span></span>

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a><span data-ttu-id="83392-219">Bailout iniziale</span><span class="sxs-lookup"><span data-stu-id="83392-219">Early Bailout</span></span>
 <span data-ttu-id="83392-220">Si consideri di essere in attesa in modo asincrono che un'operazione termini e contemporaneamente di rispondere alla richiesta di interruzione da parte di un utente (ad esempio l'utente ha fatto clic su un pulsante di annullamento).</span><span class="sxs-lookup"><span data-stu-id="83392-220">Consider that you're waiting asynchronously for an operation to complete while simultaneously responding to a user’s cancellation request (for example, the user clicked a cancel button).</span></span> <span data-ttu-id="83392-221">Il codice seguente illustra questo scenario:</span><span class="sxs-lookup"><span data-stu-id="83392-221">The following code illustrates this scenario:</span></span>

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 <span data-ttu-id="83392-222">Questa implementazione abilita nuovamente l'interfaccia utente non appena si decide di annullare l'operazione, ma non annulla le operazioni asincrone sottostanti.</span><span class="sxs-lookup"><span data-stu-id="83392-222">This implementation re-enables the user interface as soon as you decide to bail out, but doesn't cancel the underlying asynchronous operations.</span></span>  <span data-ttu-id="83392-223">Un'alternativa consiste nell'annullare le operazioni in sospeso quando si decide di interrompere, ma di non ristabilire l'interfaccia utente finché le operazioni non siano terminate, probabilmente perché a causa della richiesta dell'interruzione, sono terminate prima:</span><span class="sxs-lookup"><span data-stu-id="83392-223">Another alternative would be to cancel the pending operations when you decide to bail out, but not reestablish the user interface until the operations actually complete, potentially due to ending early due to the cancellation request:</span></span>

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 <span data-ttu-id="83392-224">Un altro esempio di bailout iniziale prevede l'uso del <xref:System.Threading.Tasks.Task.WhenAny%2A> metodo insieme al metodo <xref:System.Threading.Tasks.Task.Delay%2A>, come illustrato nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="83392-224">Another example of early bailout involves using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method in conjunction with the <xref:System.Threading.Tasks.Task.Delay%2A> method, as discussed in the next section.</span></span>

### <a name="taskdelay"></a><span data-ttu-id="83392-225">Task.Delay</span><span class="sxs-lookup"><span data-stu-id="83392-225">Task.Delay</span></span>
 <span data-ttu-id="83392-226">È possibile usare il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> per introdurre pause nell'esecuzione di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="83392-226">You can use the <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method to introduce pauses into an asynchronous method’s execution.</span></span>  <span data-ttu-id="83392-227">Ciò è utile per molti tipi di funzionalità, incluse la compilazione dei cicli di polling e il posticipo della gestione di input utente per un periodo di tempo predeterminato.</span><span class="sxs-lookup"><span data-stu-id="83392-227">This is useful for many kinds of functionality, including building polling loops and delaying the handling of user input for a predetermined period of time.</span></span>  <span data-ttu-id="83392-228">Il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> può anche essere utile in combinazione con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> per implementare i timeout sulle attese.</span><span class="sxs-lookup"><span data-stu-id="83392-228">The <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method can also be useful in combination with <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> for implementing time-outs on awaits.</span></span>

 <span data-ttu-id="83392-229">Se un'attività che fa parte di una operazione asincrona più ampia, ad esempio un servizio web ASP.NET, impiega troppo tempo per terminare, potrebbe soffrirne l'operazione globale, specialmente se non termina mai.</span><span class="sxs-lookup"><span data-stu-id="83392-229">If a task that’s part of a larger asynchronous operation (for example, an ASP.NET web service) takes too long to complete, the overall operation could suffer, especially if it fails to ever complete.</span></span>  <span data-ttu-id="83392-230">Per questo motivo, è importante poter introdurre un timeout quando si è in attesa di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="83392-230">For this reason, it’s important to be able to time out when waiting on an asynchronous operation.</span></span>  <span data-ttu-id="83392-231">I metodi sincroni <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> accettano i valori di timeout, ma i corrispondenti metodi <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> citati in precedenza non li accettano.</span><span class="sxs-lookup"><span data-stu-id="83392-231">The synchronous <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> methods accept time-out values, but the corresponding <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> and the previously mentioned <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> methods do not.</span></span>  <span data-ttu-id="83392-232">È invece possibile usare <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combinazione per implementare un timeout.</span><span class="sxs-lookup"><span data-stu-id="83392-232">Instead, you can use <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combination to implement a time-out.</span></span>

 <span data-ttu-id="83392-233">In un'applicazione con interfaccia utente si desidera, ad esempio, scaricare un'immagine e disabilitare l'interfaccia utente durante il download dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="83392-233">For example, in your UI application, let's say that you want to download an image and disable the UI while the image is downloading.</span></span> <span data-ttu-id="83392-234">Se però il download è troppo lungo, si desidera abilitare nuovamente l'interfaccia utente e rimuovere il download:</span><span class="sxs-lookup"><span data-stu-id="83392-234">However, if the download takes too long, you want to re-enable the UI and discard the download:</span></span>

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 <span data-ttu-id="83392-235">Lo stesso accade con più download, perché <xref:System.Threading.Tasks.Task.WhenAll%2A> restituisce un'attività:</span><span class="sxs-lookup"><span data-stu-id="83392-235">The same applies to multiple downloads, because <xref:System.Threading.Tasks.Task.WhenAll%2A> returns a task:</span></span>

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a><span data-ttu-id="83392-236">Sviluppo di combinatori basati su attività</span><span class="sxs-lookup"><span data-stu-id="83392-236">Building Task-based Combinators</span></span>
 <span data-ttu-id="83392-237">Poiché un'attività può rappresentare completamente un'operazione asincrona e fornire funzionalità sincrone e asincrone per effettuare join con l'operazione, recuperare i risultati e così via, è possibile compilare utili librerie dei combinatori che costituiscono le attività per costruire modelli più grandi.</span><span class="sxs-lookup"><span data-stu-id="83392-237">Because a task is able to completely represent an asynchronous operation and provide synchronous and asynchronous capabilities for joining with the operation, retrieving its results, and so on, you can build useful libraries of combinators that compose tasks to build larger patterns.</span></span>  <span data-ttu-id="83392-238">Come illustrato nella sezione precedente, .NET Framework include diversi combinatori incorporati, ma è possibile costruirne di personalizzati.</span><span class="sxs-lookup"><span data-stu-id="83392-238">As discussed in the previous section, the .NET Framework includes several built-in combinators, but you can also build your own.</span></span> <span data-ttu-id="83392-239">Le sezioni seguenti forniscono alcuni esempi di potenziali metodi e tipi di combinatori.</span><span class="sxs-lookup"><span data-stu-id="83392-239">The following sections provide several examples of potential combinator methods and types.</span></span>

### <a name="retryonfault"></a><span data-ttu-id="83392-240">RetryOnFault</span><span class="sxs-lookup"><span data-stu-id="83392-240">RetryOnFault</span></span>
 <span data-ttu-id="83392-241">In molte situazioni è possibile ritentare un'operazione se un tentativo precedente ha dato esito negativo.</span><span class="sxs-lookup"><span data-stu-id="83392-241">In many situations, you may want to retry an operation if a previous attempt fails.</span></span>  <span data-ttu-id="83392-242">Per il codice sincrono, è possibile creare un metodo helper, ad esempio `RetryOnFault` come mostrato nell'esempio seguente, per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="83392-242">For synchronous code, you might build a helper method such as `RetryOnFault` in the following example to accomplish this:</span></span>

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="83392-243">È possibile compilare un metodo helper quasi identico per le operazioni asincrone implementate con TAP e restituire in questo modo delle attività:</span><span class="sxs-lookup"><span data-stu-id="83392-243">You can build an almost identical helper method for asynchronous operations that are implemented with TAP and thus return tasks:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="83392-244">È successivamente possibile usare questo combinatore per codificare i tentativi nella logica dell'applicazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-244">You can then use this combinator to encode retries into the application’s logic; for example:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 <span data-ttu-id="83392-245">È possibile estendere ulteriormente la funzione `RetryOnFault`.</span><span class="sxs-lookup"><span data-stu-id="83392-245">You could extend the `RetryOnFault` function further.</span></span> <span data-ttu-id="83392-246">La funzione potrebbe, ad esempio, accettare un'altra `Func<Task>` che verrà richiamata tra i nuovi tentativi per determinare quando eseguire nuovamente l'operazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-246">For example, the function could accept another `Func<Task>` that will be invoked between retries to determine when to try the operation again; for example:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 <span data-ttu-id="83392-247">È quindi possibile usare la funzione come descritto di seguito per attendere un secondo prima di ritentare l'operazione:</span><span class="sxs-lookup"><span data-stu-id="83392-247">You could then use the function as follows to wait for a second before retrying the operation:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a><span data-ttu-id="83392-248">NeedOnlyOne</span><span class="sxs-lookup"><span data-stu-id="83392-248">NeedOnlyOne</span></span>
 <span data-ttu-id="83392-249">È talvolta possibile usare la ridondanza per migliorare la latenza e le probabilità di successo di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="83392-249">Sometimes, you can take advantage of redundancy to improve an operation’s latency and chances for success.</span></span>  <span data-ttu-id="83392-250">Si considerino vari servizi Web che forniscono quotazioni azionarie. In diversi momenti del giorno ogni servizio può fornire diversi livelli di qualità e tempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="83392-250">Consider multiple web services that provide stock quotes, but at various times of the day, each service may provide different levels of quality and response times.</span></span>  <span data-ttu-id="83392-251">Per la gestione di tali fluttuazioni, è possibile inviare richieste a tutti i servizi Web e non appena si riceve una risposta da una, annullare le richieste rimanenti.</span><span class="sxs-lookup"><span data-stu-id="83392-251">To deal with these fluctuations, you may issue requests to all the web services, and as soon as you get a response from one, cancel the remaining requests.</span></span>  <span data-ttu-id="83392-252">È possibile implementare una funzione helper per semplificare l'implementazione di questo modello comune basato sull'avvio di più operazioni, l'attesa della prima risposta e l'annullamento delle operazioni che non hanno fornito la risposta per prime.</span><span class="sxs-lookup"><span data-stu-id="83392-252">You can implement a helper function to make it easier to implement this common pattern of launching multiple operations, waiting for any, and then canceling the rest.</span></span> <span data-ttu-id="83392-253">La funzione `NeedOnlyOne` dell'esempio seguente illustra questo scenario:</span><span class="sxs-lookup"><span data-stu-id="83392-253">The `NeedOnlyOne` function in the following example illustrates this scenario:</span></span>

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 <span data-ttu-id="83392-254">È possibile quindi usare questa funzione come segue:</span><span class="sxs-lookup"><span data-stu-id="83392-254">You can then use this function as follows:</span></span>

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a><span data-ttu-id="83392-255">Operazioni con interfoliazione</span><span class="sxs-lookup"><span data-stu-id="83392-255">Interleaved Operations</span></span>
 <span data-ttu-id="83392-256">Esiste un potenziale problema di prestazioni quando si usa il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per supportare uno scenario di interfoliazione nel caso in cui si usino set di attività molto grandi.</span><span class="sxs-lookup"><span data-stu-id="83392-256">There is a potential performance problem with using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to support an interleaving scenario when you're working with very large sets of tasks.</span></span> <span data-ttu-id="83392-257">Ogni chiamata a <xref:System.Threading.Tasks.Task.WhenAny%2A> comporta la registrazione di una continuazione con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="83392-257">Every call to <xref:System.Threading.Tasks.Task.WhenAny%2A> results in a continuation being registered with each task.</span></span> <span data-ttu-id="83392-258">Per il numero N di attività, il risultato è una continuazione di O (N<sup>2</sup>) creata per la durata dell'operazione di interfoliazione.</span><span class="sxs-lookup"><span data-stu-id="83392-258">For N number of tasks, this results in O(N<sup>2</sup>) continuations created over the lifetime of the interleaving operation.</span></span> <span data-ttu-id="83392-259">Se si lavora con un ampio set di attività, è possibile usare un combinatore ( `Interleaved` nell'esempio seguente) per risolvere il problema di prestazioni:</span><span class="sxs-lookup"><span data-stu-id="83392-259">If you're working with a large set of tasks, you can use a combinator (`Interleaved` in the following example) to address the performance issue:</span></span>

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 <span data-ttu-id="83392-260">È quindi possibile usare il combinatore per elaborare i risultati delle attività man mano che vengono completate. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="83392-260">You can then use the combinator to process the results of tasks as they complete; for example:</span></span>

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a><span data-ttu-id="83392-261">WhenAllOrFirstException</span><span class="sxs-lookup"><span data-stu-id="83392-261">WhenAllOrFirstException</span></span>
 <span data-ttu-id="83392-262">In alcuni scenari di dispersione/raccolta di dati, potrebbe essere necessario attendere il completamento di tutti i processi di un set, a meno che uno di questi non fallisca, nel qual caso si può arrestare l'attesa non appena si verifica l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="83392-262">In certain scatter/gather scenarios, you might want to wait for all tasks in a set, unless one of them faults, in which case you want to stop waiting as soon as the exception occurs.</span></span>  <span data-ttu-id="83392-263">È possibile eseguire questa operazione con un metodo combinatore, ad esempio `WhenAllOrFirstException`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="83392-263">You can accomplish that with a combinator method such as `WhenAllOrFirstException` in the following example:</span></span>

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a><span data-ttu-id="83392-264">Creazione di strutture dei dati basate su attività</span><span class="sxs-lookup"><span data-stu-id="83392-264">Building Task-based Data Structures</span></span>
 <span data-ttu-id="83392-265">Oltre alla possibilità di costruire combinatori personalizzati basati su attività, avere una struttura dei dati in <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> che rappresenta sia i risultati di un'operazione asincrona che la sincronizzazione necessaria con cui creare un join è una soluzione molto potente su cui basare la creazione di strutture dei dati personalizzate da usare in scenari asincroni.</span><span class="sxs-lookup"><span data-stu-id="83392-265">In addition to the ability to build custom task-based combinators, having a data structure in <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> that represents both the results of an asynchronous operation and the necessary synchronization to join with it makes it a very powerful type on which to build custom data structures to be used in asynchronous scenarios.</span></span>

### <a name="asynccache"></a><span data-ttu-id="83392-266">AsyncCache</span><span class="sxs-lookup"><span data-stu-id="83392-266">AsyncCache</span></span>
 <span data-ttu-id="83392-267">Un aspetto importante di un'attività è che può essere distribuita a diversi clienti, tutti la possono attendere, registrarvi continuazioni, ottenerne il risultato o le eccezioni (nel caso di <xref:System.Threading.Tasks.Task%601>) e così via.</span><span class="sxs-lookup"><span data-stu-id="83392-267">One important aspect of a task is that it may be handed out to multiple consumers, all of whom may await it, register continuations with it, get its result or exceptions (in the case of <xref:System.Threading.Tasks.Task%601>), and so on.</span></span>  <span data-ttu-id="83392-268">Ciò rende <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> ideali per essere usati in un'infrastruttura asincrona di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="83392-268">This makes <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> perfectly suited to be used in an asynchronous caching infrastructure.</span></span>  <span data-ttu-id="83392-269">Di seguito è riportato un esempio di una piccola ma potente cache asincrona costruita basandosi su <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="83392-269">Here’s an example of a small but powerful asynchronous cache built on top of <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 <span data-ttu-id="83392-270">La [classe \<TKey,TValue> AsyncCache](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) accetta come delegato al relativo costruttore una funzione che accetta un oggetto `TKey` e restituisce un oggetto <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="83392-270">The [AsyncCache\<TKey,TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) class accepts as a delegate to its constructor a function that takes a `TKey` and returns a <xref:System.Threading.Tasks.Task%601>.</span></span>  <span data-ttu-id="83392-271">Tutti i valori della cache a cui si è acceduto precedentemente vengono archiviati nel dizionario interno e `AsyncCache` fa in modo che venga generata solo un'attività per chiave, anche si accede alla cache contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="83392-271">Any previously accessed values from the cache are stored in the internal dictionary, and the `AsyncCache` ensures that only one task is generated per key, even if the cache is accessed concurrently.</span></span>

 <span data-ttu-id="83392-272">È possibile, ad esempio, creare una cache per le pagine Web scaricate:</span><span class="sxs-lookup"><span data-stu-id="83392-272">For example, you can build a cache for downloaded web pages:</span></span>

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 <span data-ttu-id="83392-273">È quindi possibile usare tale cache nei metodi asincroni ogni volta che è necessario accedere al contenuto di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="83392-273">You can then use this cache in asynchronous methods whenever you need the contents of a web page.</span></span> <span data-ttu-id="83392-274">La classe `AsyncCache` assicura che si scarichi il minor numero di pagine possibile e memorizza i risultati nella cache.</span><span class="sxs-lookup"><span data-stu-id="83392-274">The `AsyncCache` class ensures that you’re downloading as few pages as possible, and caches the results.</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a><span data-ttu-id="83392-275">AsyncProducerConsumerCollection</span><span class="sxs-lookup"><span data-stu-id="83392-275">AsyncProducerConsumerCollection</span></span>
 <span data-ttu-id="83392-276">È inoltre possibile usare attività per creare strutture dei dati per coordinare le attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="83392-276">You can also use tasks to build data structures for coordinating asynchronous activities.</span></span>  <span data-ttu-id="83392-277">Si consideri uno dei classici modelli di progettazione paralleli: produttore/consumatore.</span><span class="sxs-lookup"><span data-stu-id="83392-277">Consider one of the classic parallel design patterns: producer/consumer.</span></span>  <span data-ttu-id="83392-278">In questo modello, i produttori generano dati che sono consumati dai consumatori e i produttori e i consumatori possono operare in parallelo.</span><span class="sxs-lookup"><span data-stu-id="83392-278">In this pattern, producers generate data that is consumed by consumers, and the producers and consumers may run in parallel.</span></span> <span data-ttu-id="83392-279">Il consumatore elabora, ad esempio, l'elemento 1, che è stato precedentemente generato da un produttore che sta scrivendo l'elemento 2.</span><span class="sxs-lookup"><span data-stu-id="83392-279">For example, the consumer processes item 1, which was previously generated by a producer who is now producing item 2.</span></span>  <span data-ttu-id="83392-280">Il modello produttore/consumatore prevede invariabilmente la presenza di una struttura dei dati in cui memorizzare il lavoro creato dai produttori in modo che i consumatori possano essere informati di nuovi dati e possano gestirli una volta disponibili.</span><span class="sxs-lookup"><span data-stu-id="83392-280">For the producer/consumer pattern, you invariably need some data structure to store the work created by producers so that the consumers may be notified of new data and find it when available.</span></span>

 <span data-ttu-id="83392-281">Questa è una semplice struttura dei dati costruita basandosi su attività che consente di usare i metodi asincroni come produttori e consumatori:</span><span class="sxs-lookup"><span data-stu-id="83392-281">Here’s a simple data structure built on top of tasks that enables asynchronous methods to be used as producers and consumers:</span></span>

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 <span data-ttu-id="83392-282">Con tale struttura dei dati è possibile scrivere codice come il seguente:</span><span class="sxs-lookup"><span data-stu-id="83392-282">With that data structure in place, you can write code such as the following:</span></span>

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

<span data-ttu-id="83392-283">Lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow> include il tipo <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, che è possibile usare in modo simile, ma senza dover compilare un tipo di raccolta personalizzato:</span><span class="sxs-lookup"><span data-stu-id="83392-283">The <xref:System.Threading.Tasks.Dataflow> namespace includes the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> type, which you can use in a similar manner, but without having to build a custom collection type:</span></span>

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> <span data-ttu-id="83392-284">Lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow> è disponibile in .NET Framework 4.5 tramite **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="83392-284">The <xref:System.Threading.Tasks.Dataflow> namespace is available in the .NET Framework 4.5 through **NuGet**.</span></span> <span data-ttu-id="83392-285">Per installare l'assembly contenente lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow>, aprire il progetto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu Progetto e cercare online il pacchetto Microsoft.Tpl.Dataflow.</span><span class="sxs-lookup"><span data-stu-id="83392-285">To install the assembly that contains the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in Visual Studio, choose **Manage NuGet Packages** from the Project menu, and search online for the Microsoft.Tpl.Dataflow package.</span></span>

## <a name="see-also"></a><span data-ttu-id="83392-286">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83392-286">See also</span></span>

- [<span data-ttu-id="83392-287">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="83392-287">Task-based Asynchronous Pattern (TAP)</span></span>](task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="83392-288">Implementazione del modello asincrono basato su attività</span><span class="sxs-lookup"><span data-stu-id="83392-288">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="83392-289">Interoperabilità con altri tipi e modelli asincroni</span><span class="sxs-lookup"><span data-stu-id="83392-289">Interop with Other Asynchronous Patterns and Types</span></span>](interop-with-other-asynchronous-patterns-and-types.md)
