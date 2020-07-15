---
title: Linee guida per la formattazione del codice F#
description: 'Informazioni sulle linee guida per la formattazione del codice F #.'
ms.date: 11/04/2019
ms.openlocfilehash: a65600a6c685929aef8582e49caded6340fb09e2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309703"
---
# <a name="f-code-formatting-guidelines"></a>Linee guida per la formattazione del codice F#

Questo articolo fornisce linee guida per la formattazione del codice in modo che il codice F # sia:

* Più leggibili
* In conformità alle convenzioni applicate dagli strumenti di formattazione in Visual Studio e altri editor
* Simile ad altro codice online

Queste linee guida sono basate su [una guida completa alle convenzioni di formattazione F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) di [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Regole generali per il rientro

Per impostazione predefinita, F # utilizza spazi vuoti significativi. Le linee guida riportate di seguito hanno lo scopo di fornire indicazioni su come manipolare alcune delle problemi che possono essere imposte.

### <a name="using-spaces"></a>Uso di spazi

Quando il rientro è obbligatorio, è necessario utilizzare spazi, non tabulazioni. È necessario almeno uno spazio. L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro; sono tipiche due, tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro.

**Si consiglia di usare quattro spazi per rientri.**

Detto questo, il rientro dei programmi è una questione soggettiva. Le variazioni sono OK, ma la prima regola da seguire è la *coerenza dei rientri*. Scegliere uno stile di rientro generalmente accettato e usarlo sistematicamente nell'intero codebase.

## <a name="formatting-white-space"></a>Formattazione dello spazio vuoto

F # è sensibile agli spazi vuoti. Sebbene la maggior parte della semantica degli spazi vuoti venga analizzata in base al rientro appropriato, è necessario prendere in considerazione altri aspetti.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Formattazione degli operatori nelle espressioni aritmetiche

Usare sempre lo spazio vuoto nelle espressioni aritmetiche binarie:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

`-`Gli operatori unari devono essere sempre seguiti immediatamente dal valore che stanno negando:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

L'aggiunta di uno spazio vuoto dopo l' `-` operatore può causare confusione per altri utenti.

In breve, è sempre importante:

* Racchiudere gli operatori binari con spazi vuoti
* Non avere mai spazi vuoti finali dopo un operatore unario

La linea guida dell'operatore aritmetico binario è particolarmente importante. Se non si riesce a racchiudere un `-` operatore binario, in combinazione con determinate scelte di formattazione, può comportare l'interpretazione come unaria `-` .

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Racchiudere una definizione di operatore personalizzato con spazio vuoto

Usare sempre gli spazi vuoti per racchiudere la definizione di un operatore:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Per qualsiasi operatore personalizzato che inizia con `*` e con più di un carattere, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare ambiguità del compilatore. Per questo motivo, è consigliabile racchiudere semplicemente le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Racchiudere le frecce dei parametri della funzione con spazio vuoto

Quando si definisce la firma di una funzione, usare uno spazio vuoto intorno al `->` simbolo:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Racchiudere gli argomenti della funzione con spazi vuoti

Quando si definisce una funzione, usare uno spazio vuoto intorno a ogni argomento.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a>Inserire i parametri in una nuova riga per le definizioni dei membri lunghi

Se si dispone di una definizione di membro molto lungo, inserire i parametri su nuove righe e rientrare in base al livello di rientro del parametro successivo.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Questo vale anche per i costruttori:

```fsharp
type C(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

Se è presente un'annotazione di tipo restituito esplicita, può trovarsi alla fine di `)` e prima di `=` o su una nuova riga. Se anche il tipo restituito ha un nome lungo, quest'ultimo potrebbe essere preferibile:

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse)
                                            : AVeryLongReturnType =
        // ... the body of the method follows
```

### <a name="type-annotations"></a>Annotazioni di tipo

#### <a name="right-pad-function-argument-type-annotations"></a>Annotazioni del tipo di argomento della funzione Right-Pad

Quando si definiscono gli argomenti con annotazioni di tipo, usare uno spazio vuoto dopo il `:` simbolo:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Annotazioni di tipo restituito Racchiudi con spazi vuoti

In un'annotazione di tipo valore o funzione associata (tipo restituito nel caso di una funzione), usare uno spazio vuoto prima e dopo il `:` simbolo:

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

