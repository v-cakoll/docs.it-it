---
title: Utilizzo del modello asincrono basato su attività
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: f80e6ae520ab03c0f5f4edc30c0b7102193ee6c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139820"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Utilizzo del modello asincrono basato su attività

Quando si usa il modello asincrono basato su attività (TAP, Task-based Asynchronous Pattern) per lavorare con operazioni asincrone, è possibile usare i callback per ottenere un'attesa non bloccante.  Per le attività, è possibile ottenere questo risultato tramite metodi come <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Il supporto asincrono basato sul linguaggio nasconde i callback consentendo alle operazioni asincrone di essere in attesa all'interno di un normale flusso di controllo e il codice generato dal compilatore fornisce lo stesso livello di supporto delle API.

## <a name="suspending-execution-with-await"></a>Sospendere l'esecuzione con Await
 A partire da .NET Framework 4.5 è possibile usare la parola chiave [await](../../csharp/language-reference/operators/await.md) in C# e l'[operatore Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic per attendere in modo asincrono gli oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601>. Quando si è in attesa di <xref:System.Threading.Tasks.Task>, l'espressione `await` è di tipo `void`. Quando si è in attesa di <xref:System.Threading.Tasks.Task%601>, l'espressione `await` è di tipo `TResult`. Un'espressione `await` deve essere presente nel corpo di un metodo asincrono. Per altre informazioni sul supporto dei linguaggi C# e Visual Basic in .NET Framework 4.5, vedere le specifiche dei linguaggi C# e Visual Basic.

 Dietro le quinte, la funzionalità await installa un callback per l'attività tramite una continuazione.  Questo callback riprende il metodo asincrono in corrispondenza del punto di sospensione. Quando il metodo asincrono viene ripreso, se l'operazione attesa è stata completata correttamente ed era <xref:System.Threading.Tasks.Task%601>, viene restituito il corrispondente elemento `TResult`.  Se l'elemento <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> atteso è terminato con lo stato <xref:System.Threading.Tasks.TaskStatus.Canceled>, viene generata un'eccezione <xref:System.OperationCanceledException>.  Se l'elemento <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> atteso è terminato con lo stato <xref:System.Threading.Tasks.TaskStatus.Faulted>, viene generata l'eccezione che ha causato l'errore. Un `Task` può fallire a causa di più eccezioni, ma solo una di queste eccezioni viene propagata. La proprietà <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> restituisce tuttavia un'eccezione <xref:System.AggregateException> contenente tutti gli errori.

 Se un contesto di sincronizzazione (oggetto <xref:System.Threading.SynchronizationContext>) è associato al thread che stava eseguendo il metodo asincrono durante la sospensione (ad esempio, se la proprietà <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> non è `null`), il metodo asincrono riprende nello stesso contesto di sincronizzazione usando il metodo <xref:System.Threading.SynchronizationContext.Post%2A> del contesto. In caso contrario, si basa sull'utilità di pianificazione (oggetto <xref:System.Threading.Tasks.TaskScheduler>) che è corrente al momento della sospensione. Si tratta in genere dell'utilità di pianificazione predefinita (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), che specifica come destinazione il pool di thread. L'utilità di pianificazione determina se l'operazione asincrona in attesa deve riprendere al momento del completamento o se la ripresa deve essere pianificata. L'utilità di pianificazione predefinita consente in genere l'esecuzione della continuazione nel thread in cui l'operazione attesa è stata completata.

 Quando un metodo asincrono viene chiamato, esegue in modo sincrono il corpo della funzione fino alla prima espressione await su un'istanza awaitable che non è ancora terminata, a quel punto la chiamata restituisce il controllo al chiamante. Se il metodo asincrono non restituisce `void`, viene restituito un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> per rappresentare il calcolo in corso. In un metodo asincrono non void, se viene rilevata un'istruzione return o viene raggiunta la fine del corpo del metodo, l'attività termina con lo stato finale <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Se un'eccezione non gestita fa in modo che il controllo lasci il corpo del metodo asincrono, l'attività termina con lo stato <xref:System.Threading.Tasks.TaskStatus.Faulted>. Se tale eccezione è <xref:System.OperationCanceledException>, l'attività termina invece con lo stato <xref:System.Threading.Tasks.TaskStatus.Canceled>. Viene in questo modo pubblicato il risultato o l'eccezione.

 Vi sono diverse varianti importanti di questo comportamento.  Per motivi di prestazioni, se un processo viene completato prima che sia atteso, il controllo non viene prodotto e la funzione prosegue nell'esecuzione.  Non è inoltre sempre desiderabile tornare al contesto originale e questo comportamento può essere modificato. La sezione seguente descrive questa situazione nei dettagli.

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Configurazione della sospensione e della ripresa con Yield e ConfigureAwait
 Esistono diversi metodi che forniscono maggiore controllo sull'esecuzione di un metodo asincrono. È ad esempio possibile usare il metodo <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> per introdurre un punto di sospensione nel metodo asincrono:

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 Questa operazione equivale a eseguire un postback asincrono o a ritornare in modo asincrono al contesto corrente tramite programmazione.

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

 È anche possibile usare il metodo <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> per controllare meglio la sospensione e la ripresa in un metodo asincrono.  Come accennato in precedenza, per impostazione predefinita il contesto corrente viene acquisito nel momento in cui un metodo asincrono viene sospeso e questo contesto acquisito viene utilizzato per richiamare la continuazione del metodo asincrono al momento della ripresa.  In molti casi questo è il comportamento desiderato.  In altri casi non è necessario preoccuparsi del contesto di continuazione ed è possibile ottenere migliori prestazioni evitando tali postback al contesto originale.  Usare a tale scopo il metodo <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> per indicare all'operazione await di non acquisire e riprendere il contesto, ma di continuare l'esecuzione quando l'operazione asincrona di cui si era in attesa viene completata:

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a>Annullamento di un'operazione asincrona
 A partire da .NET Framework 4, i metodi TAP che supportano l'annullamento forniscono almeno un overload che accetta un token di annullamento (oggetto <xref:System.Threading.CancellationToken>).

 Un token di annullamento viene creato tramite un'origine di token di annullamento (oggetto <xref:System.Threading.CancellationTokenSource>).  La proprietà <xref:System.Threading.CancellationTokenSource.Token%2A> dell'origine restituisce il token di annullamento che verrà segnalato quando il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A> dell'origine verrà chiamato.  Ad esempio, per scaricare una singola pagina Web e poter annullare l'operazione, si crea un oggetto <xref:System.Threading.CancellationTokenSource>, si passa il token al metodo TAP e quindi, quando si è pronti per annullare l'operazione, si chiama il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A> dell'origine:

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 Per annullare più chiamate asincrone, è possibile passare lo stesso token per tutte le chiamate:

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 È in alternativa possibile passare lo stesso token a un sottoinsieme selettivo di operazioni:

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 Le richieste di annullamento possono essere avviate da qualsiasi thread.

 È possibile passare il valore di <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> a ogni metodo che accetta un token di annullamento per indicare che non verrà mai richiesto l'annullamento.  In tal modo la proprietà <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> restituisce `false` e il metodo chiamato può essere ottimizzato di conseguenza.  È possibile, a scopo di test, passare un token di annullamento già annullato di cui si è creata un'istanza usando il costruttore che accetta un valore booleano per indicare se il token deve essere avviato in uno stato already-canceled (già cancellato) o not-cancelable (non cancellabile).

 Questo approccio all'annullamento presenta diversi vantaggi:

- È possibile passare lo stesso token di annullamento a un numero qualsiasi di operazioni asincrone e sincrone.

- La stessa richiesta di annullamento può essere estesa a un numero qualsiasi di listener.

- Lo sviluppatore dell'API asincrona ha il controllo totale sull'eventuale richiesta di annullamento e sull'eventuale esecuzione.

- Il codice che usa l'API può determinare in modo selettivo a quali chiamate asincrone verranno propagate le richieste di annullamento.

## <a name="monitoring-progress"></a>Monitoraggio dello stato
 Alcuni metodi asincroni espongono lo stato di avanzamento tramite un'interfaccia dello stato di avanzamento passata all'interno del metodo asincrono.  Si consideri ad esempio una funzione che scarica in modo asincrono una stringa di testo e, durante il processo, genera gli aggiornamenti dello stato di avanzamento che include la percentuale di download completata fino a quel momento.  Tale metodo può essere usato in un'applicazione Windows Presentation Foundation (WPF) come segue:

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
## <a name="using-the-built-in-task-based-combinators"></a>Utilizzo di combinatori incorporati basati su attività
 Lo spazio dei nomi <xref:System.Threading.Tasks> include diversi metodi per la composizione e l'uso delle attività.

### <a name="taskrun"></a>Task.Run
 La classe <xref:System.Threading.Tasks.Task> include diversi metodi <xref:System.Threading.Tasks.Task.Run%2A> che consentono di eseguire facilmente l'offload del lavoro come <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> nel pool di thread, ad esempio:

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

 Alcuni di questi metodi <xref:System.Threading.Tasks.Task.Run%2A>, ad esempio l'overload <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, esistono come abbreviazione per il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>.  Altri overload, come <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, consentono di usare await nel lavoro di cui è stato eseguito l'offload, ad esempio:

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

 Tali overload sono logicamente equivalenti all'uso del metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> insieme al metodo di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> in Task Parallel Library.

