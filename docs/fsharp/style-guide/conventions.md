---
title: F#convenzioni di codifica
description: Informazioni su termini e le linee guida generali durante la scrittura di F# codice.
ms.date: 05/14/2018
ms.openlocfilehash: 1ef016184180eb8d233295e8985903e07693ad26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902135"
---
# <a name="f-coding-conventions"></a>F#convenzioni di codifica

Le seguenti convenzioni vengono formulate dall'esperienza di utilizzo di grandi dimensioni F# basi di codice. Il [cinque principi buone F# codice](index.md#five-principles-of-good-f-code) sono alla base di ogni raccomandazione. Sono correlate al [ F# linee guida di progettazione componenti](component-design-guidelines.md), ma sono applicabili per qualsiasi F# del codice, non solo i componenti come le librerie.

## <a name="organizing-code"></a>Organizzazione del codice

F#offre due modi per organizzare il codice: moduli e spazi dei nomi. Questi sono simili, ma hanno le differenze seguenti:

* Gli spazi dei nomi vengono compilate come spazi dei nomi .NET. I moduli vengono compilati come le classi statiche.
* Gli spazi dei nomi sono sempre di livello superiore. I moduli possono essere nidificati all'interno di altri moduli e livello principale.
* Gli spazi dei nomi possono estendersi su più file. I moduli non possono.
* I moduli possono essere decorati con `[<RequireQualifiedAccess>]` e `[<AutoOpen>]`.

Le linee guida seguenti consentono di usarle per organizzare il codice.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferire gli spazi dei nomi di primo livello

Per il codice utilizzabile pubblicamente, gli spazi dei nomi sono preferenziali per i moduli di primo livello. Poiché vengono compilati come spazi dei nomi .NET, sono utilizzabili dal codice c# con alcun problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Uso di un modulo di primo livello potrebbe non essere visualizzati diverso quando viene chiamato solo da F#, ma per C# ai consumatori, i chiamanti potrebbero rimanere sorpresi per dover qualificare `MyClass` con il `MyCode` modulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Applicare attentamente `[<AutoOpen>]`

Il `[<AutoOpen>]` costrutto possa inquinare l'ambito di ciò che è disponibile ai chiamanti e la risposta a un elemento da cui provenienza è "magic". Non si tratta in genere una cosa positiva. Un'eccezione a questa regola è la F# libreria principale di se stessa (anche se questo fatto è anche un po' controverso).

Tuttavia, è utile se si ha la funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.

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

Ciò consente di dettagli di implementazione separato correttamente dall'API pubblica di una funzione senza doverla specificare completamente un helper ogni volta che viene chiamata.

