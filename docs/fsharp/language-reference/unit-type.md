---
title: Tipo di unità
description: Informazioni sul modo F# in cui il tipo di "unità" viene spesso usato per mantenere la posizione in cui un valore è richiesto dalla sintassi del linguaggio quando non è necessario o si desidera alcun valore.
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630169"
---
# <a name="unit-type"></a>Tipo di unità

Il `unit` tipo è un tipo che indica l'assenza di un valore specifico. il `unit` tipo dispone solo di un singolo valore, che funge da segnaposto quando non esiste alcun altro valore o è necessario.

## <a name="syntax"></a>Sintassi

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Note

Ogni F# espressione deve restituire un valore. Per le espressioni che non generano un valore di interesse, viene usato il valore di `unit` tipo. Il `unit` tipo è simile al `void` tipo in linguaggi quali C# e C++.

Il `unit` tipo ha un solo valore e tale valore è indicato dal token `()`.

Il valore del `unit` tipo viene spesso utilizzato nella programmazione F# per conservare la posizione in cui è richiesto un valore per la sintassi del linguaggio, ma quando non è necessario o desiderato alcun valore. Un esempio potrebbe essere il valore restituito di una `printf` funzione. Poiché le azioni importanti dell' `printf` operazione si verificano nella funzione, non è necessario che la funzione restituisca un valore effettivo. Pertanto, il valore restituito è di tipo `unit`.

Alcuni costrutti prevedono un `unit` valore. Ad esempio, è `do` previsto che un binding o qualsiasi codice al primo livello di un modulo restituisca un `unit` valore. Il compilatore segnala un avviso quando un' `do` associazione o un codice al livello superiore di un modulo produce un risultato diverso dal `unit` valore non usato, come illustrato nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Questo avviso è una caratteristica della programmazione funzionale. non viene visualizzato in altri linguaggi di programmazione .NET. In un programma puramente funzionale, in cui le funzioni non hanno effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione. Pertanto, quando il risultato viene ignorato, è possibile che si verifichi un errore di programmazione. Sebbene F# non sia un linguaggio di programmazione puramente funzionale, è consigliabile seguire lo stile di programmazione funzionale laddove possibile.

## <a name="see-also"></a>Vedere anche

- [Primitivi](primitive-types.md)
- [Riferimenti per il linguaggio F#](index.md)
