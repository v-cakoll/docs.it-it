---
title: "Utilizzo del modello asincrono basato su attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90b2a36f0e6bf06b0fefe2191d5b17c9c07d1588
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Utilizzo del modello asincrono basato su attività
Quando si usa il modello asincrono basato su attività (TAP, Task-based Asynchronous Pattern) per lavorare con operazioni asincrone, è possibile usare i callback per ottenere un'attesa non bloccante.  Per le attività, questo risultato viene ottenuto tramite i metodi, ad esempio <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Il supporto asincrono basato sul linguaggio nasconde i callback consentendo alle operazioni asincrone di essere in attesa all'interno di un normale flusso di controllo e il codice generato dal compilatore fornisce lo stesso livello di supporto delle API.  
  
## <a name="suspending-execution-with-await"></a>Sospendere l'esecuzione con Await  
 A partire dal [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], è possibile utilizzare il [await](~/docs/csharp/language-reference/keywords/await.md) (parola chiave) in c# e [operatore Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic per attendere in modo asincrono <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> oggetti. Quando è in attesa di un <xref:System.Threading.Tasks.Task>, `await` espressione è di tipo `void`. Quando è in attesa di un <xref:System.Threading.Tasks.Task%601>, `await` espressione è di tipo `TResult`. Un'espressione `await` deve essere presente nel corpo di un metodo asincrono. Per altre informazioni sul supporto dei linguaggi C# e Visual Basic in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], vedere le specifiche dei linguaggi C# e Visual Basic.  
  
 Dietro le quinte, la funzionalità await installa un callback per l'attività tramite una continuazione.  Questo callback riprende il metodo asincrono in corrispondenza del punto di sospensione. Quando il metodo asincrono viene riattivato, se l'operazione di attesa completata ed è stato un <xref:System.Threading.Tasks.Task%601>, l'oggetto `TResult` viene restituito.  Se il <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> che era atteso è terminata con il <xref:System.Threading.Tasks.TaskStatus.Canceled> stato, un <xref:System.OperationCanceledException> viene generata un'eccezione.  Se il <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> che era atteso è terminata con il <xref:System.Threading.Tasks.TaskStatus.Faulted> stato, viene generata l'eccezione che ha provocato l'errore. Un `Task` può fallire a causa di più eccezioni, ma solo una di queste eccezioni viene propagata. Tuttavia, il <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> proprietà restituisce un <xref:System.AggregateException> eccezione che contiene tutti gli errori.  
  
 Se un contesto di sincronizzazione (<xref:System.Threading.SynchronizationContext> oggetto) è associato al thread che era in esecuzione il metodo asincrono in fase di sospensione (ad esempio, se il <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> proprietà non è `null`), il metodo asincrono riprende che stesso contesto di sincronizzazione utilizzando il contesto <xref:System.Threading.SynchronizationContext.Post%2A> metodo. In caso contrario, si basa sull'utilità di pianificazione (<xref:System.Threading.Tasks.TaskScheduler> oggetto) che è stato corrente al momento della sospensione. Si tratta in genere, l'utilità di pianificazione predefinita (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), il pool di thread che ha come destinazione. L'utilità di pianificazione determina se l'operazione asincrona in attesa deve riprendere al momento del completamento o se la ripresa deve essere pianificata. L'utilità di pianificazione predefinita consente in genere l'esecuzione della continuazione nel thread in cui l'operazione attesa è stata completata.  
  
 Quando un metodo asincrono viene chiamato, esegue in modo sincrono il corpo della funzione fino alla prima espressione await su un'istanza awaitable che non è ancora terminata, a quel punto la chiamata restituisce il controllo al chiamante. Se il metodo asincrono non restituisce `void`, <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> oggetto viene restituito per rappresentare il calcolo in corso. In un metodo asincrono non void, se viene rilevata un'istruzione return o se viene raggiunta la fine del corpo del metodo, l'attività è stata completata nel <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> stato finale. Se un'eccezione non gestita, controllo di lasciare il corpo del metodo asincrono, l'attività termina con il <xref:System.Threading.Tasks.TaskStatus.Faulted> dello stato. Se l'eccezione è un <xref:System.OperationCanceledException>, l'attività termina invece il <xref:System.Threading.Tasks.TaskStatus.Canceled> dello stato. Viene in questo modo pubblicato il risultato o l'eccezione.  
  
 Vi sono diverse varianti importanti di questo comportamento.  Per motivi di prestazioni, se un processo viene completato prima che sia atteso, il controllo non viene prodotto e la funzione prosegue nell'esecuzione.  Non è inoltre sempre desiderabile tornare al contesto originale e questo comportamento può essere modificato. La sezione seguente descrive questa situazione nei dettagli.  
  
### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Configurazione della sospensione e della ripresa con Yield e ConfigureAwait  
 Esistono diversi metodi che forniscono maggiore controllo sull'esecuzione di un metodo asincrono. Ad esempio, è possibile utilizzare il <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> metodo introdurre un punto nel metodo asincrono:  
  
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
  
 È inoltre possibile utilizzare il <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> metodo per un controllo migliore sul sospensione e ripresa di un metodo asincrono.  Come accennato in precedenza, per impostazione predefinita il contesto corrente viene acquisito nel momento in cui un metodo asincrono viene sospeso e questo contesto acquisito viene utilizzato per richiamare la continuazione del metodo asincrono al momento della ripresa.  In molti casi questo è il comportamento desiderato.  In altri casi non è necessario preoccuparsi del contesto di continuazione ed è possibile ottenere migliori prestazioni evitando tali postback al contesto originale.  A tale scopo, utilizzare il <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> metodo per informare l'operazione await non per acquisire e ripristinare il contesto, ma per continuare l'esecuzione ogni volta che l'operazione asincrona in attesa completata:  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
```  
  
## <a name="canceling-an-asynchronous-operation"></a>Annullamento di un'operazione asincrona  
 A partire dal [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], toccare i metodi che supportano l'annullamento forniscono almeno uno degli overload che accetta un token di annullamento (<xref:System.Threading.CancellationToken> oggetto).  
  
 Viene creato un token di annullamento tramite l'origine di un token di annullamento (<xref:System.Threading.CancellationTokenSource> oggetto).  L'origine <xref:System.Threading.CancellationTokenSource.Token%2A> proprietà restituisce il token di annullamento che verrà segnalato quando l'origine <xref:System.Threading.CancellationTokenSource.Cancel%2A> metodo viene chiamato.  Ad esempio, se si desidera scaricare un'unica pagina Web e si desidera essere in grado di annullare l'operazione, si crea un <xref:System.Threading.CancellationTokenSource> dell'oggetto, passare il token per il metodo TAP e quindi chiamare l'origine <xref:System.Threading.CancellationTokenSource.Cancel%2A> metodo quando si è pronti per annullare l'operazione:  
  
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
  
 È possibile passare il <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> valore a qualsiasi metodo che accetta un token di annullamento per indicare che non verrà mai essere richiesto l'annullamento.  In questo modo il <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> proprietà da restituire `false`, e il metodo chiamato è possibile ottimizzare di conseguenza.  È possibile, a scopo di test, passare un token di annullamento già annullato di cui si è creata un'istanza usando il costruttore che accetta un valore booleano per indicare se il token deve essere avviato in uno stato already-canceled (già cancellato) o not-cancelable (non cancellabile).  
  
 Questo approccio all'annullamento presenta diversi vantaggi:  
  
-   È possibile passare lo stesso token di annullamento a un numero qualsiasi di operazioni asincrone e sincrone.  
  
-   La stessa richiesta di annullamento può essere estesa a un numero qualsiasi di listener.  
  
-   Lo sviluppatore dell'API asincrona ha il controllo totale sull'eventuale richiesta di annullamento e sull'eventuale esecuzione.  
  
-   Il codice che usa l'API può determinare in modo selettivo a quali chiamate asincrone verranno propagate le richieste di annullamento.  
  
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
 Il <xref:System.Threading.Tasks> spazio dei nomi include diversi metodi per la scrittura e l'utilizzo delle attività.  
  
### <a name="taskrun"></a>Task.Run  
 Il <xref:System.Threading.Tasks.Task> classe include diversi <xref:System.Threading.Tasks.Task.Run%2A> metodi che consentono facilmente di ripartire il lavoro come un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> al pool di thread, ad esempio:  
  
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
  
 Alcune di queste <xref:System.Threading.Tasks.Task.Run%2A> metodi, ad esempio il <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> di overload, esiste come sintassi abbreviata per il <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> (metodo).  Altri overload, ad esempio <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, attiva, è possibile utilizzare await all'interno di lavoro scaricato, ad esempio:  
  
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
  
 Tali overload sono logicamente equivale all'utilizzo di <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> metodo in combinazione con il <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> il metodo di estensione in Task Parallel Library.  
  
### <a name="taskfromresult"></a>Task.FromResult  
 Utilizzare il <xref:System.Threading.Tasks.Task.FromResult%2A> deve essere restituito da un metodo che restituisce task nei metodo negli scenari in cui dati potrebbero essere già disponibile e solo un <xref:System.Threading.Tasks.Task%601>:  
  
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
 Utilizzare il <xref:System.Threading.Tasks.Task.WhenAll%2A> metodo per attendere in modo asincrono in più operazioni asincrone che vengono rappresentate come attività.  Il metodo dispone di più overload che supportano un set di attività non generiche o un set non uniforme di attività generiche (ad esempio attendere in modo asincrono più operazioni che restituiscono void, o attendere in modo asincrono più metodi che restituiscono dei valori, dove ogni valore può essere di tipo diverso) e supportano un set uniforme di attività generiche (ad esempio attendere in modo asincrono più metodi che restituiscono `TResult`).  
  
 Si supponga di voler inviare messaggi di posta elettronica a numerosi clienti. È possibile sovrapporre l'invio dei messaggi in modo da non dover attendere che un messaggio termini prima di inviare il successivo. È inoltre possibile scoprire quando le operazioni di invio sono state completate e se si sono verificati degli errori:  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
```  
  
 Questo codice in modo esplicito non gestisce le eccezioni che possono verificarsi, ma consente di propagazione delle eccezioni di `await` nell'attività risultante da <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Per gestire le eccezioni, è possibile usare codice simile al seguente:  
  
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
  
 In questo caso, qualsiasi operazione asincrona ha esito negativo, tutte le eccezioni verranno consolidate un <xref:System.AggregateException> eccezione, che viene archiviato nel <xref:System.Threading.Tasks.Task> restituito dal <xref:System.Threading.Tasks.Task.WhenAll%2A> metodo.  Solo una di queste eccezioni viene tuttavia propagata dalla parola chiave `await`.  Se si desidera esaminare tutte le eccezioni, è possibile riscrivere il codice precedente come segue:  
  
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
 È possibile utilizzare il <xref:System.Threading.Tasks.Task.WhenAny%2A> metodo per attendere in modo asincrono da uno dei più operazioni asincrone rappresentato come attività da completare.  Questo metodo viene usato principalmente in quattro casi:  
  
