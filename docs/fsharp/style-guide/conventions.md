---
title: 'Convenzioni nel codice F #'
description: 'Altre linee guida generali e idiomi durante la scrittura di codice F #.'
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457982"
---
# <a name="f-coding-conventions"></a>Convenzioni nel codice F #

Le seguenti convenzioni vengono formulate dal esperienza di utilizzo di grandi dimensioni F # codebase. Il [cinque principi di codice F # buona](index.md#five-principles-of-good-f-code) sono alla base di ogni indicazione. Che sono correlati i [F # componente linee guida di progettazione](component-design-guidelines.md), ma sono applicabili a qualsiasi codice F #, non solo i componenti quali librerie.

## <a name="organizing-code"></a>Organizzazione del codice

F # offre due modi principali per organizzare codice: moduli e gli spazi dei nomi. Questi sono simili, ma hanno le differenze seguenti:

* Spazi dei nomi vengono compilate come spazi dei nomi .NET. I moduli vengono compilati come le classi statiche.
* Spazi dei nomi sono sempre di livello superiore. Moduli possono essere nidificati all'interno di altri moduli e livello superiore.
* Spazi dei nomi può estendersi su più file. I moduli non possono.
* I moduli possono essere decorati con `[<RequireQualifiedAccess>]` e `[<AutoOpen>]`.

Le linee guida seguenti consentono di questi elementi usati per organizzare il codice.

### <a name="prefer-namespaces-at-the-top-level"></a>Preferiscono gli spazi dei nomi al livello superiore

Per qualsiasi codice pubblicamente utilizzabile, spazi dei nomi sono preferenziale al moduli al livello superiore. Poiché vengono compilate come spazi dei nomi .NET, sono utilizzabile da parte di c# con alcun problema.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Utilizzo di un modulo di livello superiore potrebbe non essere visualizzati diverso quando viene chiamato solo da F #, ma per c# consumer, i chiamanti potrebbero essere sorprendente dover qualificare `MyClass` con il `MyCode` modulo.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Applicare attentamente `[<AutoOpen>]`

Il `[<AutoOpen>]` costrutto può inquina l'ambito di ciò che è disponibile per i chiamanti e la risposta a un elemento da cui proviene è "magica". Non si tratta in genere un vantaggio. Un'eccezione a questa regola è la libreria di base F # stesso (anche se ciò è anche un po' controversi).

Tuttavia, è utile se si dispone di funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.

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

Ciò consente di dettagli di implementazione separata correttamente dall'API pubblica di una funzione senza dover specificare in modo completo un helper ogni volta che è possibile chiamare.

