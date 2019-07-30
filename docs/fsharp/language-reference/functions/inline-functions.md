---
title: Funzioni inline
description: Informazioni su come usare F# le funzioni inline integrate direttamente nel codice chiamante.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630674"
---
# <a name="inline-functions"></a>Funzioni inline

Le *funzioni inline* sono funzioni integrate direttamente nel codice chiamante.

## <a name="using-inline-functions"></a>Uso di funzioni inline

Quando si usano parametri di tipo statici, le funzioni parametrizzate dai parametri di tipo devono essere inline. Ciò garantisce che il compilatore possa risolvere questi parametri di tipo. Quando si usano i normali parametri di tipo generico, non esiste alcuna restrizione.

Oltre ad abilitare l'utilizzo di vincoli dei membri, le funzioni inline possono essere utili per l'ottimizzazione del codice. Tuttavia, l'utilizzo eccessivo delle funzioni inline può causare una minore resistenza del codice alle modifiche apportate alle ottimizzazioni del compilatore e all'implementazione delle funzioni della libreria. Per questo motivo, è consigliabile evitare di utilizzare le funzioni inline per l'ottimizzazione, a meno che non siano state tentate tutte le altre tecniche di ottimizzazione. L'esecuzione inline di una funzione o di un metodo può talvolta migliorare le prestazioni, ma questo non è sempre il caso. Pertanto, è necessario utilizzare anche le misurazioni delle prestazioni per verificare che l'esecuzione inline di una determinata funzione abbia effetti positivi.

Il `inline` modificatore può essere applicato a funzioni a livello superiore, a livello di modulo o a livello di metodo in una classe.

Nell'esempio di codice seguente viene illustrata una funzione inline al livello principale, un metodo di istanza inline e un metodo statico inline.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>Funzioni inline e inferenza del tipo

La presenza di `inline` influiscono sull'inferenza del tipo. Ciò è dovuto al fatto che le funzioni inline possono avere parametri di tipo risolti staticamente, mentre le funzioni non inline non possono. Nell'esempio di codice riportato di seguito viene `inline` illustrato un caso in cui è utile perché si utilizza una funzione con un parametro di tipo risolto `float` in modo statico, l'operatore di conversione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Senza il `inline` modificatore, l'inferenza del tipo impone che la funzione prenda un tipo specifico `int`, in questo caso. Ma con il `inline` modificatore, la funzione viene anche dedotta per avere un parametro di tipo risolto in modo statico. Con il `inline` modificatore, il tipo viene dedotto come il seguente:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione in **float**.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Vincoli](../generics/constraints.md)
- [Parametri di tipo risolti staticamente](../generics/statically-resolved-type-parameters.md)
