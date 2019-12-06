---
title: Parametri e argomenti
description: Informazioni sul F# supporto delle lingue per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837129"
---
# <a name="parameters-and-arguments"></a>Parametri e argomenti

Questo argomento descrive il supporto del linguaggio per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà. Sono incluse informazioni su come passare per riferimento e su come definire e usare metodi che possono assumere un numero variabile di argomenti.

## <a name="parameters-and-arguments"></a>Parametri e argomenti

Il termine *parametro* viene usato per descrivere i nomi dei valori che devono essere forniti. Il termine *argomento* viene usato per i valori forniti per ogni parametro.

I parametri possono essere specificati in formato tupla o sottoposto a currying o in una combinazione dei due. È possibile passare gli argomenti usando un nome di parametro esplicito. I parametri dei metodi possono essere specificati come facoltativi e dato un valore predefinito.

## <a name="parameter-patterns"></a>Modelli di parametri

I parametri forniti alle funzioni e ai metodi sono, in generale, i modelli separati da spazi. Ciò significa che, in linea di principio, i modelli descritti nelle [espressioni di corrispondenza](match-expressions.md) possono essere utilizzati in un elenco di parametri per una funzione o un membro.

I metodi usano in genere il formato tupla per passare argomenti. Ciò consente di ottenere un risultato più chiaro dal punto di vista di altri linguaggi .NET perché il form della tupla corrisponde al modo in cui gli argomenti vengono passati nei metodi .NET.

Il modulo sottoposto a currying viene spesso usato con le funzioni create usando associazioni `let`.

Lo pseudocodice seguente mostra esempi di tupla e argomenti sottoposti a currying.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

I moduli combinati sono possibili quando alcuni argomenti si trovano in tuple e altri non lo sono.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Gli altri modelli possono essere usati anche negli elenchi di parametri, ma se il criterio del parametro non corrisponde a tutti gli input possibili, potrebbe essere presente una corrispondenza incompleta in fase di esecuzione. Il `MatchFailureException` di eccezione viene generato quando il valore di un argomento non corrisponde ai criteri specificati nell'elenco di parametri. Il compilatore genera un avviso quando un modello di parametro consente corrispondenze incomplete. Almeno un altro criterio è comunemente utile per gli elenchi di parametri e questo è il modello con caratteri jolly. Usare il modello con caratteri jolly in un elenco di parametri quando si desidera semplicemente ignorare gli argomenti forniti. Il codice seguente illustra l'uso del modello con caratteri jolly in un elenco di argomenti.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Il modello con caratteri jolly può essere utile quando non sono necessari gli argomenti passati, ad esempio nel punto di ingresso principale a un programma, quando non si è interessati agli argomenti della riga di comando normalmente specificati come matrice di stringhe, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Altri modelli che vengono talvolta utilizzati negli argomenti sono il modello di `as` e i modelli di identificatore associati alle unioni discriminate e ai modelli attivi. È possibile usare il modello di unione discriminata a caso singolo come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

L'output è indicato di seguito.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

I criteri attivi possono essere utili come parametri, ad esempio quando si trasforma un argomento nel formato desiderato, come nell'esempio seguente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

È possibile usare il modello di `as` per archiviare un valore corrispondente come valore locale, come illustrato nella riga di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Un altro modello usato occasionalmente è una funzione che lascia l'ultimo argomento senza nome fornendo, come il corpo della funzione, un'espressione lambda che esegue immediatamente una corrispondenza del criterio nell'argomento implicito. Un esempio è la seguente riga di codice.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Questo codice definisce una funzione che accetta un elenco generico e restituisce `true` se l'elenco è vuoto e `false` in caso contrario. L'utilizzo di tali tecniche può rendere il codice più difficile da leggere.

Occasionalmente, i modelli che coinvolgono corrispondenze incomplete sono utili, ad esempio, se si è certi che gli elenchi nel programma hanno solo tre elementi, è possibile usare un modello simile al seguente in un elenco di parametri.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

L'uso di modelli con corrispondenze incomplete è particolarmente riservato per la creazione rapida di prototipi e per altri usi temporanei. Il compilatore emetterà un avviso per tale codice. Questi modelli non sono in grado di coprire il caso generale di tutti gli input possibili e pertanto non sono adatti alle API dei componenti.

## <a name="named-arguments"></a>Argomenti denominati

