---
title: 'Linee guida formattin codice F #'
description: 'Altre linee guida per la formattazione del codice F #.'
ms.date: 05/14/2018
ms.openlocfilehash: e5c700ca9ae3968243f11c1237b9e4b26e580dcf
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="f-code-formatting-guidelines"></a>Formattazione di linee guida di codice F #

In questo articolo vengono fornite linee guida per la modalità di formattazione del codice in modo che il codice F # è:

* In genere visualizzati come più leggibile
* È in base alle convenzioni applicate formattando altri editor e strumenti in Visual Studio
* Simile ad altro codice in linea

Queste linee guida si basano [una guida completa alla convenzioni di formattazione di F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) da [Phan Anh letame](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Regole generali per il rientro

F # utilizza degli spazi vuoti significativi per impostazione predefinita. Le linee guida seguenti sono destinate a fornire istruzioni su come alcune problematiche ciò può imporre l'esigenza.

### <a name="using-spaces"></a>Uso di spazi

Quando è necessario il rientro, è necessario utilizzare spazi e non tabulazioni. È necessario almeno uno spazio. L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro. in genere viene due, tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro.

**Si consiglia di 4 spazi per il rientro.**

Ciò premesso, rientro dei programmi è una questione soggettiva. Le variazioni sono OK, ma è la prima regola è necessario seguire *coerenza di rientro*. Scegliere uno stile di rientro generalmente accettato e usarlo sistematicamente in tutta la codebase.

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

Le unioni discriminate istanziato divisi su più righe prestare dati in essi contenuti un nuovo ambito con rientro:

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

## <a name="formatting-tuples"></a>Formattazione Tuple

Creazione di un'istanza di tupla deve essere racchiuso tra parentesi e delimitati da virgole all'interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)`, `(x, y, z)`.

È un'eccezione comunemente accettata per omettere le parentesi nei criteri di ricerca di tuple:

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>Formattazione di record

Breve record possono essere scritti in una riga:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

I record che sono più devono utilizzare le nuove righe per le etichette:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Inserire il token di apertura nella stessa riga e il token di chiusura in una nuova riga è inoltre:

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

Le stesse regole valide per gli elementi di elenco e matrice.

## <a name="formatting-lists-and-arrays"></a>Formattazione di elenchi e matrici

Scrivere `x :: l` con spazi prima e dopo il `::` operatore (`::` è un operatore infisso, pertanto delimitato da spazi) e `[1; 2; 3]` (`;` è un delimitatore, pertanto seguito da uno spazio).

Utilizzare sempre almeno uno spazio tra due operatori simile a parentesi graffa distinti. Ad esempio, lasciare uno spazio tra un `[` e un `{`.

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

Gli elenchi e matrici divisi su più righe seguono una regola simile dei record:

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

Il rientro di istruzioni condizionali dipende le dimensioni delle espressioni che li compongono. Se `cond`, `e1` e `e2` piccole, semplicemente scriverli su un'unica riga:

```fsharp
if cond then e1 else e2
```

Se `e1` e `cond` sono di dimensioni ridotte, ma `e2` è di grandi dimensioni:

```fsharp
if cond then e1
else
    e2
```

Se `e1` e `cond` sono di grandi dimensioni e `e2` è piccolo:

```fsharp
if cond then
    e1
else e2
```

Se tutte le espressioni sono di grandi dimensioni:

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

### <a name="pattern-matching-constructs"></a>Costrutti di criterio corrispondenti

Utilizzare un `|` per ogni clausola di una corrispondenza con alcun rientro. Se l'espressione è breve, è possibile utilizzare una singola riga.

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

// OK
match l with [] -> false | _ :: _ -> true
```

Se l'espressione a destra del criteri di ricerca freccia è troppo grande, spostarla nella seguente riga, rientrato un unico passaggio dal `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Criteri di corrispondenza di funzioni anonime, a partire da `function`, devono in genere non impostare un rientro troppo lontano. Ad esempio, è correttamente i rientri di un ambito come segue:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Criteri di ricerca nelle funzioni definite dal `let` oppure `let rec` deve essere rientrati 4 spazi dopo l'avvio di `let`, anche se `function` parola chiave viene utilizzata:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Non è consigliabile allineamento frecce.

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

## <a name="formatting-function-parameter-application"></a>Formattazione dell'applicazione di parametri di funzione

In generale, la maggior parte delle applicazione di parametri di funzione viene eseguita nella stessa riga.

Se si desidera applicare parametri a una funzione in una nuova riga, impostare un rientro per un ambito.

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

Gli argomenti di funzione anonima possono essere nella riga successiva o con un inesatto `fun` nella riga di argomento:

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a>Gli operatori infissi di formattazione

Operatori separati da spazi. Ovvie eccezioni a questa regola sono il `!` e `.` operatori.

Le espressioni di infissi sono OK per l'elemento lineup nella stessa colonna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formattazione operatori pipeline

Pipeline `|>` deve essere posizionato all'inizio di una riga immediatamente sotto l'espressione sta usando:

```fsharp
// OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
               |> List.ofArray
               |> List.map (fun assm -> assm.GetTypes())
               |> Array.concat
               |> List.ofArray
               |> List.map (fun t -> t.GetMethods())
               |> Array.concat

// OK, but prefer previous
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

Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di livello superiore non deve essere rientrato. Elementi Namespace non è necessario impostare un rientro.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Formattazione di espressioni di oggetto e le interfacce

Espressioni di oggetto e le interfacce devono essere allineate in modo analogo alle `member` viene aumentato il rientro dopo 4 spazi.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>Gli spazi vuoti nelle espressioni di formattazione

Evitare gli spazi vuoti estranei nelle espressioni F #.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Argomenti denominati anche senza spazio che circonda il `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a>Formattazione di righe vuote

* Separato (funzione) e la classe definizioni di primo livello con due righe vuote.
* Le definizioni di metodo all'interno di una classe sono separate da una singola riga vuota.
* Righe vuote aggiuntive possono essere utilizzate (solo se necessario) per separare i gruppi di funzioni correlate. Le righe vuote possono essere omesse tra una serie di comandi correlati di una riga (ad esempio, un set di implementazioni fittizie).
* Utilizzare le righe vuote nelle funzioni, solo se necessario, per indicare sezioni logiche.

## <a name="formatting-comments"></a>Formattazione di commenti

In genere preferire più commenti doppia barra commenti del blocco di stile di ML.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

Commenti devono converte in maiuscolo la prima lettera.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenzioni di denominazione

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Utilizzare camelCase per le funzioni e i valori associati a classe, espressione di associazione e con associazione a modello

È normale e F # è stato accettato stile da usare camelCase per tutti i nomi associati come variabili locali o in Criteri di ricerca e le definizioni di funzione.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

In locale con associazione a funzioni nelle classi devono inoltre utilizzare camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Utilizzare camelCase per le funzioni e i valori associati a modulo interni e privati

Utilizzare camelCase per i valori associati a modulo privati, inclusi i seguenti:

* Funzioni ad hoc negli script

* Valori che costituiscono l'implementazione interna del tipo o modulo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="avoid-underscores-in-names"></a>Evitare di caratteri di sottolineatura nei nomi

In passato, alcune librerie F # Usa caratteri di sottolineatura nei nomi. Tuttavia, ciò è non è più diffuso, in parte perché è in conflitto con le convenzioni di denominazione .NET. Ciò premesso, alcuni programmatori F # usare caratteri di sottolineatura molto frequentemente, in parte per motivi cronologici e tolleranza e riguardo è importante. Tuttavia, tenere presente che lo stile è spesso disliked da altri utenti che dispongono di una scelta sulla possibilità di utilizzarlo.

Alcune eccezioni includono l'interazione con componenti nativi, in cui i caratteri di sottolineatura sono molto comuni.

### <a name="use-standard-f-operators"></a>Utilizzare gli operatori standard F #

Gli operatori seguenti vengono definiti nella libreria standard di F # e devono essere usati in sostituzione definizione equivalenti. Come tende a rendere il codice più leggibile e idiomatica, è consigliabile usare questi operatori. Gli sviluppatori con uno sfondo in OCaml o altri linguaggi di programmazione funzionale potrebbero essere familiarità con linguaggi diversi. Nell'elenco seguente sono riepilogati gli operatori F # consigliati.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Utilizzare la sintassi di prefisso per i generics (`Foo<T>`) anziché la sintassi di forma suffissa (`T Foo`)

F # eredita sia lo stile di ML suffisso di denominazione dei tipi generici (ad esempio `int list`), nonché il prefisso stile .NET (ad esempio, `list<int>`). Preferisce lo stile di .NET, ad eccezione di quattro tipi specifici:

1. Per F # sono elencate, utilizzare il form della forma suffissa: `int list` anziché `list<int>`.
2. Per le opzioni di F #, utilizzare il form della forma suffissa: `int option` anziché `option<int>`.
3. Per le matrici di F #, utilizzare il nome sintattico `int[]` anziché `int array` o `array<int>`.
4. Per le celle di riferimento, utilizzare `int ref` anziché `ref<int>` o `Ref<int>`.

Per tutti gli altri tipi, utilizzare la forma prefissa.