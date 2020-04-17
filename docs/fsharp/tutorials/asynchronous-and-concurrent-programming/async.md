---
title: Programmazione asincrona
description: Informazioni su come F è un supporto pulito per l'asincronia basato su un modello di programmazione a livello di linguaggio derivato dai concetti di programmazione funzionale di base.
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608036"
---
# <a name="async-programming-in-f"></a>Programmazione asincrona in FAsync programming in F\#

La programmazione asincrona è un meccanismo essenziale per le applicazioni moderne per motivi diversi. Esistono due casi d'uso principali che la maggior parte degli sviluppatori incontrerà:There are two primary use cases that most developers will encounter:

- La presentazione di un processo server in grado di soddisfare un numero significativo di richieste in ingresso simultanee, riducendo al minimo le risorse di sistema occupate durante l'elaborazione delle richieste attende gli input da sistemi o servizi esterni a tale processo
- Mantenimento di un'interfaccia utente reattiva o di un thread principale durante lo stato di avanzamento simultaneo del lavoro in background

Anche se il lavoro in background spesso comporta l'utilizzo di più thread, è importante considerare i concetti di asincronia e multithreading separatamente. In realtà, sono preoccupazioni separate, e una non implica l'altra. Ciò che segue in questo articolo descrive questo in modo più dettagliato.

## <a name="asynchrony-defined"></a>Asincronità definita

Il punto precedente - che l'asincronia è indipendente dall'utilizzo di più thread - vale la pena spiegare un po 'di più. Ci sono tre concetti che a volte sono correlati, ma strettamente indipendenti l'uno dall'altro:

- Concorrenza; quando più calcoli vengono eseguiti in periodi di tempo sovrapposti.
- Parallelismo; quando più calcoli o più parti di un singolo calcolo vengono eseguite esattamente nello stesso momento.
- Asincronia; quando uno o più calcoli possono essere eseguiti separatamente dal flusso principale del programma.

Tutti e tre sono concetti ortogonali, ma possono essere facilmente confusi, soprattutto quando vengono utilizzati insieme. Ad esempio, potrebbe essere necessario eseguire più calcoli asincroni in parallelo. Ciò non significa che il parallelismo o l'asincronia si implichino l'un l'altro.

Se si considera l'etimologia della parola "asincrono", ci sono due pezzi coinvolti:

- "a", che significa "non".
- "sincrono", che significa "allo stesso tempo".

Quando si mettono insieme questi due termini, si noterà che "asincrono" significa "non allo stesso tempo". L'operazione è terminata. Non vi è alcuna implicazione di concorrenza o parallelismo in questa definizione. Questo vale anche nella pratica.

In termini pratici, i calcoli asincroni in F , sono pianificati per l'esecuzione indipendentemente dal flusso di programma principale. Ciò non implica la concorrenza o il parallelismo, né implica che un calcolo avvenga sempre in background. Infatti, i calcoli asincroni possono anche essere eseguiti in modo sincrono, a seconda della natura del calcolo e dell'ambiente in cui è in esecuzione il calcolo.

L'asporto principale che si dovrebbe avere è che i calcoli asincroni sono indipendenti dal flusso di programma principale. Sebbene esistano poche garanzie su quando o come viene eseguito un calcolo asincrono, esistono alcuni approcci per orchestrarli e pianificarli. Nella parte restante di questo articolo vengono esaminati i concetti di base per l'asincronia di F e viene illustrato come usare i tipi, le funzioni e le espressioni incorporate in F.

## <a name="core-concepts"></a>Concetti principali

In F , la programmazione asincrona è incentrata su tre concetti di base:In F , asynchronous programming is centered around three core concepts:

- Tipo, `Async<'T>` che rappresenta un calcolo asincrono componibile.
- Le `Async` funzioni del modulo, che consentono di pianificare il lavoro asincrono, comporre calcoli asincroni e trasformare i risultati asincroni.
- L'espressione `async { }` di [calcolo](../../language-reference/computation-expressions.md), che fornisce una sintassi comoda per la compilazione e il controllo dei calcoli asincroni.

