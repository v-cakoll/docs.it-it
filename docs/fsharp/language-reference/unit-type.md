---
title: Tipo di unità
description: Informazioni su come il F# tipo di 'unit' viene spesso usato per indicare la posizione in cui è necessario un valore per la sintassi del linguaggio quando nessun valore è necessario o desiderato.
ms.date: 05/16/2016
ms.openlocfilehash: d515e19489bfa7de6f17194fd74176cfa0bcd7c9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645132"
---
# <a name="unit-type"></a>Tipo di unità

Il `unit` tipo è un tipo che indica l'assenza di un valore specifico; il `unit` tipo ha un solo valore, che funge da segnaposto quando nessun altro valore è presente o necessario.

## <a name="syntax"></a>Sintassi

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Note

Ogni F# espressione deve restituire un valore. Per le espressioni che non generano un valore che è di particolare interesse, il valore di tipo `unit` viene usato. Il `unit` è simile a tipo di `void` tipo nei linguaggi come c# e C++.

Il `unit` tipo ha un singolo valore e tale valore è indicato dal token `()`.

Il valore della `unit` tipo viene spesso usato in F# programmazione per indicare la posizione in cui è richiesto un valore dalla sintassi del linguaggio, ma quando nessun valore è necessario o desiderato. Un esempio potrebbe essere il valore restituito di un `printf` (funzione). Poiché le azioni di importanti il `printf` eseguire operazioni nella funzione, la funzione non deve restituire un valore effettivo. Pertanto, il valore restituito è di tipo `unit`.

Alcuni costrutti prevedono un `unit` valore. Ad esempio, un `do` binding o qualsiasi codice al livello superiore di un modulo è previsto in modo che restituisca un `unit` valore. Il compilatore genera un avviso quando un `do` al codice al livello superiore di un modulo o associazione produce un risultato diverso dal `unit` valore non usato, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Questo avviso è una caratteristica della programmazione funzionale; non fa in altri linguaggi di programmazione .NET. In un programma puramente funzionale, in cui le funzioni ha effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione. Pertanto, quando il risultato viene ignorato, è un possibile errore di programmazione. Anche se F# non è puramente funzionale linguaggio di programmazione, è buona norma da seguire dello stile di programmazione funzionale, laddove possibile.

## <a name="see-also"></a>Vedere anche

- [Primitivi](primitive-types.md)
- [Riferimenti per il linguaggio F#](index.md)