Inoltre, che espone i metodi di estensione e generatori di espressioni a livello di spazio dei nomi può essere accuratamente espresso con `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Usare `[<RequireQualifiedAccess>]` ogni volta che i nomi potrebbero essere in conflitto o si ritiene consente una migliore leggibilità

Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita completo di accesso. Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.

Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che possono entrare in conflitto con i nomi di altri moduli. Richiedere l'accesso completo può aumentare notevolmente la manutenibilità a lungo termine e capacità evolutiva di una libreria.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordinamento `open` istruzioni topologicamente

In F#, l'ordine delle questioni di dichiarazioni, incluse con `open` istruzioni. A differenza di c#, si tratta in cui l'effetto della `using` e `using static` sono indipendenti l'ordinamento di tali istruzioni in un file.

In F#, gli elementi aperti in un ambito possono nascondere gli altri è già presente. Ciò significa che la ridisposizione delle `open` istruzioni è stato possibile modificare il significato del codice. Di conseguenza, qualsiasi arbitrario l'ordinamento di tutti i `open` istruzioni (ad esempio, in ordine alfanumerico) è in genere sconsigliato, correre è generare un comportamento diverso che ci si aspetterebbe.

È invece consigliabile li Ordina [topologicamente](https://en.wikipedia.org/wiki/Topological_sorting); vale a dire, ordinare le `open` le istruzioni nell'ordine in cui _livelli_ del sistema sono definiti. In questo alfanumerico ordinamento all'interno di diversi livelli topologici inoltre può essere considerato.

Ad esempio, ecco l'ordinamento topologico per il F# file di API del compilatore servizio pubblica:

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

Si noti che un'interruzione di riga separa topologici livelli, con ogni livello da ordinare in ordine alfanumerico in un secondo momento. Normalmente, ciò consente di organizzare codice senza shadowing accidentalmente i valori.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Usare classi per contenere i valori che hanno effetti collaterali

Esistono molte volte quando un valore di inizializzazione può avere effetti collaterali, ad esempio creare un'istanza di un contesto a un database o altre risorse remote. Si è tentati di inizializzazione di elementi in un modulo e usarlo in funzioni successive:

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

Ciò è spesso una buona idea per diversi motivi:

In primo luogo, configurazione dell'applicazione viene inserita nel codebase `dep1` e `dep2`. Questo è difficile da gestire nel codebase più grandi.

I dati in secondo luogo, inizializzati in modo statico non devono includere i valori che non sono thread-safe se il componente verrà utilizzato più thread. È chiaramente sospesa dal `dep3`.

Infine, l'inizializzazione del modulo compila in un costruttore statico per l'intera unità di compilazione. Se si verifica un errore nell'inizializzazione valore associazione let in tale modulo, manifesta come un `TypeInitializationException` che viene quindi memorizzato nella cache per l'intera durata dell'applicazione. Ciò può essere difficile da diagnosticare. È in genere un'eccezione interna che è possibile tentare di ragionare sul, ma se non esiste, quindi non c'è la causa radice.

Usare invece solo una semplice classe per contenere le dipendenze:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Ciò consente quanto segue:

1. Eseguire il push di qualsiasi stato dipendente di fuori l'API stessa.
2. Configurazione a questo punto può essere eseguita all'esterno dell'API.
3. Errori di inizializzazione per i valori dipendenti non sono soggette a risolversi in un `TypeInitializationException`.
4. L'API è ora più facile da testare.

## <a name="error-management"></a>Gestione degli errori

Gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e maggior numero di sfumature e non esistono Nessun silver punti elenco nell'assicurare i sistemi sono a tolleranza di errore e anche un comportamento. Le seguenti linee guida devono offrire indicazioni nella navigazione quest'area difficile.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Rappresentano casi di errore e lo stato non valido nei tipi intrinseci al dominio

Con [unioni discriminate](../language-reference/discriminated-unions.md), F# ti offre la possibilità di rappresentare lo stato del programma guasto nel sistema tipo. Ad esempio:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In questo caso, esistono tre modi noti prelievo di denaro da un conto bancario può avere esito negativo. Ogni caso di errore è rappresentato nel tipo e può pertanto essere gestito in modo sicuro in tutto il programma.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

In generale, se è possibile modellare i diversi modi per ottenere un determinato può **esito negativo** nel dominio, quindi la gestione del codice di errore non viene non è più considerato come qualcosa si devono affrontare oltre il flusso di programma normale. È semplicemente una parte del normale flusso di programma ma non considerata **eccezionali**. Esistono due vantaggi principali a questo:

1. È più facile da gestire se il dominio viene modificato nel corso del tempo.
2. Casi di errore sono più semplici a unit test.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Utilizzare le eccezioni quando gli errori non possono essere rappresentati con i tipi

Non tutti gli errori possono essere rappresentati in un dominio del problema. Questi tipi di errori vengono *eccezionale* natura, pertanto la possibilità di generare e intercettare le eccezioni in F#.

In primo luogo, si consiglia di leggere il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md). Queste sono applicabili anche a F#.

Principale costrutti disponibili nel F# per gli scopi della generazione di eccezioni devono essere considerati nell'ordine di preferenza seguente:

| Funzione | Sintassi | Scopo |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera un `System.ArgumentNullException` con il nome dell'argomento specificato. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nome dell'argomento specificato e un messaggio. |
| `invalidOp` | `invalidOp "message"` | Genera un `System.InvalidOperationException` con il messaggio specificato. |
|`raise`| `raise (ExceptionType("message"))` | Meccanismo generico per la generazione di eccezioni. |
| `failwith` | `failwith "message"` | Genera un `System.Exception` con il messaggio specificato. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` con un messaggio in base la stringa di formato e i relativi input. |