Inoltre, che espone i metodi di estensione e generatori di espressioni a livello di spazio dei nomi può essere perfettamente espresso con `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Utilizzare `[<RequireQualifiedAccess>]` ogni volta che i nomi potrebbero essere in conflitto o si ritiene è utile con una maggiore leggibilità

Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita qualificato l'accesso. Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.

Ciò è utile quando le funzioni e valori nel modulo hanno nomi che sono probabile che sia in conflitto con i nomi di altri moduli. Che richiedono l'accesso completo può aumentare notevolmente la facilità di gestione a lungo termine ed evolvability di una libreria.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Ordinamento `open` istruzioni topologicamente

In F #, è importante l'ordine delle dichiarazioni, inclusi con `open` istruzioni. Diversamente dalla c#, in cui l'effetto della `using` e `using static` sono indipendenti l'ordinamento di tali istruzioni in un file.

In F #, elementi aperti in un ambito possono nascondere altri è già presente. Ciò significa che il riordinamento `open` istruzioni è stato possibile modificare il significato del codice. Di conseguenza, qualsiasi arbitrario l'ordinamento di tutti i `open` istruzioni (ad esempio, in ordine alfanumerico) non è consigliabile, almeno generare un comportamento diverso che ci si potrebbe aspettare.

In alternativa, è consigliabile che li si ordina [topologicamente](https://en.wikipedia.org/wiki/Topological_sorting); vale a dire, ordinare i `open` istruzioni nell'ordine in cui _livelli_ del sistema sono definiti. In questo alfanumerico ordinamento all'interno di diversi livelli topologici può anche essere considerato.

Ad esempio, ecco topologiche l'ordinamento per il file F # del compilatore servizio pubblico API:

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

Si noti che un'interruzione di riga separa topologici livelli, con ogni livello ordinata in ordine alfanumerico in un secondo momento. Normalmente, ciò consente di organizzare codice senza accidentalmente shadowing valori.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Usare le classi per contenere i valori che hanno effetti collaterali

Esistono più volte quando un valore di inizializzazione può avere effetti collaterali, ad esempio creare un'istanza di un contesto per un database o un'altra risorsa remota. Può essere tentati di inizializzare elementi in un modulo e usarla nelle funzioni successive:

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

Si tratta spesso una buona idea per una serie di motivi:

In primo luogo, configurazione dell'applicazione viene inserita nella codebase con `dep1` e `dep2`. Questo è difficile da gestire nel codebase più grande.

I dati in secondo luogo, inizializzati in modo statico non devono includere valori che non sono thread-safe se il componente verrà utilizzato più thread. In questo modo più chiaro viene violato da `dep3`.

Infine, inizializzazione del modulo viene compilato in un costruttore statico per l'intera unità di compilazione. Se si verifica un errore nell'inizializzazione associati a let di valore in tale modulo, si manifesta come una `TypeInitializationException` che viene quindi memorizzato nella cache per l'intera durata dell'applicazione. Ciò può essere difficile da diagnosticare. È in genere un'eccezione interna che è possibile tentare valutarlo, ma se non esiste, non è possibile sapere in anticipo qual è la causa principale.

Usare invece solo una classe semplice per contenere dipendenze:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Ciò consente quanto segue:

1. Il push qualsiasi stato dipendenti di fuori dell'API.
2. Configurazione ora può essere eseguita all'esterno dell'API.
3. Errori di inizializzazione per i valori dipendenti non sono più probabile che un `TypeInitializationException`.
4. L'API è ora più semplice eseguire il test.

## <a name="error-management"></a>Gestione degli errori

Gestione degli errori nei sistemi di grandi dimensioni è un complicata complessa e immagini, ed non esistono alcun silver punti elenco nell'assicurare i sistemi sono a tolleranza di errore e si comportano anche. Le linee guida seguenti devono offrire indicazioni fornite in questo spazio difficile passare.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Rappresentano casi di errore e lo stato non valido in tipi intrinseci al dominio

Con [unioni discriminate](../language-reference/discriminated-unions.md), F # offre la possibilità di rappresentare lo stato del programma non corretto nel sistema di tipo. Ad esempio:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In questo caso, esistono tre modi noti prelievo di denaro da un conto bancario può avere esito negativo. Ogni caso di errore è rappresentata nel tipo e può pertanto essere affrontato in modo sicuro in tutto il programma.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

In generale, se è possibile modellare i diversi modi per ottenere un determinato può **esito negativo** nel dominio, quindi la gestione del codice di errore non viene non è più considerato come un elemento devono essere gestiti con oltre il flusso di programma regolare. È semplicemente una parte del flusso di programma normale e non è considerato **eccezionali**. Esistono due vantaggi principali al seguente:

1. È più facile da gestire come dominio cambia nel tempo.
2. Casi di errore sono più semplici lo unit test.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Utilizzare le eccezioni quando gli errori non possono essere rappresentati con i tipi

Non tutti gli errori possono essere rappresentati in un dominio del problema. Questi tipi di errori vengono *eccezionali* in natura, pertanto la possibilità di generare e intercettare le eccezioni in F #.

In primo luogo, si consiglia di leggere il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md). Queste sono applicabili anche a F #.

I costrutti principali disponibili in F # ai fini della generazione di eccezioni devono essere considerati nell'ordine di preferenza seguente:

| Funzione | Sintassi | Scopo |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Genera un `System.ArgumentNullException` con il nome dell'argomento specificato. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Genera un `System.ArgumentException` con un nome dell'argomento specificato e un messaggio. |
| `invalidOp` | `invalidOp "message"` | Genera un `System.InvalidOperationException` con il messaggio specificato. |
|`raise`| `raise (ExceptionType("message"))` | Meccanismo generico per la generazione di eccezioni. |
| `failwith` | `failwith "message"` | Genera un `System.Exception` con il messaggio specificato. |
| `failwithf` | `failwithf "format string" argForFormatString` | Genera un `System.Exception` con un messaggio determinato dalla stringa di formato e i relativi input. |

Uso `nullArg`, `invalidArg` e `invalidOp` come meccanismo di generare `ArgumentNullException`, `ArgumentException` e `InvalidOperationException` quando appropriato.

Il `failwith` e `failwithf` le funzioni in genere sconsigliate poiché essi elevare la base `Exception` digitare, non un'eccezione specifica. Come per il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md), che si desidera generare eccezioni più specifiche, quando possibile.

### <a name="using-exception-handling-syntax"></a>Utilizzando la sintassi di gestione delle eccezioni

F # supporta i modelli di eccezione tramite la `try...with` sintassi:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Riconciliazione delle funzionalità per eseguire in caso di un'eccezione con criteri di ricerca può essere difficile se si desidera conservare il codice di pulizia. Un modo per gestire questo comportamento consiste nell'utilizzare [criteri attivi](../language-reference/active-patterns.md) come mezzo per la funzionalità di gruppo che circonda un caso di errore con un'eccezione se stesso. Ad esempio, può essere utilizzato un'API che, quando viene generata un'eccezione include informazioni utili nei metadati dell'eccezione. Annullamento del wrapping di un valore utile nel corpo dell'eccezione acquisito all'interno di (modello attivo) e la restituzione di valore può essere utile in alcune situazioni.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Non utilizzare monadic gestione degli errori per sostituire le eccezioni

Le eccezioni vengono considerate in qualche modo tabù nella programmazione funzionale. In effetti, le eccezioni violano purezza, pertanto è opportuno considerare tali siamo ancora pronti non funzionale. Tuttavia, che ignora la realtà in cui è necessario eseguire codice e che possono verificarsi errori di runtime. In generale, è possibile scrivere codice sul presupposto che la maggior parte delle operazioni non sono pure né totale, per ridurre al minimo eliminando sorprese.

È importante prendere in considerazione i seguenti dei componenti di base punti di forza/aspetti delle eccezioni rispetto alla loro pertinenza e può risultare appropriato nell'ecosistema di lingue diverse e del runtime di .NET nel suo complesso:

1. Contengono informazioni dettagliate di diagnostica, che è molto utile durante il debug di un problema.
2. Sono ben definiti dal runtime e altri linguaggi .NET.
3. Consentono di ridurre boilerplate significativo quando vengono confrontati con il codice che esce dal dirigendo verso *evitare* eccezioni implementando un subset dei loro semantica in base ad hoc.

Il terzo punto è fondamentale. Per operazioni complesse complessa, mancato utilizzo di eccezioni può comportare la gestione di strutture simile al seguente:

```fsharp
Result<Result<MyType, string>, string list>
```

Che può causare facilmente codice fragili come criteri di ricerca in caso di errori "stringly tipizzati":

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Inoltre, può essere tentato di inghiottire qualsiasi eccezione desiderio di una funzione "semplice" che restituisce un tipo "coloro":

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Sfortunatamente, `tryReadAllText` può generare numerose eccezioni in base alle numerose operazioni che possono essere eseguiti su un file system e il codice elimina le informazioni relative ciò che potrebbe effettivamente essere la causa nel proprio ambiente. Se si sostituisce il codice con un tipo di risultato, è possibile nuovamente per l'analisi del messaggio "stringly tipizzati" errore:

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

E l'oggetto eccezione stesso l'inserimento nel `Error` costruttore impone soltanto è possibile gestire in modo corretto con il tipo di eccezione nel sito di chiamata, anziché nella funzione. In questo modo efficace crea eccezioni controllate, che sono notoriamente unfun occuparsi come un chiamante di un'API.

Una valida alternativa per gli esempi precedenti consiste nell'intercettare *specifici* eccezioni e restituire un valore significativo nel contesto di tale eccezione. Se si modifica il `tryReadAllText` funzionare nel modo seguente, `None` ha un significato più:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Anziché funziona come un catch-all, questa funzione ora gestirà correttamente il case quando un file non è stato trovato e assegnare tale significato a una restituzione. Questo valore restituito possibile eseguire il mapping in questo caso di errore, mentre non eliminando eventuali informazioni contestuali o imporre ai chiamanti di affrontare un case che potrebbe non essere pertinente a questo punto nel codice.

I tipi, ad esempio `Result<'Success, 'Error>` appropriati per le operazioni di base in cui essi non sono annidati e i tipi di parametro facoltativi di F # sono ideali per la rappresentazione quando un elemento è stato possibile restituirlo *qualcosa* o *nothing*. Non sono una sostituzione per le eccezioni, tuttavia e non può essere utilizzati per sostituire le eccezioni nel tentativo. Piuttosto, che devono essere applicati cautela ad aspetti specifici indirizzi di eccezione e criteri di gestione degli errori in modi destinazione.

## <a name="partial-application-and-point-free-programming"></a>Applicazione parziale e la programmazione senza punto

F # supporta applicazione parziale e quindi vari modi per programma in uno stile senza punto. Ciò può essere utile per il riutilizzo del codice all'interno di un modulo o l'implementazione di un oggetto, ma non è in genere per esporre pubblicamente. In generale, programmazione senza punto non è un virtù in e di se stesso e può aggiungere un ostacolo significativo cognitivo per gli utenti che non sono immerso nello stile.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Non utilizzare applicazione parziale e currying nelle API pubbliche

Con un'eccezione little, l'utilizzo dell'applicazione parziale nelle API pubbliche può generare confusione per i consumer. In genere `let`-sono valori associati nel codice F # **valori**, non **valori di funzione**. Combinazione di valori e valori di funzione può comportare il salvataggio di un numero ridotto di righe di codice in cambio di un po' di adattamento cognitivi overhead, soprattutto se combinato con gli operatori, ad esempio `>>` per comporre funzioni.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Considerare le implicazioni di strumenti per la programmazione senza punto

Funzioni sottoposte a currying non etichettato i relativi argomenti. Questa operazione ha implicazioni per gli strumenti. Prendere in considerazione le due funzioni seguenti:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Entrambe le funzioni valide, ma `funcWithApplication` è una funzione sottoposte a currying. Quando si passa il mouse tramite i relativi tipi in un editor, viene visualizzato questo:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

Nel sito di chiamata, le descrizioni comandi negli strumenti, ad esempio Visual Studio non è di fornire informazioni significative da ciò che il `string` e `int` effettivamente rappresentano tipi di input.

Se si verifica senza punto di codice, ad esempio `funcWithApplication` ovvero pubblicamente consumo, si consiglia di eseguire un'espansione di η completa in modo che gli strumenti possono pick nell'inserimento nel nomi significativi per gli argomenti.

Inoltre, il debug del codice senza punto può risultare difficile, se non impossibile. Strumenti di debug si basano sui valori associati ai nomi (ad esempio, `let` associazioni) in modo da poter controllare a metà dei valori intermedi tramite l'esecuzione. Quando il codice non presenta valori da controllare, non esegue alcuna operazione per eseguire il debug. In futuro, strumenti di debug possono evolvere per sintetizzare questi valori in base ai percorsi eseguiti in precedenza, ma non è una buona idea salvaguardarsi la rilevanza nel *potenziali* funzionalità di debug.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Prendere in considerazione applicazione parziale come una tecnica per ridurre boilerplate interno

A differenza precedente punto, applicazione parziale è uno strumento eccezionale per ridurre il boilerplate all'interno di un'applicazione o le caratteristiche interne più approfondite di un'API. Può essere utile per gli unit test l'implementazione delle API più complicate, in cui boilerplate è spesso un problema per affrontare. Ad esempio, il codice seguente mostra come eseguire il framework di simulazione più offrono senza portare una dipendenza esterna su un framework di questo tipo e dover apprendere un correlati personalizzato API.

Ad esempio, si consideri la topografia di soluzioni seguenti:

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

L'applicazione parzialmente `doTransaction` con un contesto di creazione di versioni fittizie oggetto consente di chiamare la funzione in tutti gli unit test senza la necessità di creare un contesto simulato ogni volta che:

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

Questa tecnica non deve essere applicata universalmente per codebase intero, ma risulta efficace per ridurre boilerplate per elementi interni complicata e gli unit test di tali elementi interni.

## <a name="access-control"></a>Controllo di accesso

F # sono disponibili più opzioni per [il controllo degli accessi](../language-reference/access-control.md), ereditato da quella disponibile in .NET runtime. Questi non sono utilizzabili solo per i tipi, è possibile usarli per le funzioni, troppo.

* Preferisce non`public` tipi e membri fino a quando non è necessario che diventino pubblicamente utilizzabile. Ciò riduce al minimo quali paio di consumer per
* Cercare di mantenere tutte le funzionalità di supporto `private`.
* Prendere in considerazione l'utilizzo di `[<AutoOpen>]` su un modulo privato delle funzioni di supporto se diventano numerosi.

## <a name="type-inference-and-generics"></a>L'inferenza del tipo e generics

L'inferenza del tipo è possibile risparmiare dalla digitazione numerosi standard. E generalizzazione automatica nel compilatore F # consentono di scrivere codice più generico con quasi alcun lavoro aggiuntivo da parte dell'utente. Tuttavia, queste funzionalità non sono universalmente valida.

* Prendere in considerazione etichettare i nomi degli argomenti con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza del tipo per questo oggetto.

    Il motivo è che **si** deve essere nel controllo della forma dell'API, non il compilatore. Anche se il compilatore può eseguire un processo fine l'inferenza di tipi per l'utente, è possibile avere la forma apportare modifiche all'API se gli elementi interni su che si basa sono stati modificati i tipi. Ciò potrebbe essere quella desiderata, ma quasi certamente comporterà una modifica API che i consumer a valle saranno quindi necessario affrontare. Al contrario, se si ha il controllo in modo esplicito la forma dell'API pubblica, è possibile controllare queste modifiche di rilievo. In termini DDD, che può essere considerata come un livello di anti-danneggiamento.

* È consigliabile assegnare un nome significativo per gli argomenti generici.

    A meno che non si scrive codice realmente generico che non è specifico di un particolare dominio, un nome significativo consente di comprendere il dominio che in cui lavorano altri programmatori. Ad esempio, un parametro di tipo denominato `'Document` nel contesto dell'interazione con un documento database rende più chiara che tipi di documento generico possono essere accettati dalla funzione o membro si sta utilizzando.

