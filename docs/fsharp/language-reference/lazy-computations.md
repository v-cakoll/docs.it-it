---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # differiti possono migliorare le prestazioni delle App e librerie.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a>Calcoli differiti

*Calcoli differiti* sono calcoli che non vengono valutati immediatamente, ma solo quando il risultato è necessario. Questo può contribuire a migliorare le prestazioni del codice.

## <a name="syntax"></a>Sintassi

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *espressione* è codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato. Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo utilizzato per `'T` è determinato dal risultato dell'espressione.

Calcoli differiti consentono di migliorare le prestazioni limitando l'esecuzione di un calcolo in solo nelle situazioni in cui è necessario un risultato.

Per forzare il calcolo da eseguire, chiamare il metodo `Force`. `Force`Determina l'esecuzione a essere eseguita solo una volta. Le chiamate successive a `Force` restituire lo stesso risultato, ma non eseguire il codice.

Il codice seguente viene illustrato l'utilizzo di calcolo lazy e l'utilizzo di `Force`. In questo codice, il tipo di `result` è `Lazy<int>`e `Force` metodo restituisce un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Valutazione lenta, ma non il `Lazy` digitare, viene usato anche per le sequenze. Per ulteriori informazioni, vedere [sequenze](sequences.md).

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)

[LazyExtensions (modulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