Uso `nullArg`, `invalidArg` e `invalidOp` come meccanismo per generare `ArgumentNullException`, `ArgumentException` e `InvalidOperationException` quando appropriato.

Il `failwith` e `failwithf` funzioni devono essere generalmente evitate perché essi elevare la base `Exception` digitare, non un'eccezione specifica. In base il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md), che si desidera generare eccezioni più specifiche, quando possibile.

### <a name="using-exception-handling-syntax"></a>Usando la sintassi di gestione delle eccezioni

F#supporta i modelli di eccezione tramite la `try...with` sintassi:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Risoluzione delle differenze di funzionalità per eseguire in caso di un'eccezione con criteri di ricerca può essere difficile se si vuole mantenere il codice pulito. Un modo per gestire questo problema consiste nell'utilizzare [modelli attivi](../language-reference/active-patterns.md) come mezzo per la funzionalità gruppo che circonda un caso di errore con un'eccezione se stesso. Si potrebbe ad esempio, utilizza un'API che, quando viene generata un'eccezione, include informazioni utili nei metadati dell'eccezione. Annullamento del wrapping di un valore utile nel corpo di eccezione acquisito all'interno di (modello attivo) e la restituzione di valore può essere utile in alcuni casi.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Non usare monadic gestione degli errori per sostituire le eccezioni

Le eccezioni vengono interpretate come un po' tabù nella programmazione funzionale. In effetti, le eccezioni violano purezza, pertanto è opportuno considerare li non abbastanza funzionale. Tuttavia, questo ignora la realtà di in cui deve essere eseguito codice e che possono verificarsi errori di runtime. In generale, è possibile scrivere codice in base al presupposto che la maggior parte delle operazioni siano puri né totale, per ridurre al minimo spiacevoli sorprese.

È importante prendere in considerazione i seguenti punti di forza/aspetti fondamentali delle eccezioni rispetto alla loro rilevanza e può risultare appropriato nel runtime di .NET e lingue ecosistema nel suo complesso:

1. Contengono le informazioni di diagnostica dettagliate che sono molto utile durante il debug di un problema.
2. Sono ben noti dal runtime e altri linguaggi .NET.
3. Possono ridurre boilerplate significativo quando vengono confrontati con il codice esce dal dirigendo verso *evitare* eccezioni mediante l'implementazione di alcuni subset di presentano una semantica in base ad hoc.

Questo terzo punto è fondamentale. Per operazioni complesse non semplice, riesce a utilizzare le eccezioni può comportare la gestione di strutture simile al seguente:

```fsharp
Result<Result<MyType, string>, string list>
```

Che può causare facilmente codice fragile, ad esempio criteri di ricerca in "stringly tipizzata" errori:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Inoltre, può essere tentato di inghiottire qualsiasi eccezione il desiderio di una funzione "semplice" che restituisce un tipo di "coloro":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Sfortunatamente, `tryReadAllText` può generare numerose eccezioni basate la miriade di operazioni che possono verificarsi in un file system, e questo codice rimuove da subito eventuali informazioni sul possibile effettivamente causa problemi nell'ambiente in uso. Se questo codice viene sostituito con un tipo di risultato, quindi si ritorna al messaggio di errore "stringly tipizzata" analisi:

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

