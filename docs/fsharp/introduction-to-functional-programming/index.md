---
title: Introduzione alla programmazione funzionale in F#
description: Scopri i concetti fondamentali della programmazione funzionale in F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724478"
---
# <a name="introduction-to-functional-programming-in-f"></a>Introduzione alla programmazione funzionale in F# #

Programmazione funzionale è uno stile di programmazione che mette in evidenza l'utilizzo di funzioni e dati non modificabili. Programmazione funzionale tipizzata è quando la programmazione funzionale è combinata con i tipi statici, ad esempio con F#. In generale, i concetti seguenti sono evidenziati nella programmazione funzionale:

* Funzioni come i costrutti primari che è usare
* Espressioni anziché le istruzioni
* Valori non modificabili sulle variabili
* Programmazione dichiarativa tramite programmazione imperativa

In questa serie, si esamineranno concetti e modelli di programmazione funzionale con F#. Corso della trattazione, scoprirai alcune F# troppo.

## <a name="terminology"></a>Terminologia

Programmazione funzionale, ad esempio altri paradigmi di programmazione, viene fornito con un vocabolario che si sarà necessario conoscere. Ecco alcuni termini comuni si vedrà tutto il tempo:

* **Funzione** -una funzione è un costrutto che produrrà un output quando viene specificato un input. In termini più formali, si _viene eseguito il mapping_ imposta un elemento da uno a un altro set. Questo formato viene eseguito il lift nella concreti molti aspetti, soprattutto quando si usa funzioni che operano su raccolte di dati. Si tratta di concetto nella programmazione funzionale più base (e importante). 
* **Espressione** -un'espressione è un costrutto di codice che produce un valore. In F#, questo valore deve essere associato o ignorato in modo esplicito. Un'espressione può essere facilmente sostituita da una chiamata di funzione.
* **Purezza** -purezza è una proprietà di una funzione di modo che il relativo valore restituito è sempre uguale per gli stessi argomenti e che la sua valutazione ha effetti collaterali. Una funzione pura dipende interamente relativi argomenti.
* **Trasparenza referenziale** -trasparenza referenziale è una proprietà di espressioni tale che può essere sostituiti con il relativo output senza influire sul comportamento di un programma.
* **Immutabilità** -significa immutabilità che un valore non può essere modificato sul posto. Si tratta a differenza delle variabili, che può essere modificato in posizione.

## <a name="examples"></a>Esempi

Gli esempi seguenti illustrano questi concetti di base.

### <a name="functions"></a>Funzioni

Costrutto più fondamentale e comune nella programmazione funzionale sono la funzione. Di seguito è una funzione semplice che aggiunge 1 a un integer:

```fsharp
let addOne x = x + 1
```

La firma di tipo è il seguente:

```fsharp
val addOne: x:int -> int
```

La firma può essere letto come, "`addOne` accetta un `int` denominate `x` e produrrà un `int`". Più formalmente `addOne` viene _mapping_ un valore dal set di numeri interi al set di numeri interi. Il `->` token indica questo mapping. In F#, in genere è possibile esaminare la firma della funzione e farsi un'idea di cosa.

Quindi, perché è la firma importante? Nella programmazione funzionale tipizzata, l'implementazione di una funzione è spesso meno importante della firma del tipo effettivo. Il fatto che `addOne` aggiunge il valore 1 per un numero intero è interessante in fase di esecuzione, ma quando si costruisce un programma, il fatto che accetta e restituisce un `int` è ciò che indica come verrà effettivamente usata questa funzione. Inoltre, quando si utilizza questa funzione in modo corretto (in relazione la firma di tipo), la diagnosi dei problemi è possibile solo all'interno del corpo del `addOne` (funzione). Questo è l'impulso di programmazione funzionale tipizzata.

### <a name="expressions"></a>Espressioni

Le espressioni sono costrutti che restituiscono un valore. A differenza delle istruzioni che eseguono un'azione, espressioni possono essere considerate eseguendo un'azione che restituisce un valore. Le espressioni vengono usate quasi sempre a favore di istruzioni nella programmazione funzionale.

