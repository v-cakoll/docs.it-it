---
title: Generalizzazione automatica
description: Informazioni su F# come generalizza automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi, quando possibile.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630631"
---
# <a name="automatic-generalization"></a>Generalizzazione automatica

F#Usa l'inferenza del tipo per valutare i tipi di funzioni ed espressioni. In questo argomento viene F# descritto come generalizzare automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile.

## <a name="automatic-generalization"></a>Generalizzazione automatica

Il F# compilatore, quando esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico. Il compilatore esamina ogni parametro e determina se la funzione ha una dipendenza dal tipo specifico di tale parametro. In caso contrario, il tipo viene dedotto come generico.

Nell'esempio di codice seguente viene illustrata una funzione che il compilatore deduce da generica.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Il tipo viene dedotto come `'a -> 'a -> 'a`.

Il tipo indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo. Uno dei motivi per cui la funzione precedente può essere generica è che l'operatore Greater-`>`than () è generico. L'operatore Greater-than dispone della `'a -> 'a -> bool`firma. Non tutti gli operatori sono generici e se il codice in una funzione utilizza un tipo di parametro insieme a una funzione o a un operatore non generico, il tipo di parametro non può essere generalizzato.

Poiché `max` è generico, può essere usato con tipi `int`come, `float`e così via, come illustrato negli esempi seguenti.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Tuttavia, i due argomenti devono essere dello stesso tipo. La firma è `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`. Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

La `max` funzione funziona anche con qualsiasi tipo che supporta l'operatore Greater-than. Pertanto, è possibile utilizzarlo anche in una stringa, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Restrizione valore

Il compilatore esegue la generalizzazione automatica solo per le definizioni di funzione complete con argomenti espliciti e su valori non modificabili semplici.

Questo significa che il compilatore genera un errore se si tenta di compilare codice non sufficientemente vincolato per essere un tipo specifico, ma anche non generalizzabile. Il messaggio di errore per questo problema si riferisce a questa restrizione sulla generalizzazione automatica per i valori come restrizione del *valore*.

In genere, l'errore di restrizione del valore si verifica quando si vuole che un costrutto sia generico, ma il compilatore non dispone di informazioni sufficienti per generalizzarlo o quando si omette involontariamente informazioni sul tipo sufficienti in un costrutto non generico. La soluzione per l'errore di restrizione del valore consiste nel fornire informazioni più esplicite per limitare completamente il problema di inferenza del tipo, in uno dei modi seguenti:

- Vincolare un tipo come non generico aggiungendo un'annotazione di tipo esplicita a un valore o a un parametro.

- Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione della funzione o gli argomenti della funzione sottoposta a currying, provare a riscrivere la funzione come definizione di funzione ordinaria.

- Se il problema è un'espressione troppo complessa da generalizzare, impostarla in una funzione aggiungendo un parametro aggiuntivo inutilizzato.

- Aggiungere parametri di tipo generico espliciti. Questa opzione viene utilizzata raramente.

- Gli esempi di codice seguenti illustrano ognuno di questi scenari.

Caso 1: Espressione troppo complessa. In questo esempio, l'elenco `counter` è pensato `int option ref`come, ma non è definito come valore non modificabile semplice.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Caso 2: Utilizzo di un costrutto non generalizzabile per definire una funzione generica. In questo esempio il costrutto è non generalizzabile perché comporta l'applicazione parziale degli argomenti della funzione.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Caso 3: Aggiunta di un parametro aggiuntivo non utilizzato. Poiché questa espressione non è abbastanza semplice da generalizzare, il compilatore genera l'errore di restrizione del valore.

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

Nell'ultimo caso, il valore diventa una funzione di tipo, che può essere usata per creare valori di molti tipi diversi, ad esempio come segue:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Vedere anche

- [Inferenza di tipi](../type-inference.md)
- [Generics](index.md)
- [Parametri di tipo risolti staticamente](statically-resolved-type-parameters.md)
- [Vincoli](constraints.md)
