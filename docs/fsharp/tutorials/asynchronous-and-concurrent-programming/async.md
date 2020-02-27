---
title: Programmazione asincrona
description: Informazioni su F# come fornisce un supporto pulito per modalità asincrona basato su un modello di programmazione a livello di linguaggio derivato dai concetti di base della programmazione funzionale.
ms.date: 12/17/2018
ms.openlocfilehash: 7021d7936d10f9ea6fceb4aa56db3285d21624ad
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628852"
---
# <a name="async-programming-in-f"></a>Programmazione asincrona in F\#

La programmazione asincrona è un meccanismo essenziale per le applicazioni moderne per diversi motivi. Ci sono due casi d'uso principali che la maggior parte degli sviluppatori incontrerà:

- Presentazione di un processo server che può soddisfare un numero significativo di richieste in ingresso simultanee, riducendo al minimo le risorse di sistema occupate durante l'elaborazione delle richieste in attesa di input da sistemi o servizi esterni a tale processo
- Gestione di un'interfaccia utente reattiva o di un thread principale durante l'avanzamento simultaneo del lavoro in background

Sebbene il lavoro in background comporti spesso l'utilizzo di più thread, è importante prendere in considerazione i concetti di modalità asincrona e multithread separatamente. In realtà, si tratta di problemi distinti e uno non implica l'altro. Questo articolo descrive in modo più dettagliato questo aspetto.

## <a name="asynchrony-defined"></a>Modalità asincrona definito

Il punto precedente, che modalità asincrona è indipendente dall'utilizzo di più thread, vale la pena spiegare ulteriormente un po'. Esistono tre concetti a volte correlati, ma strettamente indipendenti tra loro:

- Concorrenza Quando più calcoli vengono eseguiti in periodi di tempo sovrapposti.
- Parallelismo Quando più calcoli o varie parti di un singolo calcolo vengono eseguiti esattamente allo stesso tempo.
- Modalità asincrona Quando uno o più calcoli possono essere eseguiti separatamente dal flusso principale del programma.

Tutti e tre sono concetti ortogonali, ma possono essere facilmente configurati, soprattutto quando vengono usati insieme. Ad esempio, potrebbe essere necessario eseguire più calcoli asincroni in parallelo. Questo non significa che il parallelismo o modalità asincrona ne implicano l'altro.

Se si considera l'etimologia della parola "Asynchronous", sono necessarie due parti:

- "a", che significa "not".
- "sincrono", che significa "allo stesso tempo".

Quando si impostano questi due termini, si noterà che "Asynchronous" significa "not allo stesso tempo". L'operazione è terminata. In questa definizione non esiste alcuna implicazione della concorrenza o del parallelismo. Questo vale anche per la pratica.

In termini pratici, i calcoli asincroni in F# sono pianificati per l'esecuzione indipendentemente dal flusso di programma principale. Questo non implica la concorrenza o il parallelismo, né implica che un calcolo avvenga sempre in background. Infatti, i calcoli asincroni possono anche essere eseguiti in modo sincrono, a seconda della natura del calcolo e dell'ambiente in cui è in esecuzione il calcolo.

Il principale vantaggio è che i calcoli asincroni sono indipendenti dal flusso di programma principale. Sebbene ci siano poche garanzie su quando o come viene eseguito un calcolo asincrono, esistono alcuni approcci per orchestrarli e pianificarli. Nella parte restante di questo articolo vengono esaminati F# i concetti di base per modalità asincrona e viene illustrato come utilizzare i tipi, F#le funzioni e le espressioni incorporati in.

## <a name="core-concepts"></a>Concetti principali

In F#la programmazione asincrona è incentrata su tre concetti fondamentali:

- Il tipo di `Async<'T>`, che rappresenta un calcolo asincrono componibile.
- Le funzioni del modulo `Async`, che consentono di pianificare il lavoro asincrono, comporre calcoli asincroni e trasformare risultati asincroni.
- Espressione di [calcolo](../../language-reference/computation-expressions.md)`async { }`, che fornisce una sintassi pratica per la compilazione e il controllo di calcoli asincroni.

È possibile vedere questi tre concetti nell'esempio seguente:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

Nell'esempio, la funzione `printTotalFileBytes` è di tipo `string -> Async<unit>`. La chiamata alla funzione non esegue effettivamente il calcolo asincrono. Viene invece restituito un `Async<unit>` che funge da *specifica* del lavoro da eseguire in modo asincrono. Chiama `Async.AwaitTask` nel corpo, che converte il risultato di <xref:System.IO.File.ReadAllBytesAsync%2A> in un tipo appropriato.

Un'altra linea importante è la chiamata a `Async.RunSynchronously`. Si tratta di una delle funzioni di avvio del modulo asincrono che è necessario chiamare se si desidera eseguire effettivamente un F# calcolo asincrono.