E inserire l'oggetto eccezione stesso nel `Error` costruttore impone solo è possibile gestire in modo corretto con il tipo di eccezione nel sito di chiamata invece che nella funzione. Eccezioni verificate, che sono notoriamente unfun affrontare il chiamante di un'API in modo efficace in modo da ottenere.

Una buona alternativa per gli esempi precedenti è rilevare *specifici* eccezioni e restituire un valore significativo nel contesto della nuova eccezione. Se si modifica il `tryReadAllText` funzionare nel modo seguente: `None` siano più facilmente comprensibili:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Invece di funzionare come un catch-all, questa funzione ora correttamente gestirà il caso quando un file non è stato trovato e assegnare tale significato per un valore restituito. Questo valore restituito può eseguire il mapping per tale scenario di errore, mentre non rimuovendo qualsiasi informazioni contestuali o imporre ai chiamanti di affrontare un caso che potrebbe non essere pertinente a questo punto nel codice.

I tipi, ad esempio `Result<'Success, 'Error>` siano appropriati per le operazioni di base in cui non sono annidati, e F# tipi facoltativi sono perfetti per che rappresenta quando qualcosa potrebbe restituire *qualcosa* o *nothing*. Non sono una sostituzione per le eccezioni, tuttavia e non deve essere utilizzati nel tentativo per sostituire le eccezioni. Piuttosto, si deve essere applicati con cautela per alcuni aspetti specifici di indirizzi di eccezione e criteri di gestione degli errori in modalità di destinazione.

## <a name="partial-application-and-point-free-programming"></a>Applicazione parziale e della programmazione senza punto

F#supporta l'applicazione parziale e, di conseguenza, sui vari modi al programma in uno stile privi di punti. Ciò può essere utile per il riutilizzo di codice all'interno di un modulo o l'implementazione di un elemento, ma non si tratta in genere per esporre pubblicamente. In generale, programmazione senza punto non è un essendo e in se stesso e può aggiungere un ostacolo significativo cognitivo per utenti che non sono si è immersi nello stile.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Non utilizzare applicazione parziale e currying nelle API pubbliche

Con l'eccezione piccolo, l'uso dell'applicazione parziali nelle API pubbliche può generare confusione per i consumer. In genere `let`-associati valori di F# sono codice **valori**, non **valori di funzione**. Combinazione di valori e i valori di funzione può comportare il salvataggio di un numero ridotto di righe di codice a fronte di un notevole sovraccarico cognitivo, soprattutto se combinate con gli operatori, ad esempio `>>` comporre funzioni.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Considerare le implicazioni di strumenti per la programmazione senza punto

Funzioni sottoposte a currying non assegnata un'etichetta ai relativi argomenti. Ciò ha implicazioni in termini di strumenti. Prendere in considerazione le due funzioni seguenti:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Entrambi sono funzioni valide, ma `funcWithApplication` è una funzione sottoposti a currying. Quando si posiziona i relativi tipi in un editor, viene visualizzato questo:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

Nel sito di chiamata, le descrizioni comandi in strumenti quali Visual Studio non è di fornire informazioni significative quali la `string` e `int` rappresentano effettivamente i tipi di input.

Se si verifica senza punto di codice, ad esempio `funcWithApplication` è utilizzabile pubblicamente, è consigliabile eseguire un'espansione di η completa in modo che gli strumenti possono scegliere nell'inserimento nel nomi significativi per gli argomenti.

Inoltre, il debug del codice senza punto può essere difficile, se non impossibile. Strumenti di debug si basano sui valori associati ai nomi (ad esempio, `let` associazioni) in modo che sia possibile esaminare l'esecuzione durante l'esecuzione valori intermedi. Quando il codice non contiene valori per controllare, vi è nulla di cui eseguire il debug. In futuro, gli strumenti di debug potrebbero evolversi per sintetizzare questi valori in base a percorsi eseguiti in precedenza, ma non è una buona idea per salvaguardarsi la rilevanza nel *potenziali* funzionalità di debug.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Prendere in considerazione applicazione parziale come tecnica per ridurre boilerplate interno