È possibile visualizzare questi tre concetti nell'esempio seguente:You can see these three concepts in the following example:

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

Nell'esempio, `printTotalFileBytes` la funzione `string -> Async<unit>`è di tipo . La chiamata alla funzione non esegue effettivamente il calcolo asincrono. Al contrario, `Async<unit>` restituisce un che funge da *specifica* del lavoro che deve essere eseguito in modo asincrono. Chiama `Async.AwaitTask` nel suo corpo, che converte il risultato di <xref:System.IO.File.ReadAllBytesAsync%2A> in un tipo appropriato.

Un'altra linea importante `Async.RunSynchronously`è la chiamata a . Si tratta di una delle funzioni di avvio del modulo asincrono che è necessario chiamare se si desidera eseguire effettivamente un calcolo asincrono F .

Si tratta di una differenza fondamentale con `async` lo stile di programmazione di C/Visual Basic. In F , i calcoli asincroni possono essere considerati come **attività Cold**. Devono essere avviati in modo esplicito per l'esecuzione effettiva. Questo ha alcuni vantaggi, in quanto consente di combinare e sequenza lavoro asincrono molto più facilmente rispetto a C .

## <a name="combine-asynchronous-computations"></a>Combinare i calcoli asincroniCombine asynchronous computations

Ecco un esempio che si basa su quello precedente combinando i calcoli:

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

Come si può `main` vedere, la funzione ha un bel paio di altre chiamate effettuate. Concettualmente, esegue le operazioni seguenti:Conceptually, it does the following:

1. Trasformare gli argomenti della `Async<unit>` riga `Array.map`di comando in calcoli con .
2. Creare `Async<'T[]>` un che pianifica `printTotalFileBytes` ed esegue i calcoli in parallelo durante l'esecuzione.
3. Creare `Async<unit>` un oggetto che eseguirà il calcolo parallelo e ne ignorerà il risultato.
4. Eseguire in modo `Async.RunSynchronously` esplicito l'ultimo calcolo con e bloccare fino al completamento.

Quando questo programma `printTotalFileBytes` viene eseguito, viene eseguito in parallelo per ogni argomento della riga di comando. Poiché i calcoli asincroni vengono eseguiti indipendentemente dal flusso del programma, non esiste alcun ordine in cui stampano le informazioni e completano l'esecuzione. I calcoli verranno pianificati in parallelo, ma l'ordine di esecuzione non è garantito.

## <a name="sequence-asynchronous-computations"></a>Calcoli asincroni di sequenzaSequence asynchronous computations

Poiché `Async<'T>` è una specifica di lavoro piuttosto che un'attività già in esecuzione, è possibile eseguire facilmente trasformazioni più complesse. Ecco un esempio che sequenzia un set di calcoli asincroni in modo che vengano eseguiti uno dopo l'altro.

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

Questa pianificazione `printTotalFileBytes` verrà pianificata per l'esecuzione nell'ordine degli elementi di `argv` anziché programmarli in parallelo. Poiché l'elemento successivo verrà pianificato solo dopo il termine dell'esecuzione dell'ultimo calcolo, i calcoli vengono sequenziati in modo che non vi sia alcuna sovrapposizione nella loro esecuzione.

## <a name="important-async-module-functions"></a>Importanti funzioni del modulo asincrono

Quando si scrive codice asincrono in F , in genere si interagisce con un framework che gestisce la pianificazione dei calcoli per l'utente. Tuttavia, questo non è sempre il caso, quindi è bene imparare le varie funzioni di partenza per pianificare il lavoro asincrono.