* Separare le definizioni di classi e funzioni di primo livello con due righe vuote.
* Le definizioni di metodo all'interno di una classe sono separate da un'unica riga vuota.
* Per separare i gruppi di funzioni correlate, è possibile utilizzare le righe vuote aggiuntive. Le righe vuote possono essere omesse tra un gruppo di un set di righe correlato, ad esempio un set di implementazioni fittizie.
* Utilizzare righe vuote nelle funzioni, per indicare le sezioni logiche.

## <a name="formatting-comments"></a>Formattazione di commenti

Preferiscono in genere più commenti a doppia barra rispetto ai commenti di blocco di tipo ML.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

I commenti inline devono sfruttare la prima lettera.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenzioni di denominazione

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Usare camelCase per le funzioni e i valori associati a classi, associati a espressioni e modelli

Lo stile F # è comune e accettato per usare camelCase per tutti i nomi associati come variabili locali o in corrispondenze di modelli e definizioni di funzione.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Anche le funzioni con binding localmente nelle classi devono usare camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Usare camelCase per le funzioni pubbliche con associazione al modulo

Quando una funzione associata a un modulo fa parte di un'API pubblica, deve usare camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Usare camelCase per le funzioni e i valori associati a moduli interni e privati

Usare camelCase per i valori associati al modulo privato, inclusi i seguenti:

* Funzioni ad hoc negli script

* Valori che costituiscono l'implementazione interna di un modulo o di un tipo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Usare camelCase per i parametri

Tutti i parametri devono usare camelCase in conformità alle convenzioni di denominazione .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Usare PascalCase per i moduli

Tutti i moduli (di livello superiore, interno, privato, nidificato) devono usare PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Usare PascalCase per dichiarazioni di tipo, membri ed etichette

Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase. Anche i membri all'interno dei tipi e delle etichette per i record e le unioni discriminate devono usare PascalCase.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Usare PascalCase per costrutti intrinseci a .NET

Gli spazi dei nomi, le eccezioni, gli eventi e `.dll` i nomi e i progetti devono anche usare PascalCase. In questo modo, l'utilizzo da parte di altri linguaggi .NET risulta più naturale per gli utenti, ma è anche coerente con le convenzioni di denominazione .NET che è probabile che si verifichino.

### <a name="avoid-underscores-in-names"></a>Evitare i caratteri di sottolineatura nei nomi

In passato, alcune librerie F # hanno usato caratteri di sottolineatura nei nomi. Tuttavia, questo non è più ampiamente accettato, in parte perché si scontra con le convenzioni di denominazione .NET. Detto questo, alcuni programmatori F # utilizzano molto spesso i caratteri di sottolineatura, in parte per motivi cronologici, e la tolleranza e il rispetto sono importanti. Tuttavia, tenere presente che lo stile è spesso diverso da altri utenti che hanno la possibilità di scegliere se utilizzarlo.

Un'eccezione include l'interoperabilità con i componenti nativi, dove i caratteri di sottolineatura sono comuni.

### <a name="use-standard-f-operators"></a>Usare gli operatori F # standard

Gli operatori seguenti sono definiti nella libreria standard F # e devono essere usati anziché definire equivalenti. L'uso di questi operatori è consigliato perché tende a rendere il codice più leggibile e idiomatiche. Gli sviluppatori con background in OCaml o altro linguaggio di programmazione funzionale possono essere abituati a idiomi diversi. Nell'elenco seguente sono riepilogati gli operatori F # consigliati.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Usare la sintassi di prefisso per generics ( `Foo<T>` ) in preferenza alla sintassi suffissa ( `T Foo` )

F # eredita sia lo stile di suffisso ML dei tipi generici di denominazione (ad esempio, `int list` ) sia lo stile .NET del prefisso (ad esempio, `list<int>` ). Preferisce lo stile .NET, ad eccezione di cinque tipi specifici:

1. Per gli elenchi F # usare il formato suffisso: `int list` anziché `list<int>` .
2. Per le opzioni F # usare il formato suffisso: `int option` anziché `option<int>` .
3. Per le opzioni di valore F # usare il formato suffisso: `int voption` anziché `voption<int>` .
4. Per le matrici F # usare il nome sintattico `int[]` anziché `int array` o `array<int>` .
5. Per le celle di riferimento, usare `int ref` anziché `ref<int>` o `Ref<int>` .