A differenza al punto precedente, applicazione parziale è un ottimo strumento per ridurre boilerplate all'interno di un'applicazione o gli elementi interni più approfonditi di un'API. Può essere utile per gli unit test l'implementazione di API più complicate, in cui boilerplate è spesso un problema da affrontare. Ad esempio, il codice seguente viene illustrato come è possibile ottenere il risultato quali Framework di simulazione più offrono senza una dipendenza esterna su un framework di questo tipo e dover apprendere un correlati allestita l'API.

Ad esempio, prendere in considerazione la topografia di soluzioni seguenti:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` potrebbe esporre il codice, ad esempio:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Gli unit test `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` è semplice:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Parzialmente applicando `doTransaction` con un contesto di creazione di versioni fittizie oggetto consente di chiamare la funzione in tutti gli unit test senza la necessità di costruire ogni volta che un contesto simulato:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Questa tecnica non deve essere applicata universalmente per l'intera codebase, ma è un buon metodo per ridurre boilerplate per elementi interni complicata e gli unit test di tali meccanismi interni.

## <a name="access-control"></a>Controllo di accesso

F#offre più opzioni per il [controllo di accesso](../language-reference/access-control.md), ereditato da ciò che è disponibile nel runtime di .NET. Questi non sono utilizzabili solo per i tipi: è possibile usarli per le funzioni, troppo.

* Non preferisce`public` tipi e membri fino a quando non è necessario che diventino utilizzabile pubblicamente. Ciò riduce al minimo le due consumer per.
* Cercare di mantenere tutte le funzionalità di helper `private`.
* Si consideri l'uso di `[<AutoOpen>]` su un modulo privato delle funzioni di supporto se diventano numerosi.

## <a name="type-inference-and-generics"></a>L'inferenza del tipo e generics

L'inferenza del tipo può evitare la digitazione numerosi boilerplate. Generalizzazione automatica in e il F# compilatore consentono di scrivere codice più generico quasi senza altre modifiche da parte dell'utente. Tuttavia, queste funzionalità non sono universalmente valida.

* Prendere in considerazione l'assegnazione di etichette i nomi di argomento con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza del tipo per questo oggetto.

    Il motivo è che **si** deve essere nel controllo della forma dell'API, non il compilatore. Anche se il compilatore può eseguire un processo correttamente all'inferenza di tipi per l'utente, è possibile avere la forma di apportare modifiche all'API se si affidano ai componenti interni sono stati modificati i tipi. È possibile che si desidera, ma quasi sicuramente comporterà una modifica sostanziale API consumer downstream dovrà affrontare. In alternativa, se si controlla in modo esplicito la forma dell'API pubblica, è possibile controllare queste modifiche di rilievo. Nella terminologia DDD, può essere considerata come un livello anti-danneggiamento.

* È consigliabile assegnare un nome significativo per gli argomenti generici.

    A meno che non si scrive codice realmente generico che non è specifico per un particolare dominio, un nome significativo consente agli altri programmatori informazioni sul dominio che viene utilizzato. Ad esempio, un parametro di tipo denominato `'Document` nel contesto dell'interazione con un documento di database è molto più chiaro che i tipi di documento generico possono essere accettati dalla funzione o membro si sta lavorando.

* Si consiglia di denominare i parametri di tipo generico con PascalCase.

    Questo è il modo generale per eseguire operazioni in .NET, pertanto è consigliabile usare PascalCase anziché snake_case o camelCase.

