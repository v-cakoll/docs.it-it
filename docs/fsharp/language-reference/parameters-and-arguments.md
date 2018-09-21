---
title: Parametri e argomenti (F#)
description: 'Informazioni sul supporto del linguaggio F # per la definizione dei parametri e passare argomenti a funzioni, metodi e proprietà.'
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532795"
---
# <a name="parameters-and-arguments"></a>Parametri e argomenti

In questo argomento viene descritto il supporto di language per la definizione dei parametri e passare argomenti a funzioni, metodi e proprietà. Sono incluse informazioni su come passare per riferimento e su come definire e usare i metodi che possono accettare un numero variabile di argomenti.

## <a name="parameters-and-arguments"></a>Parametri e argomenti

Il termine *parametro* viene usato per descrivere i nomi per i valori che dovrebbero essere forniti. Il termine *argomento* viene usato per i valori specificati per ogni parametro.

Parametri possono essere specificati nella tupla o sottoposto a currying o in una combinazione dei due. È possibile passare argomenti usando un nome di parametro espliciti. I parametri dei metodi possono essere specificati come facoltativi e assegnati il valore predefinito.

## <a name="parameter-patterns"></a>Modelli di parametri

I parametri specificati per le funzioni e i metodi disponibili, in generale, modelli separati da spazi. Ciò significa che, in teoria, tutti i modelli descritti in [espressioni di ricerca](match-expressions.md) può essere utilizzato in un elenco di parametri per una funzione o membro.

Metodi usano in genere il formato di tupla del passaggio di argomenti. Ciò consente di ottenere un risultato più chiaro dalla prospettiva di altri linguaggi .NET perché il formato di tupla corrisponde alla modalità di argomenti vengono passati nei metodi .NET.

Il currying viene spesso utilizzata con funzioni create con `let` associazioni.

Lo pseudocodice seguente illustra esempi di tupla e argomenti sottoposti a currying.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Form combinato sono possibili quando alcuni argomenti sono le tuple e altri non lo sono.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Altri modelli possono anche essere usati in elenchi di parametri, ma se il modello di parametro non corrisponde a tutti i possibili input, potrebbe esserci una corrispondenza completa in fase di esecuzione. L'eccezione `MatchFailureException` viene generato quando il valore di un argomento non corrisponde ai modelli specificati nell'elenco dei parametri. Il compilatore genera un avviso quando si consente a un modello di parametro per le corrispondenze incomplete. Almeno un altro modello è comunemente utile per gli elenchi di parametri e che è il carattere jolly. È consigliabile usare il modello carattere jolly in un elenco di parametri quando vuoi semplicemente ignorare gli argomenti specificati. Il codice seguente viene illustrato l'utilizzo del modello con caratteri jolly in un elenco di argomenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Il modello carattere jolly può essere utile ogni volta che gli argomenti passati non è necessario, ad esempio il punto di ingresso principale per un programma, se non si è interessati agli argomenti della riga di comando che vengono generalmente forniti come una matrice di stringhe, come nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Altri modelli che vengono a volte usati negli argomenti sono la `as` modello e i modelli di identificatori associati a criteri attivi e le unioni discriminate. È possibile usare il modello di unione discriminata case singolo come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

L'output è indicato di seguito.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Criteri attivi possono risultare utili come parametri, ad esempio, durante la trasformazione di un argomento in un formato desiderato, come nell'esempio seguente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

È possibile usare il `as` criterio per archiviare un valore corrispondente come valore locale, come illustrato nella seguente riga di codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Un altro modello che viene usato in alcuni casi è una funzione che lascia l'ultimo argomento senza nome, fornendo come corpo della funzione, un'espressione lambda che consente di eseguire immediatamente un criterio di ricerca in base all'argomento implicito. Un esempio di questa è la seguente riga di codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Questo codice definisce una funzione che accetta un elenco generico e restituisce `true` se l'elenco è vuoto, e `false` in caso contrario. L'utilizzo di tali tecniche possa rendere più difficile da leggere codice.

In alcuni casi, i modelli che prevedono corrispondenze incomplete sono utili, ad esempio, se è noto che gli elenchi nel programma dispongono solo di tre elementi, si potrebbe utilizzare un modello simile al seguente in un elenco di parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Uso di criteri di corrispondenza incompleta è consigliabile riservarla ai creazione rapida di prototipi e altri usi temporanei. Il compilatore genererà un avviso per tale codice. Tali modelli non possono coprire caso generale di tutti i possibili input e pertanto non sono adatti per le API dei componenti.

## <a name="named-arguments"></a>Argomenti denominati

Argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitati da virgole, o può essere passati in modo esplicito a un metodo, fornendo il nome, seguito da un segno di uguale e il valore deve essere passato. Se specificato, fornendo il nome, possono essere visualizzati in un ordine diverso da quello usato nella dichiarazione.

Gli argomenti denominati possono rendere codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.

Gli argomenti denominati sono consentiti solo per metodi, non per `let`-associati valori di funzioni, funzioni o le espressioni lambda.

Esempio di codice seguente viene illustrato l'utilizzo di argomenti denominati.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe utilizzando una sintassi simile a quella degli argomenti denominati. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Per altre informazioni, vedere [costruttori (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parametri facoltativi

È possibile specificare un parametro facoltativo per un metodo con un punto interrogativo davanti al nome del parametro. I parametri facoltativi vengono interpretati come tipo di opzione F #, pertanto è possibile eseguire le query in modo normale che i tipi di opzione sono sottoposti a query, usando un `match` espressione con `Some` e `None`. I parametri facoltativi sono consentiti solo per i membri, non su funzioni create tramite `let` associazioni.

È anche possibile usare una funzione `defaultArg`, che imposta un valore predefinito di un argomento facoltativo. Il `defaultArg` funzione accetta il parametro facoltativo come primo argomento e il valore predefinito come il secondo.

Nell'esempio seguente viene illustrato l'utilizzo di parametri facoltativi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

L'output è indicato di seguito.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Il passaggio per riferimento

Passaggio di un valore di F # per riferimento implica [zkratka](byrefs.md), che sono tipi puntatore gestito. Materiale sussidiario per il tipo da usare è il seguente:

* Usare `inref<'T>` se è necessario solo leggere il puntatore del mouse.
* Usare `outref<'T>` se è necessario solo scrivere il puntatore del mouse.
* Usare `byref<'T>` se è necessario leggere da e scrivere il puntatore del mouse.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

Poiché il parametro è un puntatore e il valore è modificabile, qualsiasi modifica del valore viene mantenute dopo l'esecuzione della funzione.

È possibile usare una tupla come valore restituito per archiviare qualsiasi `out` parametri nei metodi della libreria .NET. In alternativa, è possibile trattare il `out` come parametro un `byref` parametro. L'esempio di codice seguente illustra entrambe le direzioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrici di parametri

In alcuni casi è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo. Non sarebbe pratico creare tutti i possibili metodi di overload per conto di tutti i tipi che può essere usati. Le implementazioni di .NET forniscono supporto per tali metodi tramite la funzionalità di matrice di parametri. Un metodo che accetta una matrice di parametri nella sua firma può essere fornito con un numero arbitrario di parametri. I parametri vengono inseriti in una matrice. Il tipo degli elementi della matrice determina i tipi di parametro che possono essere passati alla funzione. Se si definisce la matrice di parametri con `System.Object` come tipo di elemento, quindi il codice client può passare i valori di qualsiasi tipo.

In F #, matrici di parametri possono essere definite solo nei metodi. Non possono essere usate in funzioni autonome o funzioni definite nei moduli.

Per definire una matrice di parametri, utilizzare il `ParamArray` attributo. Il `ParamArray` attributo può essere applicato solo all'ultimo parametro.

Il codice seguente viene illustrato sia la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di un tipo in F # che dispone di un metodo che accetta una matrice di parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Quando si esegue in un progetto, l'output del codice precedente è come segue:

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

- [Membri](members/index.md)