Per tutti gli altri tipi, usare il formato prefisso.

## <a name="formatting-tuples"></a>Formattazione di Tuple

La creazione di un'istanza di tupla deve essere racchiusa tra parentesi e le virgole di delimitazione al suo interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)` , `(x, y, z)` .

Viene in genere accettato per omettere le parentesi nei criteri di ricerca delle tuple:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Viene inoltre comunemente accettato di omettere le parentesi se la tupla è il valore restituito di una funzione:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

In sintesi, predilige le creazioni di istanze di Tuple tra parentesi, ma quando si usano Tuple per la corrispondenza dei modelli o un valore restituito, è opportuno evitare le parentesi.

## <a name="formatting-discriminated-union-declarations"></a>Formattazione di dichiarazioni di Unione discriminate

Rientro di `|` quattro spazi nella definizione del tipo:

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

## <a name="formatting-discriminated-unions"></a>Formattazione di unioni discriminate

Le unioni discriminate di cui è stata creata la suddivisione in più righe devono fornire ai dati contenuti un nuovo ambito con rientro:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

La parentesi di chiusura può inoltre trovarsi in una nuova riga:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formattazione di dichiarazioni di record

Rientrare `{` nella definizione del tipo di quattro spazi e avviare l'elenco dei campi sulla stessa riga:

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

L'inserimento del token di apertura su una nuova riga e il token di chiusura in una nuova riga è preferibile se si dichiarano implementazioni o membri dell'interfaccia nel record:

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

## <a name="formatting-records"></a>Formattazione di record

È possibile scrivere record brevi in una sola riga:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

I record che hanno più tempo devono usare le nuove righe per le etichette:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Inserire il token di apertura su una nuova riga, il contenuto a schede su un ambito e il token di chiusura in una nuova riga è preferibile se si è:

* Trasferimento di record nel codice con ambiti di rientro diversi
* Inviarli tramite pipe a una funzione

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

Le stesse regole si applicano agli elementi list e Array.

## <a name="formatting-copy-and-update-record-expressions"></a>Formattazione di espressioni di record di copia e aggiornamento

Un'espressione di record di copia e aggiornamento è ancora un record, quindi si applicano linee guida simili.

Le espressioni brevi possono rientrare in una sola riga:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Le espressioni più lunghe devono usare le nuove righe:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

Come per le linee guida per i record, è possibile dedicare linee separate per le parentesi graffe e rientrare un ambito a destra con l'espressione. In alcuni casi speciali, ad esempio il wrapping di un valore con un facoltativo senza parentesi, potrebbe essere necessario utilizzare una parentesi graffa in una sola riga:

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

Scrivere `x :: l` con spazi intorno all' `::` operatore ( `::` è un operatore infisso, quindi racchiuso tra gli spazi).

Gli elenchi e le matrici dichiarati in una singola riga devono avere uno spazio dopo la parentesi di apertura e prima della parentesi quadra di chiusura:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Usare sempre almeno uno spazio tra due operatori distinti di tipo parentesi graffe. Ad esempio, lasciare uno spazio tra `[` e `{` .

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

Si applicano le stesse linee guida per elenchi o matrici di Tuple.

Gli elenchi e le matrici suddivisi in più righe seguono una regola simile a quella di record:

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

E come per i record, dichiarando le parentesi quadre di apertura e chiusura sulla propria riga, si renderà più semplice lo spostamento del codice e il piping delle funzioni.

Quando si generano matrici ed elenchi a livello di codice, è preferibile `->` `do ... yield` quando viene generato sempre un valore:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

Nelle versioni precedenti del linguaggio F # è necessario specificare `yield` nelle situazioni in cui i dati possono essere generati in modo condizionale oppure è possibile che vengano valutate espressioni consecutive. È preferibile omettere queste `yield` parole chiave a meno che non sia necessario compilare con una versione precedente del linguaggio F #:

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

In alcuni casi, `do...yield` può aiutare a migliorare la leggibilità. Questi casi, anche se soggettivi, devono essere presi in considerazione.