Infine, generalizzazione automatica non è sempre un enorme vantaggio per le persone che hanno familiarità con F# o una codebase di grandi dimensioni. È sovraccarico cognitivo usando i componenti che sono di tipo generici. Inoltre, se automaticamente generalizzata di funzioni non vengono usate con diversi tipi di input (solo se sono destinati a essere usate come tali let), quindi non offre alcun vantaggio reale a tali da generico a quel punto nel tempo. Valutare sempre se si sta scrivendo codice effettivamente trarrà vantaggio dal generico.

## <a name="performance"></a>Prestazioni

F#i valori non sono modificabili per impostazione predefinita, che consente di evitare di determinate classi di bug (in particolare i che implicano parallelismo e concorrenza). Tuttavia, in alcuni casi, per ottenere l'efficienza ottima (o persino ragionevole) del tempo di esecuzione o allocazioni di memoria, un intervallo di lavoro può essere implementato in modo ottimale tramite la modifica sul posto dello stato. Ciò è possibile in modo prevede il consenso esplicito con F# con il `mutable` parola chiave.

Tuttavia, usare `mutable` in F# potrebbero sentirsi incompatibile con la purezza funzionale. Questo è tutto bene, se si modificano le aspettative da purezza al [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency). La trasparenza referenziale - non purezza - è l'obiettivo finale durante la scrittura di F# funzioni. In questo modo è possibile scrivere un'interfaccia funzionale tramite un'implementazione basata su Modifica per il codice critico delle prestazioni.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Eseguire il wrapping di codice modificabile nelle interfacce non modificabile

Con la trasparenza referenziale come obiettivo, è fondamentale per scrivere codice che non espone il underbelly modificabile delle funzioni critiche per le prestazioni. Ad esempio, il codice seguente implementa il `Array.contains` funzionare nel F# libreria di base:

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

Chiamare questa funzione più volte non modifica la matrice sottostante e non è necessario mantenere qualsiasi stato modificabile all'utilizzo dello stesso. È trasparente referenziali, anche se quasi tutte le righe di codice in esso contenuti Usa mutation.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Prendere in considerazione che incapsula dati modificabili nelle classi

L'esempio precedente Usa una singola funzione per incapsulare operazioni usando dati modificabili. Ciò non è sempre sufficiente per set di dati più complessi. Prendere in considerazione i seguenti set di funzioni:

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

Questo codice sia efficiente, ma espongono la struttura di dati basati su mutation che i chiamanti sono responsabili della gestione. Ciò può essere incapsulato all'interno di una classe senza membri sottostanti che è possibile modificare:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` incapsula la struttura di dati basati su mutation sottostante, pertanto senza imporre ai chiamanti di mantenere la struttura dei dati sottostante. Le classi sono un metodo efficace per incapsulare i dati e le routine che sono basati su mutation senza esporre i dettagli per i chiamanti.

### <a name="prefer-let-mutable-to-reference-cells"></a>Preferisce `let mutable` alle celle di riferimento

Le celle di riferimento sono un modo per rappresentare il riferimento a un valore anziché il valore stesso. Anche se possono essere usati per il codice critiche per le prestazioni, in genere non sono consigliate. Si consideri l'esempio seguente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

L'uso di una cella di riferimento adesso "falsifica" tutto il codice successivo con la necessità di dereferenziazione e fare di nuovo riferimento i dati sottostanti. Si consiglia di `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

A parte il singolo punto di mutazione durante l'espressione lambda, tutte le altre code che interessa `acc` possibile farlo in modo che non è diverso per l'utilizzo di un normale `let`-valore modificabile associato. Ciò renderà più semplice la modifica nel corso del tempo.

## <a name="object-programming"></a>Programmazione degli oggetti

F#include il supporto completo per gli oggetti e orientate a oggetti (OO) concetti. Sebbene molti concetti orientato a oggetti sono potenti e utili, non tutte sono ideali per l'utilizzo. Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità orientato a oggetti a livello generale.

**È consigliabile usare queste funzionalità in molte situazioni:**

