---
title: Tipo di unità
description: Informazioni sul modo F# in cui il tipo di "unità" viene spesso usato per mantenere la posizione in cui un valore è richiesto dalla sintassi del linguaggio quando non è necessario o si desidera alcun valore.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424036"
---
# <a name="unit-type"></a>Tipo di unità

Il tipo di `unit` è un tipo che indica l'assenza di un valore specifico. il tipo di `unit` dispone solo di un singolo valore, che funge da segnaposto quando non esiste alcun altro valore o è necessario.

## <a name="syntax"></a>Sintassi

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Note

Ogni F# espressione deve restituire un valore. Per le espressioni che non generano un valore di interesse, viene usato il valore di tipo `unit`. Il tipo di `unit` è simile al tipo di `void` in linguaggi quali C# e C++.

Il tipo di `unit` ha un solo valore e tale valore è indicato dall'`()`del token.

Il valore del tipo di `unit` viene spesso utilizzato nella F# programmazione per mantenere la posizione in cui un valore è richiesto dalla sintassi del linguaggio, ma quando non è necessario o si desidera alcun valore. Un esempio potrebbe essere il valore restituito di una funzione `printf`. Poiché le azioni importanti dell'operazione `printf` si verificano nella funzione, non è necessario che la funzione restituisca un valore effettivo. Pertanto, il valore restituito è di tipo `unit`.

Alcuni costrutti prevedono un valore `unit`. Ad esempio, un `do` associazione o qualsiasi codice al primo livello di un modulo dovrebbe restituire un valore `unit`. Il compilatore genera un avviso quando un `do` associazione o codice al primo livello di un modulo produce un risultato diverso dal valore di `unit` non usato, come illustrato nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Questo avviso è una caratteristica della programmazione funzionale. non viene visualizzato in altri linguaggi di programmazione .NET. In un programma puramente funzionale, in cui le funzioni non hanno effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione. Pertanto, quando il risultato viene ignorato, è possibile che si verifichi un errore di programmazione. Sebbene F# non sia un linguaggio di programmazione puramente funzionale, è consigliabile seguire lo stile di programmazione funzionale laddove possibile.

## <a name="see-also"></a>Vedere anche

- [Primitivi](basic-types.md)
- [Riferimenti per il linguaggio F#](index.md)
