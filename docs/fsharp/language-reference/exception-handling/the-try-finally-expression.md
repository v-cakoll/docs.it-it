---
title: 'Eccezioni: Espressione try...finally'
description: Scopri in che F# modo ' try... Infine, l'espressione consente di eseguire il codice di pulizia anche se un blocco di codice genera un'eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630280"
---
# <a name="exceptions-the-tryfinally-expression"></a>Eccezioni: Espressione try...finally

L' `try...finally` espressione consente di eseguire il codice di pulizia anche se un blocco di codice genera un'eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Note

L' `try...finally` espressione può essere usata per eseguire il codice in *expression2* nella sintassi precedente, indipendentemente dal fatto che venga generata un'eccezione durante l'esecuzione di *expression1*.

Il tipo di *expression2* non contribuisce al valore dell'intera espressione. il tipo restituito quando non si verifica un'eccezione è l'ultimo valore in *expression1*. Quando si verifica un'eccezione, non viene restituito alcun valore e il flusso di controllo viene trasferito al gestore di eccezioni corrispondente successivo fino allo stack di chiamate. Se non viene trovato alcun gestore di eccezioni, il programma termina. Prima di eseguire il codice in un gestore corrispondente o il programma termina, viene eseguito il codice nel `finally` ramo.

Nel codice seguente viene illustrato l'utilizzo dell' `try...finally` espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

Di seguito è riportato l'output della console.

```
Closing stream
Exception handled.
```

Come si può notare dall'output, il flusso è stato chiuso prima che venisse gestita l'eccezione esterna e il file `test.txt` contiene il testo `test1`, che indica che i buffer sono stati scaricati e scritti su disco anche se l'eccezione è stata trasferita controllo al gestore di eccezioni esterno.

Si noti che `try...with` il costrutto è un costrutto `try...finally` separato dal costrutto. Pertanto, se il codice richiede un `with` blocco e un `finally` blocco, è necessario annidare i due costrutti, come nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Nel contesto delle espressioni di calcolo, incluse le espressioni di sequenza e i flussi di lavoro asincroni, **provare...** le espressioni finally possono avere un'implementazione personalizzata. Per altre informazioni, vedere [espressioni di calcolo](../computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Eccezioni: `try...with` Espressione](the-try-with-expression.md)