Poiché i calcoli asincroni F , sono una _specifica_ di lavoro anziché una rappresentazione del lavoro che è già in esecuzione, devono essere avviati in modo esplicito con una funzione di avvio. Esistono molte funzioni di [avvio asincrone](https://msdn.microsoft.com/library/ee370232.aspx) che sono utili in contesti diversi. Nella sezione seguente vengono descritte alcune delle funzioni di avvio più comuni.

### <a name="asyncstartchild"></a>Async.StartChild

Avvia un calcolo figlio all'interno di un calcolo asincrono. In questo modo è possibile eseguire contemporaneamente più calcoli asincroni. Il calcolo figlio condivide un token di annullamento con il calcolo padre. Se il calcolo padre viene annullato, viene annullato anche il calcolo figlio.

Firma:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

Quando usare:

- Quando si desidera eseguire più calcoli asincroni contemporaneamente anziché uno alla volta, ma non è pianificato in parallelo.
- Quando si desidera legare la durata di un calcolo figlio a quella di un calcolo padre.

A cosa fare attenzione:

- L'avvio `Async.StartChild` di più calcoli con non è come programmarli in parallelo. Se si desidera pianificare i `Async.Parallel`calcoli in parallelo, utilizzare .
- L'annullamento di un calcolo padre attiverà l'annullamento di tutti i calcoli figlio avviati.

### <a name="asyncstartimmediate"></a>Async.StartImmediate

Esegue un calcolo asincrono, avviato immediatamente dal thread del sistema operativo corrente. Ciò è utile se è necessario aggiornare un elemento sul thread chiamante durante il calcolo. Ad esempio, se un calcolo asincrono deve aggiornare `Async.StartImmediate` un'interfaccia utente (ad esempio l'aggiornamento di un indicatore di stato), deve essere utilizzato.

Firma:

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Quando usare:

- Quando è necessario aggiornare un elemento sul thread chiamante nel mezzo di un calcolo asincrono.

A cosa fare attenzione:

- Il codice nel calcolo asincrono verrà eseguito su qualsiasi thread di uno viene pianificato. Ciò può essere problematico se tale thread è in qualche modo sensibile, ad esempio un thread dell'interfaccia utente. In questi `Async.StartImmediate` casi, è probabile che sia inappropriato da usare.

### <a name="asyncstartastask"></a>Async.StartAsTask

