---
title: Tipo di unità (F#)
description: "Informazioni su come il tipo 'unit' F # viene spesso utilizzato per indicare la posizione in cui è necessario un valore per la sintassi del linguaggio quando nessun valore è necessario o desiderato."
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44204656"
---
# <a name="unit-type"></a>Tipo di unità

Il `unit` tipo è un tipo che indica l'assenza di un valore specifico; il `unit` tipo ha un solo valore, che funge da segnaposto quando nessun altro valore è presente o necessario.

## <a name="syntax"></a>Sintassi

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Note

Tutte le espressioni F # devono restituire un valore. Per le espressioni che non generano un valore che è di particolare interesse, il valore di tipo `unit` viene usato. Il `unit` è simile a tipo di `void` tipo nei linguaggi come c# e C++.

Il `unit` tipo ha un singolo valore e tale valore è indicato dal token `()`.

Il valore della `unit` tipo viene spesso usato in F # programming per indicare la posizione in cui è richiesto un valore dalla sintassi del linguaggio, ma quando nessun valore è necessario o desiderato. Un esempio potrebbe essere il valore restituito di un `printf` (funzione). Poiché le azioni di importanti il `printf` eseguire operazioni nella funzione, la funzione non deve restituire un valore effettivo. Pertanto, il valore restituito è di tipo `unit`.

Alcuni costrutti prevedono un `unit` valore. Ad esempio, un `do` binding o qualsiasi codice al livello superiore di un modulo è previsto in modo che restituisca un `unit` valore. Il compilatore genera un avviso quando un `do` al codice al livello superiore di un modulo o associazione produce un risultato diverso dal `unit` valore non usato, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Questo avviso è una caratteristica della programmazione funzionale; non fa in altri linguaggi di programmazione .NET. In un programma puramente funzionale, in cui le funzioni ha effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione. Pertanto, quando il risultato viene ignorato, è un possibile errore di programmazione. Sebbene F # non sia un linguaggio di programmazione puramente funzionale, è buona norma da seguire dello stile di programmazione funzionale, laddove possibile.

## <a name="see-also"></a>Vedere anche

- [Primitivi](primitive-types.md)
- [Riferimenti per il linguaggio F#](index.md)