* La notazione del punto (`x.Length`)
* Membri di istanza
* Costruttori impliciti
* Membri statici
* Notazione dell'indicizzatore (`arr.[x]`)
* Argomenti denominati e facoltativi
* Interfacce e implementazioni di interfaccia

**Non raggiungere prima di tutto per queste funzionalità, ma con cautela applicarle quando essi sono utili risolvere un problema:**

* Overload di un metodo
* Dati modificabile incapsulati
* Operatori nei tipi
* Proprietà automatiche
* Implementazione `IDisposable` e `IEnumerable`
* Estensioni di tipo
* Eventi
* Struct
* Delegati
* Enumerazioni

**A meno che non è necessario utilizzarli in generale evitare queste funzionalità:**

* Le gerarchie di ereditarietà in base al tipo e l'ereditarietà di implementazione
* I valori null e `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferire la composizione di ereditarietà

[Composizione dell'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) va bene un idioma legato F# possa rispettare codice. Il principio fondamentale è che non si devono esporre una classe di base e imporre ai chiamanti di ereditare da tale classe base per ottenere funzionalità.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usare le espressioni di oggetto per implementare le interfacce se non è necessaria una classe

[Espressioni di oggetto](../language-reference/object-expressions.md) consentono di implementare le interfacce in tempo reale, associazione l'interfaccia implementata da un valore senza la necessità di eseguire questa operazione all'interno di una classe. Ciò è utile, soprattutto se si _solo_ necessario implementare l'interfaccia e non sono necessari per una classe completa.

Ad esempio, ecco il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di correzione del codice se è stato aggiunto un simbolo che non hai un `open` informativa per:

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

Poiché non è necessario per una classe quando si interagisce con l'API di Visual Studio Code, le espressioni di oggetto sono uno strumento ideale per questo oggetto. Sono anche utili per gli unit test, quando si desidera sottoporre a stub out un'interfaccia con le routine di test in modalità ad hoc.

## <a name="type-abbreviations"></a>Abbreviazioni dei tipi

[Abbreviazioni di tipo](../language-reference/type-abbreviations.md) sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma della funzione o un tipo più complesso. Ad esempio, viene assegnata un'etichetta per cosa è necessario definire un calcolo con l'alias seguente [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), una libreria di apprendimento avanzato:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Il `Computation` nome è un modo pratico per indicare qualsiasi funzione che corrisponde alla firma è l'aliasing. Uso di abbreviazioni di tipo simile al seguente è utile e consente di codice più conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evitare di usare le abbreviazioni dei tipi per rappresentare il dominio

Sebbene le abbreviazioni dei tipi sono particolarmente utili per fornire un nome alle firme di funzione, possono essere poco chiaro quando l'abbreviazione degli altri tipi. Prendere in considerazione questo abbreviazione:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Ciò può generare confusione in diversi modi:

* `BufferSize` non è un'astrazione; è semplicemente un altro nome per un numero intero.
* Se `BufferSize` viene esposto in un'API pubblica, si possono facilmente essere interpretati erroneamente da indicare più della semplice `int`. In genere, i tipi di dominio dispone di più attributi a tali e non sono tipi primitivi, ad esempio `int`. Questo abbreviazione viola questa ipotesi.
* Le maiuscole e minuscole di `BufferSize` (PascalCase) implica che questo tipo contiene più dati.
* Questo alias non offre una maggiore chiarezza confrontato con la fornitura di un argomento denominato a una funzione.
* L'abbreviazione si manifesta in linguaggio intermedio compilato; è solo un numero intero e questo alias è un costrutto in fase di compilazione.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

In sintesi, il problema con le abbreviazioni dei tipi è però **non** astrazioni sui tipi che sono abbreviando. Nell'esempio precedente, `BufferSize` è semplicemente un' `int` dietro le quinte, con nessuna dati aggiuntivi, né alcun vantaggio dal sistema di tipi oltre a ciò che `int` esiste già.
