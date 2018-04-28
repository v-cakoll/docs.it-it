---
title: 'Programmazione asincrona in F #'
description: 'Informazioni su come la programmazione asincrona F # viene eseguita tramite un modello di programmazione a livello di linguaggio che è facile da usare e il linguaggio naturale.'
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a3047b98637cb4b142f374a2a2b5e7270e850fd6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="async-programming-in-f"></a>Programmazione asincrona in F # #

> [!NOTE]
> Alcune imprecisioni sono stati individuati in questo articolo.  Da riscrivere.  Vedere [problema #666](https://github.com/dotnet/docs/issues/666) per informazioni sulle modifiche.

Programmazione F # può essere eseguita tramite un modello di programmazione a livello di linguaggio progettato per essere facile da usare e il linguaggio naturale.

La base della programmazione asincrona in F # è `Async<'T>`, una rappresentazione di lavoro che può essere attivata per l'esecuzione in background, in cui `'T` è il tipo restituito tramite speciale `return` (parola chiave) o `unit` se non include il flusso di lavoro asincroni risultato da restituire.

Il concetto chiave per comprendere è che il tipo dell'espressione async `Async<'T>`, che è semplicemente un _specifica_ di lavoro da eseguire in un contesto asincrono. Non viene eseguita finché non viene esplicitamente avviata con una delle funzioni iniziale (ad esempio `Async.RunSynchronously`). Si tratta di un modo diverso pensare di eseguire il lavoro, alla fine viene piuttosto semplice in pratica.

Ad esempio, che si desidera scaricare il codice HTML da dotnetfoundation.org senza bloccare il thread principale. È possibile ottenere questo risultato simile al seguente:

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

E questo è sufficiente. A parte l'utilizzo di `async`, `let!`, e `return`, si tratta solo normale codice F #.

Esistono alcuni costrutti sintattici che vale la pena notare:

*   `let!` Associa il risultato di un'espressione async (che viene eseguito in un altro contesto).
*   `use!` funziona come `let!`, ma elimina le risorse associate, quando esce dall'ambito.
*   `do!` attende un flusso di lavoro asincrono non restituisce alcun valore.
*   `return` Restituisce semplicemente un risultato da un'espressione di tipo asincrono.
*   `return!` esegue un altro flusso di lavoro asincrono e restituisce il valore restituito come risultato.

Inoltre, normale `let`, `use`, e `do` parole chiave possono essere utilizzate con le versioni asincrone come se fossero in una funzione normale.

## <a name="how-to-start-async-code-in-f"></a>Come avviare codice asincrono in F # #

Come accennato in precedenza, il codice asincrono è una specifica di lavoro da eseguire in un altro contesto che deve essere avviata in modo esplicito. Di seguito sono due modi principali per ottenere questo risultato:

1.  `Async.RunSynchronously` Avvia un flusso di lavoro asincrono in un altro thread e attendere il risultato.

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  `Async.Start` avviare un flusso di lavoro asincrono in un altro thread e verrà **non** attende il relativo risultato.

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

Esistono altri modi per avviare un flusso di lavoro asincroni disponibile per gli scenari più specifici. Sono descritti in dettaglio [negli argomenti di riferimento Async](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Nota sulla thread

La frase "in un altro thread" è indicata in precedenza, ma è importante sapere che **ciò non significa che i flussi di lavoro asincroni sono facciata per il multithreading**. Il flusso di lavoro effettivamente "passa" tra thread, richiesta di finanziamenti per una piccola quantità di tempo per eseguire operazioni utili. Quando un flusso di lavoro asincrono è in modo efficace "in attesa" (ad esempio, in attesa di una chiamata di rete restituire un valore), qualsiasi thread che è stata richiesta di finanziamenti al momento viene liberata fino a passare eseguire operazioni utili in un altro elemento. Questo consente di flussi di lavoro asincroni utilizzare il sistema in cui in che vengono eseguiti nel modo e li rende particolarmente efficaci per gli scenari dei / o di volumi elevati.

## <a name="how-to-add-parallelism-to-async-code"></a>Come aggiungere codice asincrono di parallelismo

In alcuni casi può necessario per eseguire più processi asincroni in parallelo, raccogliere i risultati e interpretati in qualche modo. `Async.Parallel` Consente di eseguire queste operazioni senza dover usare Task Parallel Library, che comporta la necessità di forzare `Task<'T>` e `Async<'T>` tipi.

Nell'esempio seguente utilizzerà `Async.Parallel` per scaricare il codice HTML da quattro parti comuni in parallelo, attendere il completamento di tali attività e quindi stampare il codice HTML che è stato scaricato.

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a>Consigli e informazioni importanti

*   Aggiungere "Async" alla fine di qualsiasi funzione che è possibile utilizzare

 Si tratta di una convenzione di denominazione, semplificare le operazioni come il rilevamento di API. In particolare se sono presenti versioni sincrone e asincrone della stessa routine, è consigliabile indicare esplicitamente che è asincrono tramite il nome.

*   Restare in attesa il compilatore!

 Il compilatore F # è molto rigido, rendendo quasi impossibile eseguire un'operazione troubling come eseguire il codice "async" in modo sincrono. Se si individua un avviso, che è un segno che il codice non verrà eseguito come si ritiene che verranno eseguite. Se il compilatore può rendere soddisfatti, l'esecuzione del codice probabilmente come previsto.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Per i programmatori c# /VB C in F # #

In questa sezione presuppone che si abbia familiarità con il modello asincrono in c# o VB. Se il non computer [di programmazione asincrona in c#](../../../csharp/async.md) è un punto di partenza.

È presente una differenza fondamentale tra il modello asincrono di c# /VB C e il modello asincrono di F #.

Quando si chiama una funzione che restituisce un `Task` o `Task<'T>`, tale processo ha già iniziato l'esecuzione. L'handle restituito rappresenta un processo asincrono già in esecuzione. Al contrario, quando si chiama una funzione async in F #, di `Async<'a>` restituito rappresenta un processo che sarà **generato** a un certo punto. La comprensione di questo modello è potente, perché consente infatti di processi asincroni in F # per concatenare più semplice, eseguita in modo condizionale e avviare con una granularità più preciso del controllo.

Esistono alcuni altri analogie e differenze non degni di nota.

### <a name="similarities"></a>Analogie

*   `let!`, `use!`, e `do!` sono analoghi alle `await` durante la chiamata dall'interno di un processo asincrono un `async{ }` blocco.

 Tre parole chiave possono essere utilizzate solo all'interno di un `async { }` blocco, analoga a quanto `await` può essere richiamato solo all'interno di un `async` metodo. In breve, `let!` viene utilizzata quando si desidera acquisire e utilizzare un risultato, `use!` è lo stesso, ma per un elemento il cui risorse devono ottenere eliminate dopo essere stato utilizzato, e `do!` viene utilizzata quando si desidera attendere per un flusso di lavoro asincrono senza valore restituito di fine prima di proseguire.

*   F # supporta il parallelismo dei dati in modo analogo.

 Anche se opera in modo molto diverso, `Async.Parallel` corrisponde a `Task.WhenAll` per lo scenario di che i risultati di un set di processi asincroni quando vengono completate.

### <a name="differences"></a>Differenze

*   Annidati `let!` non è consentito, a differenza di annidati `await`

 A differenza di `await`, che può essere nidificata in modo indefinito, `let!` non può e deve avere il relativo risultato associato prima di utilizzarlo all'interno di un altro `let!`, `do!`, o `use!`.

*   Supporto per l'annullamento è più semplice in F # rispetto a in c# o VB.

 Il supporto di annullamento di una metà di attività tramite l'esecuzione in C# /VB richiede il controllo di `IsCancellationRequested` proprietà o chiamare il metodo `ThrowIfCancellationRequested()` su un `CancellationToken` oggetto passato al metodo asincrono.

Al contrario, F # asincrono flussi di lavoro sono con maggiore naturalezza annullabile. Annullamento è un semplice processo in tre fasi.

1.  Creare un nuovo oggetto `CancellationTokenSource`.
2.  Passare a una funzione di avvio.
3.  Chiamare `Cancel` sul token.

Esempio:

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

E questo è sufficiente.

## <a name="further-resources"></a>Ulteriori risorse:

*   [Flussi di lavoro asincrono su MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
*   [Sequenze asincrone per F #](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [Utilità di F # dati HTTP](https://fsharp.github.io/FSharp.Data/library/Http.html)