### <a name="taskfromresult"></a>Task.FromResult
 Usare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> negli scenari in cui i dati possono essere già disponibili e devono essere solo restituiti da un metodo che restituisce attività del tipo <xref:System.Threading.Tasks.Task%601>:

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

### <a name="taskwhenall"></a>Task.WhenAll
 Usare il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A> per attendere in modo asincrono più operazioni asincrone rappresentate come attività.  Il metodo dispone di più overload che supportano un set di attività non generiche o un set non uniforme di attività generiche (ad esempio attendere in modo asincrono più operazioni che restituiscono void, o attendere in modo asincrono più metodi che restituiscono dei valori, dove ogni valore può essere di tipo diverso) e supportano un set uniforme di attività generiche (ad esempio attendere in modo asincrono più metodi che restituiscono `TResult`).

 Si supponga di voler inviare messaggi di posta elettronica a numerosi clienti. È possibile sovrapporre l'invio dei messaggi in modo da non dover attendere che un messaggio termini prima di inviare il successivo. È inoltre possibile scoprire quando le operazioni di invio sono state completate e se si sono verificati degli errori:

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 Questo codice non gestisce in modo esplicito le eccezioni che possono verificarsi, ma consente la propagazione delle eccezioni da `await` sull'attività risultante da <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Per gestire le eccezioni, è possibile usare codice simile al seguente:

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

 In questo caso, se un'operazione asincrona non riesce, tutte le eccezioni verranno consolidate in un'eccezione <xref:System.AggregateException>, archiviata nell'attività <xref:System.Threading.Tasks.Task> restituita dal metodo <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Solo una di queste eccezioni viene tuttavia propagata dalla parola chiave `await`.  Se si desidera esaminare tutte le eccezioni, è possibile riscrivere il codice precedente come segue:

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

 Si consideri un esempio in cui si scaricano più file dal Web in modo asincrono.  In questo caso tutte le operazioni asincrone hanno tipi di risultato omogenei ed è facile accedere ai risultati:

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 È possibile applicare le stesse tecniche di gestione delle eccezioni illustrate nello scenario di restituzione di void precedente:

