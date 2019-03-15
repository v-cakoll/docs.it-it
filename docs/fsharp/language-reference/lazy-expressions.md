---
title: Espressioni Lazy
description: Informazioni su come F# espressioni differite possono migliorare le prestazioni delle App e librerie.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57853325"
---
# <a name="lazy-expressions"></a>Espressioni Lazy

*Le espressioni lazy* sono espressioni che non vengono eseguite immediatamente, ma solo quando il risultato è necessaria. Questo può contribuire a migliorare le prestazioni del codice.

## <a name="syntax"></a>Sintassi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Note

Nella sintassi precedente *espressione* è il codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato. Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo che viene usato per `'T` è determinato dal risultato dell'espressione.

Le espressioni lazy consentono di migliorare le prestazioni, limitando l'esecuzione di un espressioni solo tali situazioni in cui è necessario un risultato.

Per forzare le espressioni deve essere eseguita, si chiama il metodo `Force`. `Force` Determina l'esecuzione deve essere eseguita solo una volta. Le chiamate successive a `Force` restituiscono lo stesso risultato, ma non eseguire il codice.

Il codice seguente illustra l'uso delle espressioni lazy e l'utilizzo di `Force`. In questo codice, il tipo di `result` viene `Lazy<int>`e il `Force` metodo restituisce un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Valutazione lenta, ma non la `Lazy` digitare, viene usato anche per le sequenze. Per altre informazioni, vedere [sequenze](sequences.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [LazyExtensions (modulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
