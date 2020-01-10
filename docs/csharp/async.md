---
title: Programmazione asincrona - C#
description: Informazioni sul modello di programmazione asincrona a livello del linguaggio C# fornito da .NET Core.
author: cartermp
ms.date: 06/20/2016
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 38d7c856e9a536db9ef26349175ad440a49f5fe2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713945"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="349c7-103">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="349c7-103">Asynchronous programming</span></span>

<span data-ttu-id="349c7-104">Se si hanno esigenze associate a I/O, ad esempio richiesta di dati da una rete o accesso a un database, si può usare la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="349c7-104">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="349c7-105">Si potrebbe anche usare codice associato alla CPU, ad esempio per eseguire un calcolo di spese, che rappresenta uno scenario importante per scrivere codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="349c7-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="349c7-106">C# ha un modello di programmazione asincrona a livello di linguaggio che consente di scrivere facilmente codice asincrono senza dover manipolare callback o conformarsi a una libreria che supporti l'asincronia.</span><span class="sxs-lookup"><span data-stu-id="349c7-106">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="349c7-107">Questo modalità segue ciò che è noto come [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato sull'attività).</span><span class="sxs-lookup"><span data-stu-id="349c7-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="349c7-108">Panoramica di base del modello asincrono</span><span class="sxs-lookup"><span data-stu-id="349c7-108">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="349c7-109">Il nucleo della programmazione asincrona è costituito da oggetti `Task` e `Task<T>` che modellano le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="349c7-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="349c7-110">Sono supportati dalle parole chiavi `async` e `await`.</span><span class="sxs-lookup"><span data-stu-id="349c7-110">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="349c7-111">Il modello è piuttosto semplice nella maggior parte dei casi:</span><span class="sxs-lookup"><span data-stu-id="349c7-111">The model is fairly simple in most cases:</span></span>

<span data-ttu-id="349c7-112">Per il codice associato a I/O, si usa `await` per l'operazione che restituisce un oggetto `Task` o `Task<T>` all'interno di un metodo `async`.</span><span class="sxs-lookup"><span data-stu-id="349c7-112">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="349c7-113">Per il codice associato alla CPU, si usa `await` per l'operazione che viene avviata in un thread in background con il metodo `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="349c7-113">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="349c7-114">La parola chiave `await` è l'elemento cruciale.</span><span class="sxs-lookup"><span data-stu-id="349c7-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="349c7-115">Restituisce il controllo al chiamante del metodo che esegue `await` ed è questo che in ultima analisi consente a un'interfaccia utente di essere reattiva o a un servizio di essere flessibile.</span><span class="sxs-lookup"><span data-stu-id="349c7-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="349c7-116">Sono disponibili altri modi per trattare il codice asincrono rispetto a `async` e `await` illustrati nell'articolo su TAP visto precedentemente, per cui questo documento illustrerà da questo momento in poi le attività sui costrutti a livello di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="349c7-116">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="349c7-117">Esempio associato a I/O: download di dati da un servizio Web</span><span class="sxs-lookup"><span data-stu-id="349c7-117">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="349c7-118">Potrebbe essere necessario scaricare dati da un servizio Web quando viene premuto un pulsante, ma non si vuole bloccare il thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="349c7-118">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="349c7-119">Questo risultato si può ottenere in questo modo:</span><span class="sxs-lookup"><span data-stu-id="349c7-119">It can be accomplished simply like this:</span></span>

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