* Si consiglia di denominare i parametri di tipo generico con PascalCase.

    Questo è il modo generale per eseguire operazioni in .NET, è consigliabile utilizzare PascalCase anziché snake_case o camelCase.

Infine, generalizzazione automatica non è sempre un vantaggio per chi ha familiarità con F # o una codebase di grandi dimensioni. È overhead cognitivi nell'utilizzo dei componenti che sono generici. Inoltre, se automaticamente con diversi tipi di input (consentono solo se sono progettati per essere usate come tali) non vengono utilizzate funzioni generalizzate, quindi non offre alcun vantaggio reale a tali da generico a questo punto nel tempo. Considerare sempre se il codice che si sta scrivendo effettivamente trarranno beneficio da in corso generico.

## <a name="performance"></a>Prestazioni

Valori di F # non sono modificabili per impostazione predefinita, in modo da evitare di determinate classi di bug (in particolare tali che coinvolgono concorrenza e parallelismo). Tuttavia, in alcuni casi, per ottenere l'efficienza ottimale (o persino ragionevole) della fase di esecuzione o le allocazioni di memoria, un intervallo di lavoro può essere implementato in modo ottimale utilizzo mutazione posto dello stato. Ciò è possibile in una base opt-in con F # con il `mutable` (parola chiave).

