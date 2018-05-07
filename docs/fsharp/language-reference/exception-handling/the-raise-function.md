---
title: 'Eccezioni: funzione raise (F#)'
description: "Informazioni su come la funzione F # 'raise' viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale."
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-raise-function"></a>Eccezioni: funzione raise

Il `raise` funzione viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale. Informazioni sull'errore vengono acquisite in un oggetto eccezione.


## <a name="syntax"></a>Sintassi

```fsharp
raise (expression)
```

## <a name="remarks"></a>Note
Il `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione di stack. Il processo di rimozione dello stack è gestito da common language runtime (CLR), pertanto il comportamento di questo processo è lo stesso come in qualsiasi altro linguaggio .NET. Il processo di rimozione dello stack è una ricerca di un gestore di eccezioni che corrisponde all'eccezione generata. La ricerca inizia in corrente `try...with` espressione, se presente. Ogni modello nel `with` blocco è selezionato, nell'ordine. Quando viene trovato un gestore eccezioni corrispondente, l'eccezione viene considerata gestita. in caso contrario, lo stack viene rimosso e `with` blocchi la catena di chiamate vengono controllati fino a quando non viene trovato un gestore corrispondente. Qualsiasi `finally` blocchi che vengono rilevati nella catena di chiamate vengono inoltre eseguiti in sequenza come lo stack viene rimosso.

Il `raise` funzione equivale a `throw` in c# o C++. Utilizzare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamata.

Gli esempi di codice seguente viene illustrato l'utilizzo del `raise` funzione genera un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

Il `raise` funzione nonché per la generazione di eccezioni .NET, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a>Vedere anche
[Gestione delle eccezioni](index.md)

[Tipi di eccezione](exception-types.md)

[Eccezioni: espressione `try...with`](the-try-with-expression.md)

[Eccezioni: espressione `try...finally`](the-try-finally-expression.md)

[Eccezioni: funzione `failwith`](the-failwith-function.md)

[Eccezioni: funzione `invalidArg`](the-invalidArg-function.md)
