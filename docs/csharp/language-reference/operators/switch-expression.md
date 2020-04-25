---
title: espressione switch-riferimenti per C#
description: Informazioni su come usare l'espressione switch C# per i criteri di ricerca e altri introspezione sui dati
ms.date: 03/19/2020
ms.openlocfilehash: f53cbe873c841271f64496e4e5ff1f11750c7b8a
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140659"
---
# <a name="switch-expression-c-reference"></a>espressione switch (riferimenti per C#)

Questo articolo illustra l' `switch` espressione introdotta in C# 8,0. Per informazioni sull' `switch` istruzione, vedere l'articolo sull' [ `switch` istruzione](../keywords/switch.md) nella sezione [statements](../keywords/index.md) .

## <a name="basic-example"></a>Esempio di base

L' `switch` espressione fornisce `switch`la semantica like in un contesto di espressione. Fornisce una sintassi concisa quando le braccia del commutire producono un valore. Nell'esempio seguente viene illustrata la struttura di un'espressione switch. Converte i valori da un oggetto `enum` che rappresenta le direzioni visive in un mapping online alla direzione Cardinal corrispondente:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetBasicStructure":::

L'esempio precedente Mostra gli elementi di base di un'espressione switch:

- *Espressione di intervallo*: nell'esempio precedente viene utilizzata la `direction` variabile come espressione di intervallo.
- L' *espressione switch Arms*: ogni espressione switch ARM contiene un *pattern*, un *case Guard*facoltativo, il `=>` token e un' *espressione*.

Il risultato dell' *espressione switch* è il valore dell'espressione del primo *ARM dell'espressione switch* il cui *modello* corrisponde all' *espressione di intervallo* e il cui *case Guard*, se presente, restituisce `true`. L' *espressione* a destra del `=>` token non può essere un'istruzione di espressione.

Le *armi dell'espressione switch* vengono valutate in ordine di testo. Il compilatore genera un errore quando non è possibile scegliere un ARM con un' *espressione di cambio* inferiore perché un ARM dell' *espressione del comcambio* superiore corrisponde a tutti i valori.

## <a name="patterns-and-case-guards"></a>Modelli e protezioni tra maiuscole e minuscole

Molti modelli sono supportati nelle braccia dell'espressione switch. Nell'esempio precedente è stato usato un *modello di valore*. Un *criterio di valore* confronta l'espressione di intervallo con un valore. Tale valore deve essere una costante in fase di compilazione. Il *modello di tipo* confronta l'espressione di intervallo con un tipo conosciuto. Nell'esempio seguente viene recuperato il terzo elemento da una sequenza. Usa metodi diversi in base al tipo della sequenza:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetTypePattern":::

I modelli possono essere ricorsivi, in cui un modello verifica un tipo e, se tale tipo corrisponde, il modello corrisponde a uno o più valori di proprietà nell'espressione di intervallo. Per estendere l'esempio precedente, è possibile usare modelli ricorsivi. Si aggiungono le braccia dell'espressione switch per le matrici che contengono meno di 3 elementi. I modelli ricorsivi sono illustrati nell'esempio seguente:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetRecursivePattern":::

I modelli ricorsivi possono esaminare le proprietà dell'espressione di intervallo, ma non possono eseguire codice arbitrario. È possibile usare una *protezione del case*, specificata in `when` una clausola, per fornire controlli simili per altri tipi di sequenza:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetGuardCase":::

Infine, è possibile aggiungere il `_` modello e il `null` criterio per intercettare gli argomenti che non vengono elaborati da qualsiasi altra espressione switch ARM. In questo modo l'espressione switch è *esaustiva*, ovvero viene gestito qualsiasi valore possibile dell'espressione di intervallo. Nell'esempio seguente vengono aggiunte le espressioni Arms:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetExhaustive":::

Nell'esempio precedente viene aggiunto `null` un modello e il `IEnumerable<T>` modello di tipo viene modificato `_` in un modello. Il `null` modello fornisce un controllo null come ARM dell'espressione switch. L'espressione per tale ARM genera un' <xref:System.ArgumentNullException>eccezione. Il `_` modello corrisponde a tutti gli input per i quali non sono state trovate corrispondenze con le armi precedenti. Il controllo deve essere eseguito `null` dopo il controllo oppure corrisponde `null` a input.

Per altre informazioni, vedere la proposta specifica del linguaggio C# per i [modelli ricorsivi](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression).

## <a name="see-also"></a>Vedi anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Criteri di ricerca](../../pattern-matching.md)
