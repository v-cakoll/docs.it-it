---
title: Convenzioni di codifica F#
description: Informazioni su linee guida generali e idiomi F# per la scrittura di codice.
ms.date: 01/15/2020
ms.openlocfilehash: ca86bcf714d2fb4ee5f173ee54ba12c317f9abe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737818"
---
# <a name="f-coding-conventions"></a>Convenzioni di codifica F#

Le convenzioni seguenti sono formulate dall'esperienza di utilizzo F# di codebase di grandi dimensioni. I [cinque principi del codice F# valido](index.md#five-principles-of-good-f-code) sono la base di ogni raccomandazione. Sono correlati alle [ F# linee guida di progettazione dei componenti](component-design-guidelines.md), ma sono applicabili a F# qualsiasi codice, non solo a componenti come le librerie.

## <a name="organizing-code"></a>Organizzazione del codice

F#in sono disponibili due modalità principali per organizzare il codice: moduli e spazi dei nomi. Queste sono simili, ma presentano le differenze seguenti:

* Gli spazi dei nomi vengono compilati come spazi dei nomi .NET. I moduli vengono compilati come classi statiche.
* Gli spazi dei nomi sono sempre di primo livello. I moduli possono essere di primo livello e annidati all'interno di altri moduli.
* Gli spazi dei nomi possono estendersi su più file. I moduli non possono.
* I moduli possono essere decorati con `[<RequireQualifiedAccess>]` e `[<AutoOpen>]`.

Le linee guida seguenti consentiranno di usare questi elementi per organizzare il codice.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferire gli spazi dei nomi al livello superiore

Per qualsiasi codice utilizzabile pubblicamente, gli spazi dei nomi sono preferenziali per i moduli al livello superiore. Poiché sono compilati come spazi dei nomi .NET, sono utilizzabili C# da senza problemi.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

L'uso di un modulo di primo livello potrebbe non essere diverso quando viene F#chiamato solo da C# , ma per gli utenti, i chiamanti possono essere sorpresi con la necessità di qualificare `MyClass` con il modulo di `MyCode`.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Applicare con attenzione `[<AutoOpen>]`

Il costrutto di `[<AutoOpen>]` può inquinare l'ambito di ciò che è disponibile per i chiamanti e la risposta da cui provengono gli elementi sono "Magic". Questo non è un aspetto positivo. Un'eccezione a questa regola è rappresentata dalla F# libreria principale, anche se questo fatto è anche un po' controversa.

Tuttavia, si tratta di una praticità se si dispone di funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

In questo modo è possibile separare correttamente i dettagli di implementazione dall'API pubblica di una funzione senza dover qualificare completamente un helper ogni volta che viene chiamato.

Inoltre, l'esposizione di metodi di estensione e generatori di espressioni a livello di spazio dei nomi può essere espressa in modo accurato con `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Usare `[<RequireQualifiedAccess>]` ogni volta che i nomi possono essere in conflitto o si ritiene che contribuisca alla leggibilità

L'aggiunta dell'attributo `[<RequireQualifiedAccess>]` a un modulo indica che il modulo potrebbe non essere aperto e che i riferimenti agli elementi del modulo richiedono un accesso qualificato esplicito. Ad esempio, il modulo `Microsoft.FSharp.Collections.List` dispone di questo attributo.

Questa operazione è utile quando le funzioni e i valori nel modulo hanno nomi che probabilmente sono in conflitto con i nomi in altri moduli. La richiesta di accesso qualificato può aumentare significativamente la gestibilità a lungo termine e la evolvibilità di una libreria.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordinare `open` istruzioni in modo topologico

In F#, l'ordine delle dichiarazioni è importante, incluso con le istruzioni `open`. Questo è diverso da C#, in cui l'effetto di `using` e `using static` è indipendente dall'ordine di tali istruzioni in un file.

