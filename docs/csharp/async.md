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
# <a name="asynchronous-programming"></a>Programmazione asincrona

Se si dispone di esigenze di I/O (ad esempio la richiesta di dati da una rete, l'accesso a un database o la lettura e la scrittura in un file system), è consigliabile utilizzare la programmazione asincrona. Si potrebbe anche usare codice associato alla CPU, ad esempio per eseguire un calcolo di spese, che rappresenta uno scenario importante per scrivere codice asincrono.

In C# è disponibile un modello di programmazione asincrona a livello di linguaggio che consente di scrivere facilmente codice asincrono, senza dover manipolare i callback o conformarsi a una libreria che supporta modalità asincrona. Questo modalità segue ciò che è noto come [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato sull'attività).

## <a name="overview-of-the-asynchronous-model"></a>Cenni preliminari sul modello asincrono

Il nucleo della programmazione asincrona è costituito da oggetti `Task` e `Task<T>` che modellano le operazioni asincrone. Sono supportati dalle parole chiavi `async` e `await`. Il modello è piuttosto semplice nella maggior parte dei casi:

- Per il codice associato a I/O, si attende un'operazione che restituisce un oggetto `Task` o `Task<T>` all'interno di un `async` metodo.
- Per il codice associato alla CPU, si attende un'operazione avviata in un thread in background con il <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> metodo.

La parola chiave `await` è l'elemento cruciale. Restituisce il controllo al chiamante del metodo che esegue `await` ed è questo che in ultima analisi consente a un'interfaccia utente di essere reattiva o a un servizio di essere flessibile. Sebbene [esistano modi](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) per approcciare codice asincrono diverso da `async` e `await` , questo articolo è incentrato sui costrutti a livello di linguaggio.

### <a name="io-bound-example-download-data-from-a-web-service"></a>Esempio di i/O associato: scaricare dati da un servizio Web

Potrebbe essere necessario scaricare alcuni dati da un servizio Web quando viene premuto un pulsante, ma non si vuole bloccare il thread dell'interfaccia utente. Questa operazione può essere eseguita in questo modo:

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

Il codice esprime l'intento (scaricando i dati in modo asincrono) senza rimanere impantanati nell'interazione con `Task` gli oggetti.

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a>Esempio associato alla CPU: eseguire un calcolo per un gioco

Si supponga di scrivere un gioco per dispositivi mobili in cui l'uso di un pulsante può causare danni a molti nemici visualizzati sullo schermo. L'esecuzione del calcolo del danno può essere molto onerosa e in questo modo il thread dell'interfaccia utente dà l'impressione che il gioco si arresti durante l'esecuzione del calcolo.

Il modo migliore per gestire questa situazione è avviare un thread in background, che esegue il lavoro utilizzando `Task.Run` , e attenda il risultato utilizzando `await` . In questo modo l'interfaccia utente può risultare uniforme quando il lavoro viene eseguito.

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

Questo codice esprime con precisione lo scopo dell'evento clic del pulsante, non è necessario gestire manualmente un thread in background e non blocca le funzionalità.

### <a name="what-happens-under-the-covers"></a>Operazioni eseguite in background

Sono molti gli elementi in cui sono coinvolte le operazioni asincrone. Per informazioni sulle operazioni eseguite sotto le quinte di `Task` e `Task<T>` , vedere l'articolo di [approfondimento asincrono](../standard/async-in-depth.md) per altre informazioni.

Sul lato C#, il compilatore trasforma il codice in una macchina a Stati che tiene traccia di elementi come la produzione di un'esecuzione quando `await` viene raggiunto un oggetto e la ripresa dell'esecuzione al termine di un processo in background.

Per gli utenti che amano la teoria, questa è un'implementazione del [Modello futuro di asincronia](https://en.wikipedia.org/wiki/Futures_and_promises).

## <a name="key-pieces-to-understand"></a>Elementi chiave da comprendere

* Il codice asincrono può essere usato per il codice associato a I/O e alla CPU, ma in modo diverso per ogni scenario.
* Il codice asincrono usa `Task<T>` e `Task`, che sono costrutti usati per modellare le operazioni eseguite in background.
* La parola chiave `async` trasforma un metodo in un metodo asincrono, che consente di usare la parola chiave `await` nel relativo corpo.
* Quando la parola chiave `await` viene applicata, interrompe il metodo di chiamata e restituisce il controllo al chiamante fino al completamento dell'attività attesa.
* `await` può essere usato solo all'interno di un metodo asincrono.

## <a name="recognize-cpu-bound-and-io-bound-work"></a>Riconoscere il lavoro associato alla CPU e I/O

I primi due esempi di questa guida hanno illustrato come usare `async` e `await` per operazioni associate ai I/O e alla CPU. È molto importante identificare se un processo da eseguire è associato a I/O o alla CPU perché ciò può influire notevolmente sulle prestazioni del codice e potrebbe causare un uso improprio di determinati costrutti.

Rispondere a queste due domande prima di scrivere il codice:

1. Il codice deve "attendere" l'esecuzione di operazioni, ad esempio la ricezione di dati da un database?

   Se la risposta è "Sì", l'operazione è **associata a I/O**.

1. Il codice eseguirà un calcolo costoso?

   Se la risposta è "Sì", l'operazione è **associata alla CPU**.

Se l'operazione è **associata a I/O**, usare `async` e `await` *senza* `Task.Run`. *Non si deve* usare la libreria Task Parallel Library. Il motivo è illustrato in modo asincrono in modo [approfondito](../standard/async-in-depth.md).

Se il lavoro di cui si dispone è **associato alla CPU** e si è interessati alla velocità di risposta, utilizzare `async` e `await` , ma generare il lavoro in un altro thread *con* `Task.Run` . Se il lavoro è appropriato per la concorrenza e il parallelismo, considerare anche l'uso del [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).

È anche necessario valutare sempre l'esecuzione del codice. Ad esempio, ci si potrebbe trovare in una situazione in cui l'operazione associata alla CPU non è abbastanza onerosa confrontata al sovraccarico di commutazioni di contesto durante il multithreading. Ogni scelta presenta un compromesso ed è necessario selezionare il compromesso più adatto alla situazione.

## <a name="more-examples"></a>Altri esempi

Gli esempi seguenti illustrano i diversi modi in cui è possibile scrivere codice asincrono in C#. Trattano scenari diversi molto comuni.

### <a name="extract-data-from-a-network"></a>Estrarre dati da una rete

Questo frammento Scarica il codice HTML dalla Home Page <https://dotnetfoundation.org> e conta il numero di volte in cui la stringa ".NET" viene eseguita nel codice HTML. USA ASP.NET per definire un metodo del controller API Web, che esegue questa attività e restituisce il numero.

> [!NOTE]
> Se si prevede di eseguire l'analisi del codice HTML nel codice di produzione, non usare le espressioni regolari. Usare invece una libreria di analisi.

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

Di seguito viene illustrato lo stesso scenario scritto per un'app di Windows universale, che esegue la stessa attività quando viene premuto un pulsante:

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

### <a name="wait-for-multiple-tasks-to-complete"></a>Attendi il completamento di più attività

Ci si potrebbe trovare in una situazione in cui è necessario recuperare più elementi di dati allo stesso tempo. L' `Task` API contiene due metodi, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> , che consentono di scrivere codice asincrono che esegue un'attesa non di blocco su più processi in background.

Questo esempio illustra come è possibile acquisire dati `User` per un set di `userId`.

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

Ecco un altro modo per scrivere questa operazione in modo più conciso, usando LINQ:

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

Sebbene produca una quantità minore di codice, è necessario prestare molta attenzione quando si combina LINQ con codice asincrono. Poiché LINQ usa un'esecuzione posticipata (lazy), le chiamate asincrone non verranno eseguite immediatamente come avviene in un ciclo `foreach` a meno che non si forzi la sequenza generata per l'iterazione con una chiamata a `.ToList()` o `.ToArray()`.

## <a name="important-info-and-advice"></a>Informazioni importanti e consigli

Con la programmazione asincrona è necessario tenere presenti alcuni dettagli che possono impedire un comportamento imprevisto.

* I metodi `async` ** devono avere una parola chiave ** `await` ** nel corpo, altrimenti non verranno eseguiti.**

  Questo è importante da tenere presente. Se `await` non viene usato nel corpo di un `async` metodo, il compilatore C# genera un avviso, ma il codice viene compilato ed eseguito come se fosse un metodo normale. Si tratta di un'operazione estremamente inefficiente, perché la macchina a stati generata dal compilatore C# per il metodo asincrono non esegue alcun risultato.

* **È consigliabile aggiungere "Async" come suffisso di ogni nome di metodo asincrono da scrivere.**

Si tratta della convenzione utilizzata in .NET per distinguere più facilmente i metodi sincroni e asincroni. Alcuni metodi che non vengono chiamati in modo esplicito dal codice, ad esempio i gestori eventi o i metodi del controller web, non sono necessariamente applicabili. Poiché non vengono chiamati in modo esplicito dal codice, il fatto di essere espliciti sulla denominazione non è altrettanto importante.

* `async void`**deve essere usato solo per i gestori eventi.**

`async void` è l'unico modo per consentire ai gestori eventi asincroni di funzionare correttamente, poiché gli eventi non hanno tipi restituiti (quindi non possono usare `Task` e `Task<T>`). Qualsiasi altro uso di `async void` non segue il modello TAP e può essere difficile da usare, ad esempio:

* `async void`Non è possibile intercettare le eccezioni generate in un metodo all'esterno di tale metodo.
* `async void`i metodi sono difficili da testare.
* `async void`i metodi possono causare effetti collaterali non validi se il chiamante non è in attesa di essere asincrono.

* **Prestare attenzione quando si usano le espressioni lambda asincrone in espressioni LINQ**

Le espressioni lambda in LINQ usano l'esecuzione posticipata, ovvero il codice potrebbe terminare l'esecuzione in un momento in cui non è previsto. L'introduzione delle attività di blocco in questa operazione produce facilmente un deadlock se il codice non è scritto in maniera corretta. L'annidamento di codice asincrono come questo può anche rendere più difficile la valutazione dell'esecuzione del codice. Async e LINQ sono molto efficaci, ma devono essere usati insieme con precauzione e in modo chiaro.

* **Scrivere codice che attende attività in modo non bloccante**

Il blocco del thread corrente come mezzo per attendere il completamento di un oggetto `Task` può provocare deadlock e thread di contesto bloccati e può richiedere una gestione degli errori più complessa. La tabella seguente fornisce indicazioni su come gestire l'attesa di attività in modo non bloccante:

| Opzione          | Invece di questo           | Quando si desidera eseguire questa operazione...                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | `Task.Wait` o `Task.Result` | Recuperare il risultato di un'attività in background |
| `await Task.WhenAny` | `Task.WaitAny`               | Attendere che un'attività sia completa           |
| `await Task.WhenAll` | `Task.WaitAll`               | Attendere che tutte le attività siano complete          |
| `await Task.Delay`   | `Thread.Sleep`               | Attendere un periodo di tempo               |

* **Prendere in considerazione l'uso** `ValueTask` di **dove possibile**

La restituzione di un oggetto `Task` dai metodi asincroni può introdurre colli di bottiglia delle prestazioni in determinati percorsi. `Task` è un tipo di riferimento, quindi usarlo significa allocare un oggetto. Nei casi in cui un metodo dichiarato con il `async` modificatore restituisce un risultato memorizzato nella cache o viene completato in modo sincrono, le allocazioni aggiuntive possono diventare un costo significativo in termini di tempo nelle sezioni del codice critiche per le prestazioni. Possono diventare onerose se si verificano in cicli ridotti. Per altre informazioni, vedere [tipi restituiti asincroni generalizzati](whats-new/csharp-7.md#generalized-async-return-types).

* **Prendere in considerazione l'uso** di`ConfigureAwait(false)`

Una domanda comune è: "quando è consigliabile usare il <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> metodo?". Il metodo consente a un' `Task` istanza di di configurare il relativo awaiter. Si tratta di una considerazione importante e l'impostazione non corretta potrebbe potenzialmente avere implicazioni in termini di prestazioni e persino deadlock. Per altre informazioni su `ConfigureAwait` , vedere le [domande frequenti su ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq).

* **Scrivere codice con meno dettagli sullo stato**

Non dipendono dallo stato degli oggetti globali o dall'esecuzione di determinati metodi. È preferibile dipendere dai valori restituiti dei metodi. Perché?

* Sarà più facile valutare il codice.
* Sarà più facile testare il codice.
* La combinazione di codice sincrono e asincrono è molto più semplice.
* È possibile evitare completamente le race condition.
* La dipendenza dai valori restituiti semplifica il coordinamento di codice asincrono.
* (Extra) funziona particolarmente bene con l'inserimento di dipendenze.

È consigliabile raggiungere una completa o quasi completa [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) nel codice. Ciò risulterà in una base di codice completamente prevedibile, testabile e gestibile.

## <a name="other-resources"></a>Altre risorse

* L'articolo [La programmazione asincrona in dettaglio](../standard/async-in-depth.md) offre altre informazioni sul funzionamento di Task.
* [Programmazione asincrona con Async e await (C#)](./programming-guide/concepts/async/index.md)
* L'articolo [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Sei suggerimenti essenziali per la modalità asincrona) di Lucian Wischik è una risorsa eccellente per la programmazione asincrona.