<span data-ttu-id="349c7-120">E questo è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="349c7-120">And that’s it!</span></span> <span data-ttu-id="349c7-121">Il codice esprime lo scopo (scaricando alcuni dati in modo asincrono) senza perdere tempo per interagire con gli oggetti Task.</span><span class="sxs-lookup"><span data-stu-id="349c7-121">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="349c7-122">Esempio associato alla CPU: esecuzione di un calcolo per un gioco</span><span class="sxs-lookup"><span data-stu-id="349c7-122">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="349c7-123">Si supponga di scrivere un gioco per dispositivi mobili in cui l'uso di un pulsante può causare danni a molti nemici visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="349c7-123">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="349c7-124">L'esecuzione del calcolo del danno può essere molto onerosa e in questo modo il thread dell'interfaccia utente dà l'impressione che il gioco si arresti durante l'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="349c7-124">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="349c7-125">Il modo migliore per gestire questa situazione è avviare un thread in background che esegua l'operazione tramite `Task.Run`, e usa `await` per il risultato.</span><span class="sxs-lookup"><span data-stu-id="349c7-125">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="349c7-126">Ciò consentirà all'interfaccia utente di essere disponibile durante l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="349c7-126">This will allow the UI to feel smooth as the work is being done.</span></span>

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
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="349c7-127">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="349c7-127">And that's it!</span></span>  <span data-ttu-id="349c7-128">Questo codice esprime con precisione lo scopo dell'evento clic del pulsante, non è necessario gestire manualmente un thread in background e non blocca le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="349c7-128">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="349c7-129">Operazioni eseguite in background</span><span class="sxs-lookup"><span data-stu-id="349c7-129">What happens under the covers</span></span>

<span data-ttu-id="349c7-130">Le operazioni asincrone coinvolgono molti elementi.</span><span class="sxs-lookup"><span data-stu-id="349c7-130">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="349c7-131">Se si vuole sapere cosa accade in background con `Task` e `Task<T>`, vedere l'articolo [La programmazione asincrona in dettaglio](../standard/async-in-depth.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="349c7-131">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="349c7-132">Sul lato degli elementi di C#, il compilatore trasforma il codice in una macchina a stati che tiene traccia di varie operazioni, ad esempio sospendere l'esecuzione quando viene raggiunto `await` e riprendere l'esecuzione quando un'operazione di background è stata completata.</span><span class="sxs-lookup"><span data-stu-id="349c7-132">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="349c7-133">Per gli utenti che amano la teoria, questa è un'implementazione del [Modello futuro di asincronia](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="349c7-133">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="349c7-134">Nozioni fondamentali da sapere</span><span class="sxs-lookup"><span data-stu-id="349c7-134">Key Pieces to Understand</span></span>

