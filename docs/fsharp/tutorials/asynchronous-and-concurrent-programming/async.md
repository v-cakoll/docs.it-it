---
title: Il linguaggio di programmazione asincronaF#
description: Informazioni su come F# programmazione asincrona viene eseguita tramite un modello di programmazione a livello di linguaggio naturale per la lingua e facile da usare.
ms.date: 06/20/2016
ms.openlocfilehash: de07f1252df56e3dfec5ea7a34a283b1c9508523
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "50195060"
---
# <a name="async-programming-in-f"></a>Il linguaggio di programmazione asincronaF# #

> [!NOTE]
> Alcune imprecisioni sono stati individuati in questo articolo.  Si viene riscritta.  Visualizzare [problema & 666](https://github.com/dotnet/docs/issues/666) per informazioni sulle modifiche.

Async programming in F# può essere eseguita tramite un modello di programmazione a livello di linguaggio progettato per essere facile da usare e il linguaggio naturale.

Il nucleo della programmazione F# viene `Async<'T>`, una rappresentazione di lavoro che può essere attivato per l'esecuzione in background, in cui `'T` è il tipo restituito tramite la speciale `return` (parola chiave) o `unit` se il flusso di lavoro asincroni non produce alcun risultato da restituire.

Il concetto chiave da comprendere è che il tipo dell'espressione async è `Async<'T>`, che è semplicemente un _specification_ del lavoro da eseguire in un contesto asincrono. Non viene eseguita fino a quando non è esplicitamente avviarlo con una delle funzioni iniziale (ad esempio `Async.RunSynchronously`). Anche se si tratta di pensare a lavorare in modo diverso, finisce per essere piuttosto semplice in pratica.

Ad esempio che si vuole scaricare il codice HTML da dotnetfoundation.org senza bloccare il thread principale. È possibile ottenere questo risultato simile al seguente:

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

E questo è sufficiente. A parte l'utilizzo di `async`, `let!`, e `return`, questo è solo normale F# codice.

Esistono alcuni costrutti sintattici che vale la pena notare:

*   `let!` Associa il risultato di un'espressione di async (che viene eseguito in un altro contesto).
*   `use!` funziona come `let!`, ma elimina le risorse associate quando esce dall'ambito.
*   `do!` attende un flusso di lavoro asincrono non restituisce alcun valore.
*   `return` Restituisce semplicemente un risultato da un'espressione di async.
*   `return!` esegue un altro flusso di lavoro asincrono e restituisce il relativo valore restituito come risultato.

Inoltre, normal `let`, `use`, e `do` parole chiave possono essere usate insieme le versioni asincrone esattamente come accade in una funzione normale.

## <a name="how-to-start-async-code-in-f"></a>Come avviare il codice asincrono inF# #

Come accennato in precedenza, il codice asincrono è una specifica di lavoro da eseguire in un altro contesto che deve essere avviata in modo esplicito. Di seguito sono due modi principali per eseguire questa operazione:

1.  `Async.RunSynchronously` Avvia un flusso di lavoro asincrono in un altro thread e attende il relativo risultato.

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

Esistono altri modi per avviare un flusso di lavoro asincroni disponibile per gli scenari più specifici. Sono descritti in dettaglio [nel riferimento Async](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Nota sulla thread

La frase "in un altro thread" è indicato in precedenza, ma è importante sapere che **ciò non significa che i flussi di lavoro asincroni sono un'interfaccia per il multithreading**. Il flusso di lavoro effettivamente "passa" tra i thread, richiesta di finanziamenti per una piccola quantità di tempo per eseguire operazioni utili. Quando un flusso di lavoro asincrono è effettivamente "in attesa" (ad esempio, in attesa di una chiamata di rete restituire un valore), uno o più thread che è stata richiesta di finanziamenti al momento viene liberata fino a passare eseguire operazioni utili per qualcos'altro. Ciò consente asincrona dei flussi di lavoro usano il sistema che vengono eseguiti nel modo e li rende particolarmente efficaci per gli scenari dei / o di volumi elevati.

## <a name="how-to-add-parallelism-to-async-code"></a>Come aggiungere il parallelismo a codice asincrono

In alcuni casi potrebbe necessarie per eseguire più operazioni asincrone in parallelo, raccogliere i risultati e interpretarli in qualche modo. `Async.Parallel` Consente di eseguire questa operazione senza dover usare Task Parallel Library, che comporta la necessità di soggetti a coercizione `Task<'T>` e `Async<'T>` tipi.

Nell'esempio seguente userà `Async.Parallel` per scaricare il codice HTML da quattro parti più diffusi in parallelo, attendere il completamento di tali attività e quindi stampa l'HTML che è stato scaricato.

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

*   Aggiungere "Async" alla fine di qualsiasi funzione che verrà utilizzi

 Anche se si tratta di una convenzione di denominazione, rende le cose, ad esempio l'individuazione di API più semplice. In particolare se sono presenti versioni sincrone e asincrone della routine stessa, è consigliabile dichiarare in modo esplicito che è asincrono tramite il nome.

*   Ascolto al compilatore.

 F#del compilatore è molto precise, rendendo quasi Impossibile operare preoccupante, ad esempio eseguire codice di "async" in modo sincrono. Se si riscontra un avviso, che è un segno più che il codice non verrà eseguito come pensi che si verifica. Se il compilatore può rendere felici, il codice molto probabilmente verrà eseguito come previsto.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Per il C#programmatore /VB analizzandoF# #

In questa sezione presuppone si abbia familiarità con il modello async in C#/VB. Se non sei [programmazione asincrona in C# ](../../../csharp/async.md) è un punto di partenza.

È presente una differenza fondamentale tra il C#modello asincrono /VB e il F# modello asincrono.

Quando si chiama una funzione che restituisce un `Task` o `Task<'T>`, tale processo ha già iniziato l'esecuzione. L'handle restituito rappresenta un processo asincrono già in esecuzione. Al contrario, quando si chiama una funzione asincrona F#, il `Async<'a>` restituito rappresenta un processo che sarà **generato** a un certo punto. Comprendere questo modello è potente, perché consente processi asincroni in F# di essere concatenate più semplice, eseguita in modo condizionale ed essere avviata con un livello di dettaglio più preciso del controllo.

Esistono alcuni altri analogie e differenze da notare.

### <a name="similarities"></a>Analogie

*   `let!`, `use!`, e `do!` sono analoghe alle `await` quando si chiama un processo asincrono dall'interno una `async{ }` blocco.

 Le tre parole chiave possono essere usate solo all'interno di un' `async { }` blocco, analoga a quanto `await` può essere richiamata solo all'interno di un `async` (metodo). In breve, `let!` viene utilizzata quando si vuole acquisire e usare un risultato `use!` è lo stesso, ma per un elemento le cui risorse devono ottenere pulite dopo l'uso, e `do!` viene utilizzata quando si vuole attendere per un flusso di lavoro asincrono senza valore restituito alla fine prima di procedere.

*   F#supporta il parallelismo dei dati in modo analogo.

 Anche se funziona in modo molto diverso `Async.Parallel` corrisponde a `Task.WhenAll` per lo scenario seguendo i risultati di una serie di processi asincroni quando vengono tutte completate.

### <a name="differences"></a>Differenze

*   Annidati `let!` non è consentita, a differenza di annidati `await`

 A differenza `await`, che possono essere annidati a tempo indeterminato `let!` non può e deve avere il relativo risultato associato prima di utilizzarlo in un'altra `let!`, `do!`, o `use!`.

*   Supporto dell'annullamento è più semplice in F# rispetto a C#/VB.

 Che supportano l'annullamento di una metà di attività tramite l'esecuzione in C#/VB richiede il controllo di `IsCancellationRequested` proprietà o chiamare il metodo `ThrowIfCancellationRequested()` su un `CancellationToken` oggetto passato nel metodo asincrono.

Al contrario, F# flussi di lavoro asincroni sono più naturalmente annullabile. L'annullamento è un semplice processo in tre fasi.

1.  Creare un nuovo oggetto `CancellationTokenSource`.
2.  Passare alla funzione in una funzione di partenza.
3.  Chiamare `Cancel` sul token.

Esempio:

```fsharp
open System
open System.Net
open System.Threading

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token.Token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

E questo è sufficiente.

## <a name="further-resources"></a>Altre risorse:

*   [Flussi di lavoro asincroni su MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
*   [Sequenze asincrone perF#](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [F#Utilità dei dati HTTP](https://fsharp.github.io/FSharp.Data/library/Http.html)
