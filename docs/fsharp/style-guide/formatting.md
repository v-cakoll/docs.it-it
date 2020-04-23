---
title: Linee guida per la formattazione del codice F#
description: Informazioni sulle linee guida per la formattazione del codice F.
ms.date: 11/04/2019
ms.openlocfilehash: dd48380a90ee92b2c1edaaabc116fa1cd8010390
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102489"
---
# <a name="f-code-formatting-guidelines"></a>Linee guida per la formattazione del codice F#

In questo articolo vengono fornite linee guida per la formattazione del codice in modo che il codice F .NET sia:This article offers guidelines for how to format your code so that your F's code is:

* Più leggibile
* In conformità con le convenzioni applicate dagli strumenti di formattazione in Visual Studio e altri editor
* Simile ad altro codice online

Queste linee guida sono basate su [una guida completa alle convenzioni](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) di formattazione di F , di [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Regole generali per il rientro

Per impostazione predefinita, in F, per impostazione predefinita viene utilizzato uno spazio vuoto significativo. Le seguenti linee guida hanno lo scopo di fornire indicazioni su come destreggiarsi tra alcune sfide che questo può imporre.

### <a name="using-spaces"></a>Utilizzo degli spazi

Quando è richiesto il rientro, è necessario utilizzare spazi, non tabulazioni. È necessario almeno uno spazio. L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro; due, tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro è tipico.

**Sono consigliati quattro spazi per rientro.**

Detto questo, l'indentazione dei programmi è una questione soggettiva. Le variazioni sono OK, ma la prima regola da seguire è la *coerenza del rientro*. Scegliere uno stile di rientro generalmente accettato e utilizzarlo sistematicamente in tutta la codebase.

## <a name="formatting-white-space"></a>Formattazione degli spazi vuoti

Il f è sensibile allo spazio vuoto. Anche se la maggior parte della semantica da spazi vuoti sono coperti da un rientro corretto, ci sono alcune altre cose da considerare.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Formattazione di operatori nelle espressioni aritmeticheFormatting operators in arithmetic expressions

Utilizzare sempre spazi vuoti intorno alle espressioni aritmetiche binarie:Always use white space around binary arithmetic expressions:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Gli `-` operatori unari devono sempre essere immediatamente seguiti dal valore che stanno negando:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

L'aggiunta di un `-` carattere di spazio vuoto dopo l'operatore può causare confusione per gli altri utenti.

In sintesi, è importante:

* Circondare gli operatori binari con spazi vuoti
* Non avere mai spazi vuoti finali dopo un operatore unario

La linea guida dell'operatore aritmetico binario è particolarmente importante. La mancata `-` circonciazione di un operatore binario, se `-`combinata con determinate scelte di formattazione, potrebbe comportare l'interpretazione come unario .

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Racchiudere una definizione di operatore personalizzato con spazi vuoti

Utilizzare sempre spazi vuoti per racchiudere una definizione di operatore:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Per qualsiasi operatore `*` personalizzato che inizia con e che dispone di più di un carattere, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare un'ambiguità del compilatore. Per questo motivo, è consigliabile racchiudere semplicemente le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Frecce dei parametri della funzione surround con spazi vuoti

Quando si definisce la firma di `->` una funzione, utilizzare uno spazio bianco intorno al simbolo:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Argomenti della funzione surround con spazi vuoti

Quando si definisce una funzione, utilizzare uno spazio vuoto intorno a ogni argomento.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a>Inserire i parametri in una nuova riga per le definizioni dei membri lunghi

Se si dispone di una definizione di membro molto lunga, posizionare i parametri in nuove righe e applicare loro un rientro di un ambito.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Questo vale anche per i costruttori:This applies also to constructors:

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>Annotazioni del tipo

#### <a name="right-pad-function-argument-type-annotations"></a>Annotazioni del tipo di argomento della funzione di blocco a destraRight-pad function argument type annotations

Quando si definiscono argomenti con annotazioni `:` di tipo, utilizzare uno spazio vuoto dopo il simbolo:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Racchiudere le annotazioni del tipo restituito con spazi vuoti

In un'annotazione di tipo funzione o tipo di valore let-bound (tipo `:` restituito nel caso di una funzione), utilizzare gli spazi vuoti prima e dopo il simbolo:

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Formattazione di righe vuote

* Separare le definizioni di funzione e classe di primo livello con due righe vuote.
* Le definizioni dei metodi all'interno di una classe sono separate da una singola riga vuota.
* È possibile utilizzare (sparingly) righe vuote per separare gruppi di funzioni correlate. Le righe vuote possono essere omesse tra un gruppo di one-liner correlati (ad esempio, un insieme di implementazioni fittizie).
* Utilizzare righe vuote nelle funzioni, con parsimonia, per indicare le sezioni logiche.

## <a name="formatting-comments"></a>Formattazione dei commenti

In genere preferiscono più commenti a doppia barra rispetto ai commenti di blocco in stile ML.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

I commenti in linea devono scrivere in maiuscolo la prima lettera.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenzioni di denominazione

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Usare camelCase per funzioni e valori associati a classi, espressioni e modelliUse camelCase for class-bound, expression-bound, and pattern-bound values and functions

È comune e accettato lo stile di F , utilizzare camelCase per tutti i nomi associati come variabili locali o in corrispondenze di modelli e definizioni di funzione.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Anche le funzioni associate localmente nelle classi devono usare camelCase.Locally bound functions in classes should also use camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Usare camelCase per le funzioni pubbliche associate ai moduliUse camelCase for module-bound public functions

Quando una funzione associata a un modulo fa parte di un'API pubblica, deve usare camelCase:When a module-bound function is part of a public API, it should use camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Usare camelCase per funzioni e valori interni e privati associati a moduliUse camelCase for internal and private module-bound values and functions

Utilizzare camelCase per i valori associati a moduli privati, inclusi i seguenti:

* Funzioni ad hoc negli script

* Valori che costituiscono l'implementazione interna di un modulo o di un tipo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Utilizzare camelCase per i parametri

Tutti i parametri devono utilizzare camelCase in base alle convenzioni di denominazione .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Utilizzare PascalCase per i moduliUse PascalCase for modules

Tutti i moduli (di livello superiore, interno, privato, annidato) devono utilizzare PascalCase.All modules (top-level, internal, private, nested) should use PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Utilizzare PascalCase per dichiarazioni di tipo, membri ed etichetteUse PascalCase for type declarations, members, and labels

Classi, interfacce, struct, enumerazioni, delegati, record e unioni discriminate devono essere tutti denominati con PascalCase.Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase. Anche i membri all'interno di tipi ed etichette per i record e le unioni discriminate devono utilizzare PascalCase.Members within types and labels for records and discriminated unions should also use PascalCase.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Utilizzare PascalCase per i costrutti intrinseci a .NETUse PascalCase for constructs intrinsic to .NET

Anche gli spazi dei nomi,`.dll` le eccezioni, gli eventi e i nomi di progetto devono usare PascalCase.Namespaces, exceptions, events, and project/ names should also use PascalCase. Questo non solo rende il consumo da altri linguaggi .NET sentire più naturale per i consumatori, è anche coerente con le convenzioni di denominazione .NET che si rischia di incontrare.

### <a name="avoid-underscores-in-names"></a>Evitare i caratteri di sottolineatura nei nomi

Storicamente, alcune librerie di F , hanno usato caratteri di sottolineatura nei nomi. Tuttavia, questo non è più ampiamente accettato, in parte perché si contrae con le convenzioni di denominazione .NET. Detto questo, alcuni programmatori F , utilizzare sottolineature pesantemente, in parte per motivi storici, e la tolleranza e il rispetto è importante. Tuttavia, essere consapevoli del fatto che lo stile è spesso antipatico da altri che hanno una scelta su se usarlo.

Un'eccezione include l'interoperabilità con i componenti nativi, dove i caratteri di sottolineatura sono comuni.

### <a name="use-standard-f-operators"></a>Usare gli operatori standard di F

Gli operatori seguenti sono definiti nella libreria standard di F e devono essere usati invece di definire equivalenti. L'utilizzo di questi operatori è consigliato in quanto tende a rendere il codice più leggibile e idiomatico. Gli sviluppatori con un background in OCaml o altro linguaggio di programmazione funzionale possono essere abituati a diversi idiomi. Nell'elenco seguente vengono riepilogati gli operatori consigliati di F.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Utilizzare la sintassi`Foo<T>`del prefisso per i`T Foo`generics ( ) nella preferenza per postfix syntax ( )

Il valore di Fè eredita sia lo stile ML `int list`suffisso di denominazione dei tipi `list<int>`generici ( ad esempio , ) sia lo stile .NET del prefisso (ad esempio, ). Preferire lo stile .NET, ad eccezione di cinque tipi specifici:

1. Per gli elenchi F, utilizzare `int list` la `list<int>`forma suffissa: anziché .
2. Per le opzioni Di F, `int option` utilizzare `option<int>`la forma suffissa: anziché .
3. Per le opzioni di valore F `int voption` , `voption<int>`utilizzare la forma suffissa: anziché .
4. Per le matrici F, utilizzare `int[]` il `int array` nome `array<int>`sintattico anziché o .
5. Per le celle `int ref` di `ref<int>` `Ref<int>`riferimento, utilizzare anziché o .

Per tutti gli altri tipi, utilizzare la forma del prefisso.

## <a name="formatting-tuples"></a>Formattazione di tuple

Una creazione di un'istanza di tupla deve essere racchiusa tra parentesi e `(1, 2)` `(x, y, z)`le virgole di delimitazione al suo interno devono essere seguite da un singolo spazio, ad esempio: , .

È comunemente accettato per omettere le parentesi nel criterio di ricerca delle tuple:It is commonly accepted to omit parentheses in pattern matching of tuples:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

È anche comunemente accettato per omettere le parentesi se la tupla è il valore restituito di una funzione:It is also commonly accepted to omit parentheses if the tuple is the return value of a function:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

In sintesi, preferire le istanze di tupla tra parentesi, ma quando si usano tuple per criteri di ricerca o un valore restituito, è considerato fine per evitare le parentesi.

## <a name="formatting-discriminated-union-declarations"></a>Formattazione delle dichiarazioni di unione discriminate

Applicare `|` un rientro nella definizione del tipo di quattro spazi:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>Formattazione delle unioni discriminate

Unioni discriminate istanziate di istanziate che si dividono su più righe devono fornire ai dati contenuti un nuovo ambito con rientro:Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

La parentesi di chiusura può anche essere su una nuova riga:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formattazione delle dichiarazioni di record

Applicare `{` un rientro nella definizione del tipo di quattro spazi e iniziare l'elenco dei campi sulla stessa riga:

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

Inserire il token di apertura in una nuova riga e il token di chiusura in una nuova riga è preferibile se si dichiarano le implementazioni dell'interfaccia o i membri nel record:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Formattazione dei record

I record brevi possono essere scritti in un'unica riga:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

I record più lunghi devono utilizzare nuove righe per le etichette:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

L'inserimento del token di apertura in una nuova riga, il contenuto a schede in un ambito e il token di chiusura su una nuova riga è preferibile se si è:

* Spostamento di record nel codice con ambiti di rientro diversi
* Trasformare in una funzione

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Le stesse regole si applicano agli elementi di elenco e matrice.

## <a name="formatting-copy-and-update-record-expressions"></a>Formattazione delle espressioni di record di copia e aggiornamento

Un'espressione di record di copia e aggiornamento è ancora un record, pertanto si applicano linee guida simili.

Le espressioni brevi possono essere inserite in un'unica riga:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Le espressioni più lunghe devono utilizzare nuove righe:Longer expressions should use new lines:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

E come con le linee guida di record, si consiglia di dedicare righe separate per le parentesi graffe e far rientrare un ambito a destra con l'espressione. In alcuni casi speciali, ad esempio il wrapping di un valore con un optional senza parentesi, potrebbe essere necessario mantenere una parentesi graffa su una riga:In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>Formattazione di elenchi e matrici

Scrivere `x :: l` con gli `::` spazi`::` intorno all'operatore (è un operatore infisso, quindi circondato da spazi).

Gli elenchi e le matrici dichiarati su una singola riga devono avere uno spazio dopo la parentesi quadra di apertura e prima della parentesi quadra di chiusura:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Utilizzare sempre almeno uno spazio tra due operatori simili a parentesi graffe distinti. Ad esempio, lasciare uno `[` spazio `{`tra a e un .

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

La stessa linea guida si applica per elenchi o matrici di tuple.

Gli elenchi e le matrici suddivisi su più righe seguono una regola simile a quella dei record:

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

E come con i record, dichiarando le parentesi di apertura e chiusura sulla propria riga renderà più facile lo spostamento del codice e delle tubazioni nelle funzioni.

Quando si generano matrici ed `->` elenchi `do ... yield` a livello di codice, preferire quando viene sempre generato un valore:When generating arrays and lists programmatically, prefer over when a value is always generated:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

Le versioni precedenti del linguaggio `yield` F , richiedevano la specifica in situazioni in cui i dati possono essere generati in modo condizionale o se possono essere presenti espressioni consecutive da valutare. Preferisci omettere queste parole chiave a meno che non sia necessario compilare con una versione del linguaggio F. precedente:Prefer omitting these `yield` keywords unless you must compile with an older F' language version:

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

In alcuni `do...yield` casi, può aiutare nella leggibilità. Questi casi, anche se soggettivi, dovrebbero essere presi in considerazione.

## <a name="formatting-if-expressions"></a>Formattazione delle espressioni if

Il rientro delle condizioni dipende dalle dimensioni delle espressioni che le costituiscono. Se `cond` `e1` , `e2` e sono brevi, è sufficiente scriverli su una riga:

```fsharp
if cond then e1 else e2
```

Se `cond`uno `e1` `e2` dei due , o sono più lunghi, ma non multi-linea:

```fsharp
if cond
then e1
else e2
```

Se una qualsiasi delle espressioni è su più righe:

```fsharp
if cond then
    e1
else
    e2
```

Più condizionali con `elif` e `else` sono rientrate `if`nello stesso ambito del :

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Costrutti di criteri di ricercaPattern matching constructs

Utilizzare `|` un per ogni clausola di una corrispondenza senza rientro. Se l'espressione è breve, è possibile usare una singola riga se anche ogni sottoespressione è semplice.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Se l'espressione a destra della freccia di corrispondenza dei criteri è troppo grande, `match` / `|`spostarla nella riga seguente, rientrata di un passaggio rispetto alla proprietà .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

I criteri di ricerca `function`delle funzioni anonime, a partire da , in genere non devono rientrare troppo. Ad esempio, il rientro di un ambito come segue va bene:For example, indenting one scope as follows and am:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Criteri di ricerca `let` nelle `let rec` funzioni definite da o devono `let`essere `function` rientrate di quattro spazi dopo l'avvio di , anche se viene utilizzata la parola chiave:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Si sconsiglia di allineare le frecce.

## <a name="formatting-trywith-expressions"></a>Formattazione delle espressioni try/with

I criteri di ricerca sul tipo di eccezione `with`devono essere rientrati allo stesso livello di .

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>Applicazione dei parametri della funzione di formattazione

In generale, la maggior parte dell'applicazione dei parametri di funzione viene eseguita sulla stessa riga.

Se si desidera applicare parametri a una funzione in una nuova riga, applicare un rientro di un ambito.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

Le stesse linee guida si applicano per le espressioni lambda come argomenti della funzione. Se il corpo di un'espressione lambda, il corpo può avere un'altra riga, rientrata da un ambito

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

Tuttavia, se il corpo di un'espressione lambda è più di una riga, è consigliabile eseguire il factoring in una funzione separata anziché applicare un costrutto su più righe come singolo argomento a una funzione.

### <a name="formatting-infix-operators"></a>Formattazione degli operatori infissi

Separare gli operatori in base agli spazi. Eccezioni ovvie a `!` questa `.` regola sono gli operatori e .

Le espressioni infisse sono OK per allineare sulla stessa colonna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formattazione degli operatori della pipelineFormatting pipeline operators

Gli `|>` operatori di pipeline devono andare sotto le espressioni su cui operano.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>Formattazione dei moduli

Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non deve essere rientrato. Gli elementi dello spazio dei nomi non devono essere rientrati.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Formattazione di espressioni e interfacce di oggetti

Le espressioni oggetto e le interfacce devono `member` essere allineate nello stesso modo con il rientro dopo quattro spazi.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formattazione degli spazi vuoti nelle espressioni

Evitare spazi vuoti estranei nelle espressioni F .

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Gli argomenti denominati non `=`devono inoltre avere spazio che circonda il :

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Attributi di formattazione

[Gli attributi](../language-reference/attributes.md) vengono posizionati sopra un costrutto:Attributes are placed above a construct:

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>Formattazione degli attributi sui parametri

Gli attributi possono anche essere posizionati sui parametri. In questo caso, posizionare quindi sulla stessa riga del parametro e prima del nome:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Formattazione di più attributi

Quando più attributi vengono applicati a un costrutto che non è un parametro, devono essere posizionati in modo che sia presente un attributo per riga:When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Quando vengono applicati a un parametro, devono trovarsi `;` sulla stessa riga e separati da un separatore.

## <a name="formatting-literals"></a>Formattazione di valori letterali

[I valori letterali F ,](../language-reference/literals.md) usando l'attributo, `Literal` devono inserire l'attributo nella propria riga e usare la denominazione PascalCase:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Evitare di posizionare l'attributo sulla stessa riga del valore.