Si tratta di una differenza fondamentale con C#lo stile di base di/Visual della programmazione `async`. In F#i calcoli asincroni possono essere considerati **attività a freddo**. Devono essere avviate in modo esplicito per eseguire effettivamente. Questo offre alcuni vantaggi, in quanto consente di combinare e sequenziare il lavoro asincrono molto più facilmente rispetto C# a o Visual Basic.

## <a name="combine-asynchronous-computations"></a>Combinare calcoli asincroni

Di seguito è riportato un esempio che si basa su quello precedente combinando i calcoli:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

Come si può notare, la funzione `main` dispone di molte altre chiamate effettuate. A livello concettuale, esegue le operazioni seguenti:

1. Trasformare gli argomenti della riga di comando in `Async<unit>` calcoli con `Array.map`.
2. Creare un `Async<'T[]>` per pianificare ed eseguire i calcoli di `printTotalFileBytes` in parallelo durante l'esecuzione.
3. Creare un `Async<unit>` che eseguirà il calcolo parallelo e ne ignorerà il risultato.
4. Eseguire in modo esplicito l'ultimo calcolo con `Async.RunSynchronously` e bloccarlo finché non viene completato.

Quando il programma viene eseguito, `printTotalFileBytes` viene eseguito in parallelo per ogni argomento della riga di comando. Poiché i calcoli asincroni vengono eseguiti indipendentemente dal flusso di programma, non è presente alcun ordine in cui stampano le informazioni e terminano l'esecuzione. I calcoli verranno pianificati in parallelo, ma l'ordine di esecuzione non è garantito.

## <a name="sequence-asynchronous-computations"></a>Sequenza di calcoli asincroni

Poiché `Async<'T>` è una specifica di lavoro anziché un'attività già in esecuzione, è possibile eseguire facilmente trasformazioni più complesse. Di seguito è riportato un esempio che consente di sequenziare un set di calcoli asincroni in modo che vengano eseguiti uno dopo l'altro.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

In questo modo si pianifica `printTotalFileBytes` eseguire nell'ordine degli elementi di `argv` anziché pianificarli in parallelo. Poiché l'elemento successivo non verrà pianificato fino al termine dell'esecuzione dell'ultimo calcolo, i calcoli vengono sequenziati in modo che non si verifichi alcuna sovrapposizione nell'esecuzione.

## <a name="important-async-module-functions"></a>Funzioni del modulo Async importanti

Quando si scrive codice asincrono in F# , in genere si interagisce con un Framework che gestisce la pianificazione dei calcoli. Tuttavia, questo non è sempre il caso, quindi è consigliabile apprendere le varie funzioni di avvio per pianificare il lavoro asincrono.

Poiché F# i calcoli asincroni sono una _specifica_ di lavoro anziché una rappresentazione di un lavoro già in esecuzione, è necessario avviarli in modo esplicito con una funzione iniziale. Sono disponibili molte [funzioni di avvio asincrone](https://msdn.microsoft.com/library/ee370232.aspx) che risultano utili in contesti diversi. Nella sezione seguente vengono descritte alcune delle funzioni di avvio più comuni.

### <a name="asyncstartchild"></a>Async. StartChild

Avvia un calcolo figlio all'interno di un calcolo asincrono. Questo consente l'esecuzione simultanea di più calcoli asincroni. Il calcolo figlio condivide un token di annullamento con il calcolo padre. Se il calcolo padre viene annullato, viene annullato anche il calcolo figlio.

Firma

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

Quando usare:

- Quando si desidera eseguire contemporaneamente più calcoli asincroni anziché uno alla volta, ma non sono stati pianificati in parallelo.
- Quando si desidera associare la durata di un calcolo figlio a quella di un calcolo padre.

Elementi da controllare:

- L'avvio di più calcoli con `Async.StartChild` non corrisponde alla pianificazione in parallelo. Se si desidera pianificare calcoli in parallelo, utilizzare `Async.Parallel`.
- L'annullamento di un calcolo padre attiverà l'annullamento di tutti i calcoli figlio avviati.

### <a name="asyncstartimmediate"></a>Async. StartImmediate

Esegue un calcolo asincrono, a partire immediatamente dal thread del sistema operativo corrente. Questa operazione è utile se è necessario aggiornare qualcosa nel thread chiamante durante il calcolo. Se, ad esempio, un calcolo asincrono deve aggiornare un'interfaccia utente, ad esempio l'aggiornamento di un indicatore di stato, è necessario usare `Async.StartImmediate`.

Firma

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Quando usare:

- Quando è necessario aggiornare qualcosa nel thread chiamante durante un calcolo asincrono.

Elementi da controllare:

