---
title: 'Eccezioni: funzione raise'
description: Informazioni su come il F# 'raise' funzione viene utilizzata per indicare che si è verificato un errore o condizione eccezionale.
ms.date: 05/16/2016
ms.openlocfilehash: 9e2515ad7b85c1025bc3aa0aa2a6929a8d35436d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641957"
---
# <a name="exceptions-the-raise-function"></a>Eccezioni: funzione raise

Il `raise` funzione viene utilizzata per indicare che si è verificato un errore o condizione eccezionale. Informazioni sull'errore vengono acquisite in un oggetto eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
raise (expression)
```

## <a name="remarks"></a>Note

Il `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione dello stack. Il processo di rimozione dello stack viene gestito da common language runtime (CLR), quindi il comportamento di questo processo è lo stesso perché si trova in qualsiasi altro linguaggio .NET. Il processo di rimozione dello stack è una ricerca per un gestore di eccezioni che corrisponde all'eccezione generata. Viene avviata la ricerca nell'attuale `try...with` espressione, se presente. I modelli di `with` blocco è selezionato, nell'ordine. Quando viene trovato un gestore eccezioni corrispondente, l'eccezione viene considerata come gestito; in caso contrario, lo stack viene rimosso e `with` blocchi la catena di chiamate vengono controllati fino a quando non viene trovato un gestore corrispondente. Qualsiasi `finally` blocchi che si verificano nella catena di chiamate vengono anche eseguiti in sequenza come lo stack viene rimosso.

Il `raise` funzione equivale a `throw` in c# o C++. Usare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamata.

Gli esempi di codice seguenti illustrano l'uso del `raise` funzione per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

Il `raise` funzione può essere usata anche per la generazione di eccezioni .NET, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: Il `try...with` espressione](the-try-with-expression.md)
- [Eccezioni: Il `try...finally` espressione](the-try-finally-expression.md)
- [Eccezioni: Il `failwith` (funzione)](the-failwith-function.md)
- [Eccezioni: Il `invalidArg` (funzione)](the-invalidArg-function.md)