```csharp
Task [] asyncOps =
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

### <a name="taskwhenany"></a>Task.WhenAny
 È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per attendere in modo asincrono più operazioni asincrone rappresentate come attività da completare.  Questo metodo viene usato principalmente in quattro casi:

- Ridondanza: esecuzione ripetuta di un'operazione e selezione di quella che viene terminata per prima (ad esempio contatto di più servizi Web di quotazioni di borsa tramite cui verrà generato un solo risultato e selezione di quello che viene completato più velocemente).

- Interfoliazione: avvio di più operazioni e attesa del completamento di tutte, ma elaborazione al termine delle operazioni in questione.

- Limitazione: consentire l'avvio di operazioni aggiuntive al completamento delle altre.  Questa è un'estensione dello scenario di interfoliazione.

- Bailout iniziale: ad esempio, un'operazione rappresentata dall'attività t1 può essere raggruppata in un'attività <xref:System.Threading.Tasks.Task.WhenAny%2A> con un'altra attività t2 ed è possibile attendere l'attività <xref:System.Threading.Tasks.Task.WhenAny%2A>. L'attività t2 potrebbe rappresentare un timeout, un annullamento o un altro segnale che fa sì che l'attività <xref:System.Threading.Tasks.Task.WhenAny%2A> termini prima di t1.

#### <a name="redundancy"></a>Ridondanza
 Si consideri il caso in cui si desidera decidere se comprare o meno dei titoli.  Esistono numerosi servizi Web attendibili che consigliano su azioni, ma a seconda del traffico giornaliero, ogni servizio può risultare lento in determinati momenti.  È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per ricevere una notifica quando un'operazione termina:

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

 Diversamente da <xref:System.Threading.Tasks.Task.WhenAll%2A>, che restituisce i risultati da cui è stato rimosso il wrapping di tutte le attività completate correttamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> restituisce l'attività completata. Se un'attività ha esito negativo, è importante sottolineare che ha avuto esito negativo e se l'attività ha esito positivo, è importante sapere a quale attività è associato il valore restituito.  Pertanto, è necessario accedere al risultato dell'attività restituita o attenderlo ulteriormente, come mostrato nell'esempio riportato di seguito.

 Come per <xref:System.Threading.Tasks.Task.WhenAll%2A>, è necessario poter adattare le eccezioni.  Poiché l'attività terminata viene restituita, è possibile attendere l'attività restituita per propagare gli errori ed eseguire `try/catch` in modo appropriato, ad esempio:

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

 Anche se il primo processo viene completato correttamente, le attività successive possono dare esito negativo.  A questo punto, sono disponibili diverse opzioni per la gestione delle eccezioni: è possibile attendere il completamento di tutte le attività avviate e, in questo caso, è possibile utilizzare il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A> oppure è possibile decidere che tutte le eccezioni sono importanti e devono essere registrate.  È possibile a tale scopo usare le continuazioni per ricevere una notifica quando le attività terminano in modo asincrono:

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 oppure:

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 o anche:

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

 È possibile, infine, annullare tutte le operazioni rimanenti:

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

#### <a name="interleaving"></a>Interfoliazione
 Si consideri il caso in cui si scarichino delle immagini dal Web e ogni immagine venga elaborata, ad esempio aggiungendo l'immagine a un controllo dell'interfaccia utente.  È necessario eseguire l'elaborazione sequenzialmente nell'interfaccia utente del thread, ma si desidera scaricare quante più immagini possibili contemporaneamente. Non si desidera, tra l'altro, aspettare che le immagini siano tutte scaricate prima di aggiungerle all'interfaccia utente, ma si desidera aggiungerle man mano che vengono scaricate:

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

 È anche possibile applicare l'interfoliazione a uno scenario che include un'elaborazione complessa a livello di calcolo nella classe <xref:System.Threading.ThreadPool> delle immagini scaricate, ad esempio:

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

#### <a name="throttling"></a>Limitazione
 Si consideri l'esempio dell'interfoliazione, con la differenza che l'utente sta scaricando un numero così elevato di immagini che i download devono essere limitati. Si desidera, ad esempio, che solo uno specifico numero di download sia realizzato contemporaneamente. È possibile a tale scopo avviare un sottoinsieme di operazioni asincrone.  Mentre le operazioni terminano, è possibile avviare operazioni aggiuntive che prendano il loro posto:

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

#### <a name="early-bailout"></a>Bailout iniziale
 Si consideri di essere in attesa in modo asincrono che un'operazione termini e contemporaneamente di rispondere alla richiesta di interruzione da parte di un utente (ad esempio l'utente ha fatto clic su un pulsante di annullamento). Il codice seguente illustra questo scenario:

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

 Questa implementazione abilita nuovamente l'interfaccia utente non appena si decide di annullare l'operazione, ma non annulla le operazioni asincrone sottostanti.  Un'alternativa consiste nell'annullare le operazioni in sospeso quando si decide di interrompere, ma di non ristabilire l'interfaccia utente finché le operazioni non siano terminate, probabilmente perché a causa della richiesta dell'interruzione, sono terminate prima:

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

 Un altro esempio di bailout iniziale prevede l'uso del <xref:System.Threading.Tasks.Task.WhenAny%2A> metodo insieme al metodo <xref:System.Threading.Tasks.Task.Delay%2A>, come illustrato nella sezione successiva.

### <a name="taskdelay"></a>Task.Delay
 È possibile usare il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> per introdurre pause nell'esecuzione di un metodo asincrono.  Ciò è utile per molti tipi di funzionalità, incluse la compilazione dei cicli di polling e il posticipo della gestione di input utente per un periodo di tempo predeterminato.  Il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> può anche essere utile in combinazione con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> per implementare i timeout sulle attese.

 Se un'attività che fa parte di una operazione asincrona più ampia, ad esempio un servizio web ASP.NET, impiega troppo tempo per terminare, potrebbe soffrirne l'operazione globale, specialmente se non termina mai.  Per questo motivo, è importante poter introdurre un timeout quando si è in attesa di un'operazione asincrona.  I metodi sincroni <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> accettano i valori di timeout, ma i corrispondenti metodi <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> citati in precedenza non li accettano.  È invece possibile usare <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combinazione per implementare un timeout.

 In un'applicazione con interfaccia utente si desidera, ad esempio, scaricare un'immagine e disabilitare l'interfaccia utente durante il download dell'immagine. Se però il download è troppo lungo, si desidera abilitare nuovamente l'interfaccia utente e rimuovere il download:

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

 Lo stesso accade con più download, perché <xref:System.Threading.Tasks.Task.WhenAll%2A> restituisce un'attività:

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

## <a name="building-task-based-combinators"></a>Sviluppo di combinatori basati su attività
 Poiché un'attività può rappresentare completamente un'operazione asincrona e fornire funzionalità sincrone e asincrone per effettuare join con l'operazione, recuperare i risultati e così via, è possibile compilare utili librerie dei combinatori che costituiscono le attività per costruire modelli più grandi.  Come illustrato nella sezione precedente, .NET Framework include diversi combinatori incorporati, ma è possibile costruirne di personalizzati. Le sezioni seguenti forniscono alcuni esempi di potenziali metodi e tipi di combinatori.

### <a name="retryonfault"></a>RetryOnFault
 In molte situazioni è possibile ritentare un'operazione se un tentativo precedente ha dato esito negativo.  Per il codice sincrono, è possibile creare un metodo helper, ad esempio `RetryOnFault` come mostrato nell'esempio seguente, per eseguire questa operazione:

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

 È possibile compilare un metodo helper quasi identico per le operazioni asincrone implementate con TAP e restituire in questo modo delle attività:

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

 È successivamente possibile usare questo combinatore per codificare i tentativi nella logica dell'applicazione. Ad esempio:

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 È possibile estendere ulteriormente la funzione `RetryOnFault`. La funzione potrebbe, ad esempio, accettare un'altra `Func<Task>` che verrà richiamata tra i nuovi tentativi per determinare quando eseguire nuovamente l'operazione. Ad esempio:

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

 È quindi possibile usare la funzione come descritto di seguito per attendere un secondo prima di ritentare l'operazione:

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a>NeedOnlyOne
 È talvolta possibile usare la ridondanza per migliorare la latenza e le probabilità di successo di un'operazione.  Si considerino vari servizi Web che forniscono quotazioni azionarie. In diversi momenti del giorno ogni servizio può fornire diversi livelli di qualità e tempi di risposta.  Per la gestione di tali fluttuazioni, è possibile inviare richieste a tutti i servizi Web e non appena si riceve una risposta da una, annullare le richieste rimanenti.  È possibile implementare una funzione helper per semplificare l'implementazione di questo modello comune basato sull'avvio di più operazioni, l'attesa della prima risposta e l'annullamento delle operazioni che non hanno fornito la risposta per prime. La funzione `NeedOnlyOne` dell'esempio seguente illustra questo scenario:

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

 È possibile quindi usare questa funzione come segue:

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a>Operazioni con interfoliazione
 Esiste un potenziale problema di prestazioni quando si usa il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per supportare uno scenario di interfoliazione nel caso in cui si usino set di attività molto grandi. Ogni chiamata a <xref:System.Threading.Tasks.Task.WhenAny%2A> comporta la registrazione di una continuazione con ogni attività. Per il numero N di attività, ciò comporta la creazione di continuazioni O(N<sup>2)</sup>per tutta la durata dell'operazione di interfoliazione. Se si utilizza un set di attività di grandi dimensioni, è possibile utilizzare un combinatore (nell'esempio`Interleaved` seguente) per risolvere il problema di prestazioni:

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

 È quindi possibile usare il combinatore per elaborare i risultati delle attività man mano che vengono completate. Ad esempio:

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a>WhenAllOrFirstException
 In alcuni scenari di dispersione/raccolta di dati, potrebbe essere necessario attendere il completamento di tutti i processi di un set, a meno che uno di questi non fallisca, nel qual caso si può arrestare l'attesa non appena si verifica l'eccezione.  È possibile eseguire questa operazione con un metodo combinatore, ad esempio `WhenAllOrFirstException`, come illustrato nell'esempio seguente:

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

## <a name="building-task-based-data-structures"></a>Creazione di strutture dei dati basate su attività
 Oltre alla possibilità di costruire combinatori personalizzati basati su attività, avere una struttura dei dati in <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> che rappresenta sia i risultati di un'operazione asincrona che la sincronizzazione necessaria con cui creare un join è una soluzione molto potente su cui basare la creazione di strutture dei dati personalizzate da usare in scenari asincroni.

### <a name="asynccache"></a>AsyncCache
 Un aspetto importante di un'attività è che può essere distribuita a diversi clienti, tutti la possono attendere, registrarvi continuazioni, ottenerne il risultato o le eccezioni (nel caso di <xref:System.Threading.Tasks.Task%601>) e così via.  Ciò rende <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> ideali per essere usati in un'infrastruttura asincrona di memorizzazione nella cache.  Di seguito è riportato un esempio di una piccola ma potente cache asincrona costruita basandosi su <xref:System.Threading.Tasks.Task%601>:

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

 La classe [AsyncCache\<TKey, TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) accetta come delegato al costruttore una funzione che accetta `TKey` e restituisce <xref:System.Threading.Tasks.Task%601>.  Tutti i valori della cache a cui si è acceduto precedentemente vengono archiviati nel dizionario interno e `AsyncCache` fa in modo che venga generata solo un'attività per chiave, anche si accede alla cache contemporaneamente.

 È possibile, ad esempio, creare una cache per le pagine Web scaricate:

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 È quindi possibile usare tale cache nei metodi asincroni ogni volta che è necessario accedere al contenuto di una pagina Web. La classe `AsyncCache` assicura che si scarichi il minor numero di pagine possibile e memorizza i risultati nella cache.

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

### <a name="asyncproducerconsumercollection"></a>AsyncProducerConsumerCollection
 È inoltre possibile usare attività per creare strutture dei dati per coordinare le attività asincrone.  Si consideri uno dei classici modelli di progettazione paralleli: produttore/consumatore.  In questo modello, i produttori generano dati che sono consumati dai consumatori e i produttori e i consumatori possono operare in parallelo. Il consumatore elabora, ad esempio, l'elemento 1, che è stato precedentemente generato da un produttore che sta scrivendo l'elemento 2.  Il modello produttore/consumatore prevede invariabilmente la presenza di una struttura dei dati in cui memorizzare il lavoro creato dai produttori in modo che i consumatori possano essere informati di nuovi dati e possano gestirli una volta disponibili.

 Questa è una semplice struttura dei dati costruita basandosi su attività che consente di usare i metodi asincroni come produttori e consumatori:

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

 Con tale struttura dei dati è possibile scrivere codice come il seguente:

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

Lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow> include il tipo <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, che è possibile usare in modo simile, ma senza dover compilare un tipo di raccolta personalizzato:

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
> Lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow> è disponibile in .NET Framework 4.5 tramite **NuGet**. Per installare l'assembly contenente lo spazio dei nomi <xref:System.Threading.Tasks.Dataflow>, aprire il progetto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu Progetto e cercare online il pacchetto Microsoft.Tpl.Dataflow.

## <a name="see-also"></a>Vedere anche

- [Modello asincrono basato su attività (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Implementazione del modello asincrono basato su attività](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [Interoperabilità con altri tipi e modelli asincroni](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
