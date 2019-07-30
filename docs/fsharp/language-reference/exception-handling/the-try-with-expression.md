---
title: 'Eccezioni: Espressione try...with'
description: Informazioni su come usare il F# ' try... with ' espressione per la gestione delle eccezioni.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630256"
---
# <a name="exceptions-the-trywith-expression"></a>Eccezioni: Espressione try...with

In questo argomento viene `try...with` descritta l'espressione, che viene utilizzata per la gestione delle eccezioni F# nel linguaggio.

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

L' `try...with` espressione viene utilizzata per gestire le eccezioni F#in. È simile all' `try...catch` istruzione in. C# Nella sintassi precedente, il codice in *expression1* potrebbe generare un'eccezione. L' `try...with` espressione restituisce un valore. Se non viene generata alcuna eccezione, l'intera espressione restituisce il valore di *expression1*. Se viene generata un'eccezione, ogni *modello* viene confrontato a sua volta con l'eccezione e per il primo criterio di corrispondenza, viene eseguita l' *espressione*corrispondente, nota come *gestore di eccezioni*, per quel ramo e l'espressione complessiva Restituisce il valore dell'espressione nel gestore di eccezioni. Se non corrisponde alcun criterio, l'eccezione propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente. I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nel `try` blocco.

Spesso, il fatto che si è verificato un errore significa anche che non esiste alcun valore valido che può essere restituito dalle espressioni in ogni gestore di eccezioni. Un modello frequente consiste nel fare in modo che il tipo dell'espressione sia un tipo di opzione. Questo modello è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Le eccezioni possono essere eccezioni .NET oppure possono essere F# eccezioni. È possibile definire F# le eccezioni tramite la `exception` parola chiave.

È possibile usare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e ad altre condizioni; le opzioni sono riepilogate nella tabella seguente.

|Modello|Descrizione|
|-------|-----------|
|:? *exception-type*|Corrisponde al tipo di eccezione .NET specificato.|
|:? *tipo di eccezione* come *identificatore*|Corrisponde al tipo di eccezione .NET specificato, ma restituisce un valore denominato all'eccezione.|
|*nome eccezione* (*argomenti*)|Corrisponde a F# un tipo di eccezione e associa gli argomenti.|
|*identifier*|Corrisponde a qualsiasi eccezione e associa il nome all'oggetto eccezione. Equivalente a **:? System. Exception come**_identificatore_|
|*identificatore* quando la *condizione*|Corrisponde a qualsiasi eccezione se la condizione è true.|

## <a name="examples"></a>Esempi

Negli esempi di codice seguenti viene illustrato l'utilizzo dei diversi modelli di gestione delle eccezioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> Il `try...with` costrutto è un'espressione separata `try...finally` dall'espressione. Pertanto, se il codice richiede un `with` blocco e un `finally` blocco, sarà necessario nidificare le due espressioni.

> [!NOTE]
> È possibile utilizzare `try...with` in flussi di lavoro asincroni e altre espressioni `try...with` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione. Per altre informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md)ed [espressioni di calcolo](../computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: `try...finally` Espressione](the-try-finally-expression.md)