In F#gli elementi aperti in un ambito possono nascondere altri elementi già presenti. Questo significa che il riordino di `open` le istruzioni potrebbe modificare il significato del codice. Di conseguenza, non è consigliabile usare qualsiasi ordinamento arbitrario di tutte le istruzioni `open` (ad esempio, in modo alfanumerico), perché non si genera un comportamento diverso che ci si potrebbe aspettare.

È invece consigliabile ordinarle in modo [topologico](https://en.wikipedia.org/wiki/Topological_sorting); ovvero ordinare le istruzioni `open` nell'ordine in cui sono definiti i _livelli_ del sistema. È anche possibile prendere in considerazione l'ordinamento alfanumerico in livelli topologici diversi.

Ecco ad esempio l'ordinamento topologico per il F# file API pubblico del servizio del compilatore:

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

Si noti che un'interruzioni di riga separa i livelli topologici, in cui ogni livello viene ordinato in ordine alfanumerico in seguito. In questo modo, il codice viene organizzato in modo semplice senza ombreggiatura accidentale dei valori.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Usare classi per contenere valori con effetti collaterali

In molti casi l'inizializzazione di un valore può avere effetti collaterali, ad esempio la creazione di un'istanza di un contesto in un database o in un'altra risorsa remota. Si tenta di inizializzare tali elementi in un modulo e di utilizzarlo nelle funzioni successive:

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

Spesso si tratta di una cattiva idea per alcuni motivi:

Per prima cosa, viene effettuato il push della configurazione dell'applicazione nella codebase con `dep1` e `dep2`. Questa operazione è difficile da gestire nelle codebase più grandi.

In secondo luogo, i dati inizializzati staticamente non devono includere valori non thread-safe se il componente utilizzerà più thread. Questo è chiaramente violato da `dep3`.

Infine, l'inizializzazione del modulo viene compilata in un costruttore statico per l'intera unità di compilazione. Se si verifica un errore durante l'inizializzazione del valore associato al limite, si manifesterà come un `TypeInitializationException` che viene quindi memorizzato nella cache per l'intera durata dell'applicazione. Questa operazione può essere difficile da diagnosticare. Esiste in genere un'eccezione interna a cui è possibile tentare di ragionare, ma in caso contrario, non viene indicato quale sia la causa principale.

In alternativa, è sufficiente usare una classe semplice per mantenere le dipendenze:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Ciò consente quanto segue:

1. Push di qualsiasi stato dipendente al di fuori dell'API stessa.
2. È ora possibile eseguire la configurazione al di fuori dell'API.
3. Gli errori nell'inizializzazione per i valori dipendenti non possono essere manifesti come `TypeInitializationException`.
4. L'API è ora più facile da testare.

## <a name="error-management"></a>Gestione degli errori

La gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e sfumata e non ci sono Bulletti Silver per garantire che i sistemi siano a tolleranza d'errore e si comportino correttamente. Le linee guida seguenti forniscono indicazioni per l'esplorazione di questo spazio difficile.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Rappresentano i casi di errore e lo stato non valido nei tipi intrinseci al dominio

Con le [unioni discriminate](../language-reference/discriminated-unions.md), F# offre la possibilità di rappresentare lo stato del programma difettoso nel sistema di tipi. Ad esempio:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In questo caso, è possibile che si verifichino tre modi noti per ritirare denaro da un conto bancario. Ogni caso di errore è rappresentato nel tipo e può quindi essere gestito in modo sicuro in tutto il programma.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

In generale, se è possibile modellare i diversi modi in cui un problema può **avere esito negativo** nel dominio, il codice di gestione degli errori non viene più considerato come un elemento che è necessario gestire oltre al normale flusso di programma. È semplicemente una parte del normale flusso di programma e non è considerata **eccezionale**. Questa operazione presenta due vantaggi principali:

1. È più facile da gestire quando il dominio cambia nel tempo.
2. I casi di errore sono più facili da unit test.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Usare le eccezioni quando non è possibile rappresentare gli errori con i tipi

Non tutti gli errori possono essere rappresentati in un dominio di problema. Questi tipi di errori sono di natura *eccezionale* , quindi la possibilità di generare e rilevare eccezioni in F#.

Prima di tutto, è consigliabile leggere le [linee guida](../../standard/design-guidelines/exceptions.md)per la progettazione delle eccezioni. Sono applicabili anche a F#.

I costrutti principali disponibili in F# ai fini della generazione di eccezioni devono essere considerati nell'ordine di preferenza seguente:

| Funzione | Sintassi | Scopo |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera un `System.ArgumentNullException` con il nome dell'argomento specificato. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nome e un messaggio di argomento specificati. |
| `invalidOp` | `invalidOp "message"` | Genera un `System.InvalidOperationException` con il messaggio specificato. |
|`raise`| `raise (ExceptionType("message"))` | Meccanismo di utilizzo generale per la generazione di eccezioni. |
| `failwith` | `failwith "message"` | Genera un `System.Exception` con il messaggio specificato. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` con un messaggio determinato dalla stringa di formato e dai relativi input. |

Utilizzare `nullArg`, `invalidArg` e `invalidOp` come meccanismo per generare `ArgumentNullException`, `ArgumentException` e `InvalidOperationException` quando appropriato.

È in genere consigliabile evitare le funzioni `failwith` e `failwithf` perché generano il tipo di `Exception` di base, non un'eccezione specifica. Come per le [linee guida di progettazione delle eccezioni](../../standard/design-guidelines/exceptions.md), si desidera generare eccezioni più specifiche quando possibile.

### <a name="using-exception-handling-syntax"></a>Uso della sintassi di gestione delle eccezioni

F#supporta i modelli di eccezione tramite la sintassi `try...with`:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

La riconciliazione delle funzionalità da eseguire in caso di eccezione con criteri di ricerca può risultare un po' difficile se si desidera che il codice venga pulito. Un modo per gestire questa situazione consiste nell'usare i [criteri attivi](../language-reference/active-patterns.md) come mezzo per raggruppare le funzionalità che racchiudono un caso di errore con un'eccezione. È possibile, ad esempio, che si stia consumando un'API che, quando viene generata un'eccezione, racchiuda informazioni importanti nei metadati dell'eccezione. L'annullamento del wrapping di un valore utile nel corpo dell'eccezione acquisita all'interno del criterio attivo e la restituzione di tale valore può essere utile in alcune situazioni.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Non utilizzare la gestione di errori monadici per sostituire le eccezioni

Le eccezioni vengono considerate un tabù nella programmazione funzionale. In realtà, le eccezioni violano la purezza, quindi è sicuro considerarle non molto funzionanti. Tuttavia, in questo modo si ignora la realtà in cui il codice deve essere eseguito e possono verificarsi errori di Runtime. In generale, scrivere codice sul presupposto che la maggior parte degli elementi non sia pura né totale, per ridurre al minimo le sorprese spiacevoli.

È importante considerare i seguenti punti di forza/aspetti delle eccezioni in relazione alla pertinenza e all'idoneità nel Runtime .NET e nell'ecosistema tra più linguaggi:

1. Contengono informazioni di diagnostica dettagliate, molto utili per il debug di un problema.
2. Sono ben comprensibili per il runtime e altri linguaggi .NET.
3. Possono ridurre lo standard significativo se confrontato con il codice che non viene più utilizzato per *evitare* eccezioni implementando alcuni subset della loro semantica in modo ad hoc.

Questo terzo punto è fondamentale. Per operazioni complesse non semplici, l'impossibilità di usare le eccezioni può comportare la gestione di strutture come le seguenti:

```fsharp
Result<Result<MyType, string>, string list>
```

In questo modo è possibile ottenere facilmente codice fragile, ad esempio i criteri di ricerca sugli errori "tipizzati in modo stringa":

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Inoltre, può essere tentata di inghiottire qualsiasi eccezione nel desiderio di una funzione "semplice" che restituisce un tipo "più gradevole":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Sfortunatamente, `tryReadAllText` possibile generare numerose eccezioni in base alla miriade di elementi che possono verificarsi in un file system e questo codice elimina tutte le informazioni sul problema che potrebbe essere effettivamente errato nell'ambiente in uso. Se si sostituisce questo codice con un tipo di risultato, si tornerà all'analisi dei messaggi di errore "stringa tipizzata":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

L'inserimento dell'oggetto eccezione nel costruttore `Error` impone semplicemente di gestire correttamente il tipo di eccezione nel sito di chiamata anziché nella funzione. Questa operazione crea efficacemente le eccezioni controllate, che sono notoriamente Unfun per gestire come un chiamante di un'API.

Una valida alternativa agli esempi precedenti è l'intercettazione di eccezioni *specifiche* e la restituzione di un valore significativo nel contesto di tale eccezione. Se si modifica la funzione `tryReadAllText` come indicato di seguito, `None` ha un significato maggiore:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Anziché funzionare come catch-all, questa funzione gestirà correttamente il caso in cui un file non è stato trovato e assegna tale significato a un valore restituito. Questo valore restituito può essere mappato a tale caso di errore, senza scartare eventuali informazioni contestuali o forzare i chiamanti a gestire un caso che potrebbe non essere pertinente in quel punto del codice.

I tipi come `Result<'Success, 'Error>` sono appropriati per le operazioni di base in cui non sono F# annidati e i tipi facoltativi sono perfetti per la rappresentazione quando un elemento può restituire *qualcosa* o *nulla*. Non sono tuttavia una sostituzione per le eccezioni e non devono essere usate nel tentativo di sostituire le eccezioni. Ma devono essere applicati in modo sensato per risolvere specifici aspetti dei criteri di gestione degli errori e delle eccezioni in modi mirati.

## <a name="partial-application-and-point-free-programming"></a>Programmazione parziale di applicazioni e senza punto

F#supporta applicazioni parziali e, di conseguenza, diversi modi per programmare in uno stile senza punto. Questo può essere utile per il riutilizzo del codice all'interno di un modulo o l'implementazione di un elemento, ma non è un elemento da esporre pubblicamente. In generale, la programmazione senza punti non è una virtù di per sé e può aggiungere una barriera cognitiva significativa per gli utenti che non sono immersi nello stile.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Non usare applicazioni parziali e currying nelle API pubbliche

Con poche eccezioni, l'uso di applicazioni parziali in API pubbliche può creare confusione per i consumer. In genere, i valori associati a F# `let`nel codice sono **valori**, non **valori di funzione**. La combinazione di valori e valori di funzione può comportare il salvataggio di un numero ridotto di righe di codice in Exchange per un notevole sovraccarico cognitivo, soprattutto se combinato con operatori quali `>>` per comporre funzioni.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Considerare le implicazioni degli strumenti per la programmazione senza punti

Le funzioni sottoposte a currying non etichettano gli argomenti. Questa operazione ha implicazioni sugli strumenti. Prendere in considerazione le due funzioni seguenti:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Entrambe sono funzioni valide, ma `funcWithApplication` è una funzione sottoposta a currying. Quando si passa il mouse sui tipi in un editor, viene visualizzato quanto segue:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

Nel sito di chiamata, le descrizioni comandi degli strumenti, ad esempio Visual Studio, non forniranno informazioni significative per quanto riguarda effettivamente i tipi di input `string` e `int`.

Se si riscontra codice senza punti, ad esempio `funcWithApplication` che può essere utilizzato pubblicamente, è consigliabile eseguire un'espansione η completa, in modo che gli strumenti possano prelevare nomi significativi per gli argomenti.

Inoltre, il debug del codice senza punto può risultare complesso, se non è impossibile. Gli strumenti di debug si basano sui valori associati ai nomi, ad esempio `let` bindings, in modo da poter ispezionare i valori intermedi a metà dell'esecuzione. Quando il codice non ha valori da ispezionare, non è necessario eseguire il debug. In futuro, gli strumenti di debug possono evolversi per sintetizzare questi valori in base ai percorsi eseguiti in precedenza, ma non è una scelta ideale per coprire le scommesse sulle *potenziali* funzionalità di debug.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Si consideri un'applicazione parziale come tecnica per ridurre lo standard interno

A differenza del punto precedente, l'applicazione parziale è uno strumento straordinario per la riduzione di standard all'interno di un'applicazione o degli elementi interni più profondi di un'API. Può essere utile per eseguire unit test dell'implementazione di API più complesse, dove lo standard è spesso un problema da affrontare. Il codice seguente, ad esempio, Mostra come è possibile eseguire la maggior parte dei framework di simulazione senza assumere una dipendenza esterna su un Framework di questo tipo ed è necessario apprendere un'API su misura correlata.

Si consideri ad esempio la seguente topografia di soluzioni:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` possibile esporre codice, ad esempio:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Il testing unità `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` è facile:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

L'applicazione parziale di `doTransaction` con un oggetto contesto fittizio consente di chiamare la funzione in tutti gli unit test senza la necessità di creare un contesto fittizio ogni volta:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Questa tecnica non deve essere applicata universalmente all'intera codebase, ma è un modo efficace per ridurre gli standard per gli elementi interni complessi e per il testing degli unit test.

## <a name="access-control"></a>Controllo di accesso

F#include più opzioni per il [controllo di accesso](../language-reference/access-control.md), ereditate da quanto disponibile nel Runtime .NET. Questi non sono semplicemente utilizzabili per i tipi. è anche possibile usarli per le funzioni.

* Preferisce i tipi e i membri non`public` fino a quando non sono necessari per essere pubblicamente utilizzabili. Ciò consente anche di ridurre al minimo le coppie di consumer.
* Si impegna a garantire la `private`di tutte le funzionalità di supporto.
* Si consideri l'uso di `[<AutoOpen>]` in un modulo privato di funzioni helper se diventano numerose.

## <a name="type-inference-and-generics"></a>Inferenza del tipo e generics

L'inferenza del tipo può evitare di digitare una grande quantità di standard. E la generalizzazione automatica nel F# compilatore può essere utile per scrivere codice più generico senza alcuna ulteriore operazione da parte dell'utente. Tuttavia, queste funzionalità non sono universalmente valide.

* È consigliabile assegnare etichette ai nomi degli argomenti con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza del tipo per.

    Il motivo **è che è necessario avere** il controllo della forma dell'API, non del compilatore. Sebbene il compilatore possa eseguire un processo ottimale per l'inferenza dei tipi, è possibile che la forma dell'API venga modificata se gli elementi interni sui quali si basano i tipi modificati. Questo potrebbe essere quello che si desidera, ma quasi certamente comporterà una modifica dell'API di rilievo che i consumer downstream dovranno gestire. Se invece si controlla in modo esplicito la forma dell'API pubblica, è possibile controllare queste modifiche di rilievo. Nei termini DDD, questo può essere considerato come un livello Anti-danneggiamento.

* Provare a assegnare un nome significativo agli argomenti generici.

    A meno che non si stia scrivendo codice realmente generico che non è specifico di un determinato dominio, un nome significativo può aiutare gli altri programmatori a comprendere il dominio in cui stanno lavorando. Ad esempio, un parametro di tipo denominato `'Document` nel contesto dell'interazione con un database di documenti rende più chiaro che i tipi di documenti generici possono essere accettati dalla funzione o dal membro che si sta utilizzando.

* Prendere in considerazione la denominazione di parametri di tipo generico con PascalCase.

    Questo è il modo generale per eseguire operazioni in .NET, quindi è consigliabile usare PascalCase anziché snake_case o camelCase.

Infine, la generalizzazione automatica non è sempre un vantaggio per gli utenti che non F# hanno familiarità con o con una codebase di grandi dimensioni. L'utilizzo di componenti generici comporta un sovraccarico cognitivo. Inoltre, se le funzioni generalizzate automaticamente non vengono usate con tipi di input diversi (indipendentemente dal fatto che siano destinate a essere usate come tali), non vi è alcun vantaggio reale che sia generico in quel momento. Tenere sempre presente che il codice che si sta scrivendo trarrà vantaggio dal fatto che sia generico.

## <a name="performance"></a>Prestazioni

### <a name="prefer-structs-for-small-data-types"></a>Preferire gli struct per i tipi di dati di piccole dimensioni

L'uso di struct (detti anche tipi di valore) può spesso comportare prestazioni più elevate per il codice, perché in genere evita l'allocazione di oggetti. Tuttavia, gli struct non sono sempre un pulsante "Go Faster": se le dimensioni dei dati in uno struct superano i 16 byte, la copia dei dati può spesso comportare un tempo di utilizzo maggiore della CPU rispetto all'utilizzo di un tipo di riferimento.

Per determinare se è necessario usare uno struct, tenere presenti le condizioni seguenti:

- Se le dimensioni dei dati sono pari a 16 byte o inferiori.
- Se è probabile che molti di questi tipi di dati siano residenti in memoria in un programma in esecuzione.

Se si applica la prima condizione, in genere è consigliabile usare uno struct. Se si applicano entrambe le condizioni, è consigliabile utilizzare quasi sempre uno struct. Potrebbero esserci casi in cui si applicano le condizioni precedenti, ma l'uso di uno struct non è migliore o peggiore rispetto all'uso di un tipo riferimento, ma è probabile che sia raro. È importante misurare sempre quando si apportano modifiche come questa, ma non agire su presupposto o intuizione.

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>Preferisci Tuple struct quando si raggruppano tipi valore piccoli

Prendere in considerazione le due funzioni seguenti:

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che la funzione `runWithStructTuple` che usa le tuple struct viene eseguita più velocemente del 40% e non alloca memoria.

Tuttavia, questi risultati non sono sempre il caso nel codice. Se si contrassegna una funzione come `inline`, il codice che usa le tuple di riferimento può ottenere alcune ottimizzazioni aggiuntive oppure il codice che verrebbe allocato potrebbe essere semplicemente ottimizzato. È consigliabile misurare sempre i risultati ogni volta che le prestazioni sono interessate e non funzionano mai in base a presupposti o all'intuizione.

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>Preferire i record struct quando il tipo di dati è ridotto

La regola empirica descritta in precedenza include anche [ F# ](../language-reference/records.md)per i tipi di record. Considerare i tipi di dati e le funzioni seguenti che li elaborano:

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

Questa operazione è simile al codice della tupla precedente, ma questa volta nell'esempio vengono usati i record e una funzione interna inline.

Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `processStructPoint` viene eseguito quasi il 60% più velocemente e non alloca nulla nell'heap gestito.

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>Preferisce le unioni discriminate struct quando il tipo di dati è ridotto

Le osservazioni precedenti sulle prestazioni con tuple e record di struct contengono anche per [ F# le unioni discriminate](../language-reference/discriminated-unions.md). Esaminare il codice seguente:

```fsharp
    type Name = Name of string
    
    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

È comune definire unioni discriminate a caso singolo come questa per la modellazione di dominio. Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `structReverseName` viene eseguito circa il 25% più velocemente rispetto `reverseName` per le stringhe di piccole dimensioni. Per le stringhe di grandi dimensioni, entrambe le prestazioni sono uguali. Quindi, in questo caso, è sempre preferibile usare uno struct. Come indicato in precedenza, misurare sempre e non operare su presupposti o intuizioni.

Sebbene nell'esempio precedente sia stata illustrata un'unione discriminata struct che ha prodotto prestazioni migliori, è comune disporre di unioni discriminate più grandi durante la modellazione di un dominio. I tipi di dati più grandi, ad esempio, potrebbero non funzionare anche se sono struct a seconda delle operazioni su di essi, dal momento che potrebbero essere necessarie altre operazioni di copia.

### <a name="functional-programming-and-mutation"></a>Programmazione funzionale e mutazione

F#per impostazione predefinita, i valori non sono modificabili, che consente di evitare determinate classi di bug (soprattutto quelli che coinvolgono la concorrenza e il parallelismo). Tuttavia, in alcuni casi, per ottenere l'efficienza ottimale (o anche ragionevole) del tempo di esecuzione o delle allocazioni di memoria, è possibile implementare una sezione di lavoro in modo ottimale tramite la mutazione sul posto dello stato. Questa operazione è possibile in base al consenso esplicito F# con la parola chiave `mutable`.

L'uso di `mutable` F# in può essere in contrasto con la purezza funzionale. Questa operazione è comprensibile, ma la purezza funzionale può essere in contrasto con gli obiettivi di prestazioni. Un compromesso consiste nell'incapsulare la mutazione in modo che i chiamanti non debbano preoccuparsi di ciò che accade quando chiamano una funzione. In questo modo è possibile scrivere un'interfaccia funzionale su un'implementazione basata sulla mutazione per il codice critico per le prestazioni.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Eseguire il wrapping del codice modificabile nelle interfacce non modificabili

Con la trasparenza referenziale come obiettivo, è fondamentale scrivere codice che non esponga la parte mutevole delle funzioni critiche per le prestazioni. Il codice seguente, ad esempio, implementa la funzione `Array.contains` nella F# libreria principale:

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

La chiamata di questa funzione più volte non comporta la modifica della matrice sottostante né la necessità di mantenere uno stato modificabile per l'utilizzo. È referenzialemente trasparente, anche se quasi ogni riga di codice all'interno di essa usa la mutazione.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considerare l'incapsulamento dei dati modificabili nelle classi

Nell'esempio precedente è stata usata una singola funzione per incapsulare le operazioni usando dati modificabili. Questa operazione non è sempre sufficiente per set di dati più complessi. Considerare i set di funzioni seguenti:

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

Questo codice è efficiente, ma espone la struttura dei dati basata sulla mutazione che i chiamanti sono responsabili della gestione. Questa operazione può essere racchiusa all'interno di una classe senza membri sottostanti che possono cambiare:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` incapsula la struttura dei dati basata sulla mutazione sottostante, quindi non impone ai chiamanti di mantenere la struttura dei dati sottostante. Le classi sono un modo efficace per incapsulare i dati e le routine che sono basati sulla mutazione senza esporre i dettagli ai chiamanti.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Preferisci `let mutable` alle celle di riferimento

Le celle di riferimento rappresentano un modo per rappresentare il riferimento a un valore anziché il valore stesso. Sebbene possano essere utilizzate per codice critico per le prestazioni, non sono consigliate. Si consideri l'esempio seguente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

L'uso di una cella di riferimento ora "inquina" tutto il codice successivo con la necessità di dereferenziare e rifare riferimento ai dati sottostanti. In alternativa, prendere in considerazione `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Oltre all'unico punto di mutazione al centro dell'espressione lambda, tutto il resto del codice che tocca `acc` può eseguire questa operazione in modo che non sia diverso dall'utilizzo di un normale valore non modificabile associato a `let`. In questo modo sarà più semplice cambiare nel tempo.

## <a name="object-programming"></a>Programmazione di oggetti

F#dispone del supporto completo per oggetti e concetti orientati a oggetti (OO). Sebbene molti concetti di OO siano potenti e utili, non tutti sono ideali da usare. Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità OO a un livello elevato.

**Considerare l'uso di queste funzionalità in molte situazioni:**

* Notazione del punto (`x.Length`)
* Membri di istanza
* Costruttori impliciti
* Membri statici
* Notazione indicizzatore (`arr.[x]`)
* Argomenti denominati e facoltativi
* Interfacce e implementazioni di interfaccia

**Non raggiungere innanzitutto queste funzionalità, ma è possibile applicarle in modo accurato quando sono utili per risolvere un problema:**

* Overload di un metodo
* Dati modificabili incapsulati
* Operatori sui tipi
* Proprietà automatiche
* Implementazione di `IDisposable` e `IEnumerable`
* Estensioni di tipo
* Events
* Strutture
* Delegati
* Enumerazioni

**In genere, evitare queste funzionalità, a meno che non sia necessario usarle:**

* Gerarchie di tipo e ereditarietà di implementazione basate su ereditarietà
* Valori null e `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferisci composizione sull'ereditarietà

La [composizione sull'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) è un idioma di lunga durata F# a cui è possibile aderire il codice valido. Il principio fondamentale è che non esporre una classe base e forzare i chiamanti a ereditare da tale classe di base per ottenere la funzionalità.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usare espressioni di oggetto per implementare le interfacce se non è necessaria una classe

Le [espressioni di oggetto](../language-reference/object-expressions.md) consentono di implementare interfacce in tempo reale, associando l'interfaccia implementata a un valore senza dover eseguire questa operazione all'interno di una classe. Questa operazione è utile, soprattutto se è necessario implementare _solo_ l'interfaccia e non è necessaria una classe completa.

Ecco, ad esempio, il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di correzione del codice se è stato aggiunto un simbolo per cui non si dispone di un'istruzione `open` per:

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

Poiché non è necessaria alcuna classe quando si interagisce con l'API Visual Studio Code, le espressioni di oggetto sono uno strumento ideale per questa operazione. Sono utili anche per il testing unità, quando si vuole eseguire lo stub di un'interfaccia con routine di test in modo ad hoc.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Prendere in considerazione abbreviazioni di tipo per abbreviare le firme

Le [abbreviazioni di tipo](../language-reference/type-abbreviations.md) sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma di funzione o un tipo più complesso. Ad esempio, l'alias seguente assegna un'etichetta a ciò che è necessario per definire un calcolo con [CNTK](https://docs.microsoft.com/cognitive-toolkit/), una libreria Deep Learning:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Il nome del `Computation` è un modo pratico per indicare qualsiasi funzione corrispondente alla firma a cui è associato l'alias. L'uso di abbreviazioni di tipo come questo è utile e consente di scrivere codice più conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evitare di usare le abbreviazioni di tipo per rappresentare il dominio

Sebbene le abbreviazioni di tipo siano utili per assegnare un nome alle firme di funzione, possono generare confusione quando abbreviare altri tipi. Prendere in considerazione questa abbreviazione:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Questa operazione può generare confusione in diversi modi:

* `BufferSize` non è un'astrazione; si tratta semplicemente di un altro nome per un numero intero.
* Se `BufferSize` è esposto in un'API pubblica, può essere facilmente interpretato in modo non semplice da `int`. In genere, i tipi di dominio hanno più attributi e non sono tipi primitivi come `int`. Questa abbreviazione viola questo presupposto.
* La combinazione di maiuscole e minuscole di `BufferSize` (PascalCase) implica che questo tipo contenga più dati.
* Questo alias non offre una maggiore chiarezza rispetto alla fornitura di un argomento denominato a una funzione.
* L'abbreviazione non si manifesterà in IL compilato IL; si tratta semplicemente di un intero e questo alias è un costrutto in fase di compilazione.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

In breve, il trabocchetto con abbreviazioni di tipo è che **non** sono astrazioni sui tipi che sono abbreviare. Nell'esempio precedente `BufferSize` è semplicemente una `int` sotto le quinte, senza dati aggiuntivi, né i vantaggi del sistema di tipi oltre a ciò che `int` già.

Un approccio alternativo all'uso delle abbreviazioni di tipo per rappresentare un dominio consiste nell'usare unioni discriminate a singolo caso. L'esempio precedente può essere modellato come indicato di seguito:

```fsharp
type BufferSize = BufferSize of int
```

Se si scrive codice che opera in termini di `BufferSize` e del relativo valore sottostante, è necessario crearne uno anziché passare qualsiasi Integer arbitrario:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

In questo modo si riduce la probabilità che venga erroneamente passato un numero intero arbitrario nella funzione `send`, perché il chiamante deve costruire un tipo di `BufferSize` per eseguire il wrapping di un valore prima di chiamare la funzione.