-   Ridondanza: esecuzione ripetuta di un'operazione e selezione di quella che viene terminata per prima (ad esempio contatto di più servizi Web di quotazioni di borsa tramite cui verrà generato un solo risultato e selezione di quello che viene completato più velocemente).  
  
-   Interfoliazione: avvio di più operazioni e attesa del completamento di tutte, ma elaborazione al termine delle operazioni in questione.  
  
-   Limitazione: consentire l'avvio di operazioni aggiuntive al completamento delle altre.  Questa è un'estensione dello scenario di interfoliazione.  
  
-   Bailout iniziale: ad esempio, un'operazione rappresentata dall'attività t1 può essere raggruppata in un'attività <xref:System.Threading.Tasks.Task.WhenAny%2A> con un'altra attività t2 ed è possibile attendere l'attività <xref:System.Threading.Tasks.Task.WhenAny%2A>. Attività t2 può rappresentare un timeout, o di annullamento o di alcuni altri segnale che causa il <xref:System.Threading.Tasks.Task.WhenAny%2A> attività da completare prima che venga completata t1.  
  
#### <a name="redundancy"></a>Ridondanza  
 Si consideri il caso in cui si desidera decidere se comprare o meno dei titoli.  Esistono numerosi servizi Web attendibili che consigliano su azioni, ma a seconda del traffico giornaliero, ogni servizio può risultare lento in determinati momenti.  È possibile utilizzare il <xref:System.Threading.Tasks.Task.WhenAny%2A> per ricevere una notifica al completamento di qualsiasi operazione:  
  
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
  
 A differenza di <xref:System.Threading.Tasks.Task.WhenAll%2A>, che restituisce i risultati annullato il wrapping di tutte le attività che è stata completata correttamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> restituisce l'attività completata. Se un'attività ha esito negativo, è importante sottolineare che ha avuto esito negativo e se l'attività ha esito positivo, è importante sapere a quale attività è associato il valore restituito.  Pertanto, è necessario accedere al risultato dell'attività restituita o attenderlo ulteriormente, come mostrato nell'esempio riportato di seguito.  
  
 Come con <xref:System.Threading.Tasks.Task.WhenAll%2A>, è necessario essere in grado di gestire eccezioni.  Poiché l'attività terminata viene restituita, è possibile attendere l'attività restituita per propagare gli errori ed eseguire `try/catch` in modo appropriato, ad esempio:  
  
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
  
