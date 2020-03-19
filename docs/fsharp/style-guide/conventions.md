---
title: Convenzioni di codifica F#
description: Informazioni sulle linee guida generali e sui linguaggi durante la scrittura di codice F.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400309"
---
# <a name="f-coding-conventions"></a>Convenzioni di codifica F#

Le convenzioni seguenti sono formulate dall'esperienza di lavoro con codebase F . I [cinque principi di buon codice F ,](index.md#five-principles-of-good-f-code) sono alla base di ogni raccomandazione. Sono correlati alle linee guida per la [progettazione](component-design-guidelines.md)dei componenti F , ma sono applicabili per qualsiasi codice F, non solo per i componenti, ad esempio le librerie.

## <a name="organizing-code"></a>Organizzazione del codice

Funzionalità di F : due modi principali per organizzare il codice: moduli e spazi dei nomi. Questi sono simili, ma hanno le seguenti differenze:

* Gli spazi dei nomi vengono compilati come spazi dei nomi .NET. I moduli vengono compilati come classi statiche.
* Gli spazi dei nomi sono sempre di primo livello. I moduli possono essere di primo livello e nidificati all'interno di altri moduli.
* Gli spazi dei nomi possono estendersi su più file. I moduli non possono.
* I moduli possono `[<RequireQualifiedAccess>]` `[<AutoOpen>]`essere decorati con e .

Le linee guida seguenti consentono di utilizzarli per organizzare il codice.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferisci gli spazi dei nomi al livello superiore

Per qualsiasi codice consumabile pubblicamente, gli spazi dei nomi sono preferenziali ai moduli al livello superiore. Poiché vengono compilati come spazi dei nomi .NET, sono utilizzabili da C , senza problemi.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

L'utilizzo di un modulo di primo livello potrebbe non essere diverso quando viene chiamato solo `MyClass` da `MyCode` F, ma per i consumer di C, i chiamanti potrebbero essere sorpresi di dover qualificarsi con il modulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Applicare con attenzione`[<AutoOpen>]`

Il `[<AutoOpen>]` costrutto può inquinare la portata di ciò che è disponibile per i chiamanti, e la risposta a dove qualcosa viene da è "magia". Non è una buona cosa. Un'eccezione a questa regola è la libreria di base di F , anche se questo fatto è anche un po ' controverso).

Tuttavia, è una comodità se si dispone di funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.

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

In questo modo è possibile separare in modo pulito i dettagli di implementazione dall'API pubblica di una funzione senza dover qualificare completamente un helper ogni volta che viene chiamato.

Inoltre, l'esposizione di metodi di estensione e generatori di `[<AutoOpen>]`espressioni a livello di spazio dei nomi può essere espressa in modo non completo con .

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Utilizzare `[<RequireQualifiedAccess>]` ogni volta che i nomi potrebbero entrare in conflitto o si ritiene che aiuta con la leggibilità

L'aggiunta dell'attributo `[<RequireQualifiedAccess>]` a un modulo indica che il modulo non può essere aperto e che i riferimenti agli elementi del modulo richiedono l'accesso completo esplicito. Ad esempio, `Microsoft.FSharp.Collections.List` il modulo ha questo attributo.

Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che potrebbero entrare in conflitto con i nomi in altri moduli. Richiedere l'accesso qualificato può aumentare notevolmente la manutenibilità a lungo termine e l'evolvabilità di una libreria.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordinare `open` le istruzioni in modo topologico

In F , l'ordine delle dichiarazioni è importante, ad esempio con `open` le istruzioni. Questo è a differenza di `using` c'è, in cui l'effetto di e `using static` è indipendente dall'ordine di tali istruzioni in un file.

In F , gli elementi aperti in un ambito possono nascondere altri già presenti. Ciò significa che `open` le istruzioni di riordino potrebbero modificare il significato del codice. Di conseguenza, qualsiasi ordinamento `open` arbitrario di tutte le istruzioni (ad esempio, alfanumericamente) non è consigliato, per esservi un comportamento diverso che ci si potrebbe aspettare.