Si consideri la funzione precedente, `addOne`. Il corpo di `addOne` è un'espressione:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

È il risultato dell'espressione che definisce il tipo di risultato di `addOne` (funzione). Ad esempio, l'espressione che costituisce questa funzione è stato possibile modificare per essere un tipo diverso, ad esempio un `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

È ora la firma della funzione:

```fsharp
val addOne: x:'a -> string
```

Poiché qualsiasi tipo in F# può avere `ToString()` chiamati su di esso, il tipo di `x` apportata generico (chiamato [generalizzazione automatica](../language-reference/generics/automatic-generalization.md)), e il tipo risultante è un `string`.

Le espressioni non sono appena i corpi delle funzioni. È possibile disporre le espressioni che producono un valore utilizzato in un' posizione. Un comune è `if`:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

Il `if` espressione produce un valore chiamato `result`. Si noti che è possibile omettere `result` interamente, rendendo il `if` il corpo di espressione del `addOneIfOdd` (funzione). L'aspetto principale da ricordare riguardo a espressioni è che producono un valore.

È presente un tipo speciale, `unit`, che viene usato quando sono presenti elementi da restituire. Ad esempio, prendere in considerazione questa semplice funzione:

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

La firma è simile alla seguente:

```fsharp
val printString: str:string -> unit
```

Il `unit` tipo non indica che è presente alcun valore effettivo restituito. Ciò è utile quando si dispone di una routine che deve "aziendale", anche non se nessun valore da restituire in seguito a tale lavoro.

Si tratta in netto contrasto con la programmazione imperativa, in cui l'equivalente `if` costrutto è un'istruzione e restituendo valori viene spesso eseguita con le variabili di mutazione. Ad esempio, in C#, il codice potrebbe essere scritto come segue:

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

Vale la pena notare che C# e altri linguaggi di tipo C supportano i [espressione ternaria](../../csharp/language-reference/operators/conditional-operator.md), che consentono una programmazione condizionale basata su espressione.

Nella programmazione funzionale, è raro che venga modificato i valori con le istruzioni. Sebbene alcuni linguaggi funzionali supportano le istruzioni e modifica, non è più comune per usare questi concetti in programmazione funzionale.

### <a name="pure-functions"></a>Funzioni pure

Come accennato in precedenza le funzioni pure sono funzioni che:

* Restituiscono sempre lo stesso valore per lo stesso input.
* Non hanno effetti collaterali.

È utile pensare a funzioni matematiche in questo contesto. In matematica, le funzioni dipendono unicamente i relativi argomenti e non dispongono di tutti gli effetti collaterali. Alla funzione matematica `f(x) = x + 1`, il valore di `f(x)` dipende solo dal valore di `x`. Nella programmazione funzionale le funzioni pure sono allo stesso modo.

Quando si scrive una funzione pura, la funzione deve dipendere dai relativi argomenti e non esegue alcuna azione che comporta un effetto collaterale.

Ecco un esempio di una funzione non pura perché dipende da stato globale, o modificabile:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

Il `addOneToValue` funzione è chiaramente non pure, poiché `value` è stato possibile modificare in qualsiasi momento per avere un valore diverso da 1. Questo modello di base a un valore globale è di evitare nella programmazione funzionale.

Ecco un altro esempio di una funzione non pura, perché consente di eseguire un effetto collaterale:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

Anche se questa funzione non dipende da un valore globale, scrive il valore di `x` all'output del programma. Anche se non vi sono intrinsecamente problemi con questa operazione, significa che la funzione non pura.

Rimozione di `printfn` istruzione finally rende la funzione pure:

```fsharp
let addOneToValue x = x + 1
```

Anche se questa funzione non è intrinsecamente _migliori_ rispetto alla versione precedente con il `printfn` istruzione, ma questa soluzione garantisce che questa funzione non è di restituire un valore. Chiamare questa funzione una sola volta o 1 miliardi di volte in cui verrà comunque comportare la stessa operazione: semplicemente che restituisce un valore. Questo prevedibilità è importante nella programmazione funzionale, quanto significa che qualsiasi funzione pura è referenziali trasparente.

### <a name="referential-transparency"></a>Trasparenza referenziale

La trasparenza referenziale è una proprietà di espressioni e funzioni. Per un'espressione referenziali Transparent, deve essere in grado di essere sostituito con il relativo valore risulta senza modificare il comportamento del programma. Tutte le funzioni pure sono trasparenti referenziali.

Come con le funzioni pure, può essere utile pensare a trasparenza referenziale dal punto di vista matematico. Nell'espressione matematica `y = f(x)`, `f(x)` può essere sostituito dal risultato della funzione e rimarrà comunque disponibile uguale a `y`. Questo vale anche per la trasparenza referenziale nella programmazione funzionale.

Si consiglia di chiamare definita in precedenza `addOneIfOdd` funzione due volte:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

Non è possibile sostituire ogni chiamata di funzione con il corpo della funzione, sostituendo l'argomento `input` con ogni valore:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

Entrambe `res1` e `res2` hanno lo stesso valore come se la funzione è stata chiamata, che indica che `addOneIfOdd` referenziali trasparente.

Inoltre, non ha una funzione pure in modo che sia anche referenziali trasparente. Prendere in considerazione una definizione precedente di `addOneTovalue`:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

Qualsiasi chiamata a questa funzione può anche essere sostituita dal rispettivo corpo e gli stessi elementi si verificherà ogni volta che:

* L'output viene stampato il valore, prima dell'aggiunta
* Il valore è 1 aggiunto

Durante la programmazione in F#, è spesso trasparenza referenziale che è l'obiettivo, anziché di purezza. Tuttavia, è comunque consigliabile scrivere funzioni pure quando possibile.

### <a name="immutability"></a>Immutabilità

Infine, uno dei concetti più importanti della programmazione funzionale tipizzato è immutabilità. In F#, tutti i valori non sono modificabili per impostazione predefinita. Pertanto, che non è possibile modificare sul posto a meno che non è esplicitamente contrassegnarli come modificabile.

In pratica, funzionante con i valori non modificabili significa che si modifica l'approccio alla programmazione da, "Devo modificare un elemento", per "è necessario produrre un nuovo valore".

Ad esempio, aggiungendo 1 al valore significa che produce un nuovo valore, non mutazione quello esistente:

```fsharp
let value = 1
let secondValue = value + 1
```

In F#, il codice seguente esegue **non** modificare le `value` funzione; al contrario, esegue un controllo di uguaglianza:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Alcuni linguaggi di programmazione funzionale non supportano affatto mutation. In F#, è supportato, ma non è il comportamento predefinito per i valori.

Questo concetto consente di estendere ulteriormente le strutture di dati. Nella programmazione funzionale, le strutture di dati non modificabili, ad esempio set (e molto altro ancora) avere un'implementazione diversa rispetto a inizialmente potrebbe prevedono. Concettualmente, un valore, ad esempio l'aggiunta di un elemento a un set non modifica il set, genera una _nuovo_ impostata con il valore aggiunto. Dietro le quinte, questa operazione viene spesso eseguita da una struttura di dati diversi che consente di rilevamento in modo efficiente un valore in modo che la rappresentazione appropriata dei dati può essere fornita come risultato.

Questo stile di valori e le strutture di dati è fondamentale, poiché costringe a trattare qualsiasi operazione che modifica un elemento come se crea una nuova versione di tale operazione. In questo modo per elementi quali l'uguaglianza e la comparabilità coerenza nei programmi.

## <a name="next-steps"></a>Passaggi successivi

Nella sezione successiva illustrerà accuratamente le funzioni, esplorazione di modi diversi, è possibile usarli nella programmazione funzionale.

[Funzioni di prima classe](first-class-functions.md) esamina le funzioni in profondità, che mostra come è possibile usarli in contesti diversi.

## <a name="further-reading"></a>Ulteriori informazioni

Il [pensando a livello funzionale](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) serie è un'altra risorsa eccezionale per apprendere la programmazione funzionale con F#. Vengono descritti i concetti fondamentali della programmazione funzionale in modo pragmatico e facile da leggere, tramite F# funzionalità per illustrare i concetti.