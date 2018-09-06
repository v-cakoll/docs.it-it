---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # calcoli differiti possono migliorare le prestazioni delle App e librerie.'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037068"
---
# <a name="lazy-computations"></a>Calcoli differiti

*Calcoli differiti* calcoli che non vengono eseguiti immediatamente, ma solo quando il risultato è necessaria. Questo può contribuire a migliorare le prestazioni del codice.

## <a name="syntax"></a>Sintassi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Note

Nella sintassi precedente *espressione* è il codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato. Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo che viene usato per `'T` è determinato dal risultato dell'espressione.

Calcoli differiti consentono di migliorare le prestazioni, limitando l'esecuzione di un calcolo solo tali situazioni in cui è necessario un risultato.

Per forzare il calcolo da eseguire, si chiama il metodo `Force`. `Force` Determina l'esecuzione deve essere eseguita solo una volta. Le chiamate successive a `Force` restituiscono lo stesso risultato, ma non eseguire il codice.

Il codice seguente illustra l'utilizzo di calcolo lazy e l'uso di `Force`. In questo codice, il tipo di `result` viene `Lazy<int>`e il `Force` metodo restituisce un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Valutazione lenta, ma non la `Lazy` digitare, viene usato anche per le sequenze. Per altre informazioni, vedere [sequenze](sequences.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [LazyExtensions (modulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