```  
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
  
 È inoltre possibile applicare interfoliazione a uno scenario che prevede l'elaborazione complesse nel <xref:System.Threading.ThreadPool> delle immagini scaricate, ad esempio:  
  
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
  
 Comporta l'utilizzo di un altro esempio di bailout iniziale di <xref:System.Threading.Tasks.Task.WhenAny%2A> metodo in combinazione con il <xref:System.Threading.Tasks.Task.Delay%2A> (metodo), come descritto nella sezione successiva.  
  
### <a name="taskdelay"></a>Task.Delay  
 È possibile utilizzare il <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> metodo introdurre sospende le attività in esecuzione asincrona del metodo.  Ciò è utile per molti tipi di funzionalità, incluse la compilazione dei cicli di polling e il posticipo della gestione di input utente per un periodo di tempo predeterminato.  Il <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> metodo può anche essere utile in combinazione con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> per l'implementazione di timeout su resta in attesa.  
  
 Se un'attività che fa parte di una operazione asincrona più ampia, ad esempio un servizio web ASP.NET, impiega troppo tempo per terminare, potrebbe soffrirne l'operazione globale, specialmente se non termina mai.  Per questo motivo, è importante poter introdurre un timeout quando si è in attesa di un'operazione asincrona.  Sincroni <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, e <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> metodi accettano valori di timeout, ma le corrispondenti <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> e indicati in precedenza <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>non metodi.  In alternativa, è possibile utilizzare <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combinazione per implementare un timeout.  
  
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
  
 Lo stesso vale per il download di più, perché <xref:System.Threading.Tasks.Task.WhenAll%2A> restituisce un'attività:  
  
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
 È un potenziale problema di prestazioni con il <xref:System.Threading.Tasks.Task.WhenAny%2A> metodo per supportare uno scenario di intervalli di interfoliazione quando si lavora con grandi set di attività.  Ogni chiamata a <xref:System.Threading.Tasks.Task.WhenAny%2A> comporta una continuazione che viene registrata con ogni attività. Per un numero N di attività, questo comporta O(N2) continuazioni create durante l'operazione di interfoliazione.  Se si utilizza un ampio set di attività, è possibile utilizzare un operatore combinatorio (nell'esempio seguente `Interleaved`) per risolvere il problema di prestazioni:  
  
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
 Oltre alla capacità di compilazione personalizzate combinatori basato su attività, la presenza di una struttura di dati in <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> che rappresenta sia i risultati di un'operazione asincrona e la sincronizzazione necessaria per creare un join con esso rende molto potenti tipo su cui fondare le strutture di dati personalizzati da utilizzare negli scenari asincroni.  
  
### <a name="asynccache"></a>AsyncCache  
 Un aspetto importante di un'attività è quello che si può passare a più consumer, ciascuno dei quali può attendere, le continuazioni di registro, ottenere il risultato o eccezioni (nel caso di <xref:System.Threading.Tasks.Task%601>) e così via.  In questo modo <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> ideale da utilizzare in un'infrastruttura di memorizzazione nella cache asincrona.  Di seguito è riportato un esempio di una piccola ma potente cache asincrona creato in cima <xref:System.Threading.Tasks.Task%601>:  
  
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
  
 Il [AsyncCache\<TKey, TValue >](http://go.microsoft.com/fwlink/p/?LinkId=251941) classe accetta un delegato per il relativo costruttore di una funzione che accetta un `TKey` e restituisce un <xref:System.Threading.Tasks.Task%601>.  Tutti i valori della cache a cui si è acceduto precedentemente vengono archiviati nel dizionario interno e `AsyncCache` fa in modo che venga generata solo un'attività per chiave, anche si accede alla cache contemporaneamente.  
  
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
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
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
  
 Il <xref:System.Threading.Tasks.Dataflow> spazio dei nomi include il <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> tipo, è possibile utilizzare in modo simile, ma senza la necessità di creare un tipo di raccolta personalizzato:  
  
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
>  Il <xref:System.Threading.Tasks.Dataflow> è disponibile in spazio dei nomi di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] tramite **NuGet**. Per installare l'assembly che contiene il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il pacchetto di DataFlow.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello asincrono basato su attività (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 [Implementazione del modello asincrono basato su attività](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [Interoperabilità con altri tipi e modelli asincroni](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
