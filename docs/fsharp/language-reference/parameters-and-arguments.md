---
title: Parametri e argomenti
description: Informazioni sul supporto del linguaggio F , per la definizione di parametri e il passaggio di argomenti a funzioni, metodi e proprietà.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400197"
---
# <a name="parameters-and-arguments"></a>Parametri e argomenti

In questo argomento viene descritto il supporto del linguaggio per la definizione di parametri e il passaggio di argomenti a funzioni, metodi e proprietà. Include informazioni su come passare per riferimento e su come definire e utilizzare metodi che possono accettare un numero variabile di argomenti.

## <a name="parameters-and-arguments"></a>Parametri e argomenti

Il termine *parametro* viene utilizzato per descrivere i nomi per i valori che si prevede di fornire. Il termine *argomento* viene utilizzato per i valori forniti per ogni parametro.

I parametri possono essere specificati in formato tupla o sottoposto a currying o in una combinazione dei due. È possibile passare argomenti utilizzando un nome di parametro esplicito. I parametri dei metodi possono essere specificati come facoltativi e viene assegnato un valore predefinito.

## <a name="parameter-patterns"></a>Modelli di parametroParameter Patterns

I parametri forniti a funzioni e metodi sono, in generale, modelli separati da spazi. Ciò significa che, in linea di principio, qualsiasi modello descritto in [Espressioni](match-expressions.md) di corrispondenza può essere utilizzato in un elenco di parametri per una funzione o un membro.

I metodi usano in genere la forma di tupla di passaggio di argomenti. Ciò consente di ottenere un risultato più chiaro dal punto di vista di altri linguaggi .NET perché il formato della tupla corrisponde al modo in cui gli argomenti vengono passati nei metodi .NET.

Il formato sottoposto a currysima viene `let` utilizzato più spesso con le funzioni create tramite associazioni.

Lo pseudocodice seguente mostra esempi di tuple e argomenti sottoposti a currying.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Le forme combinate sono possibili quando alcuni argomenti sono in tuple e altri no.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Altri modelli possono essere usati anche negli elenchi di parametri, ma se il modello di parametro non corrisponde a tutti i possibili input, potrebbe esserci una corrispondenza incompleta in fase di esecuzione. L'eccezione `MatchFailureException` viene generata quando il valore di un argomento non corrisponde ai modelli specificati nell'elenco di parametri. Il compilatore genera un avviso quando un modello di parametro consente corrispondenze incomplete. Almeno un altro modello è in genere utile per gli elenchi di parametri, ovvero il modello con caratteri jolly. Utilizzare il modello con caratteri jolly in un elenco di parametri quando si desidera semplicemente ignorare gli argomenti forniti. Nel codice seguente viene illustrato l'utilizzo del modello con caratteri jolly in un elenco di argomenti.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Il modello con caratteri jolly può essere utile ogni volta che non sono necessari gli argomenti passati, ad esempio nel punto di ingresso principale di un programma, quando non si è interessati agli argomenti della riga di comando normalmente forniti come matrice di stringhe, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Altri modelli che vengono talvolta `as` utilizzati negli argomenti sono il modello e i modelli di identificatore associati alle unioni discriminate e ai modelli attivi. È possibile utilizzare il modello di unione discriminato caso singolo come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

L'output è indicato di seguito.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

I modelli attivi possono essere utili come parametri, ad esempio quando si trasforma un argomento in un formato desiderato, come nell'esempio seguente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

È possibile `as` utilizzare il modello per archiviare un valore corrispondente come valore locale, come illustrato nella riga di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Un altro modello utilizzato occasionalmente è una funzione che lascia l'ultimo argomento senza nome fornendo, come corpo della funzione, un'espressione lambda che esegue immediatamente una corrispondenza del modello sull'argomento implicito. Un esempio è la seguente riga di codice.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Questo codice definisce una funzione che `true` accetta un elenco generico e restituisce se l'elenco è vuoto e `false` in caso contrario. L'uso di tali tecniche può rendere il codice più difficile da leggere.

Occasionalmente, i modelli che implicano corrispondenze incomplete sono utili, ad esempio, se si sa che gli elenchi nel programma hanno solo tre elementi, è possibile utilizzare un modello simile al seguente in un elenco di parametri.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

L'uso di modelli con corrispondenze incomplete è meglio riservato per la prototipazione rapida e altri usi temporanei. Il compilatore genererà un avviso per tale codice. Tali modelli non possono coprire il caso generale di tutti i possibili input e pertanto non sono adatti per le API dei componenti.

## <a name="named-arguments"></a>Argomenti denominati

Gli argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitati da virgole oppure possono essere passati a un metodo in modo esplicito fornendo il nome, seguito da un segno di uguale e dal valore da passare. Se specificati specificando il nome, possono essere visualizzati in un ordine diverso da quello utilizzato nella dichiarazione.