Invece, si consiglia di ordinarli [topologicamente](https://en.wikipedia.org/wiki/Topological_sorting); ovvero ordinare le `open` istruzioni nell'ordine in cui sono definiti i _livelli_ del sistema. Si può anche prendere in considerazione l'esecuzione di ordinamento alfanumerico all'interno di diversi livelli topologici.

Ad esempio, ecco l'ordinamento topologico per il file API pubblico del servizio del compilatore F .

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

Si noti che un'interruzione di riga separa i livelli topologici, con ogni livello ordinato alfanumericamente in seguito. Questo organizza correttamente il codice senza eseguire accidentalmente lo shadowing dei valori.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Utilizzare le classi per contenere valori che hanno effetti collateraliUse classes to contain values that have side effects

Esistono molte volte quando l'inizializzazione di un valore può avere effetti collaterali, ad esempio la creazione di un'istanza di un contesto in un database o in un'altra risorsa remota. Si è tentati di inizializzare tali elementi in un modulo e utilizzarlo nelle funzioni successive:It istempting to initialize such things in a module and use it in subsequent functions:

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

Questa è spesso una cattiva idea per alcuni motivi:

Innanzitutto, la configurazione dell'applicazione `dep1` `dep2`viene inserita nella codebase con e . Questo è difficile da gestire in codebase più grandi.

In secondo luogo, i dati inizializzati in modo statico non devono includere valori che non sono thread-safe se il componente stesso utilizzerà più thread. Questo è chiaramente `dep3`violato da .

Infine, l'inizializzazione del modulo viene compilata in un costruttore statico per l'intera unità di compilazione. Se si verifica un errore nell'inizializzazione del valore `TypeInitializationException` let-bound in tale modulo, si manifesta come un che viene quindi memorizzato nella cache per l'intera durata dell'applicazione. Questo può essere difficile da diagnosticare. Di solito c'è un'eccezione interna che si può tentare di ragionare, ma se non c'è, allora non si può dire quale sia la causa principale.

Usare invece una classe semplice per contenere le dipendenze:Instead, just use a simple class to hold dependencies:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Ciò consente quanto segue:

1. Push di qualsiasi stato dipendente all'esterno dell'API stessa.
2. La configurazione può ora essere eseguita al di fuori dell'API.
3. Gli errori di inizializzazione per i `TypeInitializationException`valori dipendenti non si manifestano probabilmente come file .
4. L'API è ora più facile da testare.

## <a name="error-management"></a>Gestione degli errori

La gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e sfumata, e non ci sono proiettili d'argento nel garantire che i sistemi siano a tolleranza di errore e si comportino bene. Le seguenti linee guida dovrebbero offrire indicazioni per la navigazione in questo spazio difficile.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Rappresentare i casi di errore e lo stato non valido nei tipi intrinseci al dominio

Con [le unioni discriminate](../language-reference/discriminated-unions.md), F , consente di rappresentare lo stato del programma difettoso nel sistema di tipi. Ad esempio:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In questo caso, ci sono tre modi noti che il prelievo di denaro da un conto bancario può fallire. Ogni caso di errore è rappresentato nel tipo e può quindi essere gestito in modo sicuro in tutto il programma.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

In generale, se è possibile modellare i diversi modi in cui può **verificarsi** un errore nel dominio, il codice di gestione degli errori non viene più considerato come un elemento analogo a quello che è necessario gestire oltre al normale flusso del programma. È semplicemente una parte del normale flusso del programma, e non considerato **eccezionale**. Ci sono due vantaggi principali a questo:

1. È più facile da gestire quando il dominio cambia nel tempo.
2. I casi di errore sono più facili da unit test.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Utilizzare le eccezioni quando gli errori non possono essere rappresentati con i tipi

Non tutti gli errori possono essere rappresentati in un dominio problematico. Questi tipi di errori sono di natura *eccezionale,* pertanto la possibilità di generare e intercettare le eccezioni in F.

In primo luogo, si consiglia di leggere le linee guida per la progettazione delle [eccezioni](../../standard/design-guidelines/exceptions.md). Questi sono applicabili anche a F .

I costrutti principali disponibili in F , ai fini della generazione di eccezioni devono essere considerati nel seguente ordine di preferenza:

| Funzione | Sintassi | Scopo |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera `System.ArgumentNullException` un con il nome dell'argomento specificato. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera `System.ArgumentException` un con un messaggio e un nome di argomento specificati. |
| `invalidOp` | `invalidOp "message"` | Genera `System.InvalidOperationException` un con il messaggio specificato. |
|`raise`| `raise (ExceptionType("message"))` | Meccanismo generico per la generazione di eccezioni. |
| `failwith` | `failwith "message"` | Genera `System.Exception` un con il messaggio specificato. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera `System.Exception` un con un messaggio determinato dalla stringa di formato e dai relativi input. |

Utilizzare `nullArg` `invalidArg` , `invalidOp` e come `ArgumentNullException`meccanismo per generare , `ArgumentException` e `InvalidOperationException` quando appropriato.

Le `failwith` `failwithf` funzioni e in genere devono `Exception` essere evitate perché generano il tipo di base, non un'eccezione specifica. In base alle Linee guida per la progettazione delle [eccezioni](../../standard/design-guidelines/exceptions.md), si desidera generare eccezioni più specifiche quando è possibile.

### <a name="using-exception-handling-syntax"></a>Utilizzo della sintassi di gestione delle eccezioni

F , supporta i `try...with` modelli di eccezione tramite la sintassi:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

La riconciliazione della funzionalità da eseguire in caso di eccezione con criteri di ricerca può essere un po' complessa se si desidera mantenere pulito il codice. Uno di questi modi per gestire questa situazione consiste nell'utilizzare [i modelli attivi](../language-reference/active-patterns.md) come mezzo per raggruppare la funzionalità che circonda un caso di errore con un'eccezione stessa. Ad esempio, è possibile utilizzare un'API che, quando genera un'eccezione, racchiude informazioni importanti nei metadati dell'eccezione. Annullare il wrapping di un valore utile nel corpo dell'eccezione acquisita all'interno del modello attivo e restituire tale valore può essere utile in alcune situazioni.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Non utilizzare la gestione degli errori monadica per sostituire le eccezioni

Le eccezioni sono considerate un po' tabù nella programmazione funzionale. Infatti, le eccezioni violano la purezza, quindi è sicuro considerarle non abbastanza funzionali. Tuttavia, questo ignora la realtà di dove deve essere eseguito il codice e che possono verificarsi errori di runtime. In generale, scrivere codice sul presupposto che la maggior parte delle cose non sono né puro né totale, per ridurre al minimo spiacevoli sorprese.

È importante considerare i seguenti punti di forza/aspetti di base delle eccezioni in relazione alla loro pertinenza e appropriatezza nel runtime .NET e nell'ecosistema multilingua nel suo complesso:

1. Essi contengono informazioni diagnostiche dettagliate, che è molto utile quando si esegue il debug di un problema.
2. Sono ben compresi dal runtime e da altri linguaggi .NET.
3. Possono ridurre boilerplate significativo rispetto al codice che va fuori del suo modo di *evitare* eccezioni implementando qualche sottoinsieme della loro semantica su una base ad hoc.

Questo terzo punto è fondamentale. Per le operazioni complesse non banali, la mancata utilizzo delle eccezioni può comportare la gestione di strutture come questa:

```fsharp
Result<Result<MyType, string>, string list>
```

Che può facilmente portare a codice fragile come pattern matching su errori "tipizzati a stringa":

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Inoltre, si può essere tentati di ingoiare qualsiasi eccezione nel desiderio di una funzione "semplice" che restituisce un tipo "bello":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Sfortunatamente, `tryReadAllText` può generare numerose eccezioni in base alla miriade di cose che possono accadere in un file system e questo codice elimina tutte le informazioni su ciò che potrebbe effettivamente andare storto nel proprio ambiente. Se si sostituisce questo codice con un tipo di risultato, si torna all'analisi dei messaggi di errore "con tipo stringa":

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

E l'inserimento dell'oggetto eccezione stesso nel `Error` costruttore impone solo di gestire correttamente il tipo di eccezione nel sito di chiamata anziché nella funzione. In questo modo in modo efficace crea eccezioni controllate, che sono notoriamente poco divertente da gestire come chiamante di un'API.

Una buona alternativa agli esempi precedenti consiste nell'intercettare eccezioni *specifiche* e restituire un valore significativo nel contesto di tale eccezione. Se si `tryReadAllText` modifica la `None` funzione come segue, ha più significato:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Invece di funzionare come un catch-all, questa funzione ora gestirà correttamente il caso quando un file non è stato trovato e assegnare tale significato a un ritorno. Questo valore restituito può eseguire il mapping a tale caso di errore, senza eliminare le informazioni contestuali o forzare i chiamanti a gestire un caso che potrebbe non essere rilevante in quel punto del codice.

I tipi, ad `Result<'Success, 'Error>` esempio, sono appropriati per le operazioni di base in cui non sono annidati e i tipi facoltativi F , sono perfetti per rappresentare quando un elemento può restituire *qualcosa* o *niente.* Tuttavia, non sostituiscono le eccezioni e non devono essere utilizzati nel tentativo di sostituire le eccezioni. Piuttosto, dovrebbero essere applicati con giudizio per affrontare aspetti specifici della politica di gestione delle eccezioni e degli errori in modi mirati.

## <a name="partial-application-and-point-free-programming"></a>Applicazione parziale e programmazione senza punti

F è supporta l'applicazione parziale e, pertanto, vari modi per programmare in uno stile senza punti. Questo può essere utile per il riutilizzo del codice all'interno di un modulo o l'implementazione di qualcosa, ma non è qualcosa da esporre pubblicamente. In generale, la programmazione senza punti non è una virtù in sé e per sé e può aggiungere una barriera cognitiva significativa per le persone che non sono immerse nello stile.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Non usare applicazioni parziali e currying in API pubblicheDo not use partial application and currying in public APIs

Con poche eccezioni, l'uso dell'applicazione parziale nelle API pubbliche può creare confusione per i consumer. In `let`genere, i valori associati a -e-bound nel codice F , sono **valori**, non **valori di funzione**. La combinazione di valori e valori di funzione può comportare il salvataggio di un numero ridotto di `>>` righe di codice in cambio di un bel po ' di sovraccarico cognitivo, soprattutto se combinato con operatori come comporre funzioni.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Considerare le implicazioni degli strumenti per la programmazione senza punti

Le funzioni sottoposte a currysima non etichettano i relativi argomenti. Questo ha implicazioni di strumenti. Si considerino le due funzioni seguenti:Consider the following two functions:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Entrambe sono funzioni `funcWithApplication` valide, ma è una funzione sottoposta a currysima. Quando si passa il mouse sui relativi tipi in un editor, viene visualizzato quanto segue:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

Nel sito di chiamata, le descrizioni comandi negli strumenti come Visual `string` Studio `int` non foranno informazioni significative su ciò che i tipi di input e rappresentano effettivamente.

Se si incontra codice `funcWithApplication` senza punti come quello che è pubblicamente consumabile, si consiglia di fare un'espansione completa in modo che gli strumenti possono raccogliere nomi significativi per gli argomenti.

Inoltre, il debug di codice privo di punti può essere difficile, se non impossibile. Gli strumenti di debug si basano `let` su valori associati a nomi (ad esempio, associazioni) in modo che sia possibile esaminare i valori intermedi a metà dell'esecuzione. Quando il codice non ha valori da controllare, non c'è nulla di cui eseguire il debug. In futuro, gli strumenti di debug potrebbero evolvere per sintetizzare questi valori in base ai percorsi eseguiti in precedenza, ma non è una buona idea coprire le scommesse su *potenziali* funzionalità di debug.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Considerare l'applicazione parziale come una tecnica per ridurre la boilerplate interna

A differenza del punto precedente, l'applicazione parziale è uno strumento meraviglioso per ridurre boilerplate all'interno di un'applicazione o le profondità interne di un'API. Può essere utile per unit test l'implementazione di API più complesse, in cui boilerplate è spesso un problema da gestire. Ad esempio, il codice seguente mostra come è possibile ottenere ciò che la maggior parte dei framework di simulazione offrono senza prendere una dipendenza esterna da tale framework e dover imparare un'API su misura correlata.

Si consideri ad esempio la topografia della soluzione seguente:For example, consider the following solution toography:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj`potrebbe esporre codice come:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Unit `Transactions.doTransaction` test `ImplementationLogic.Tests.fsproj` in è facile:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

L'applicazione `doTransaction` parziale con un oggetto di contesto fittizio consente di chiamare la funzione in tutti gli unit test senza dover costruire ogni volta un contesto fittizio:Partially applying with a mocking context object lets you call the function in all of your unit tests without needing construct a mocked context each time:

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

Questa tecnica non deve essere applicata universalmente all'intera codebase, ma è un buon modo per ridurre boilerplate per interni complicati e unit test tali elementi interni.

## <a name="access-control"></a>Controllo di accesso

Per il controllo [di accesso,](../language-reference/access-control.md)f è disponibile più opzioni, ereditate da quelle disponibili nel runtime di .NET. Questi non sono utilizzabili solo per i tipi - è possibile utilizzarli anche per le funzioni.

* Preferisci`public` tipi e membri non disponibili fino a quando non ne hai bisogno per essere pubblicamente consumabili. Questo riduce al minimo anche ciò che i consumatori coppia a.
* Sforzarsi di mantenere `private`tutte le funzionalità di supporto .
* Si consideri `[<AutoOpen>]` l'uso di in un modulo privato di funzioni di supporto se diventano numerosi.

## <a name="type-inference-and-generics"></a>Inferenza del tipo e genericsType inference and generics

L'inferenza del tipo può evitare di digitare un sacco di boilerplate. E la generalizzazione automatica nel compilatore F , può aiutare a scrivere codice più generico senza quasi alcuno sforzo aggiuntivo da parte vostra. Tuttavia, queste caratteristiche non sono universalmente buone.

* Valutare la possibilità di etichettare i nomi degli argomenti con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza dei tipi per questo scopo.

    Il motivo è che **si** dovrebbe avere il controllo della forma dell'API, non il compilatore. Anche se il compilatore può eseguire un ottimo lavoro nell'inferenza dei tipi per l'utente, è possibile modificare la forma dell'API se gli elementi interni su cui si basa hanno tipi modificati. Questo può essere quello che vuoi, ma quasi certamente si tradurrà in una modifica DELL'API di rottura che i consumatori a valle dovranno quindi affrontare. Al contrario, se controlli in modo esplicito la forma dell'API pubblica, puoi controllare queste modifiche di rilievo. In termini DDD, questo può essere considerato come un livello anti-corruzione.

* È consigliabile assegnare un nome significativo agli argomenti generici.

    A meno che non si stia scrivendo codice veramente generico che non sia specifico di un particolare dominio, un nome significativo può aiutare altri programmatori a comprendere il dominio in cui stanno lavorando. Ad esempio, un `'Document` parametro di tipo denominato nel contesto dell'interazione con un database di documenti rende più chiaro che i tipi di documento generici possono essere accettati dalla funzione o dal membro con cui si sta lavorando.

* Valutare la possibilità di denominare i parametri di tipo generico con PascalCase.Consider naming generic type parameters with PascalCase.

    Questo è il modo generale per eseguire operazioni in .NET, pertanto è consigliabile usare PascalCase anziché snake_case o camelCase.

Infine, la generalizzazione automatica non è sempre una manna per gli utenti che non hanno familiarità con F o una base di codice di grandi dimensioni. L'utilizzo di componenti generici comporta un sovraccarico cognitivo. Inoltre, se le funzioni generalizzate automaticamente non vengono utilizzate con tipi di input diversi (per non parlare se sono destinate a essere utilizzate come tali), non vi è alcun vantaggio reale per loro di essere generici in quel momento. Considerare sempre se il codice che si sta scrivendo trarrà effettivamente vantaggio dall'essere generico.

## <a name="performance"></a>Prestazioni

### <a name="prefer-structs-for-small-data-types"></a>Preferisci struct per tipi di dati di piccole dimensioni

L'uso di struct (chiamati anche tipi di valore) può spesso comportare prestazioni più elevate per un codice perché in genere evita l'allocazione di oggetti. Tuttavia, gli struct non sono sempre un pulsante "go faster": se la dimensione dei dati in uno struct supera i 16 byte, la copia dei dati può spesso comportare una maggiore produttività rispetto all'utilizzo di un tipo di riferimento.

Per determinare se è necessario utilizzare uno struct, considerare le condizioni seguenti:To determine if you should use a struct, consider the following conditions:

- Se le dimensioni dei dati sono di 16 byte o inferiori.
- Se è probabile che molti di questi tipi di dati siano residenti in memoria in un programma in esecuzione.

Se si applica la prima condizione, è in genere necessario usare uno struct. Se si applicano entrambi, è necessario usare quasi sempre uno struct. Ci possono essere alcuni casi in cui si applicano le condizioni precedenti, ma l'utilizzo di uno struct non è migliore o peggiore rispetto all'utilizzo di un tipo di riferimento, ma è probabile che siano rari. È importante misurare sempre quando si apportano modifiche come questa, però, e non operare su ipotesi o intuizione.

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>Preferisci le tuple struct quando si raggruppano tipi di valori di piccole dimensioni

Si considerino le due funzioni seguenti:Consider the following two functions:

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

Quando si confrontano queste funzioni con uno strumento di benchmarking `runWithStructTuple` statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che la funzione che utilizza tuple struct viene eseguita il 40% più velocemente e non alloca memoria.

Tuttavia, questi risultati non saranno sempre il caso nel proprio codice. Se si contrassegna `inline`una funzione come , il codice che utilizza tuple di riferimento può ottenere alcune ottimizzazioni aggiuntive o codice che verrà allocato potrebbe semplicemente essere ottimizzato. Si dovrebbe sempre misurare i risultati ogni volta che le prestazioni sono interessate, e non operare mai sulla base di presupposti o intuizioni.

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>Preferisci i record struct quando il tipo di dati è piccolo

La regola generale descritta in precedenza vale anche per i [tipi di record F .](../language-reference/records.md) Considerare i tipi di dati e le funzioni seguenti che li elaborano:Consider the following data types and functions that process them:

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

È simile al codice di tupla precedente, ma questa volta l'esempio usa record e una funzione interna inline.

Quando si confrontano queste funzioni con uno strumento di benchmarking `processStructPoint` statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che viene eseguito quasi il 60% più velocemente e non alloca nulla nell'heap gestito.

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>Preferire le unioni discriminate struct quando il tipo di dati è piccolo

Le osservazioni precedenti sulle prestazioni con tuple struct e record sono inoltre valida per [le unioni discriminate](../language-reference/discriminated-unions.md)di F . Esaminare il codice seguente:

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

È comune definire unioni discriminate con un solo caso come questa per la modellazione di dominio. Quando si confrontano queste funzioni con uno strumento di benchmarking statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `structReverseName` viene eseguito circa il 25% più velocemente rispetto `reverseName` alle stringhe di piccole dimensioni. Per le stringhe di grandi dimensioni, entrambe le prestazioni più o meno lo stesso. Quindi, in questo caso, è sempre preferibile usare uno struct. Come accennato in precedenza, misurare sempre e non operare su presupposti o intuizioni.

Anche se l'esempio precedente ha mostrato che una struttura Discriminateed Union ha prodotto prestazioni migliori, è comune avere unioni discriminate più grandi durante la modellazione di un dominio. Tipi di dati più grandi di questo tipo potrebbero non funzionare altrettanto bene se sono struct a seconda delle operazioni su di essi, poiché potrebbero essere coinvolti più copie.

### <a name="functional-programming-and-mutation"></a>Programmazione funzionale e mutazione

I valori di F , non sono modificabili per impostazione predefinita, che consente di evitare determinate classi di bug (in particolare quelli che coinvolgono la concorrenza e il parallelismo). Tuttavia, in alcuni casi, al fine di ottenere un'efficienza ottimale (o anche ragionevole) del tempo di esecuzione o allocazioni di memoria, un intervallo di lavoro può essere implementato meglio utilizzando la mutazione di stato sul posto. Ciò è possibile in una base opt-in con F , con la `mutable` parola chiave.

L'uso di `mutable` in F , può essere in contrasto con la purezza funzionale. Questo è comprensibile, ma la purezza funzionale ovunque può essere in contrasto con gli obiettivi di prestazioni. Un compromesso consiste nell'incapsulare la mutazione in modo che i chiamanti non devono preoccuparsi di ciò che accade quando chiamano una funzione. In questo modo è possibile scrivere un'interfaccia funzionale su un'implementazione basata su mutazione per il codice critico per le prestazioni.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Eseguire il wrapping di codice modificabile in interfacce non modificabiliWrap mutable code in unmutable interfaces

Con la trasparenza referenziale come obiettivo, è fondamentale scrivere codice che non esponga il ventre modificabile delle funzioni critiche per le prestazioni. Ad esempio, il codice `Array.contains` seguente implementa la funzione nella libreria di base di F , che segue:

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

La chiamata di questa funzione più volte non modifica la matrice sottostante, né richiede di mantenere qualsiasi stato modificabile nell'utilizzo. È referenzialmente trasparente, anche se quasi ogni riga di codice al suo interno utilizza la mutazione.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Considerare l'incapsulamento di dati modificabili nelle classiConsider encapsulating mutable data in classes

Nell'esempio precedente è stata utilizzata una singola funzione per incapsulare le operazioni utilizzando dati modificabili. Questo non è sempre sufficiente per set di dati più complessi. Si considerino i seguenti set di funzioni:

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

Questo codice è performante, ma espone la struttura di dati basata sulla mutazione che i chiamanti sono responsabili della gestione. È possibile eseguire il wrapping all'interno di una classe senza membri sottostanti che possono essere modificati:This can be wrapped inside of a class with no underlying members that can change:

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

`Closure1Table`incapsula la struttura di dati basata sulla mutazione sottostante, non costringendo i chiamanti a mantenere la struttura di dati sottostante. Le classi sono un modo efficace per incapsulare dati e routine basate su mutazioni senza esporre i dettagli ai chiamanti.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Preferire `let mutable` fare riferimento alle celle

Le celle di riferimento sono un modo per rappresentare il riferimento a un valore anziché il valore stesso. Sebbene possano essere utilizzati per il codice critico per le prestazioni, non sono consigliati. Prendere in considerazione gli esempi seguenti:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

L'uso di una cella di riferimento ora "inquina" tutto il codice successivo con la dover dereferenziare e rireferenziare i dati sottostanti. Invece, `let mutable`considerare :

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

A parte il singolo punto di mutazione nel mezzo dell'espressione `acc` lambda, tutto il codice che tocca può farlo `let`in un modo che non è diverso dall'uso di un valore non modificabile associato a normal. Questo renderà più facile cambiare nel tempo.

## <a name="object-programming"></a>Programmazione di oggetti

F è il supporto completo per gli oggetti e concetti orientati agli oggetti (OO). Anche se molti concetti di OO sono potenti e utili, non tutti sono ideali da usare. Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità OO a livello generale.

**Considerare l'utilizzo di queste funzionalità in molte situazioni:Consider using these features in many situations:**

* Notazione del`x.Length`punto ( )
* Membri di istanza
* Costruttori impliciti
* Membri statici
* Notazione indicizzatore (`arr.[x]`)
* Argomenti denominati e facoltativi
* Interfacce e implementazioni di interfacce

**Non raggiungere per queste caratteristiche prima, ma non applicarle giudiziosamente quando sono convenienti per risolvere un problema:**

* Overload di un metodo
* Dati modificabili incapsulatiEncapsulated mutable data
* Operatori sui tipi
* Proprietà automatiche
* Implementazione `IDisposable` e`IEnumerable`
* Estensioni del tipo
* Eventi
* Struct
* Delegati
* Enumerazioni

**In genere evitare queste funzionalità a meno che non sia necessario utilizzarle:**

* Gerarchie di tipi basate sull'ereditarietà e ereditarietà dell'implementazione
* Null e`Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferire la composizione all'ereditarietà

[La composizione sull'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) è un linguaggio di lunga data che può rispettare un buon codice F. Il principio fondamentale è che non è necessario esporre una classe base e forzare i chiamanti a ereditare da tale classe di base per ottenere funzionalità.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Usare le espressioni di oggetto per implementare le interfacce se non è necessaria una classeUse object expressions to implement interfaces if you don't need a class

[Le espressioni di](../language-reference/object-expressions.md) oggetto consentono di implementare interfacce in tempo reale, associando l'interfaccia implementata a un valore senza dover eseguire questa operazione all'interno di una classe. Ciò è utile, soprattutto se è _necessario implementare solo_ l'interfaccia e non è necessario per una classe completa.

Ad esempio, ecco il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di `open` correzione del codice se è stato aggiunto un simbolo per il fatto per il seguente:

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

Poiché non è necessaria una classe quando si interagisce con l'API del codice di Visual Studio, le espressioni di oggetto sono uno strumento ideale per questo. Sono inoltre utili per gli unit test, quando si desidera eseguire lo stub di un'interfaccia con routine di test in modo ad hoc.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Considerare le abbreviazioni di tipo per abbreviare le firmeConsider Type Abbreviations to shorten signatures

[Abbreviazioni](../language-reference/type-abbreviations.md) di tipo sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma di funzione o un tipo più complesso. Ad esempio, l'alias seguente assegna un'etichetta a ciò che è necessario per definire un calcolo con [CNTK](https://docs.microsoft.com/cognitive-toolkit/), una libreria di deep learning:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Il `Computation` nome è un modo pratico per indicare qualsiasi funzione che corrisponde alla firma che è aliasing. L'utilizzo di abbreviazioni di tipo come questa è conveniente e consente codice più conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evitare di utilizzare abbreviazioni di tipo per rappresentare il dominio

Anche se le abbreviazioni di tipo sono utili per assegnare un nome alle firme delle funzioni, possono creare confusione quando si abbreviano altri tipi. Si consideri questa abbreviazione:Consider this abbreviation:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Questo può essere fonte di confusione in diversi modi:This can be confusing in multiple ways:

* `BufferSize`non è un'astrazione; è solo un altro nome per un numero intero.
* Se `BufferSize` viene esposto in un'API pubblica, può essere `int`facilmente interpretato erroneamente per significare più di un semplice . In genere, i tipi di dominio hanno più `int`attributi e non sono tipi primitivi come . Questa abbreviazione viola tale ipotesi.
* L'utilizzo `BufferSize` di maiuscole e minuscole di (PascalCase) implica che questo tipo contiene più dati.
* Questo alias non offre maggiore chiarezza rispetto a fornire un argomento denominato a una funzione.
* L'abbreviazione non si manifesterà nel linguaggio intermedio compilato; è solo un numero intero e questo alias è un costrutto in fase di compilazione.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

In sintesi, la trappola con le abbreviazioni di tipo è che **non** sono astrazioni sui tipi che stanno abbreviando. Nell'esempio precedente, `BufferSize` è `int` solo un sotto le coperte, senza dati aggiuntivi, `int` né alcun beneficio dal sistema di tipi oltre a quello che già ha.

Un approccio alternativo all'utilizzo delle abbreviazioni di tipo per rappresentare un dominio consiste nell'utilizzare unioni discriminate caso singolo. Il campione precedente può essere modellato come segue:The previous sample can be modeled as follows:

```fsharp
type BufferSize = BufferSize of int
```

Se si scrive codice che `BufferSize` opera in termini di e il relativo valore sottostante, è necessario costruirne uno anziché passare qualsiasi intero arbitrario:If you write code that operates in terms of and its underlying value, you need to construct one rather than pass in any arbitrary integer:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

In questo modo si riduce la probabilità di `send` passare erroneamente un `BufferSize` numero intero arbitrario nella funzione, perché il chiamante deve costruire un tipo per eseguire il wrapping di un valore prima di chiamare la funzione.
