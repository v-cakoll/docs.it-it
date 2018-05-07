---
title: 'Cicli: espressioni while...do (F#)'
description: Vedere come while... tale espressione viene utilizzata per l'esecuzione iterativa (ciclo) quando una condizione di test specificato è true.
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="loops-whiledo-expression"></a>Espressione Loops: while...do

Il `while...do` espressione viene utilizzata per l'esecuzione iterativa (ciclo) quando una condizione di test specificato è true.


## <a name="syntax"></a>Sintassi

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Note
Il *espressione di test* viene valutato; se è `true`, *espressione corpo* viene eseguita e l'espressione di test viene valutata nuovamente. Il *espressione corpo* deve avere tipo `unit`. Se l'espressione di test è `false`, termina l'iterazione.

Nell'esempio seguente viene illustrato l'utilizzo del `while...do` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

L'output del codice precedente è un flusso di numeri casuali compresi tra 1 e 20, di cui l'ultimo è 10.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
È possibile utilizzare `while...do` in espressioni sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `while...do` viene utilizzata l'espressione. Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Cicli: espressione `for...in`](loops-for-in-expression.md)

[Cicli: espressione `for...to`](loops-for-to-expression.md)
