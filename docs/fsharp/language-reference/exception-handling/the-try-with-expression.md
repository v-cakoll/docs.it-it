---
title: 'Eccezioni: espressione try...with (F#)'
description: "Informazioni su come utilizzare l'espressione 'try... with' di F # per la gestione delle eccezioni."
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565288"
---
# <a name="exceptions-the-trywith-expression"></a>Eccezioni: espressione try...with

Questo argomento viene descritto il `try...with` expression, l'espressione che viene utilizzato per la gestione delle eccezioni nel linguaggio F #.


## <a name="syntax"></a>Sintassi

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>Note
Il `try...with` espressione viene utilizzata per gestire le eccezioni in F #. È simile al `try...catch` istruzione in c#. Nella sintassi precedente, il codice in *expression1* potrebbe generare un'eccezione. Il `try...with` espressione restituisce un valore. Se viene generata alcuna eccezione, l'intera espressione restituisce il valore di *expression1*. Se viene generata un'eccezione, ogni *modello* viene confrontato a sua volta con l'eccezione e per il primo modello corrispondente, corrispondente *espressione*, noti come il *gestoredieccezioni*per tale branch viene eseguita e l'espressione complessiva restituisce il valore dell'espressione in tale gestore di eccezioni. Se non corrisponde alcun modello, l'eccezione si propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente. I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nel `try` blocco.

Il fatto che si verificato un errore anche spesso significa che è presente alcun valore valido che può essere restituito da espressioni in ogni gestore eccezioni. Un motivo frequente è che il tipo dell'espressione di essere un tipo di opzione. Esempio di codice seguente viene illustrato questo modello.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Le eccezioni possono essere eccezioni .NET, o possono essere eccezioni F #. È possibile definire eccezioni F # utilizzando il `exception` (parola chiave).

È possibile utilizzare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e altre condizioni. le opzioni sono riepilogate nella tabella seguente.


|Modello|Descrizione|
|-------|-----------|
|:? *tipo di eccezione*|Corrisponde al tipo di eccezione .NET specificato.|
|:? *tipo di eccezione* come *identificatore*|Corrisponde al tipo di eccezione .NET specificato, ma consente l'eccezione di un valore denominato.|
|*nome di eccezione*(*argomenti*)|Corrisponde a un tipo di eccezione F # e associa gli argomenti.|
|*identifier*|Corrisponde a qualsiasi eccezione e associa il nome dell'oggetto eccezione. Equivalente a **:? System. Exception come * * * identificatore*|
|*Identificatore* quando *condizione*|Consente di ricercare qualsiasi eccezione se la condizione è true.|

## <a name="examples"></a>Esempi
Gli esempi di codice seguente viene illustrato l'utilizzo di vari modelli di gestore di eccezioni.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
Il `try...with` costrutto è un'espressione separata dal `try...finally` espressione. Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario nidificare le due espressioni.

>[!NOTE] 
È possibile utilizzare `try...with` in flussi di lavoro asincroni e altre espressioni di calcolo, in cui una versione personalizzata di caso di `try...with` viene utilizzata l'espressione. Per ulteriori informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md), e [espressioni di calcolo](../computation-expressions.md).


## <a name="see-also"></a>Vedere anche
[Gestione delle eccezioni](index.md)

[Tipi di eccezione](exception-types.md)

[Eccezioni: espressione `try...finally`](the-try-finally-expression.md)
