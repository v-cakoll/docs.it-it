---
title: Espressioni lazy
description: Informazioni su F# come le espressioni Lazy possono migliorare le prestazioni delle app e delle librerie.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630743"
---
# <a name="lazy-expressions"></a>Espressioni lazy

Le *espressioni Lazy* sono espressioni che non vengono valutate immediatamente, ma vengono invece valutate quando il risultato è necessario. Questo può contribuire a migliorare le prestazioni del codice.

## <a name="syntax"></a>Sintassi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *Expression* è il codice che viene valutato solo quando è necessario un risultato e *Identifier* è un valore che archivia il risultato. Il valore è di tipo [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo usato per `'T` è determinato dal risultato dell'espressione.

Le espressioni Lazy consentono di migliorare le prestazioni limitando l'esecuzione di espressioni solo alle situazioni in cui è necessario un risultato.

Per forzare l'esecuzione delle espressioni, chiamare il metodo `Force`. `Force`fa in modo che l'esecuzione venga eseguita una sola volta. Le chiamate successive `Force` a restituiscono lo stesso risultato, ma non eseguono alcun codice.

Nel codice seguente viene illustrato l'utilizzo di espressioni Lazy e l'utilizzo di `Force`. In questo codice, il tipo di `result` è `Lazy<int>` `int`e il `Force` metodo restituisce.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La valutazione lazy, ma non `Lazy` il tipo, viene usata anche per le sequenze. Per ulteriori informazioni, vedere [sequences](sequences.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Modulo LazyExtensions](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
