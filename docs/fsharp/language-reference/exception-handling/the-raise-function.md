---
title: 'Eccezioni: funzione raise'
description: Informazioni sul modo F# in cui viene usata la funzione ' raise ' per indicare che si è verificato un errore o una condizione eccezionale.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630293"
---
# <a name="exceptions-the-raise-function"></a>Eccezioni: funzione raise

La `raise` funzione viene usata per indicare che si è verificato un errore o una condizione eccezionale. Le informazioni sull'errore vengono acquisite in un oggetto eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
raise (expression)
```

## <a name="remarks"></a>Note

La `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione dello stack. Il processo di rimozione dello stack è gestito dal Common Language Runtime (CLR), quindi il comportamento di questo processo è identico a quello in qualsiasi altro linguaggio .NET. Il processo di rimozione dello stack è una ricerca di un gestore di eccezioni che corrisponde all'eccezione generata. La ricerca inizia nell'espressione corrente `try...with` , se ne esiste una. Ogni modello nel `with` blocco è selezionato, in ordine. Quando viene trovato un gestore di eccezioni corrispondente, l'eccezione viene considerata gestita; in caso contrario, lo stack viene rimosso `with` e il blocco della catena di chiamate viene verificato fino a quando non viene trovato un gestore corrispondente. Tutti `finally` i blocchi rilevati nella catena di chiamate vengono eseguiti anche in sequenza come rimozione dello stack.

La `raise` funzione è l'equivalente di `throw` in C# o C++. Utilizzare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamate.

Negli esempi di codice seguenti viene illustrato l'utilizzo della `raise` funzione per generare un'eccezione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

La `raise` funzione può essere utilizzata anche per generare eccezioni .NET, come illustrato nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: `try...with` Espressione](the-try-with-expression.md)
- [Eccezioni: `try...finally` Espressione](the-try-finally-expression.md)
- [Eccezioni: `failwith` Funzione](the-failwith-function.md)
- [Eccezioni: `invalidArg` Funzione](the-invalidArg-function.md)