Tuttavia, l'utilizzo di `mutable` potrebbero sentirsi incompatibile con la purezza funzionale in F #. L'operazione è corretta, se si modificano le aspettative da purezza per [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency). La trasparenza referenziale - non purezza - è l'obiettivo finale durante la scrittura di funzioni F #. In questo modo è possibile scrivere un'interfaccia funzionale tramite un'implementazione basata su mutazione per il codice critico delle prestazioni.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Eseguire il wrapping codice modificabile nelle interfacce non modificabile

Con la trasparenza referenziale come obiettivo, è fondamentale per scrivere codice che non espongono underbelly modificabile delle funzioni critiche per le prestazioni. Ad esempio, il codice seguente implementa il `Array.contains` funzione nella libreria di base F #:

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

Chiamata più volte a questa funzione non modifica la matrice sottostante e non è necessario per mantenere uno stato modificabile all'utilizzo dello stesso. È referentially trasparente, anche se ogni riga di codice all'interno di essa utilizza mutazione.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Si consideri che incapsula dati modificabili nelle classi

Nell'esempio precedente viene utilizzata una singola funzione per incapsulare operazioni utilizzando dati modificabili. Ciò non è sempre sufficiente per set di dati più complessi. Prendere in considerazione i seguenti set di funzioni:

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

