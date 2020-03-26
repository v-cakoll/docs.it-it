---
title: Espressione switch - Riferimento in C
description: Informazioni su come usare l'espressione switch di C'è per i criteri di ricerca e altre introspezion i dati
ms.date: 03/19/2020
ms.openlocfilehash: 9e609bcea0f92f492b5f9b07840e47f75c1b71e4
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249788"
---
# <a name="switch-expression-c-reference"></a>espressione switch (riferimento C

In questo `switch` articolo viene illustrata l'espressione, introdotta in C . Per informazioni `switch` sulla dichiarazione, vedere l'articolo sulla [ `switch` dichiarazione](../keywords/switch.md) nella sezione [delle istruzioni.](../keywords/index.md)

## <a name="basic-example"></a>Esempio di base

L'espressione `switch` `switch`fornisce una semantica simile a questa espressione in un contesto di espressione. Fornisce una sintassi concisa quando i bracci switch producono un valore. Nell'esempio seguente viene illustrata la struttura di un'espressione switch. Converte i valori `enum` da un rappresentante direzioni visive in una mappa online nella direzione cardinale corrispondente:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetBasicStructure":::

Nell'esempio precedente vengono illustrati gli elementi di base di un'espressione switch:The preceding sample shows the basic elements of a switch expression:

- Espressione *di intervallo*: nell'esempio precedente viene utilizzata la variabile `direction` come espressione di intervallo.
- Le *braccia dell'espressione switch*: Ogni braccio di espressione switch contiene un *modello*, un case *guard*facoltativo, il `=>` token e *un'espressione*.

Il risultato dell'espressione *switch* è il valore dell'espressione del primo *braccio dell'espressione switch* il `true`cui *modello* di espressione corrisponde *all'espressione di intervallo* e il cui nome *causa*, se presente, restituisce . *L'espressione* a destra `=>` del token non può essere un'istruzione di espressione.

I *bracci* delle espressioni switch vengono valutati in ordine di testo. Il compilatore genera un errore quando non è possibile scegliere un braccio di *espressione switch* inferiore perché un braccio di espressione di *commutatore* superiore corrisponde a tutti i relativi valori.

## <a name="patterns-and-case-guards"></a>Modelli e guardie dei casi

Molti modelli sono supportati nei bracci di espressione switch. Nell'esempio precedente è stato utilizzato un *pattern di valori.* Un criterio di *valore* confronta l'espressione di intervallo con un valore. Tale valore deve essere una costante in fase di compilazione. Il modello di *tipo* confronta l'espressione di intervallo con un tipo noto. Nell'esempio seguente viene recuperato il terzo elemento da una sequenza. Esso utilizza diversi metodi in base al tipo della sequenza:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetTypePattern":::

I motivi possono essere ricorsivi, in cui un modello verifica un tipo e se tale tipo corrisponde, il modello corrisponde a uno o più valori di proprietà nell'espressione di intervallo. È possibile utilizzare modelli ricorsivi per estendere l'esempio precedente. Aggiungere i bracci di espressione switch per le matrici che hanno meno di 3 elementi. I modelli ricorsivi sono illustrati nell'esempio seguente:Recursive patterns are shown in the following example:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetRecursivePattern":::

I modelli ricorsivi possono esaminare le proprietà dell'espressione di intervallo, ma non possono eseguire codice arbitrario. È possibile utilizzare un *case* `when` guard , specificato in una clausola, per fornire controlli simili per altri tipi di sequenza:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetGuardCase":::

Infine, è possibile `_` aggiungere `null` il modello e il modello per intercettare gli argomenti che non vengono elaborati da qualsiasi altro braccio di espressione switch. In questo modo l'espressione switch è *esaustiva,* ovvero viene gestito qualsiasi valore possibile dell'espressione di intervallo. L'esempio seguente aggiunge tali bracci di espressione:The following example adds those expression arms:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetExhaustive":::

L'esempio precedente `null` aggiunge un modello `IEnumerable<T>` e modifica `_` il modello di tipo in un modello. Il `null` modello fornisce un controllo null come braccio di espressione switch. L'espressione per quel <xref:System.ArgumentNullException>braccio genera un ' Il `_` modello corrisponde a tutti gli ingressi che non sono stati abbinati da bracci precedenti. Deve venire dopo `null` il controllo, `null` o corrisponderebbe input.

È possibile leggere ulteriori informazioni nella proposta di specifiche del linguaggio C 'C' per [i modelli ricorsivi](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Criteri](../../pattern-matching.md)
