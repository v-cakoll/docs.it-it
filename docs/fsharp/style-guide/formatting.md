---
title: Linee guida per la formattazione del codice F#
description: Altre linee guida per la formattazione del codice F#.
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858005"
---
# <a name="f-code-formatting-guidelines"></a>Linee guida per la formattazione del codice F#

Questo articolo offre linee guida per la modalità di formattazione del codice in modo che sia il codice F#:

* In genere visualizzati come più leggibili
* È in base alle convenzioni applicate formattando altri editor e strumenti in Visual Studio
* Simile ad altro codice online

Queste indicazioni si basano [una guida completa alle convenzioni di formattazione F#](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) dal [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Regole generali per il rientro

F# per impostazione predefinita, utilizza gli spazi vuoti significativi. Le linee guida seguenti sono utili per fornire istruzioni su come organizzare alcune problematiche di che ciò può essere imposti.

### <a name="using-spaces"></a>Uso di spazi

Quando il rientro è necessario, è necessario utilizzare spazi, tabulazioni non. È necessario almeno uno spazio. L'organizzazione può creare gli standard di codifica per specificare il numero di spazi da utilizzare per il rientro. due, tre o quattro spazi del rientro a ogni livello in cui si verifica il rientro è tipico.

**Si consiglia di 4 spazi per il rientro.**

Ciò premesso, rientro dei programmi è una questione soggettiva. Le variazioni sono OK, ma è la prima regola è necessario seguire *coerenza di rientro*. Scegliere uno stile di rientro in genere accettato e usarlo in modo sistematico in tutta la codebase.

## <a name="formatting-blank-lines"></a>Formattazione di righe vuote

* Separati (funzione) e classe definizioni di primo livello con due righe vuote.
* Le definizioni di metodo all'interno di una classe sono separate da una singola riga vuota.
* Righe vuote aggiuntive possono essere usate (solo se necessario) per separare gruppi di funzioni correlate. È possibile omettere le righe vuote tra una serie di istruzioni a riga singola correlati (ad esempio, un set di implementazioni fittizie).
* Usare le righe vuote in funzioni, solo se necessario, per indicare sezioni logiche.

## <a name="formatting-comments"></a>Formattazione di commenti

In genere preferire più commenti con barra doppia commenti del blocco di stile di Machine Learning.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Commenti inline devono convertire in maiuscolo la prima lettera.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenzioni di denominazione

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Usano la notazione camel per le funzioni e i valori associati a classe, espressione di associazione e con associazione a modello

È comune e accettati F# stile usano la notazione camel per tutti i nomi associati come variabili locali o in Criteri di corrispondenza e le definizioni di funzione.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

In locale con associazione a funzioni nelle classi devono inoltre usano la notazione camel.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Usano la notazione camel per le funzioni pubbliche associata al modulo

Quando una funzione associata al modulo fa parte di un'API pubblica, è necessario utilizzare camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Usano la notazione camel per le funzioni e i valori associati a modulo interni e privati

Usano la notazione camel per i valori privati associata al modulo, inclusi i seguenti:

* Funzioni ad hoc negli script

* Valori che compongono l'implementazione interna di un tipo o un modulo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Usano la notazione camel per i parametri

Tutti i parametri devono usano la notazione camel in base alle convenzioni di denominazione .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Per i moduli usano la notazione Pascal

Tutti i moduli (livello superiore, interni, privati, annidati) utilizzino PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Usano la notazione Pascal per le dichiarazioni di tipi, membri e le etichette

Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase. I membri all'interno di tipi e le etichette per i record e unioni discriminate devono inoltre usano la notazione Pascal.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Usano la notazione Pascal per i costrutti intrinseci per .NET

Spazi dei nomi, le eccezioni, eventi e progetto /`.dll` nomi dovrebbero inoltre usano la notazione Pascal. Non solo si rende il consumo da altri linguaggi .NET sembrano più naturali agli utenti, è anche coerenza con le convenzioni di denominazione .NET che probabile incontrare.

### <a name="avoid-underscores-in-names"></a>Evitare caratteri di sottolineatura nei nomi

In passato, alcune librerie F# sono utilizzati caratteri di sottolineatura nei nomi. Tuttavia, questo è non è più diffuso, in parte perché è in conflitto con le convenzioni di denominazione di .NET. Ciò premesso, alcuni programmatori F# usano caratteri di sottolineatura frequentemente, in parte per motivi storici e tolleranza d'errore e riguardo è importante. Tuttavia, tenere presente che lo stile è spesso disliked da altri utenti che dispongono di una scelta sull'opportunità di usarlo.

Alcune eccezioni includono l'interoperabilità con i componenti nativi, in cui i caratteri di sottolineatura sono molto comuni.

### <a name="use-standard-f-operators"></a>Usare gli operatori standard F#

Gli operatori seguenti vengono definiti nella libreria standard di F# e devono essere usati invece di definire gli equivalenti. Utilizzo di questi operatori è consigliata perché tende a rendere il codice più leggibile e idiomatico. Gli sviluppatori con esperienza in OCaml o altri linguaggi di programmazione funzionale possono essere abituati a diversi linguaggi. Nell'elenco seguente sono riepilogati gli operatori F# consigliati.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Utilizzare la sintassi di prefisso per i generics (`Foo<T>`) anziché la sintassi in forma suffissa (`T Foo`)

F# eredita sia lo stile di Machine Learning suffisso di denominazione dei tipi generici (ad esempio, `int list`), nonché il prefisso stile .NET (ad esempio, `list<int>`). Preferisce lo stile di .NET, ad eccezione di quattro tipi specifici:

1. Per gli elenchi F#, utilizzare la forma suffissa: `int list` anziché `list<int>`.
2. Per opzioni di F#, utilizzare la forma suffissa: `int option` anziché `option<int>`.
3. Per le matrici di F#, usare il nome sintattico `int[]` invece `int array` o `array<int>`.
4. Per le celle di riferimento, usare `int ref` invece `ref<int>` o `Ref<int>`.

Per tutti gli altri tipi, usare la forma prefissa.

## <a name="formatting-tuples"></a>Formattazione di tuple

Creazione di un'istanza di tupla devono essere racchiusi tra parentesi, e le virgole di delimitazione all'interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)`, `(x, y, z)`.

Viene comunemente accettato per omettere le parentesi nei criteri di ricerca di tuple:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a>Formattazione di dichiarazioni di unione discriminata

Impostare un rientro `|` nella definizione del tipo da 4 spazi:

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

Un'istanza le unioni discriminate suddivisi su più righe deve fornire dati in essi contenuti un nuovo ambito con rientro:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

La parentesi di chiusura può essere anche in una nuova riga:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Dichiarazioni di record di formattazione

Impostare un rientro `{` nel tipo di definizione da 4 spazi e avviare l'elenco dei campi nella stessa riga:

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

Inserire il token di apertura nella stessa riga e il token di chiusura in una nuova riga è valida, ma tenere presente che è necessario usare il [sintassi dettagliata](../language-reference/verbose-syntax.md) per definire i membri (il `with` parola chiave):

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a>Formattazione di record

Record brevi possono essere scritti in una sola riga:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Record più lunghe deve utilizzare le nuove righe per le etichette:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Inserire il token di apertura nella stessa riga e il token di chiusura in una nuova riga è valida:

```fsharp
let rainbow = {
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
```

Per gli elementi di elenco e la matrice si applicano le stesse regole.

## <a name="formatting-lists-and-arrays"></a>Formattazione di elenchi e matrici

Scrivere `x :: l` con spazi prima e dopo il `::` operator (`::` è un operatore di infissi, di conseguenza precedute e seguito da spazi) e `[1; 2; 3]` (`;` è un delimitatore, quindi seguito da uno spazio).

Usare sempre almeno uno spazio tra due operatori simile a parentesi graffa distinti. Ad esempio, lasciare uno spazio tra un `[` e un `{`.

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

Gli elenchi e matrici suddivisi su più righe seguono una regola simile dei record:

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>Formattazione se le espressioni

Rientro di istruzioni condizionali varia a seconda di dimensioni delle espressioni che li compongono. Se `cond`, `e1` e `e2` sono brevi, è sufficiente scriverli su un'unica riga:

```fsharp
if cond then e1 else e2
```

Se uno dei due `cond`, `e1` o `e2` sono più lunghi, ma non su più righe:

```fsharp
if cond
then e1
else e2
```

Se le espressioni sono su più righe:

```fsharp
if cond then
    e1
else
    e2
```

Più istruzioni condizionali, con `elif` e `else` vengono rientrate nello stesso ambito come il `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Costrutti di modello corrispondenti

Usare un `|` per ogni clausola di una corrispondenza con alcun rientro. Se l'espressione è breve, è possibile utilizzare una singola riga se ogni sottoespressione anche è semplice.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Se l'espressione a destra del criterio corrispondente freccia è troppo grande, spostarlo alla riga seguente, con rientro un unico passaggio dai `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Criteri di ricerca di funzioni anonime, a partire da `function`, devono in genere non impostare un rientro troppo lontano. Ad esempio, è bene il rientro di un ambito come segue:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Criteri di ricerca nelle funzioni definite dal `let` oppure `let rec` deve essere rientrati 4 spazi dopo l'avvio di `let`, anche se `function` parola chiave viene usata:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Non è consigliabile allineare le frecce.

## <a name="formatting-trywith-expressions"></a>Formattazione try / with espressioni

Criteri di ricerca nel tipo di eccezione devono essere rientrato allo stesso livello `with`.

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

## <a name="formatting-function-parameter-application"></a>Formattazione dell'applicazione di parametro (funzione)

In generale, la maggior parte delle applicazione di parametro di funzione viene eseguita nella stessa riga.

Se si vuole applicare parametri a una funzione in una nuova riga, impostare un rientro per un ambito.

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

Le stesse linee guida applicano per le espressioni lambda come argomenti della funzione. Se il corpo di un'espressione lambda, il corpo può contenere un'altra riga, rientrata in base a un ambito

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

Tuttavia, se il corpo di un'espressione lambda su più righe, è consigliabile estrarla factoring in funzioni separate piuttosto che dispone di un costrutto multilinea applicato come un singolo argomento a una funzione.

### <a name="formatting-infix-operators"></a>Gli operatori infissi di formattazione

Operatori separati da spazi. Sono evidenti eccezioni a questa regola il `!` e `.` operatori.

Le espressioni di infissi sono OK lineup nella stessa colonna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formattazione operatori pipeline

Pipeline `|>` operatori devono essere inserito sotto le espressioni operano in base a.

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

Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non debba essere rientrato. Elementi Namespace non sono necessario impostare un rientro.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Formattazione di espressioni di oggetto e interfacce

Interfacce e le espressioni di oggetto devono essere allineate nello stesso modo con `member` viene applicato un rientro dopo 4 spazi.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Spazi vuoti nelle espressioni di formattazione

Evitare gli spazi vuoti estranei nelle espressioni F#.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Gli argomenti denominati non necessario anche spazio che racchiudono il `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
