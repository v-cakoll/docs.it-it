---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # differiti possono migliorare le prestazioni delle App e librerie.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="lazy-computations"></a>Calcoli differiti

*Calcoli differiti* sono calcoli che non vengono valutati immediatamente, ma solo quando è necessario il risultato. Questo può contribuire a migliorare le prestazioni del codice.

## <a name="syntax"></a>Sintassi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *espressione* è codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato. Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo utilizzato per `'T` è determinato dal risultato dell'espressione.

Calcoli differiti consentono di migliorare le prestazioni limitando l'esecuzione di un calcolo in solo nelle situazioni in cui è necessario un risultato.

Per forzare il calcolo da eseguire, chiamare il metodo `Force`. `Force` Determina l'esecuzione deve essere eseguita solo una volta. Le chiamate successive a `Force` restituire lo stesso risultato, ma non eseguire il codice.

Il codice seguente viene illustrato l'utilizzo di calcolo lazy e l'utilizzo di `Force`. In questo codice, il tipo di `result` è `Lazy<int>`e `Force` metodo restituisce un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Valutazione lenta, ma non il `Lazy` digitare, viene usato anche per le sequenze. Per ulteriori informazioni, vedere [sequenze](sequences.md).

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)

[LazyExtensions (modulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
