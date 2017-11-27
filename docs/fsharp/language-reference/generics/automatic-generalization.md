---
title: Generalizzazione automatica (F#)
description: "Informazioni su come F # generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a>Generalizzazione automatica

F # utilizza l'inferenza del tipo per valutare i tipi di espressioni e funzioni. In questo argomento viene descritto come F # generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile.


## <a name="automatic-generalization"></a>Generalizzazione automatica
Il compilatore F # quando si esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico. Il compilatore esamina ogni parametro e determina se la funzione presenta una dipendenza dal tipo specifico di tale parametro. In caso contrario, viene dedotto il tipo generico.

Esempio di codice seguente viene illustrata una funzione che il compilatore deduce per essere generico.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Il tipo viene dedotto da `'a -> 'a -> 'a`.

Il tipo di indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo. Uno dei motivi per cui la funzione precedente può essere generico è che la maggiore-operatore (`>`) è generico. Maggiore-rispetto a operatore ha la firma `'a -> 'a -> bool`. Non tutti gli operatori sono generici e se il codice in una funzione utilizza un tipo di parametro insieme a una funzione non generico o un operatore, tale tipo di parametro non può essere generalizzato.

Poiché `max` è generico, può essere utilizzato con tipi, ad esempio `int`, `float`e così via, come illustrato negli esempi seguenti.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Tuttavia, i due argomenti devono essere dello stesso tipo. La firma è `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`. Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

Il `max` funzione funziona anche con qualsiasi tipo che supporta la maggiore-operatore. Di conseguenza, è possibile usare anche su una stringa, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a>Limitazione valore
Il compilatore esegue generalizzazione automatica solo definizioni di funzione completa che includono argomenti espliciti e valori semplici non modificabili.

Ciò significa che il compilatore genera un errore se si tenta di compilare il codice che non è sufficientemente vincolato a un tipo specifico, ma anche non generalizzabile. Il messaggio di errore per questo problema si riferisce a questa restrizione sulla generalizzazione automatica per i valori come il *valore restrizione*.

L'errore di restrizione di valore si verifica in genere, quando si desidera un costrutto generico, ma il compilatore dispone di informazioni insufficienti per generalizzarla o quando si omettono involontariamente sufficienti informazioni sul tipo di un costrutto non generico. La soluzione all'errore di restrizione di valore consiste nel fornire ulteriori informazioni esplicite per vincolare meglio il problema di inferenza del tipo, in uno dei modi seguenti:


- Vincolare un tipo deve essere non generici mediante l'aggiunta di un'annotazione di tipo esplicito per un parametro o valore.

- Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione di funzione o in modo incompleto applicati gli argomenti della funzione sottoposte a currying, provare a riscrivere la funzione come una definizione di funzione ordinaria.

- Se il problema è un'espressione troppo complessa per essere generalizzato, è necessario inserirla in una funzione mediante l'aggiunta di un parametro aggiuntivo e inutilizzato.

- Aggiungere parametri di tipo generico espliciti. Questa opzione viene utilizzata raramente.

- Gli esempi di codice seguenti illustrano ognuno di questi scenari.

Caso 1: Espressione troppo complessa. In questo esempio, l'elenco `counter` deve essere `int option ref`, ma non è definito come valore semplice non modificabile.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Caso 2: Utilizzo di un costrutto non generalizzabile per definire una funzione generica. In questo esempio, il costrutto è non generalizzabile perché implica applicazione parziale degli argomenti della funzione.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Caso 3: Aggiunta di un parametro aggiuntivo e inutilizzato. Poiché questa espressione non è abbastanza semplice per la generalizzazione, il compilatore genera l'errore di restrizione di valore.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Caso 4: Aggiunta di parametri di tipo.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

Nell'ultimo caso, il valore diventa una funzione di tipo, che può essere utilizzata per creare valori di molti tipi diversi, ad esempio come indicato di seguito:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Vedere anche
[Inferenza di tipi](../type-inference.md)

[Generics](index.md)

[Parametri di tipo risolti staticamente](statically-resolved-type-parameters.md)

[Vincoli](constraints.md)