* <span data-ttu-id="349c7-135">Il codice asincrono può essere usato per il codice associato a I/O e alla CPU, ma in modo diverso per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="349c7-135">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="349c7-136">Il codice asincrono usa `Task<T>` e `Task`, che sono costrutti usati per modellare le operazioni eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="349c7-136">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="349c7-137">La parola chiave `async` trasforma un metodo in un metodo asincrono, che consente di usare la parola chiave `await` nel relativo corpo.</span><span class="sxs-lookup"><span data-stu-id="349c7-137">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="349c7-138">Quando la parola chiave `await` viene applicata, interrompe il metodo di chiamata e restituisce il controllo al chiamante fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="349c7-138">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="349c7-139">`await` può essere usato solo all'interno di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="349c7-139">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="349c7-140">Riconoscere le operazioni associate alla CPU e a I/O</span><span class="sxs-lookup"><span data-stu-id="349c7-140">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="349c7-141">I primi due esempi di questa guida hanno illustrato come usare `async` e `await` per operazioni associate ai I/O e alla CPU.</span><span class="sxs-lookup"><span data-stu-id="349c7-141">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="349c7-142">È molto importante identificare se un processo da eseguire è associato a I/O o alla CPU perché ciò può influire notevolmente sulle prestazioni del codice e potrebbe causare un uso improprio di determinati costrutti.</span><span class="sxs-lookup"><span data-stu-id="349c7-142">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="349c7-143">Rispondere a queste due domande prima di scrivere il codice:</span><span class="sxs-lookup"><span data-stu-id="349c7-143">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="349c7-144">Il codice deve "attendere" l'esecuzione di operazioni, ad esempio la ricezione di dati da un database?</span><span class="sxs-lookup"><span data-stu-id="349c7-144">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="349c7-145">Se la risposta è "Sì", l'operazione è **associata a I/O**.</span><span class="sxs-lookup"><span data-stu-id="349c7-145">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="349c7-146">Il codice eseguirà un calcolo molto oneroso?</span><span class="sxs-lookup"><span data-stu-id="349c7-146">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="349c7-147">Se la risposta è "Sì", l'operazione è **associata alla CPU**.</span><span class="sxs-lookup"><span data-stu-id="349c7-147">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="349c7-148">Se il lavoro è associato a **i/O**, usare `async` e `await` *senza* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="349c7-148">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="349c7-149">*Non si deve* usare la libreria Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="349c7-149">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="349c7-150">Il motivo viene illustrato nell'articolo [La programmazione asincrona in dettaglio](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="349c7-150">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="349c7-151">Se il lavoro di cui si dispone è **associato alla CPU** e si è interessati alla velocità di risposta, utilizzare `async` e `await` ma generare il lavoro in un altro thread *con* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="349c7-151">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="349c7-152">Se l'operazione è appropriata per parallelismo e concorrenza, è consigliabile usare anche la libreria [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="349c7-152">If the work is appropriate for concurrency and parallelism, you should also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="349c7-153">È anche necessario valutare sempre l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="349c7-153">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="349c7-154">Ad esempio, ci si potrebbe trovare in una situazione in cui l'operazione associata alla CPU non è abbastanza onerosa confrontata al sovraccarico di commutazioni di contesto durante il multithreading.</span><span class="sxs-lookup"><span data-stu-id="349c7-154">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="349c7-155">Ogni scelta presenta un compromesso ed è necessario selezionare il compromesso più adatto alla situazione.</span><span class="sxs-lookup"><span data-stu-id="349c7-155">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="349c7-156">Altri esempi</span><span class="sxs-lookup"><span data-stu-id="349c7-156">More Examples</span></span>

<span data-ttu-id="349c7-157">Gli esempi seguenti illustrano i diversi modi in cui è possibile scrivere codice asincrono in C#.</span><span class="sxs-lookup"><span data-stu-id="349c7-157">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="349c7-158">Trattano scenari diversi molto comuni.</span><span class="sxs-lookup"><span data-stu-id="349c7-158">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="349c7-159">Estrazione di dati da una rete</span><span class="sxs-lookup"><span data-stu-id="349c7-159">Extracting Data from a Network</span></span>

<span data-ttu-id="349c7-160">Questo frammento di codice scarica il contenuto HTML dalla home page di [www.dotnetfoundation.org](https://www.dotnetfoundation.org) e conta il numero di volte in cui la stringa ".NET" è inclusa nel contenuto HTML.</span><span class="sxs-lookup"><span data-stu-id="349c7-160">This snippet downloads the HTML from the homepage at [www.dotnetfoundation.org](https://www.dotnetfoundation.org) and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="349c7-161">Usa MVC di ASP.NET per definire un metodo del controller Web che esegue questa attività, restituendo il numero.</span><span class="sxs-lookup"><span data-stu-id="349c7-161">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="349c7-162">Se si prevede di eseguire l'analisi del codice HTML nel codice di produzione, non usare le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="349c7-162">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="349c7-163">Usare invece una libreria di analisi.</span><span class="sxs-lookup"><span data-stu-id="349c7-163">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="349c7-164">Di seguito viene illustrato lo stesso scenario scritto per un'app di Windows universale, che esegue la stessa attività quando viene premuto un pulsante:</span><span class="sxs-lookup"><span data-stu-id="349c7-164">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

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

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="349c7-165">Attesa per il completamento di più attività</span><span class="sxs-lookup"><span data-stu-id="349c7-165">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="349c7-166">Ci si potrebbe trovare in una situazione in cui è necessario recuperare più elementi di dati allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="349c7-166">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="349c7-167">L'API `Task` include due metodi, `Task.WhenAll` e `Task.WhenAny` che consentono di scrivere codice asincrono che esegue un'attesa senza blocchi su più processi in background.</span><span class="sxs-lookup"><span data-stu-id="349c7-167">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="349c7-168">Questo esempio illustra come è possibile acquisire dati `User` per un set di `userId`.</span><span class="sxs-lookup"><span data-stu-id="349c7-168">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

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

<span data-ttu-id="349c7-169">Questo è un altro modo per scrivere il codice in maniera più concisa tramite LINQ:</span><span class="sxs-lookup"><span data-stu-id="349c7-169">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

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

<span data-ttu-id="349c7-170">Sebbene produca una quantità minore di codice, è necessario prestare molta attenzione quando si combina LINQ con codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="349c7-170">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="349c7-171">Poiché LINQ usa un'esecuzione posticipata (lazy), le chiamate asincrone non verranno eseguite immediatamente come avviene in un ciclo `foreach()` a meno che non si forzi la sequenza generata per l'iterazione con una chiamata a `.ToList()` o `.ToArray()`.</span><span class="sxs-lookup"><span data-stu-id="349c7-171">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="349c7-172">Consigli e informazioni importanti</span><span class="sxs-lookup"><span data-stu-id="349c7-172">Important Info and Advice</span></span>

<span data-ttu-id="349c7-173">Sebbene la programmazione asincrona è relativamente semplice, ci sono alcuni dettagli da tenere presente per evitare comportamenti non previsti.</span><span class="sxs-lookup"><span data-stu-id="349c7-173">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="349c7-174">`async` **metodi devono avere una** **parola chiave `await` nel corpo o non verranno mai procedono.**</span><span class="sxs-lookup"><span data-stu-id="349c7-174">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="349c7-175">Questo è importante da tenere presente.</span><span class="sxs-lookup"><span data-stu-id="349c7-175">This is important to keep in mind.</span></span>  <span data-ttu-id="349c7-176">Se `await` non viene usato nel corpo di un metodo `async`, il compilatore C# genererà un avviso, ma il codice verrà compilato ed eseguito come se fosse un metodo normale.</span><span class="sxs-lookup"><span data-stu-id="349c7-176">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="349c7-177">Si noti che anche questo sarebbe estremamente inefficiente, perché la macchina a stati generata dal compilatore C# per il metodo asincrono non produrrebbe niente.</span><span class="sxs-lookup"><span data-stu-id="349c7-177">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

* <span data-ttu-id="349c7-178">**È consigliabile aggiungere "async" come suffisso di ogni nome di metodo scritto.**</span><span class="sxs-lookup"><span data-stu-id="349c7-178">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="349c7-179">Questa è la convenzione usata in .NET per differenziare più facilmente i metodi sincroni dai metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="349c7-179">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="349c7-180">Si noti che alcuni metodi non chiamati in modo esplicito dal codice, ad esempio un gestore di eventi o un metodo di controller del Web, non vengono necessariamente applicati.</span><span class="sxs-lookup"><span data-stu-id="349c7-180">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="349c7-181">Poiché questi metodi non vengono chiamati in modo esplicito dal codice, non è importante denominarli in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="349c7-181">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

* <span data-ttu-id="349c7-182">`async void` **deve essere usato solo per i gestori eventi.**</span><span class="sxs-lookup"><span data-stu-id="349c7-182">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="349c7-183">`async void` è l'unico modo per consentire ai gestori eventi asincroni di funzionare correttamente, poiché gli eventi non hanno tipi restituiti (quindi non possono usare `Task` e `Task<T>`).</span><span class="sxs-lookup"><span data-stu-id="349c7-183">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="349c7-184">Qualsiasi altro uso di `async void` non segue il modello TAP e può essere difficile da usare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="349c7-184">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="349c7-185">Le eccezioni generate in un metodo `async void` non possono essere rilevate al di fuori di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="349c7-185">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
* <span data-ttu-id="349c7-186">I metodi `async void` sono molto difficili da testare.</span><span class="sxs-lookup"><span data-stu-id="349c7-186">`async void` methods are very difficult to test.</span></span>
* <span data-ttu-id="349c7-187">I metodi `async void` possono causare effetti collaterali seri se il chiamante non li prevede asincroni.</span><span class="sxs-lookup"><span data-stu-id="349c7-187">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

* <span data-ttu-id="349c7-188">**Prestare attenzione quando si usano le espressioni lambda asincrone in espressioni LINQ**</span><span class="sxs-lookup"><span data-stu-id="349c7-188">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="349c7-189">Le espressioni lambda in LINQ usano esecuzioni posticipate, ovvero il codice potrebbe essere eseguito in qualsiasi momento quando meno previsto.</span><span class="sxs-lookup"><span data-stu-id="349c7-189">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="349c7-190">L'introduzione delle attività di blocco in questa operazione produce facilmente un deadlock se il codice non è scritto in maniera corretta.</span><span class="sxs-lookup"><span data-stu-id="349c7-190">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="349c7-191">L'annidamento di codice asincrono come questo può anche rendere più difficile la valutazione dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="349c7-191">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="349c7-192">Async e LINQ sono molto efficaci, ma devono essere usati insieme con precauzione e in modo chiaro.</span><span class="sxs-lookup"><span data-stu-id="349c7-192">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="349c7-193">**Scrivere codice che attende attività in modo non bloccante**</span><span class="sxs-lookup"><span data-stu-id="349c7-193">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="349c7-194">Il blocco del thread corrente come mezzo per attendere il completamento di un'attività può risultare in deadlock e in thread di contesto bloccati e può richiedere una gestione degli errori più complessa.</span><span class="sxs-lookup"><span data-stu-id="349c7-194">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="349c7-195">La tabella seguente offre indicazioni su come gestire l'attesa di attività in un modo non bloccante:</span><span class="sxs-lookup"><span data-stu-id="349c7-195">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="349c7-196">Usare questo</span><span class="sxs-lookup"><span data-stu-id="349c7-196">Use this...</span></span> | <span data-ttu-id="349c7-197">Invece di questo</span><span class="sxs-lookup"><span data-stu-id="349c7-197">Instead of this...</span></span> | <span data-ttu-id="349c7-198">Quando si vuole eseguire questa operazione</span><span class="sxs-lookup"><span data-stu-id="349c7-198">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="349c7-199">`Task.Wait` o `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="349c7-199">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="349c7-200">Recuperare il risultato di un'attività in background</span><span class="sxs-lookup"><span data-stu-id="349c7-200">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="349c7-201">Attendere che un'attività sia completa</span><span class="sxs-lookup"><span data-stu-id="349c7-201">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="349c7-202">Attendere che tutte le attività siano complete</span><span class="sxs-lookup"><span data-stu-id="349c7-202">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="349c7-203">Attendere un periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="349c7-203">Waiting for a period of time</span></span> |

* <span data-ttu-id="349c7-204">**Scrivere codice con meno dettagli sullo stato**</span><span class="sxs-lookup"><span data-stu-id="349c7-204">**Write less stateful code**</span></span>

<span data-ttu-id="349c7-205">È consigliabile non dipendere dallo stato di oggetti globali o dall'esecuzione di alcuni metodi.</span><span class="sxs-lookup"><span data-stu-id="349c7-205">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="349c7-206">È preferibile dipendere dai valori restituiti dei metodi.</span><span class="sxs-lookup"><span data-stu-id="349c7-206">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="349c7-207">Perché?</span><span class="sxs-lookup"><span data-stu-id="349c7-207">Why?</span></span>

* <span data-ttu-id="349c7-208">Sarà più facile valutare il codice.</span><span class="sxs-lookup"><span data-stu-id="349c7-208">Code will be easier to reason about.</span></span>
* <span data-ttu-id="349c7-209">Sarà più facile testare il codice.</span><span class="sxs-lookup"><span data-stu-id="349c7-209">Code will be easier to test.</span></span>
* <span data-ttu-id="349c7-210">La combinazione di codice sincrono e asincrono è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="349c7-210">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="349c7-211">È possibile evitare completamente le race condition.</span><span class="sxs-lookup"><span data-stu-id="349c7-211">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="349c7-212">La dipendenza dai valori restituiti semplifica il coordinamento di codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="349c7-212">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="349c7-213">(Extra) funziona particolarmente bene con l'inserimento di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="349c7-213">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="349c7-214">È consigliabile raggiungere una completa o quasi completa [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) nel codice.</span><span class="sxs-lookup"><span data-stu-id="349c7-214">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="349c7-215">Ciò risulterà in una base di codice completamente prevedibile, testabile e gestibile.</span><span class="sxs-lookup"><span data-stu-id="349c7-215">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="349c7-216">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="349c7-216">Other Resources</span></span>

* <span data-ttu-id="349c7-217">L'articolo [La programmazione asincrona in dettaglio](../standard/async-in-depth.md) offre altre informazioni sul funzionamento di Task.</span><span class="sxs-lookup"><span data-stu-id="349c7-217">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="349c7-218">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="349c7-218">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="349c7-219">L'articolo [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Sei suggerimenti essenziali per la modalità asincrona) di Lucian Wischik è una risorsa eccellente per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="349c7-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