Esegue un calcolo nel pool di thread. Restituisce <xref:System.Threading.Tasks.Task%601> un che verrà completato nello stato corrispondente una volta terminato il calcolo (produce il risultato, genera un'eccezione o viene annullato). Se non viene fornito alcun token di annullamento, viene utilizzato il token di annullamento predefinito.

Firma:

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

Quando usare:

- Quando è necessario chiamare in un'API <xref:System.Threading.Tasks.Task%601> .NET che prevede che un per rappresentare il risultato di un calcolo asincrono.

A cosa fare attenzione:

- Questa chiamata allocherà un oggetto aggiuntivo, `Task` che può aumentare l'overhead se viene utilizzato spesso.

### <a name="asyncparallel"></a>Async.Parallel

Pianifica una sequenza di calcoli asincroni da eseguire in parallelo. Il grado di parallelismo può essere facoltativamente sintonizzato/limitato specificando `maxDegreesOfParallelism` il parametro.

Firma:

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Quando usarlo:

- Se è necessario eseguire un set di calcoli contemporaneamente e non si fa affidamento sull'ordine di esecuzione.
- Se non sono necessari risultati dai calcoli pianificati in parallelo fino al completamento di tutti.

A cosa fare attenzione:

- È possibile accedere alla matrice di valori risultante solo dopo aver completato tutti i calcoli.
- I calcoli verranno eseguiti comunque finiscano per essere pianificati. Ciò significa che non è possibile fare affidamento sul loro ordine di esecuzione.

### <a name="asyncsequential"></a>Async.Sequential

Pianifica una sequenza di calcoli asincroni da eseguire nell'ordine in cui vengono passati. Verrà eseguito il primo calcolo, quindi il successivo e così via. Nessun calcolo verrà eseguito in parallelo.

Firma:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Quando usarlo:

- Se è necessario eseguire più calcoli in ordine.

A cosa fare attenzione:

- È possibile accedere alla matrice di valori risultante solo dopo aver completato tutti i calcoli.
- I calcoli verranno eseguiti nell'ordine in cui vengono passati a questa funzione, il che può significare che verrà trascorso più tempo prima che vengano restituiti i risultati.

### <a name="asyncawaittask"></a>Async.AwaitTask

Restituisce un calcolo asincrono <xref:System.Threading.Tasks.Task%601> che attende il completamento dell'utente e ne restituisce il risultato come`Async<'T>`

Firma:

```fsharp
task: Task<'T>  -> Async<'T>
```

Quando usare:

- Quando si utilizza un'API .NET che restituisce un all'interno di un <xref:System.Threading.Tasks.Task%601> calcolo asincrono F .

A cosa fare attenzione:

- Le eccezioni <xref:System.AggregateException> vengono incapsulate in seguito alla convenzione della libreria Task Parallel Library e questo è diverso dal modo in cui il asincrono di F , in genere espone le eccezioni.

### <a name="asynccatch"></a>Async.Catch

Crea un calcolo asincrono `Async<'T>`che esegue `Async<Choice<'T, exn>>`un determinato oggetto , restituendo un oggetto . Se l'oggetto specificato `Async<'T>` viene `Choice1Of2` completato correttamente, viene restituito un oggetto con il valore risultante. Se viene generata un'eccezione `Choice2of2` prima del completamento, viene restituito un oggetto con l'eccezione generata. Se viene utilizzato su un calcolo asincrono che è a sua volta composto da molti calcoli e uno di questi calcoli genera un'eccezione, il calcolo di chelo comprende verrà interrotto completamente.

Firma:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Quando usare:

- Quando si esegue un lavoro asincrono che potrebbe non riuscire con un'eccezione e si desidera gestire tale eccezione nel chiamante.

A cosa fare attenzione:

- Quando si utilizzano calcoli asincroni combinati o in sequenza, il calcolo di comprendente si interrompe completamente se uno dei relativi calcoli "interni" genera un'eccezione.

### <a name="asyncignore"></a>Async.Ignore

Crea un calcolo asincrono che esegue il calcolo specificato e ne ignora il risultato.

Firma:

```fsharp
computation: Async<'T> -> Async<unit>
```

Quando usare:

- Quando si dispone di un calcolo asincrono il cui risultato non è necessario. Questo è analogo `ignore` al codice per il codice non asincrono.

A cosa fare attenzione:

- Se è necessario utilizzare questo `Async.Start` perché si desidera `Async<unit>`utilizzare o un'altra funzione che richiede , considerare se scartare il risultato è bene fare. L'eliminazione dei risultati solo per adattarsi a una firma del tipo non deve essere in genere eseguita.

### <a name="asyncrunsynchronously"></a>Async.RunSynchronously

Esegue un calcolo asincrono e attende il risultato sul thread chiamante. Questa chiamata è bloccante.

Firma:

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

Quando usarlo:

- Se è necessario, utilizzarlo solo una volta in un'applicazione - nel punto di ingresso per un eseguibile.
- Quando non si è a cuore le prestazioni e si desidera eseguire un set di altre operazioni asincrone contemporaneamente.

A cosa fare attenzione:

- La `Async.RunSynchronously` chiamata blocca il thread chiamante fino al completamento dell'esecuzione.

### <a name="asyncstart"></a>Async.Start

Avvia un calcolo asincrono `unit`nel pool di thread che restituisce . Non aspetta il suo risultato. I calcoli annidati iniziati con `Async.Start` vengono avviati completamente indipendentemente dal calcolo padre che li ha chiamati. La loro durata non è legata ad alcun calcolo padre. Se il calcolo padre viene annullato, non viene annullato alcun calcolo figlio.

Firma:

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Utilizzare solo quando:

- Si dispone di un calcolo asincrono che non produce un risultato e/o richiede l'elaborazione di uno.
- Non è necessario sapere quando viene completato un calcolo asincrono.
- Non si è a cuore il thread su cui viene eseguito un calcolo asincrono.
- Non è necessario essere a conoscenza o segnalare le eccezioni risultanti dall'attività.

A cosa fare attenzione:

- Le eccezioni generate dai `Async.Start` calcoli avviati con non vengono propagate al chiamante. Lo stack di chiamate verrà completamente rimosso.
- Qualsiasi lavoro effettivo (ad `printfn`esempio `Async.Start` la chiamata ) avviato con non causerà l'effetto si verifica sul thread principale dell'esecuzione di un programma.

## <a name="interoperate-with-net"></a>Interoperabilità con .NET

È possibile che si stia lavorando con una libreria .NET o una codebase di codice di C, che utilizza la programmazione asincrona in stile [async/await.](../../../standard/async.md) Poiché il linguaggio C e <xref:System.Threading.Tasks.Task%601> la <xref:System.Threading.Tasks.Task> maggior parte delle librerie `Async<'T>`.NET utilizzano i tipi e come astrazioni di base anziché , è necessario attraversare un limite tra questi due approcci all'asincronia.

### <a name="how-to-work-with-net-async-and-taskt"></a>Come utilizzare .NET async e`Task<T>`

L'utilizzo di librerie asincrone <xref:System.Threading.Tasks.Task%601> e codebase .NET che usano ,vale a dire i calcoli asincroni che hanno valori restituiti, è semplice e dispone di supporto incorporato con F.

È possibile `Async.AwaitTask` utilizzare la funzione per attendere un calcolo asincrono .NET:You can use the function to await a .NET asynchronous computation:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

È possibile `Async.StartAsTask` utilizzare la funzione per passare un calcolo asincrono a un chiamante .NET:You can use the function to pass an asynchronous computation to a .NET caller:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Come utilizzare .NET async e`Task`

Per utilizzare le API <xref:System.Threading.Tasks.Task> che utilizzano, ovvero i calcoli asincroni .NET che non restituiscono un valore, potrebbe essere necessario aggiungere una funzione aggiuntiva che convertirà un `Async<'T>` <xref:System.Threading.Tasks.Task>oggetto in :

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Esiste già `Async.AwaitTask` un che <xref:System.Threading.Tasks.Task> accetta un come input. Con questa e `startTaskFromAsyncUnit` la funzione definita in <xref:System.Threading.Tasks.Task> precedenza, è possibile avviare e attendere i tipi da un calcolo asincrono di F.

## <a name="relationship-to-multi-threading"></a>Relazione con il multithreading

Anche se il threading è menzionato in tutto questo articolo, ci sono due cose importanti da ricordare:

1. Non esiste alcuna affinità tra un calcolo asincrono e un thread, a meno che non venga avviato in modo esplicito nel thread corrente.
1. La programmazione asincrona in F non è un'astrazione per il multithreading.

Ad esempio, un calcolo può effettivamente essere eseguito sul thread del chiamante, a seconda della natura del lavoro. Un calcolo potrebbe anche "saltare" tra i thread, prendendoli in prestito per una piccola quantità di tempo per fare un lavoro utile tra i periodi di "attesa" (ad esempio quando una chiamata di rete è in transito).

Anche se F , fornisce alcune funzionalità per avviare un calcolo asincrono sul thread corrente (o in modo esplicito non nel thread corrente), l'asincronia in genere non è associata a una particolare strategia di threading.

## <a name="see-also"></a>Vedere anche

- [Modello di programmazione asincrona di F](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Guida asincrona di Jet.com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [Guida alla programmazione asincrona per il divertimento e il profitto](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async in C 'NET e F ': ottenutri asincroni in C #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
