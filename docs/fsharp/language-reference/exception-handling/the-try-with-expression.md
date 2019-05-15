---
title: 'Eccezioni: Espressione try...with'
description: Informazioni su come usare il F# 'try... con' espressione per la gestione delle eccezioni.
ms.date: 05/16/2016
ms.openlocfilehash: 3ba13227ac55eff770ceb7631d3406ad80b6ea45
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641930"
---
# <a name="exceptions-the-trywith-expression"></a>Eccezioni: Espressione try...with

Questo argomento viene descritto il `try...with` expression, l'espressione che viene usato per la gestione delle eccezioni nel F# lingua.

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

Il `try...with` espressione viene usata per gestire le eccezioni in F#. È simile al `try...catch` istruzione in c#. Nella sintassi precedente, il codice nel *expression1* potrebbe generare un'eccezione. Il `try...with` espressione restituisce un valore. Se viene generata alcuna eccezione, l'intera espressione restituisce il valore della *expression1*. Se viene generata un'eccezione, ognuna *pattern* viene confrontato a sua volta con l'eccezione e per il primo modello corrisponda, corrispondente *expression*, noto come il *gestoredieccezioni*, per quel ramo viene eseguito e l'espressione globale restituisce il valore dell'espressione in tale gestore di eccezioni. Se nessun criterio corrisponde, l'eccezione si propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente. I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nella `try` blocco.

Spesso, il fatto che si verificato un errore anche significa che vi è alcun valore validi che può essere restituite dalle espressioni in ogni gestore eccezioni. Un modello frequente consiste nell'avere il tipo dell'espressione sia un tipo di opzione. L'esempio di codice seguente illustra questo modello.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Le eccezioni possono essere le eccezioni .NET, o possono essere F# le eccezioni. È possibile definire F# le eccezioni tramite il `exception` parola chiave.

È possibile usare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e altre condizioni. Nella tabella seguente sono riepilogate le opzioni.

|Modello|Descrizione|
|-------|-----------|
|:? *exception-type*|Corrisponde al tipo di eccezione .NET specificato.|
|:? *tipo di eccezione* come *identificatore*|Corrisponde al tipo di eccezione .NET specificato, ma offre un valore denominato l'eccezione.|
|*exception-name*(*arguments*)|Corrisponde a un F# tipo di eccezione e associa gli argomenti.|
|*identifier*|Corrisponde a tutte le eccezioni e associa il nome dell'oggetto eccezione. Equivalente a **:? System. Exception come**_identificatore_|
|*Identificatore* quando *condizione*|Corrisponde a tutte le eccezioni se la condizione è true.|

## <a name="examples"></a>Esempi

Gli esempi di codice seguenti illustrano l'uso di vari modelli di gestore di eccezioni.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> Il `try...with` costrutto è un'espressione separata dal `try...finally` espressione. Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario annidare le due espressioni.

> [!NOTE]
> È possibile usare `try...with` nei flussi di lavoro asincroni e altre espressioni di calcolo, in cui una versione personalizzata di case di `try...with` espressione viene usata. Per altre informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md), e [espressioni di calcolo](../computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: Il `try...finally` espressione](the-try-finally-expression.md)