Gli argomenti denominati possono rendere il codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.

Gli argomenti denominati sono consentiti solo per i metodi, non per `let`le funzioni associate, i valori di funzione o le espressioni lambda.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di argomenti denominati.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe utilizzando una sintassi simile a quella degli argomenti denominati. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Per ulteriori informazioni, vedere [Costruttori (F )](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parametri facoltativi

È possibile specificare un parametro facoltativo per un metodo utilizzando un punto interrogativo prima del nome del parametro. I parametri facoltativi vengono interpretati come il tipo di opzione F, pertanto è possibile `match` eseguire `Some` `None`una query in modo regolare in cui vengono eseguite query sui tipi di opzione, utilizzando un'espressione con e . I parametri facoltativi sono consentiti solo `let` sui membri, non sulle funzioni create tramite associazioni.

È possibile passare i valori facoltativi esistenti `?arg=None` `?arg=Some(3)` al `?arg=arg`metodo in base al nome del parametro, ad esempio o o . Ciò può essere utile quando si compila un metodo che passa argomenti facoltativi a un altro metodo.

È inoltre possibile `defaultArg`utilizzare una funzione , che imposta un valore predefinito di un argomento facoltativo. La `defaultArg` funzione accetta il parametro facoltativo come primo argomento e il valore predefinito come secondo.

Nell'esempio seguente viene illustrato l'utilizzo di parametri facoltativi.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

L'output è indicato di seguito.

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

Ai fini dell'interoperabilità di C e `[<Optional; DefaultParameterValue<(...)>]` Visual Basic è possibile utilizzare gli attributi in F , in modo che i chiamanti vedranno un argomento come facoltativo. Ciò equivale a definire l'argomento come `MyMethod(int i = 3)`facoltativo in C , come in .

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

È inoltre possibile specificare un nuovo oggetto come valore di parametro predefinito. Ad esempio, `Foo` il membro `CancellationToken` potrebbe avere un optional come input invece:For example, the member could have an optional as input instead:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

Il valore fornito `DefaultParameterValue` come argomento deve corrispondere al tipo del parametro. Ad esempio, non è consentito quanto segue:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

In questo caso, il compilatore genera un avviso e ignorerà entrambi gli attributi del tutto. Si noti `null` che il valore predefinito deve essere annotato in tipo, altrimenti il `[<Optional; DefaultParameterValue(null:obj)>] o:obj`compilatore deduce il tipo errato, ad esempio .

## <a name="passing-by-reference"></a>Passaggio per riferimentoPassing by Reference

Il passaggio di un valore F , per riferimento, implica byrefs , che sono tipi puntatore [gestiti.](byrefs.md) Le indicazioni per il tipo da utilizzare sono le seguenti:

- Utilizzare `inref<'T>` se è sufficiente leggere il puntatore.
- Utilizzare `outref<'T>` se è necessario scrivere solo nel puntatore.
- Utilizzare `byref<'T>` se è necessario leggere e scrivere nel puntatore.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

Poiché il parametro è un puntatore e il valore è modificabile, tutte le modifiche apportate al valore vengono mantenute dopo l'esecuzione della funzione.

È possibile usare una tupla `out` come valore restituito per archiviare tutti i parametri nei metodi della libreria .NET. In alternativa, è `out` possibile considerare `byref` il parametro come parametro. Nell'esempio di codice riportato di seguito vengono illustrate entrambe le modalità.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrici di parametri

Occasionalmente è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo. Non sarebbe pratico creare tutti i possibili metodi di overload per tenere conto di tutti i tipi che potrebbero essere utilizzati. Le implementazioni di .NET forniscono il supporto per tali metodi tramite la funzionalità di matrice di parametri. Un metodo che accetta una matrice di parametri nella firma può essere fornito con un numero arbitrario di parametri. I parametri vengono inseriti in una matrice. Il tipo degli elementi della matrice determina i tipi di parametro che possono essere passati alla funzione. Se si definisce `System.Object` la matrice di parametri con il tipo di elemento, il codice client può passare valori di qualsiasi tipo.

In F , le matrici di parametri possono essere definite solo nei metodi. Non possono essere utilizzati in funzioni autonome o funzioni definite nei moduli.

Per definire una matrice `ParamArray` di parametri, utilizzare l'attributo . L'attributo `ParamArray` può essere applicato solo all'ultimo parametro.

Nel codice riportato di seguito viene illustrata la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di un tipo in F , che dispone di un metodo che accetta una matrice di parametri.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Quando viene eseguito in un progetto, l'output del codice precedente è il seguente:

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Vedere anche

- [Membri](./members/index.md)
