---
title: 'Espressione Loops: while...do'
description: Scopri come... l'espressione do viene utilizzata per eseguire l'esecuzione iterativa (ciclo) mentre una condizione di test specificata è true.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216628"
---
# <a name="loops-whiledo-expression"></a>Espressione Loops: while...do

L' `while...do` espressione viene utilizzata per eseguire l'esecuzione iterativa (ciclo), mentre una condizione di test specificata è true.

## <a name="syntax"></a>Sintassi

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Note

*Test-Expression* viene valutato. in caso contrario ,l'espressioneBodyvieneeseguitael'espressioneditestvienenuovamentevalutata`true`. *Body-Expression* deve essere di tipo `unit`. Se l'espressione di test `false`è, termina l'iterazione.

Nell'esempio seguente viene illustrato l'utilizzo dell' `while...do` espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

L'output del codice precedente è un flusso di numeri casuali compresi tra 1 e 20, l'ultimo dei quali è 10.

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> È possibile utilizzare `while...do` nelle espressioni di sequenza e in altre espressioni `while...do` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di calcolo](computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli `for...in`Espressione](loops-for-in-expression.md)
- [Cicli `for...to`Espressione](loops-for-to-expression.md)