Questo codice è ad alte prestazioni, ma vengono esposti la struttura di dati basati su mutazione che i chiamanti siano responsabili della manutenzione. Ciò può essere incapsulato all'interno di una classe senza membri sottostanti che possono essere modificati:

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

`Closure1Table` incapsula la struttura di dati basati su mutazione sottostante, pertanto senza imporre ai chiamanti di mantenere la struttura dei dati sottostante. Le classi sono un metodo efficace per incapsulare i dati e le routine che sono basate su mutazione senza esporre i dettagli per i chiamanti.

### <a name="prefer-let-mutable-to-reference-cells"></a>Preferisce `let mutable` alle celle di riferimento

Le celle di riferimento sono un modo per rappresentare il riferimento a un valore anziché il valore stesso. Anche se possono essere utilizzati per il codice critico per le prestazioni, non sono in genere consigliate. Si consideri l'esempio seguente:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

L'utilizzo di una cella di riferimento ora "falsifica" tutto il codice successivo con la necessità di risolvere e nuovamente riferimento i dati sottostanti. Si consideri invece `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

A parte il singolo punto di mutazione nella parte centrale dell'espressione lambda, tutti gli altri codice che deve essere unito `acc` possibile farlo in modo che non è diverso per l'utilizzo di una normale `let`-valore non modificabile associato. Ciò rende più facile da modificare nel corso del tempo.