Gli argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitati da virgole oppure possono essere passati a un metodo in modo esplicito fornendo il nome, seguito da un segno di uguale e dal valore da passare. Se specificato specificando il nome, questi possono essere visualizzati in un ordine diverso rispetto a quello usato nella dichiarazione.

Gli argomenti denominati possono rendere il codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.

Gli argomenti denominati sono consentiti solo per i metodi, non per le funzioni associate a `let`, i valori di funzione o le espressioni lambda.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di argomenti denominati.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe usando una sintassi simile a quella degli argomenti denominati. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Per ulteriori informazioni, vedere [costruttori (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parametri facoltativi

È possibile specificare un parametro facoltativo per un metodo usando un punto interrogativo davanti al nome del parametro. I parametri facoltativi vengono interpretati come tipo di F# opzione, quindi è possibile eseguire query su di essi nel modo normale in cui vengono eseguite query sui tipi di opzioni, usando un'espressione `match` con `Some` e `None`. I parametri facoltativi sono consentiti solo per i membri, non per le funzioni create usando associazioni `let`.

È possibile passare i valori facoltativi esistenti al metodo in base al nome del parametro, ad esempio `?arg=None` o `?arg=Some(3)` o `?arg=arg`. Questa operazione può essere utile quando si compila un metodo che passa argomenti facoltativi a un altro metodo.

È anche possibile usare una funzione `defaultArg`, che imposta un valore predefinito di un argomento facoltativo. La funzione `defaultArg` accetta il parametro facoltativo come primo argomento e il valore predefinito come secondo.

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

Ai fini di C# e Visual Basic interoperabilità è possibile utilizzare gli attributi `[<Optional; DefaultParameterValue<(...)>]` F#in, in modo che i chiamanti visualizzino un argomento come facoltativo. Questa operazione equivale a definire l'argomento come facoltativo in C# come in `MyMethod(int i = 3)`.

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

È anche possibile specificare un nuovo oggetto come valore di parametro predefinito. È possibile, ad esempio, che il membro `Foo` disponga di un `CancellationToken` facoltativo come input:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

Il valore specificato come argomento per `DefaultParameterValue` deve corrispondere al tipo del parametro. Ad esempio, non sono consentiti gli elementi seguenti:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

In questo caso, il compilatore genera un avviso e ignorerà il totale di entrambi gli attributi. Si noti che il valore predefinito `null` deve essere con annotazioni di tipo, altrimenti il compilatore deduce il tipo errato, ad esempio `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.

## <a name="passing-by-reference"></a>Passaggio per riferimento

Il passaggio F# di un valore per riferimento comporta [ByRef](byrefs.md), che sono tipi di puntatore gestiti. Di seguito sono riportate le linee guida per il tipo da usare:

- Utilizzare `inref<'T>` se è necessario leggere solo il puntatore.
- Utilizzare `outref<'T>` se è necessario scrivere solo sull'indicatore di misura.
- Usare `byref<'T>` se è necessario leggere e scrivere sul puntatore.

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

È possibile utilizzare una tupla come valore restituito per archiviare qualsiasi parametro di `out` nei metodi della libreria .NET. In alternativa, è possibile considerare il parametro `out` come parametro di `byref`. Nell'esempio di codice seguente vengono illustrate entrambe le modalità.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrici di parametri

Occasionalmente è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo. Non sarebbe pratico creare tutti i possibili metodi di overload per tenere conto di tutti i tipi che potevano essere usati. Le implementazioni di .NET forniscono supporto per tali metodi tramite la funzionalità di matrice di parametri. Un metodo che accetta una matrice di parametri nella relativa firma può essere fornito con un numero arbitrario di parametri. I parametri vengono inseriti in una matrice. Il tipo degli elementi della matrice determina i tipi di parametro che è possibile passare alla funzione. Se si definisce la matrice di parametri con `System.Object` come tipo di elemento, il codice client può passare valori di qualsiasi tipo.

In F#le matrici di parametri possono essere definite solo nei metodi. Non possono essere usati in funzioni o funzioni autonome definite nei moduli.

Per definire una matrice di parametri, usare l'attributo `ParamArray`. L'attributo `ParamArray` può essere applicato solo all'ultimo parametro.

Nel codice seguente viene illustrata la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di F# un tipo in che dispone di un metodo che accetta una matrice di parametri.

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
