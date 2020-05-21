---
title: Programmazione asincrona - C#
description: Informazioni sul modello di programmazione asincrona a livello del linguaggio C# fornito da .NET Core.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: ee5edc80d9c020dbbeced3fc36d3ff273036d7b1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761889"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="16bd1-103">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="16bd1-103">Asynchronous programming</span></span>

<span data-ttu-id="16bd1-104">Se si dispone di esigenze di I/O (ad esempio la richiesta di dati da una rete, l'accesso a un database o la lettura e la scrittura in un file system), è consigliabile utilizzare la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="16bd1-104">If you have any I/O-bound needs (such as requesting data from a network, accessing a database, or reading and writing to a file system), you'll want to utilize asynchronous programming.</span></span> <span data-ttu-id="16bd1-105">Si potrebbe anche usare codice associato alla CPU, ad esempio per eseguire un calcolo di spese, che rappresenta uno scenario importante per scrivere codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="16bd1-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="16bd1-106">In C# è disponibile un modello di programmazione asincrona a livello di linguaggio che consente di scrivere facilmente codice asincrono, senza dover manipolare i callback o conformarsi a una libreria che supporta modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="16bd1-106">C# has a language-level asynchronous programming model, which allows for easily writing asynchronous code, without having to juggle callbacks or conform to a library that supports asynchrony.</span></span> <span data-ttu-id="16bd1-107">Questo modalità segue ciò che è noto come [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato sull'attività).</span><span class="sxs-lookup"><span data-stu-id="16bd1-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="overview-of-the-asynchronous-model"></a><span data-ttu-id="16bd1-108">Cenni preliminari sul modello asincrono</span><span class="sxs-lookup"><span data-stu-id="16bd1-108">Overview of the asynchronous model</span></span>

<span data-ttu-id="16bd1-109">Il nucleo della programmazione asincrona è costituito da oggetti `Task` e `Task<T>` che modellano le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="16bd1-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span> <span data-ttu-id="16bd1-110">Sono supportati dalle parole chiavi `async` e `await`.</span><span class="sxs-lookup"><span data-stu-id="16bd1-110">They are supported by the `async` and `await` keywords.</span></span> <span data-ttu-id="16bd1-111">Il modello è piuttosto semplice nella maggior parte dei casi:</span><span class="sxs-lookup"><span data-stu-id="16bd1-111">The model is fairly simple in most cases:</span></span>

- <span data-ttu-id="16bd1-112">Per il codice associato a I/O, si attende un'operazione che restituisce un oggetto `Task` o `Task<T>` all'interno di un `async` metodo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-112">For I/O-bound code, you await an operation that returns a `Task` or `Task<T>` inside of an `async` method.</span></span>
- <span data-ttu-id="16bd1-113">Per il codice associato alla CPU, si attende un'operazione avviata in un thread in background con il <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-113">For CPU-bound code, you await an operation that is started on a background thread with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="16bd1-114">La parola chiave `await` è l'elemento cruciale.</span><span class="sxs-lookup"><span data-stu-id="16bd1-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="16bd1-115">Restituisce il controllo al chiamante del metodo che esegue `await` ed è questo che in ultima analisi consente a un'interfaccia utente di essere reattiva o a un servizio di essere flessibile.</span><span class="sxs-lookup"><span data-stu-id="16bd1-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span> <span data-ttu-id="16bd1-116">Sebbene [esistano modi](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) per approcciare codice asincrono diverso da `async` e `await` , questo articolo è incentrato sui costrutti a livello di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="16bd1-116">While [there are ways](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) to approach async code other than `async` and `await`, this article focuses on the language-level constructs.</span></span>

### <a name="io-bound-example-download-data-from-a-web-service"></a><span data-ttu-id="16bd1-117">Esempio di i/O associato: scaricare dati da un servizio Web</span><span class="sxs-lookup"><span data-stu-id="16bd1-117">I/O-bound example: Download data from a web service</span></span>

<span data-ttu-id="16bd1-118">Potrebbe essere necessario scaricare alcuni dati da un servizio Web quando viene premuto un pulsante, ma non si vuole bloccare il thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="16bd1-118">You may need to download some data from a web service when a button is pressed, but don't want to block the UI thread.</span></span> <span data-ttu-id="16bd1-119">Questa operazione può essere eseguita in questo modo:</span><span class="sxs-lookup"><span data-stu-id="16bd1-119">It can be accomplished like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="16bd1-120">Il codice esprime l'intento (scaricando i dati in modo asincrono) senza rimanere impantanati nell'interazione con `Task` gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="16bd1-120">The code expresses the intent (downloading data asynchronously) without getting bogged down in interacting with `Task` objects.</span></span>

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a><span data-ttu-id="16bd1-121">Esempio associato alla CPU: eseguire un calcolo per un gioco</span><span class="sxs-lookup"><span data-stu-id="16bd1-121">CPU-bound example: Perform a calculation for a game</span></span>

<span data-ttu-id="16bd1-122">Si supponga di scrivere un gioco per dispositivi mobili in cui l'uso di un pulsante può causare danni a molti nemici visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-122">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span> <span data-ttu-id="16bd1-123">L'esecuzione del calcolo del danno può essere molto onerosa e in questo modo il thread dell'interfaccia utente dà l'impressione che il gioco si arresti durante l'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-123">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="16bd1-124">Il modo migliore per gestire questa situazione è avviare un thread in background, che esegue il lavoro utilizzando `Task.Run` , e attenda il risultato utilizzando `await` .</span><span class="sxs-lookup"><span data-stu-id="16bd1-124">The best way to handle this is to start a background thread, which does the work using `Task.Run`, and await its result using `await`.</span></span> <span data-ttu-id="16bd1-125">In questo modo l'interfaccia utente può risultare uniforme quando il lavoro viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="16bd1-125">This allows the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="16bd1-126">Questo codice esprime con precisione lo scopo dell'evento clic del pulsante, non è necessario gestire manualmente un thread in background e non blocca le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="16bd1-126">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="16bd1-127">Operazioni eseguite in background</span><span class="sxs-lookup"><span data-stu-id="16bd1-127">What happens under the covers</span></span>

<span data-ttu-id="16bd1-128">Sono molti gli elementi in cui sono coinvolte le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="16bd1-128">There are many moving pieces where asynchronous operations are concerned.</span></span> <span data-ttu-id="16bd1-129">Per informazioni sulle operazioni eseguite sotto le quinte di `Task` e `Task<T>` , vedere l'articolo di [approfondimento asincrono](../standard/async-in-depth.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="16bd1-129">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, see the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="16bd1-130">Sul lato C#, il compilatore trasforma il codice in una macchina a Stati che tiene traccia di elementi come la produzione di un'esecuzione quando `await` viene raggiunto un oggetto e la ripresa dell'esecuzione al termine di un processo in background.</span><span class="sxs-lookup"><span data-stu-id="16bd1-130">On the C# side of things, the compiler transforms your code into a state machine that keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="16bd1-131">Per gli utenti che amano la teoria, questa è un'implementazione del [Modello futuro di asincronia](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="16bd1-131">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="16bd1-132">Elementi chiave da comprendere</span><span class="sxs-lookup"><span data-stu-id="16bd1-132">Key pieces to understand</span></span>

* <span data-ttu-id="16bd1-133">Il codice asincrono può essere usato per il codice associato a I/O e alla CPU, ma in modo diverso per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="16bd1-133">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="16bd1-134">Il codice asincrono usa `Task<T>` e `Task`, che sono costrutti usati per modellare le operazioni eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="16bd1-134">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="16bd1-135">La parola chiave `async` trasforma un metodo in un metodo asincrono, che consente di usare la parola chiave `await` nel relativo corpo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-135">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="16bd1-136">Quando la parola chiave `await` viene applicata, interrompe il metodo di chiamata e restituisce il controllo al chiamante fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="16bd1-136">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="16bd1-137">`await` può essere usato solo all'interno di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="16bd1-137">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="16bd1-138">Riconoscere il lavoro associato alla CPU e I/O</span><span class="sxs-lookup"><span data-stu-id="16bd1-138">Recognize CPU-bound and I/O-bound work</span></span>

<span data-ttu-id="16bd1-139">I primi due esempi di questa guida hanno illustrato come usare `async` e `await` per operazioni associate ai I/O e alla CPU.</span><span class="sxs-lookup"><span data-stu-id="16bd1-139">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span> <span data-ttu-id="16bd1-140">È molto importante identificare se un processo da eseguire è associato a I/O o alla CPU perché ciò può influire notevolmente sulle prestazioni del codice e potrebbe causare un uso improprio di determinati costrutti.</span><span class="sxs-lookup"><span data-stu-id="16bd1-140">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="16bd1-141">Rispondere a queste due domande prima di scrivere il codice:</span><span class="sxs-lookup"><span data-stu-id="16bd1-141">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="16bd1-142">Il codice deve "attendere" l'esecuzione di operazioni, ad esempio la ricezione di dati da un database?</span><span class="sxs-lookup"><span data-stu-id="16bd1-142">Will your code be "waiting" for something, such as data from a database?</span></span>

   <span data-ttu-id="16bd1-143">Se la risposta è "Sì", l'operazione è **associata a I/O**.</span><span class="sxs-lookup"><span data-stu-id="16bd1-143">If your answer is "yes", then your work is **I/O-bound**.</span></span>

1. <span data-ttu-id="16bd1-144">Il codice eseguirà un calcolo costoso?</span><span class="sxs-lookup"><span data-stu-id="16bd1-144">Will your code be performing an expensive computation?</span></span>

   <span data-ttu-id="16bd1-145">Se la risposta è "Sì", l'operazione è **associata alla CPU**.</span><span class="sxs-lookup"><span data-stu-id="16bd1-145">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="16bd1-146">Se l'operazione è **associata a I/O**, usare `async` e `await` *senza* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="16bd1-146">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span> <span data-ttu-id="16bd1-147">*Non si deve* usare la libreria Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="16bd1-147">You *should not* use the Task Parallel Library.</span></span> <span data-ttu-id="16bd1-148">Il motivo è illustrato in modo asincrono in modo [approfondito](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="16bd1-148">The reason for this is outlined in [Async in Depth](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="16bd1-149">Se il lavoro di cui si dispone è **associato alla CPU** e si è interessati alla velocità di risposta, utilizzare `async` e `await` , ma generare il lavoro in un altro thread *con* `Task.Run` .</span><span class="sxs-lookup"><span data-stu-id="16bd1-149">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await`, but spawn off the work on another thread *with* `Task.Run`.</span></span> <span data-ttu-id="16bd1-150">Se il lavoro è appropriato per la concorrenza e il parallelismo, considerare anche l'uso del [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="16bd1-150">If the work is appropriate for concurrency and parallelism, also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="16bd1-151">È anche necessario valutare sempre l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-151">Additionally, you should always measure the execution of your code.</span></span> <span data-ttu-id="16bd1-152">Ad esempio, ci si potrebbe trovare in una situazione in cui l'operazione associata alla CPU non è abbastanza onerosa confrontata al sovraccarico di commutazioni di contesto durante il multithreading.</span><span class="sxs-lookup"><span data-stu-id="16bd1-152">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span> <span data-ttu-id="16bd1-153">Ogni scelta presenta un compromesso ed è necessario selezionare il compromesso più adatto alla situazione.</span><span class="sxs-lookup"><span data-stu-id="16bd1-153">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="16bd1-154">Altri esempi</span><span class="sxs-lookup"><span data-stu-id="16bd1-154">More examples</span></span>

<span data-ttu-id="16bd1-155">Gli esempi seguenti illustrano i diversi modi in cui è possibile scrivere codice asincrono in C#.</span><span class="sxs-lookup"><span data-stu-id="16bd1-155">The following examples demonstrate various ways you can write async code in C#.</span></span> <span data-ttu-id="16bd1-156">Trattano scenari diversi molto comuni.</span><span class="sxs-lookup"><span data-stu-id="16bd1-156">They cover a few different scenarios you may come across.</span></span>

### <a name="extract-data-from-a-network"></a><span data-ttu-id="16bd1-157">Estrarre dati da una rete</span><span class="sxs-lookup"><span data-stu-id="16bd1-157">Extract data from a network</span></span>

<span data-ttu-id="16bd1-158">Questo frammento Scarica il codice HTML dalla Home Page <https://dotnetfoundation.org> e conta il numero di volte in cui la stringa ".NET" viene eseguita nel codice HTML.</span><span class="sxs-lookup"><span data-stu-id="16bd1-158">This snippet downloads the HTML from the homepage at <https://dotnetfoundation.org> and counts the number of times the string ".NET" occurs in the HTML.</span></span> <span data-ttu-id="16bd1-159">USA ASP.NET per definire un metodo del controller API Web, che esegue questa attività e restituisce il numero.</span><span class="sxs-lookup"><span data-stu-id="16bd1-159">It uses ASP.NET to define a Web API controller method, which performs this task and returns the number.</span></span>

> [!NOTE]
> <span data-ttu-id="16bd1-160">Se si prevede di eseguire l'analisi del codice HTML nel codice di produzione, non usare le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="16bd1-160">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="16bd1-161">Usare invece una libreria di analisi.</span><span class="sxs-lookup"><span data-stu-id="16bd1-161">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="16bd1-162">Di seguito viene illustrato lo stesso scenario scritto per un'app di Windows universale, che esegue la stessa attività quando viene premuto un pulsante:</span><span class="sxs-lookup"><span data-stu-id="16bd1-162">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a><span data-ttu-id="16bd1-163">Attendi il completamento di più attività</span><span class="sxs-lookup"><span data-stu-id="16bd1-163">Wait for multiple tasks to complete</span></span>

<span data-ttu-id="16bd1-164">Ci si potrebbe trovare in una situazione in cui è necessario recuperare più elementi di dati allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-164">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span> <span data-ttu-id="16bd1-165">L' `Task` API contiene due metodi, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> , che consentono di scrivere codice asincrono che esegue un'attesa non di blocco su più processi in background.</span><span class="sxs-lookup"><span data-stu-id="16bd1-165">The `Task` API contains two methods, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, that allow you to write asynchronous code that performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="16bd1-166">Questo esempio illustra come è possibile acquisire dati `User` per un set di `userId`.</span><span class="sxs-lookup"><span data-stu-id="16bd1-166">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="16bd1-167">Ecco un altro modo per scrivere questa operazione in modo più conciso, usando LINQ:</span><span class="sxs-lookup"><span data-stu-id="16bd1-167">Here's another way to write this more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="16bd1-168">Sebbene produca una quantità minore di codice, è necessario prestare molta attenzione quando si combina LINQ con codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="16bd1-168">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span> <span data-ttu-id="16bd1-169">Poiché LINQ usa un'esecuzione posticipata (lazy), le chiamate asincrone non verranno eseguite immediatamente come avviene in un ciclo `foreach` a meno che non si forzi la sequenza generata per l'iterazione con una chiamata a `.ToList()` o `.ToArray()`.</span><span class="sxs-lookup"><span data-stu-id="16bd1-169">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="16bd1-170">Informazioni importanti e consigli</span><span class="sxs-lookup"><span data-stu-id="16bd1-170">Important info and advice</span></span>

<span data-ttu-id="16bd1-171">Con la programmazione asincrona è necessario tenere presenti alcuni dettagli che possono impedire un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="16bd1-171">With async programming there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="16bd1-172">I metodi `async` \*\* devono avere una parola chiave \*\* `await` \*\* nel corpo, altrimenti non verranno eseguiti.\*\*</span><span class="sxs-lookup"><span data-stu-id="16bd1-172">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

  <span data-ttu-id="16bd1-173">Questo è importante da tenere presente.</span><span class="sxs-lookup"><span data-stu-id="16bd1-173">This is important to keep in mind.</span></span> <span data-ttu-id="16bd1-174">Se `await` non viene usato nel corpo di un `async` metodo, il compilatore C# genera un avviso, ma il codice viene compilato ed eseguito come se fosse un metodo normale.</span><span class="sxs-lookup"><span data-stu-id="16bd1-174">If `await` is not used in the body of an `async` method, the C# compiler generates a warning, but the code compiles and runs as if it were a normal method.</span></span> <span data-ttu-id="16bd1-175">Si tratta di un'operazione estremamente inefficiente, perché la macchina a stati generata dal compilatore C# per il metodo asincrono non esegue alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="16bd1-175">This is incredibly inefficient, as the state machine generated by the C# compiler for the async method is not accomplishing anything.</span></span>

* <span data-ttu-id="16bd1-176">**È consigliabile aggiungere "Async" come suffisso di ogni nome di metodo asincrono da scrivere.**</span><span class="sxs-lookup"><span data-stu-id="16bd1-176">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="16bd1-177">Si tratta della convenzione utilizzata in .NET per distinguere più facilmente i metodi sincroni e asincroni.</span><span class="sxs-lookup"><span data-stu-id="16bd1-177">This is the convention used in .NET to more easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="16bd1-178">Alcuni metodi che non vengono chiamati in modo esplicito dal codice, ad esempio i gestori eventi o i metodi del controller web, non sono necessariamente applicabili.</span><span class="sxs-lookup"><span data-stu-id="16bd1-178">Certain methods that aren't explicitly called by your code (such as event handlers or web controller methods) don't necessarily apply.</span></span> <span data-ttu-id="16bd1-179">Poiché non vengono chiamati in modo esplicito dal codice, il fatto di essere espliciti sulla denominazione non è altrettanto importante.</span><span class="sxs-lookup"><span data-stu-id="16bd1-179">Because they are not explicitly called by your code, being explicit about their naming isn't as important.</span></span>

* <span data-ttu-id="16bd1-180">`async void`**deve essere usato solo per i gestori eventi.**</span><span class="sxs-lookup"><span data-stu-id="16bd1-180">`async void` **should only to be used for event handlers.**</span></span>

<span data-ttu-id="16bd1-181">`async void` è l'unico modo per consentire ai gestori eventi asincroni di funzionare correttamente, poiché gli eventi non hanno tipi restituiti (quindi non possono usare `Task` e `Task<T>`).</span><span class="sxs-lookup"><span data-stu-id="16bd1-181">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="16bd1-182">Qualsiasi altro uso di `async void` non segue il modello TAP e può essere difficile da usare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="16bd1-182">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="16bd1-183">`async void`Non è possibile intercettare le eccezioni generate in un metodo all'esterno di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="16bd1-183">Exceptions thrown in an `async void` method can't be caught outside of that method.</span></span>
* <span data-ttu-id="16bd1-184">`async void`i metodi sono difficili da testare.</span><span class="sxs-lookup"><span data-stu-id="16bd1-184">`async void` methods are difficult to test.</span></span>
* <span data-ttu-id="16bd1-185">`async void`i metodi possono causare effetti collaterali non validi se il chiamante non è in attesa di essere asincrono.</span><span class="sxs-lookup"><span data-stu-id="16bd1-185">`async void` methods can cause bad side effects if the caller isn't expecting them to be async.</span></span>

* <span data-ttu-id="16bd1-186">**Prestare attenzione quando si usano le espressioni lambda asincrone in espressioni LINQ**</span><span class="sxs-lookup"><span data-stu-id="16bd1-186">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="16bd1-187">Le espressioni lambda in LINQ usano l'esecuzione posticipata, ovvero il codice potrebbe terminare l'esecuzione in un momento in cui non è previsto.</span><span class="sxs-lookup"><span data-stu-id="16bd1-187">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you're not expecting it to.</span></span> <span data-ttu-id="16bd1-188">L'introduzione delle attività di blocco in questa operazione produce facilmente un deadlock se il codice non è scritto in maniera corretta.</span><span class="sxs-lookup"><span data-stu-id="16bd1-188">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="16bd1-189">L'annidamento di codice asincrono come questo può anche rendere più difficile la valutazione dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-189">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="16bd1-190">Async e LINQ sono molto efficaci, ma devono essere usati insieme con precauzione e in modo chiaro.</span><span class="sxs-lookup"><span data-stu-id="16bd1-190">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="16bd1-191">**Scrivere codice che attende attività in modo non bloccante**</span><span class="sxs-lookup"><span data-stu-id="16bd1-191">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="16bd1-192">Il blocco del thread corrente come mezzo per attendere il completamento di un oggetto `Task` può provocare deadlock e thread di contesto bloccati e può richiedere una gestione degli errori più complessa.</span><span class="sxs-lookup"><span data-stu-id="16bd1-192">Blocking the current thread as a means to wait for a `Task` to complete can result in deadlocks and blocked context threads, and can require more complex error-handling.</span></span> <span data-ttu-id="16bd1-193">La tabella seguente fornisce indicazioni su come gestire l'attesa di attività in modo non bloccante:</span><span class="sxs-lookup"><span data-stu-id="16bd1-193">The following table provides guidance on how to deal with waiting for tasks in a non-blocking way:</span></span>

| <span data-ttu-id="16bd1-194">Opzione</span><span class="sxs-lookup"><span data-stu-id="16bd1-194">Use this...</span></span>          | <span data-ttu-id="16bd1-195">Invece di questo</span><span class="sxs-lookup"><span data-stu-id="16bd1-195">Instead of this...</span></span>           | <span data-ttu-id="16bd1-196">Quando si desidera eseguire questa operazione...</span><span class="sxs-lookup"><span data-stu-id="16bd1-196">When wishing to do this...</span></span>                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | <span data-ttu-id="16bd1-197">`Task.Wait` o `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="16bd1-197">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="16bd1-198">Recuperare il risultato di un'attività in background</span><span class="sxs-lookup"><span data-stu-id="16bd1-198">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny`               | <span data-ttu-id="16bd1-199">Attendere che un'attività sia completa</span><span class="sxs-lookup"><span data-stu-id="16bd1-199">Waiting for any task to complete</span></span>           |
| `await Task.WhenAll` | `Task.WaitAll`               | <span data-ttu-id="16bd1-200">Attendere che tutte le attività siano complete</span><span class="sxs-lookup"><span data-stu-id="16bd1-200">Waiting for all tasks to complete</span></span>          |
| `await Task.Delay`   | `Thread.Sleep`               | <span data-ttu-id="16bd1-201">Attendere un periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="16bd1-201">Waiting for a period of time</span></span>               |

* <span data-ttu-id="16bd1-202">**Prendere in considerazione l'uso** `ValueTask` di **dove possibile**</span><span class="sxs-lookup"><span data-stu-id="16bd1-202">**Consider using** `ValueTask` **where possible**</span></span>

<span data-ttu-id="16bd1-203">La restituzione di un oggetto `Task` dai metodi asincroni può introdurre colli di bottiglia delle prestazioni in determinati percorsi.</span><span class="sxs-lookup"><span data-stu-id="16bd1-203">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="16bd1-204">`Task` è un tipo di riferimento, quindi usarlo significa allocare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="16bd1-204">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="16bd1-205">Nei casi in cui un metodo dichiarato con il `async` modificatore restituisce un risultato memorizzato nella cache o viene completato in modo sincrono, le allocazioni aggiuntive possono diventare un costo significativo in termini di tempo nelle sezioni del codice critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="16bd1-205">In cases where a method declared with the `async` modifier returns a cached result or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="16bd1-206">Possono diventare onerose se si verificano in cicli ridotti.</span><span class="sxs-lookup"><span data-stu-id="16bd1-206">It can become costly if those allocations occur in tight loops.</span></span> <span data-ttu-id="16bd1-207">Per altre informazioni, vedere [tipi restituiti asincroni generalizzati](whats-new/csharp-7.md#generalized-async-return-types).</span><span class="sxs-lookup"><span data-stu-id="16bd1-207">For more information, see [generalized async return types](whats-new/csharp-7.md#generalized-async-return-types).</span></span>

* <span data-ttu-id="16bd1-208">**Prendere in considerazione l'uso** di`ConfigureAwait(false)`</span><span class="sxs-lookup"><span data-stu-id="16bd1-208">**Consider using** `ConfigureAwait(false)`</span></span>

<span data-ttu-id="16bd1-209">Una domanda comune è: "quando è consigliabile usare il <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> metodo?".</span><span class="sxs-lookup"><span data-stu-id="16bd1-209">A common question is, "when should I use the <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> method?".</span></span> <span data-ttu-id="16bd1-210">Il metodo consente a un' `Task` istanza di di configurare il relativo awaiter.</span><span class="sxs-lookup"><span data-stu-id="16bd1-210">The method allows for a `Task` instance to configure its awaiter.</span></span> <span data-ttu-id="16bd1-211">Si tratta di una considerazione importante e l'impostazione non corretta potrebbe potenzialmente avere implicazioni in termini di prestazioni e persino deadlock.</span><span class="sxs-lookup"><span data-stu-id="16bd1-211">This is an important consideration and setting it incorrectly could potentially have performance implications and even deadlocks.</span></span> <span data-ttu-id="16bd1-212">Per altre informazioni su `ConfigureAwait` , vedere le [domande frequenti su ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span><span class="sxs-lookup"><span data-stu-id="16bd1-212">For more information on `ConfigureAwait`, see the [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span></span>

* <span data-ttu-id="16bd1-213">**Scrivere codice con meno dettagli sullo stato**</span><span class="sxs-lookup"><span data-stu-id="16bd1-213">**Write less stateful code**</span></span>

<span data-ttu-id="16bd1-214">Non dipendono dallo stato degli oggetti globali o dall'esecuzione di determinati metodi.</span><span class="sxs-lookup"><span data-stu-id="16bd1-214">Don't depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="16bd1-215">È preferibile dipendere dai valori restituiti dei metodi.</span><span class="sxs-lookup"><span data-stu-id="16bd1-215">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="16bd1-216">Perché?</span><span class="sxs-lookup"><span data-stu-id="16bd1-216">Why?</span></span>

* <span data-ttu-id="16bd1-217">Sarà più facile valutare il codice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-217">Code will be easier to reason about.</span></span>
* <span data-ttu-id="16bd1-218">Sarà più facile testare il codice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-218">Code will be easier to test.</span></span>
* <span data-ttu-id="16bd1-219">La combinazione di codice sincrono e asincrono è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-219">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="16bd1-220">È possibile evitare completamente le race condition.</span><span class="sxs-lookup"><span data-stu-id="16bd1-220">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="16bd1-221">La dipendenza dai valori restituiti semplifica il coordinamento di codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="16bd1-221">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="16bd1-222">(Extra) funziona particolarmente bene con l'inserimento di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="16bd1-222">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="16bd1-223">È consigliabile raggiungere una completa o quasi completa [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) nel codice.</span><span class="sxs-lookup"><span data-stu-id="16bd1-223">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="16bd1-224">Ciò risulterà in una base di codice completamente prevedibile, testabile e gestibile.</span><span class="sxs-lookup"><span data-stu-id="16bd1-224">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="16bd1-225">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="16bd1-225">Other resources</span></span>

* <span data-ttu-id="16bd1-226">L'articolo [La programmazione asincrona in dettaglio](../standard/async-in-depth.md) offre altre informazioni sul funzionamento di Task.</span><span class="sxs-lookup"><span data-stu-id="16bd1-226">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="16bd1-227">Programmazione asincrona con Async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="16bd1-227">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="16bd1-228">L'articolo [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Sei suggerimenti essenziali per la modalità asincrona) di Lucian Wischik è una risorsa eccellente per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="16bd1-228">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