## <a name="object-programming"></a>Oggetto di programmazione

F # contiene il supporto completo per gli oggetti e concetti (OO) orientata agli oggetti. Sebbene molti concetti OO siano potenti e utili, non tutte sono ideali per l'utilizzo. Gli elenchi seguenti offrono informazioni aggiuntive sulle categorie di funzionalità OO a un livello elevato.

**Considerare l'uso di queste funzionalità in molte situazioni:**

* La notazione del punto (`x.Length`)
* Membri di istanza
* Costruttori impliciti
* Membri statici
* Notazione dell'indicizzatore (`arr.[x]`)
* Argomenti denominati e facoltativi
* Le interfacce e implementazioni di interfaccia

**Non raggiungere prima di tutto per queste funzionalità, ma cautela applicarli quando essi sono utili risolvere un problema:**

* Overload di un metodo
* Dati modificabile incapsulati
* Operatori sui tipi
* Proprietà automatica
* Implementazione `IDisposable` e `IEnumerable`
* Estensioni di tipo
* Eventi
* Struct
* Delegati
* Enumerazioni

**In genere di evitare queste funzionalità a meno che non è necessario utilizzarli:**

* L'implementazione dell'ereditarietà e le gerarchie di tipi basato sull'ereditarietà
* I valori null e `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Preferire l'ereditarietà di composizione

[Composizione dell'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) costituisce un idioma da molto tempo che possa rispettare buona codice F #. Il principio fondamentale è che è consigliabile non esporre una classe di base e imporre ai chiamanti di ereditare da quella classe base per ottenere funzionalità.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Utilizzare le espressioni di oggetto per implementare le interfacce se non è necessaria una classe

[Espressioni di oggetto](../language-reference/object-expressions.md) consentono di implementare le interfacce in tempo reale, associazione l'interfaccia implementata da un valore senza la necessità di eseguire questa operazione all'interno di una classe. Questa operazione è utile, soprattutto se si _solo_ necessario implementare l'interfaccia e non sono necessari per una classe completa.

Ad esempio, ecco il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di correzione di codice se hai aggiungo un simbolo che non è necessario un `open` informativa per:

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

Perché non è necessario per una classe durante l'interazione con l'API di codice di Visual Studio, le espressioni di oggetto sono uno strumento ideale per questo oggetto. Sono anche utili per gli unit test, quando si desidera sottoporre a stub out un'interfaccia con le routine del test in modalità ad hoc.

## <a name="type-abbreviations"></a>Abbreviazioni dei tipi

[Abbreviazioni di tipo](../language-reference/type-abbreviations.md) sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma della funzione o un tipo più complesso. Ad esempio, viene assegnata un'etichetta per cosa è necessario definire un calcolo con il seguente alias [CNTK](https://www.microsoft.com/cognitive-toolkit/), un deep learning libreria:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Il `Computation` nome è un modo pratico per indicare qualsiasi funzione che corrisponde alla firma è aliasing. Utilizzando le abbreviazioni di tipo simile al seguente è conveniente e consente di codice più conciso.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Evitare di usare le abbreviazioni di tipo per rappresentare il dominio

Sebbene le abbreviazioni di tipo sono utili per assegnare un nome alle firme di funzione, è possibile confusione quando abbreviazione degli altri tipi. Prendere in considerazione questa abbreviazione:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Può trattarsi di confusione in diversi modi:

* `BufferSize` non è un'astrazione; è semplicemente un altro nome per un numero intero.
* Se `BufferSize` viene esposto in un'API pubblica, si può facilmente siano interpretati erroneamente da indicare più della semplice `int`. In genere, i tipi di dominio dispongono più attributi ad essi e non sono tipi primitivi, ad esempio `int`. Questa abbreviazione viola questo presupposto.
* Maiuscole e minuscole di `BufferSize` (PascalCase) implica che questo tipo contiene più dati.
* Questo alias non offre una maggiore chiarezza confrontato con un argomento denominato a una funzione.
* L'abbreviazione si manifesta in linguaggio intermedio compilato; è semplicemente un integer e questo alias è un costrutto in fase di compilazione.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

In breve, il problema con le abbreviazioni di tipo è che si trovano **non** astrazioni di sovrascrivere i tipi che sono abbreviando. Nell'esempio precedente, `BufferSize` è semplicemente un' `int` dietro le quinte, con alcun dato supplementare, né i vantaggi dal sistema di tipi oltre a ciò che `int` esiste già.
