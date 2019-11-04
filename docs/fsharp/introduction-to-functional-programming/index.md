---
title: Introduzione alla programmazione funzionale in F#
description: Informazioni sulle nozioni di base della programmazione F#funzionale in.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424706"
---
# <a name="introduction-to-functional-programming-in-f"></a>Introduzione alla programmazione funzionale in F\#

La programmazione funzionale è uno stile di programmazione che enfatizza l'uso di funzioni e dati non modificabili. La programmazione funzionale tipizzata si verifica quando la programmazione funzionale è combinata con tipi statici F#, ad esempio con. In generale, i concetti seguenti sono evidenziati nella programmazione funzionale:

* Funzioni come costrutti primari usati
* Espressioni anziché istruzioni
* Valori non modificabili sulle variabili
* Programmazione dichiarativa sulla programmazione imperativa

In questa serie verranno illustrati concetti e modelli nella programmazione funzionale tramite F#. Si apprenderà anche un F# altro aspetto.

## <a name="terminology"></a>Terminologia

La programmazione funzionale, come altri paradigmi di programmazione, viene fornita con un vocabolario che dovrà essere apprese in futuro. Di seguito sono riportati alcuni termini comuni:

* **Function** : una funzione è un costrutto che produce un output quando viene specificato un input. Più formalmente, viene eseguito il _mapping_ di un elemento da un set a un altro set. Questo formalismo viene sollevato nel concreto in molti modi, soprattutto quando si usano funzioni che operano su raccolte di dati. Si tratta del concetto più semplice e importante nella programmazione funzionale.
* **Espressione** : un'espressione è un costrutto nel codice che produce un valore. In F#, questo valore deve essere associato o ignorato in modo esplicito. Un'espressione può essere sostituita in modo banale da una chiamata di funzione.
* **Purezza** -purezza è una proprietà di una funzione in modo che il valore restituito sia sempre lo stesso per gli stessi argomenti e che la relativa valutazione non abbia effetti collaterali. Una funzione pura dipende interamente dagli argomenti.
* **Trasparenza referenziale** : la trasparenza referenziale è una proprietà di espressioni in modo che possano essere sostituite con il relativo output senza influire sul comportamento di un programma.
* **Immutabilità-** immutabilità indica che un valore non può essere modificato sul posto. Questo si differenzia dalle variabili, che possono cambiare sul posto.

## <a name="examples"></a>Esempi

Gli esempi seguenti illustrano questi concetti di base.

### <a name="functions"></a>Funzioni

Il costrutto più comune e fondamentale nella programmazione funzionale è la funzione. Ecco una funzione semplice che aggiunge 1 a un numero intero:

```fsharp
let addOne x = x + 1
```

La firma del tipo è la seguente:

```fsharp
val addOne: x:int -> int
```

La firma può essere letta come "`addOne` accetta una `int` denominata `x` e produrrà un `int`". Più formalmente, `addOne` sta _eseguendo il mapping_ di un valore dal set di numeri interi al set di numeri interi. Il token `->` significa questo mapping. In F#è in genere possibile esaminare la firma della funzione per ottenere un'idea di come funziona.

Perché la firma è importante? Nella programmazione funzionale tipizzata, l'implementazione di una funzione è spesso meno importante della firma del tipo effettivo. Il fatto che `addOne` aggiunge il valore 1 a un intero è interessante in fase di esecuzione, ma quando si costruisce un programma, il fatto che accetta e restituisce un `int` è ciò che informa come si userà effettivamente questa funzione. Inoltre, una volta utilizzata correttamente questa funzione (rispetto alla firma del tipo), la diagnosi di eventuali problemi può essere eseguita solo all'interno del corpo della funzione `addOne`. Si tratta dell'impeto dietro la programmazione funzionale tipizzata.

### <a name="expressions"></a>Espressioni

Le espressioni sono costrutti che restituiscono un valore. Diversamente dalle istruzioni che eseguono un'azione, le espressioni possono essere considerate l'esecuzione di un'azione che restituisce un valore. Le espressioni vengono quasi sempre utilizzate a favore delle istruzioni nella programmazione funzionale.

Si consideri la funzione precedente `addOne`. Il corpo di `addOne` è un'espressione:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

È il risultato di questa espressione che definisce il tipo di risultato della funzione `addOne`. Ad esempio, l'espressione che costituisce questa funzione può essere modificata in modo che sia un tipo diverso, ad esempio un `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

La firma della funzione è ora:

```fsharp
val addOne: x:'a -> string
```

Poiché qualsiasi tipo in F# può avere `ToString()` chiamato su di esso, il tipo di `x` è stato reso generico (chiamato [generalizzazione automatica](../language-reference/generics/automatic-generalization.md)) e il tipo risultante è un `string`.

Le espressioni non sono solo i corpi di funzioni. È possibile avere espressioni che producono un valore usato altrove. Uno più comune è `if`:

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

L'espressione `if` produce un valore denominato `result`. Si noti che è possibile omettere `result` completamente, rendendo l'espressione `if` il corpo della funzione `addOneIfOdd`. La cosa principale da ricordare sulle espressioni è che producono un valore.

È disponibile un tipo speciale, `unit`, che viene usato quando non è necessario restituire alcun valore. Si consideri, ad esempio, questa semplice funzione:

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

La firma ha un aspetto simile al seguente:

```fsharp
val printString: str:string -> unit
```

