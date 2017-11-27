---
title: Parametri e argomenti (F#)
description: "Informazioni sul supporto del linguaggio F # per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9b37a5c4-9263-4513-822a-fbb0d1004254
ms.openlocfilehash: 50f54bacd9ba7ec20a7151794734f93200df9f2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="parameters-and-arguments"></a>Parametri e argomenti

In questo argomento viene descritto il supporto lingua per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà. Sono incluse informazioni su come passare per riferimento e come definire e utilizzare i metodi che possono accettare un numero variabile di argomenti.


## <a name="parameters-and-arguments"></a>Parametri e argomenti
Il termine *parametro* viene utilizzato per descrivere i nomi per i valori che devono essere forniti. Il termine *argomento* viene utilizzato per i valori forniti per ogni parametro.

Parametri possono essere specificati in tupla o a currying, o in una combinazione dei due. È possibile passare argomenti tramite un nome di parametro espliciti. I parametri dei metodi possono essere specificati come facoltativi e assegnati un valore predefinito.


## <a name="parameter-patterns"></a>Modelli di parametri
I parametri specificati per le funzioni e metodi sono in genere, separati da spazi. Ciò significa che, in sostanza, uno dei modelli descritti in [espressioni Match](match-expressions.md) può essere utilizzato in un elenco di parametri per una funzione o membro.

I metodi usano in genere la forma di tupla di passaggio di argomenti. Questo consente di ottenere un risultato più chiaro dalla prospettiva di altri linguaggi .NET perché il formato tupla corrisponde il modo in cui gli argomenti vengono passati nei metodi .NET.

Il modulo sottoposte a currying viene generalmente utilizzato con funzioni create tramite `let` associazioni.

Nello pseudocodice seguente vengono illustrati esempi di tupla e argomenti sottoposti a currying.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Form combinato sono possibili quando alcuni argomenti sono tuple e altri non lo sono.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Altri modelli possono essere utilizzati anche negli elenchi di parametri, ma se il modello di parametri non corrisponde a tutti i possibili input, potrebbe esserci una corrispondenza incompleta in fase di esecuzione. L'eccezione `MatchFailureException` viene generato quando il valore di un argomento non corrisponde ai modelli specificati nell'elenco di parametri. Il compilatore genera un avviso quando un modello di parametri consente corrispondenze incomplete. Almeno un altro modello è in genere utile per gli elenchi di parametri, ovvero il carattere jolly. Utilizzare il carattere jolly in un elenco di parametri quando si desidera semplicemente ignorare tutti gli argomenti forniti. Il codice seguente viene illustrato l'utilizzo del modello in un elenco di argomenti con caratteri jolly.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Il carattere jolly può essere utile quando gli argomenti passati non è necessario, ad esempio il punto di ingresso principale per un programma, quando non si è interessati negli argomenti della riga di comando che vengono generalmente forniti come matrice di stringhe, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Altri modelli talvolta utilizzati negli argomenti sono di `as` modello e i modelli di identificatori associati unioni discriminate e i criteri attivi. È possibile utilizzare il modello di unione discriminata singolo case, come indicato di seguito.

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

È possibile utilizzare il `as` modello per archiviare un valore corrispondente come un valore locale, come illustrato nella seguente riga di codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Un altro modello utilizzato in alcuni casi è una funzione che lascia l'ultimo argomento senza nome fornendo, come il corpo della funzione, un'espressione lambda che esegue immediatamente i criteri di ricerca per l'argomento implicito. Un esempio di questa è la seguente riga di codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Questo codice definisce una funzione che accetta un elenco generico e restituisce `true` se l'elenco è vuoto, e `false` in caso contrario. L'utilizzo di tali tecniche può rendere più difficile da leggere codice.

In alcuni casi, i modelli che comportano corrispondenze incomplete sono utili, ad esempio, se si sa che gli elenchi nel programma dispongono solo di tre elementi, è possibile utilizzare un modello simile al seguente in un elenco di parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Uso di criteri di corrispondenza incompleti è ideale per la creazione rapida di prototipi e altri utilizzi temporanei. Il compilatore emetterà un avviso per tale codice. Tali modelli non possono coprire nel caso generale di tutti i possibili input e pertanto non sono adatti per le API dei componenti.

## <a name="named-arguments"></a>Argomenti denominati
Argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitato da virgole, o può essere passati in modo esplicito a un metodo, fornendo il nome, seguito da un segno di uguale e il valore deve essere passato. Se specificato, fornendo il nome, possono essere visualizzati in un ordine diverso da quello utilizzato nella dichiarazione.

Argomenti denominati possono rendere il codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.

Argomenti denominati sono consentiti solo per metodi, non per `let`-associati valori di funzione, funzioni o espressioni lambda.

Esempio di codice seguente viene illustrato l'utilizzo di argomenti denominati.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe utilizzando una sintassi simile a quella degli argomenti denominati. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Per ulteriori informazioni, vedere [costruttori (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parametri facoltativi
È possibile specificare un parametro facoltativo per un metodo con un punto interrogativo davanti al nome del parametro. Parametri facoltativi vengono interpretati come il tipo di opzione F #, pertanto è possibile eseguire le query in modo regolare che i tipi di opzioni vengono eseguite query sulle, utilizzando un `match` espressione con `Some` e `None`. Parametri facoltativi sono consentiti solo per i membri, non nelle funzioni create tramite `let` associazioni.

È inoltre possibile utilizzare una funzione `defaultArg`, che imposta un valore predefinito di un argomento facoltativo. Il `defaultArg` funzione accetta il parametro facoltativo come primo argomento e il valore predefinito come il secondo.

Nell'esempio seguente viene illustrato l'utilizzo di parametri facoltativi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

L'output è indicato di seguito.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Il passaggio per riferimento
F # supporta la `byref` (parola chiave), che specifica che un parametro viene passato per riferimento. Questo significa che qualsiasi modifica del valore venga mantenute dopo l'esecuzione della funzione. I valori forniti per un `byref` parametro deve essere modificabile. In alternativa, è possibile passare le celle di riferimento del tipo appropriato.

Il passaggio per riferimento nei linguaggi .NET che si è evoluto come un modo per restituire più valori da una funzione. In F #, è possibile restituire una tupla a questo scopo, o utilizzare una cella di riferimento modificabile come parametro. Il `byref` parametro viene fornito principalmente per l'interoperabilità con le librerie .NET.

Nell'esempio seguente viene illustrato l'utilizzo del `byref` (parola chiave). Si noti che quando si utilizza una cella di riferimento come parametro, è necessario creare una cella di riferimento come un valore denominato e utilizzarlo come parametro, non è sufficiente aggiungere il `ref` operatore, come illustrato nella prima chiamata a `Increment` nel codice seguente. Poiché la creazione di una cella di riferimento, viene creata una copia del valore sottostante, la prima chiamata incrementa semplicemente un valore temporaneo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

È possibile utilizzare una tupla come valore restituito per archiviare qualsiasi `out` parametri nei metodi della libreria .NET. In alternativa, è possibile trattare il `out` parametro come un `byref` parametro. Esempio di codice seguente viene illustrata in entrambe le direzioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrici di parametri
In alcuni casi è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo. Non sarebbe pratico creare tutti i possibili metodi di overload per l'account per tutti i tipi che può essere utilizzati. Le implementazioni .NET forniscono supporto per tali metodi tramite la funzionalità di parametro matrice. Un metodo che accetta una matrice di parametri nella firma può essere fornito con un numero arbitrario di parametri. I parametri vengono inseriti in una matrice. Il tipo degli elementi della matrice determina i tipi di parametro che possono essere passati alla funzione. Se si definisce la matrice di parametri con `System.Object` come tipo di elemento, quindi il codice client può passare i valori di qualsiasi tipo.

In F #, matrici di parametro possono essere definite solo nei metodi. Non possono essere utilizzate in funzioni che sono definite nei moduli o funzioni autonome.

Per definire una matrice di parametri, utilizzare il `ParamArray` attributo. Il `ParamArray` attributo può essere applicato solo all'ultimo parametro.

Il codice seguente illustra sia la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di un tipo in F # che dispone di un metodo che accetta una matrice di parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Durante l'esecuzione in un progetto, l'output del codice precedente è come segue:

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Vedere anche
[Membri](members/index.md)
