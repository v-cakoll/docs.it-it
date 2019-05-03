---
title: 'Espressione Loops: while...do'
description: Vedere come while... tale espressione viene usata per l'esecuzione iterativa (ciclo) quando viene soddisfatta una condizione di test specificato.
ms.date: 05/16/2016
ms.openlocfilehash: d2a77e0bfefe3b6b026012e6b2938ba670326bcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904020"
---
# <a name="loops-whiledo-expression"></a>Espressione Loops: while...do

Il `while...do` espressione viene usata per l'esecuzione iterativa (ciclo) quando viene soddisfatta una condizione di test specificato.

## <a name="syntax"></a>Sintassi

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Note

Il *test-expression* viene valutata; in caso `true`, il *espressione corpo* viene eseguita e l'espressione di test viene valutata nuovamente. Il *corpo-expression* deve avere tipo `unit`. Se l'espressione di test è `false`, le entità finali dell'iterazione.

Nell'esempio seguente viene illustrato l'utilizzo del `while...do` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

L'output del codice precedente è un flusso di numeri casuale compreso tra 1 e 20, l'ultimo dei quali è 10.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> È possibile usare `while...do` nelle espressioni di sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `while...do` espressione viene usata. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli: `for...in` Expression](loops-for-in-expression.md)
- [Cicli: `for...to` Expression](loops-for-to-expression.md)