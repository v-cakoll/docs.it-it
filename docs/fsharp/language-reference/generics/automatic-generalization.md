---
title: Generalizzazione automatica
description: Informazioni su come F# generalizza automaticamente gli argomenti e i tipi di funzioni in modo che funzionano con più tipi, laddove possibile.
ms.date: 05/16/2016
ms.openlocfilehash: 8fc61b5e0c227474a5e913b37f4c0dad9b235a6f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641877"
---
# <a name="automatic-generalization"></a>Generalizzazione automatica

F#utilizza l'inferenza per valutare i tipi di funzioni ed espressioni. Questo argomento viene descritto come F# generalizza automaticamente gli argomenti e i tipi di funzioni in modo che funzionano con più tipi quando possibile.

## <a name="automatic-generalization"></a>Generalizzazione automatica

Il F# compilatore, quando esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico. Il compilatore esamina ogni parametro e determina se la funzione ha una dipendenza dal tipo specifico di tale parametro. Se non esiste, il tipo viene dedotto come generici.

Esempio di codice seguente viene illustrata una funzione che il compilatore deduce automaticamente per essere generica.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Il tipo viene dedotto per essere `'a -> 'a -> 'a`.

Il tipo indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo. Uno dei motivi per cui la funzione precedente può essere generica è che il maggiore-operatore (`>`) è a sua volta generico. Maggiore-di operatore ha la firma `'a -> 'a -> bool`. Non tutti gli operatori sono generici e se il codice in una funzione Usa un tipo di parametro insieme a una funzione non generico o un operatore, tale tipo di parametro non può essere generalizzato.

In quanto `max` è generico e può essere utilizzato con i tipi, ad esempio `int`, `float`e così via, come illustrato negli esempi seguenti.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Tuttavia, i due argomenti devono essere dello stesso tipo. La firma viene `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`. Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

Il `max` funzione funziona anche con qualsiasi tipo che supporta il valore maggiore: operatore di maggioranza. Pertanto, si può anche usarlo in una stringa, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Limitazione dei valori

Il compilatore esegue generalizzazione automatica solo nelle definizioni di funzione completa che includono argomenti espliciti e sul semplici valori non modificabili.

Ciò significa che il compilatore genera un errore se si prova a compilare il codice che non è sufficientemente vincolato a un tipo specifico, ma anche non generalizzabile. Il messaggio di errore per questo problema è relativo a questa limitazione per la generalizzazione automatica per i valori come il *limitazione valore*.

L'errore di limitazione valore si verifica in genere, quando si desidera un costrutto per essere generico, ma il compilatore dispone di informazioni sufficienti per generalizzarla o quando si omette involontariamente sufficienti informazioni sul tipo in un costrutto non generico. La soluzione per l'errore di limitazione valore consiste nel fornire informazioni più esplicite per comprenderle appieno limitare il problema di inferenza del tipo, in uno dei modi seguenti:

- Vincolare un tipo può essere non generica aggiungendo un'annotazione di tipo esplicito a un parametro o valore.

- Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione di funzione o in modo incompleto applicati gli argomenti della funzione sottoposti a currying, provare a riscrivere la funzione come una definizione di funzione ordinaria.

- Se il problema è un'espressione troppo complessa per procedere alla generalizzazione, trasformarlo in una funzione mediante l'aggiunta di un parametro aggiuntivo e non usato.

- Aggiungere parametri di tipo generico esplicita. Questa opzione viene utilizzata raramente.

- Gli esempi di codice seguente viene illustrato ognuno di questi scenari.

Caso 1: Espressione troppo complessa. In questo esempio, nell'elenco `counter` è destinato a essere `int option ref`, ma non è definito come un semplice valore non modificabile.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Caso 2: Per definire una funzione generica, utilizzando un costrutto non generalizzabile. In questo esempio, il costrutto è non generalizzabile dal momento che implica l'applicazione parziale degli argomenti della funzione.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Caso 3: Aggiunta di un parametro aggiuntivo e non usato. Poiché questa espressione non è abbastanza semplice per la generalizzazione, il compilatore genera l'errore di limitazione valore.

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

- [Inferenza di tipi](../type-inference.md)
- [Generics](index.md)
- [Parametri di tipo risolti staticamente](statically-resolved-type-parameters.md)
- [Vincoli](constraints.md)