Il tipo di `unit` indica che non viene restituito alcun valore effettivo. Questa operazione è utile quando si dispone di una routine che deve "lavorare", anche se non è disponibile alcun valore da restituire come risultato di tale operazione.

Si tratta di un contrasto acuto rispetto alla programmazione imperativa, in cui il costrutto `if` equivalente è un'istruzione e la produzione di valori viene spesso eseguita con le variabili mutanti. Ad esempio, in C#il codice potrebbe essere scritto come segue:

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

Vale la pena notare che C# e altri linguaggi di tipo C supportano l' [espressione ternaria](../../csharp/language-reference/operators/conditional-operator.md), che consente la programmazione condizionale basata su espressioni.

Nella programmazione funzionale è raro mutare i valori con le istruzioni. Sebbene alcuni linguaggi funzionali supportino istruzioni e mutazioni, non è comune usare questi concetti nella programmazione funzionale.

### <a name="pure-functions"></a>Funzioni pure

Come indicato in precedenza, le funzioni pure sono funzioni che:

* Restituisce sempre lo stesso valore per lo stesso input.
* Non hanno effetti collaterali.

È utile considerare le funzioni matematiche in questo contesto. In matematica le funzioni dipendono solo dai rispettivi argomenti e non hanno effetti collaterali. Nella funzione matematica `f(x) = x + 1`il valore di `f(x)` dipende solo dal valore di `x`. Le funzioni pure nella programmazione funzionale hanno lo stesso modo.

Quando si scrive una funzione pura, la funzione deve dipendere solo dai relativi argomenti e non eseguire alcuna azione che abbia come risultato un effetto collaterale.

Di seguito è riportato un esempio di una funzione non pura perché dipende da uno stato modificabile globale:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

La funzione `addOneToValue` è chiaramente impura, perché `value` può essere modificata in qualsiasi momento per avere un valore diverso da 1. Questo modello di a seconda di un valore globale deve essere evitato nella programmazione funzionale.

Di seguito è riportato un altro esempio di una funzione non pura, perché esegue un effetto collaterale:

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

Sebbene questa funzione non dipenda da un valore globale, scrive il valore di `x` nell'output del programma. Sebbene non vi sia alcun problema intrinseco, significa che la funzione non è pura. Se un'altra parte del programma dipende da un elemento esterno al programma, ad esempio il buffer di output, la chiamata a questa funzione può influire sull'altra parte del programma.

La rimozione dell'istruzione `printfn` rende la funzione pure:

```fsharp
let addOneToValue x = x + 1
```

Anche se questa funzione non è intrinsecamente _migliore_ della versione precedente con l'istruzione `printfn`, garantisce che la funzione restituisca un valore. La chiamata di questa funzione un numero qualsiasi di volte produce lo stesso risultato: produce solo un valore. La prevedibilità fornita dalla purezza è un elemento che molti programmatori funzionali si impegnano.

### <a name="immutability"></a>Immutabilità

Infine, uno dei concetti fondamentali della programmazione funzionale tipizzata è l'immutabilità. In F#tutti i valori non sono modificabili per impostazione predefinita. Ciò significa che non possono essere mutate sul posto a meno che non vengano contrassegnate in modo esplicito come modificabile.

In pratica, l'utilizzo di valori non modificabili significa che è possibile modificare l'approccio alla programmazione da, "devo modificare qualcosa", a "è necessario produrre un nuovo valore".

Se ad esempio si aggiunge 1 a un valore, viene generato un nuovo valore, senza mutare quello esistente:

```fsharp
let value = 1
let secondValue = value + 1
```

In F#il codice seguente **non** modifica la funzione `value`. viene invece eseguito un controllo di uguaglianza:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Alcuni linguaggi di programmazione funzionale non supportano alcuna mutazione. In F#è supportato, ma non è il comportamento predefinito per i valori.

Questo concetto si estende anche ulteriormente alle strutture di dati. Nella programmazione funzionale, le strutture di dati non modificabili, ad esempio set (e molti altri), hanno un'implementazione diversa da quella prevista inizialmente. Concettualmente, qualcosa come l'aggiunta di un elemento a un set non modifica il set, produce un _nuovo_ set con il valore aggiunto. Dietro le quinte, questa operazione viene spesso eseguita da una struttura di dati diversa che consente di tenere traccia di un valore in modo efficiente, in modo che sia possibile assegnare la rappresentazione appropriata dei dati di conseguenza.

Questo stile di utilizzo di valori e strutture di dati è fondamentale, in quanto impone di trattare qualsiasi operazione che modifica un elemento come se creasse una nuova versione di tale elemento. Ciò consente di verificare la coerenza tra uguaglianza e comparabilità nei programmi.

## <a name="next-steps"></a>Passaggi successivi

Nella sezione successiva vengono illustrate in modo approfondito le funzioni, esplorando i diversi modi in cui è possibile usarle nella programmazione funzionale.

[Funzioni di prima classe](first-class-functions.md) Esplora le funzioni in modo approfondito, mostrando come è possibile usarle in diversi contesti.

## <a name="further-reading"></a>Ulteriori informazioni

La serie [funzionale Thinking](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) è un'altra risorsa ideale per apprendere la programmazione F#funzionale con. Vengono illustrati i concetti fondamentali della programmazione funzionale in modo pragmatico e di facile lettura, usando F# le funzionalità per illustrare i concetti.