- Il codice nel calcolo asincrono verrà eseguito su qualsiasi thread su cui si verifica la pianificazione. Questa operazione può risultare problematica se il thread è in qualche modo sensibile, ad esempio un thread dell'interfaccia utente. In questi casi, `Async.StartImmediate` probabilmente non è appropriato per l'utilizzo di.

### <a name="asyncstartastask"></a>Async. StartAsTask

Esegue un calcolo nel pool di thread. Restituisce un <xref:System.Threading.Tasks.Task%601> che verrà completato nello stato corrispondente al termine del calcolo (genera il risultato, genera un'eccezione o viene annullato). Se non viene fornito alcun token di annullamento, viene utilizzato il token di annullamento predefinito.

Firma

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

Quando usare:

- Quando è necessario chiamare un'API .NET che prevede un <xref:System.Threading.Tasks.Task%601> per rappresentare il risultato di un calcolo asincrono.

Elementi da controllare:

- Questa chiamata consente di allocare un oggetto `Task` aggiuntivo, che può aumentare il sovraccarico se usato spesso.

### <a name="asyncparallel"></a>Async. Parallel

Pianifica una sequenza di calcoli asincroni da eseguire in parallelo. Il grado di parallelismo può essere facoltativamente ottimizzato/limitato specificando il parametro `maxDegreesOfParallelism`.

Firma

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Quando usarlo:

- Se è necessario eseguire contemporaneamente un set di calcoli e non si ha alcuna dipendenza dall'ordine di esecuzione.
- Se non sono necessari i risultati dei calcoli pianificati in parallelo fino a quando non sono stati completati.

Elementi da controllare:

- Una volta completati tutti i calcoli, è possibile accedere alla matrice di valori risultante.
- I calcoli verranno eseguiti, ma finiranno per essere pianificati. Ciò significa che non è possibile fare affidamento sull'ordine di esecuzione.

### <a name="asyncsequential"></a>Asincrono. sequenziale

Pianifica una sequenza di calcoli asincroni da eseguire nell'ordine in cui vengono passati. Il primo calcolo verrà eseguito, quindi il successivo e così via. Nessun calcolo verrà eseguito in parallelo.

Firma

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Quando usarlo:

- Se è necessario eseguire più calcoli in ordine.

Elementi da controllare:

- Una volta completati tutti i calcoli, è possibile accedere alla matrice di valori risultante.
- I calcoli verranno eseguiti nell'ordine in cui vengono passati a questa funzione, il che può comportare una maggiore quantità di tempo prima che vengano restituiti i risultati.

### <a name="asyncawaittask"></a>Async. AwaitTask

Restituisce un calcolo asincrono che attende il completamento del <xref:System.Threading.Tasks.Task%601> specificato e ne restituisce il risultato come `Async<'T>`

Firma

```fsharp
task: Task<'T>  -> Async<'T>
```

Quando usare:

- Quando si utilizza un'API .NET che restituisce un <xref:System.Threading.Tasks.Task%601> all'interno di un F# calcolo asincrono.

Elementi da controllare:

- Le eccezioni vengono incapsulate in <xref:System.AggregateException> in base alla convenzione della Task Parallel Library ed è diverso dal F# modo in cui async genera generalmente le eccezioni.

### <a name="asynccatch"></a>Asincrono. catch

Crea un calcolo asincrono che esegue un `Async<'T>`specificato, restituendo una `Async<Choice<'T, exn>>`. Se il `Async<'T>` specificato viene completato correttamente, viene restituita una `Choice1Of2` con il valore risultante. Se viene generata un'eccezione prima che venga completata, viene restituita una `Choice2of2` con l'eccezione generata. Se viene usato in un calcolo asincrono costituito da un numero elevato di calcoli e uno di questi calcoli genera un'eccezione, il calcolo che la comprende verrà interrotto interamente.

Firma

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Quando usare:

- Quando si eseguono operazioni asincrone che possono avere esito negativo con un'eccezione e si desidera gestire tale eccezione nel chiamante.

Elementi da controllare:

- Quando si usano calcoli asincroni combinati o sequenziati, il calcolo comprendente verrà interrotto completamente se uno dei calcoli "interni" genera un'eccezione.

### <a name="asyncignore"></a>Async. ignore

Crea un calcolo asincrono che esegue il calcolo specificato e ne ignora il risultato.

Firma

```fsharp
computation: Async<'T> -> Async<unit>
```

Quando usare:

- Quando si dispone di un calcolo asincrono il cui risultato non è necessario. Questo è analogo al codice `ignore` per il codice non asincrono.

Elementi da controllare:

- Se è necessario usare questo oggetto perché si vuole usare `Async.Start` o un'altra funzione che richiede `Async<unit>`, valutare se l'eliminazione del risultato è accettabile. Non è in genere consigliabile ignorare i risultati solo per adattarli a una firma di tipo.

### <a name="asyncrunsynchronously"></a>Async. RunSynchronously

Esegue un calcolo asincrono e ne attende il risultato nel thread chiamante. Questa chiamata è in blocco.

Firma

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

Quando usarlo:

- Se necessario, usarlo una sola volta in un'applicazione, in corrispondenza del punto di ingresso di un file eseguibile.
- Quando non si è interessati alle prestazioni e si desidera eseguire contemporaneamente un set di altre operazioni asincrone.

Elementi da controllare:

- La chiamata di `Async.RunSynchronously` blocca il thread chiamante fino al completamento dell'esecuzione.

### <a name="asyncstart"></a>Async. Start

Avvia un calcolo asincrono nel pool di thread che restituisce `unit`. Non attende il risultato. I calcoli annidati avviati con `Async.Start` vengono avviati completamente indipendentemente dal calcolo padre che li ha chiamati. La loro durata non è associata ad alcun calcolo padre. Se il calcolo padre viene annullato, nessun calcolo figlio viene annullato.

Firma

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Usare solo nei casi seguenti:

- Si dispone di un calcolo asincrono che non restituisce un risultato e/o ne richiede l'elaborazione.
- Non è necessario stabilire quando un calcolo asincrono viene completato.
- Non si è interessati al thread in cui viene eseguito un calcolo asincrono.
- Non è necessario conoscere o segnalare le eccezioni derivanti dall'attività.

Elementi da controllare:

- Le eccezioni generate da calcoli avviati con `Async.Start` non vengono propagate al chiamante. Lo stack di chiamate verrà completamente rimosso.
- Qualsiasi lavoro con effetto, ad esempio la chiamata di `printfn`, avviato con `Async.Start` non provocherà l'effetto sul thread principale dell'esecuzione di un programma.

## <a name="interoperate-with-net"></a>Interoperabilità con .NET

È possibile che si stia lavorando a una libreria C# .NET o a una codebase che usa la programmazione asincrona di tipo [Async/Await](../../../standard/async.md). Poiché C# e la maggior parte delle librerie .NET utilizzano i tipi <xref:System.Threading.Tasks.Task%601> e <xref:System.Threading.Tasks.Task> come astrazioni di base anziché `Async<'T>`, è necessario superare un limite tra questi due approcci a modalità asincrona.

### <a name="how-to-work-with-net-async-and-taskt"></a>Come usare Async e `Task<T>` .NET

L'uso di librerie asincrone .NET e codebase che usano <xref:System.Threading.Tasks.Task%601>, ovvero calcoli asincroni con valori restituiti, è semplice e offre supporto incorporato con F#.

È possibile utilizzare la funzione `Async.AwaitTask` per attendere un calcolo asincrono di .NET:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

È possibile usare la funzione `Async.StartAsTask` per passare un calcolo asincrono a un chiamante .NET:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Come usare Async e `Task` .NET

Per lavorare con le API che usano <xref:System.Threading.Tasks.Task> (ovvero i calcoli asincroni .NET che non restituiscono un valore), potrebbe essere necessario aggiungere una funzione aggiuntiva che consentirà di convertire una `Async<'T>` in un <xref:System.Threading.Tasks.Task>:

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Esiste già un `Async.AwaitTask` che accetta come input una <xref:System.Threading.Tasks.Task>. Con questa e la funzione `startTaskFromAsyncUnit` definita in precedenza, è possibile avviare e attendere <xref:System.Threading.Tasks.Task> tipi da F# un calcolo asincrono.

## <a name="relationship-to-multi-threading"></a>Relazione con il multithreading

Sebbene il threading venga indicato in questo articolo, ci sono due aspetti importanti da ricordare:

1. Non esiste alcuna affinità tra un calcolo asincrono e un thread, a meno che non sia stato avviato in modo esplicito sul thread corrente.
1. La programmazione asincrona F# in non è un'astrazione per il multithreading.

Un calcolo, ad esempio, può essere effettivamente eseguito sul thread del chiamante, a seconda della natura del lavoro. Un calcolo potrebbe anche "passare" tra i thread, per consentirne il prestito per un periodo di tempo ridotto per eseguire operazioni utili tra i periodi di "attesa", ad esempio quando una chiamata di rete è in transito.

Sebbene F# fornisca alcune capacità per avviare un calcolo asincrono sul thread corrente (o non in modo esplicito nel thread corrente), modalità asincrona in genere non è associato a una particolare strategia di Threading.

## <a name="see-also"></a>Vedere anche

- [Modello F# di programmazione asincrona](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Guida asincrona di F# Jet. com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [F#Guida alla programmazione asincrona di Fun and profit](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async in C# e F#: aspetti asincroni inC#](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