## <a name="formatting-if-expressions"></a>Formattazione di espressioni if

Il rientro delle condizioni dipende dalle dimensioni delle espressioni che li costituiscono. Se `cond` `e1` e `e2` sono brevi, è sufficiente scriverli in una sola riga:

```fsharp
if cond then e1 else e2
```

Se `cond` `e1` o `e2` sono più lunghi, ma non a più righe:

```fsharp
if cond
then e1
else e2
```

Se una delle espressioni è a più righe:

```fsharp
if cond then
    e1
else
    e2
```

Più condizionali con `elif` e `else` vengono rientrati nello stesso ambito di `if` :

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Costrutti di criteri di ricerca

Utilizzare un oggetto `|` per ogni clausola di una corrispondenza senza rientro. Se l'espressione è breve, è possibile prendere in considerazione l'uso di una singola riga se anche ogni sottoespressione è semplice.

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

Se l'espressione a destra della freccia che corrisponde al criterio di ricerca è troppo grande, spostarla nella riga seguente, rientrata di un passaggio da `match` / `|` .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

I criteri di ricerca delle funzioni anonime, a partire da `function` , non dovrebbero in genere rientrare troppo a lungo. È ad esempio possibile rientrare in un ambito come segue:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

I criteri di ricerca nelle funzioni definite da `let` o `let rec` devono essere rientrati in quattro spazi dopo l'avvio di `let` , anche se `function` viene usata la parola chiave:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Non è consigliabile allineare le frecce.

## <a name="formatting-trywith-expressions"></a>Formattazione di espressioni try/with

I criteri di ricerca nel tipo di eccezione devono essere rientrati allo stesso livello di `with` .

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

## <a name="formatting-function-parameter-application"></a>Formattazione applicazione parametri funzione

In generale, la maggior parte delle applicazioni per i parametri di funzione viene eseguita sulla stessa riga.

Se si desidera applicare parametri a una funzione su una nuova riga, rientrare in un solo ambito.

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

Le stesse linee guida si applicano alle espressioni lambda come argomenti della funzione. Se il corpo di un'espressione lambda, il corpo può avere un'altra riga, rientrato da un ambito

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

Tuttavia, se il corpo di un'espressione lambda è più di una riga, provare a fattorizzarlo in una funzione separata anziché avere un costrutto a più righe applicato come singolo argomento a una funzione.

### <a name="formatting-infix-operators"></a>Formattazione di operatori infissi

Separare gli operatori per spazi. Le eccezioni ovvie a questa regola sono gli `!` `.` operatori e.

Le espressioni infissi sono OK per la scaletta nella stessa colonna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formattazione degli operatori pipeline

`|>`Gli operatori pipeline dovrebbero andare sotto le espressioni su cui operano.

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

### <a name="formatting-modules"></a>Formattazione di moduli

Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di livello principale non deve essere rientrato. Non è necessario rientrare gli elementi dello spazio dei nomi.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Formattazione di espressioni di oggetti e interfacce

Le interfacce e le espressioni di oggetto devono essere allineate nello stesso modo in cui `member` vengono rientrate dopo quattro spazi.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formattazione di spazi vuoti nelle espressioni

Evitare spazi vuoti estranei nelle espressioni F #.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Gli argomenti denominati non devono inoltre contenere spazio per l'oggetto `=` :

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Attributi di formattazione

[Gli attributi](../language-reference/attributes.md) vengono posizionati sopra un costrutto:

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

### <a name="formatting-attributes-on-parameters"></a>Formattazione degli attributi nei parametri

Gli attributi possono essere inseriti anche nei parametri. In questo caso, posizionare quindi nella stessa riga del parametro e prima del nome:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Formattazione di più attributi

Quando si applicano più attributi a un costrutto che non è un parametro, questi devono essere posizionati in modo che esista un attributo per riga:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Quando vengono applicati a un parametro, devono trovarsi sulla stessa riga e separati da un `;` separatore.

## <a name="formatting-literals"></a>Formattazione di valori letterali

I [valori letterali F #](../language-reference/literals.md) che usano l' `Literal` attributo devono inserire l'attributo sulla propria riga e usare la denominazione PascalCase:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Evitare di posizionare l'attributo sulla stessa riga del valore.
