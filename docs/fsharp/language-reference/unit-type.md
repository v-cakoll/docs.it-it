---
title: Tipo di unità (F#)
description: "Informazioni su come il tipo 'unit' F # viene spesso utilizzato per indicare la posizione in cui è necessario un valore per la sintassi del linguaggio quando il valore non è necessario o desiderato."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1a8c8f74e31c5426a9fb6a7143e9d2ac9a7104c0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="unit-type"></a>Tipo di unità

Il `unit` tipo è un tipo che indica l'assenza di un valore specifico; il `unit` tipo ha un solo valore, che funge da segnaposto quando nessun altro valore è presente o è necessario.


## <a name="syntax"></a>Sintassi

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Note
Tutte le espressioni F # devono restituire un valore. Per le espressioni che non generano un valore che è di particolare interesse, il valore di tipo `unit` viene utilizzato. Il `unit` tipo simile di `void` tipo in linguaggi come c# e C++.

Il `unit` tipo dispone di un singolo valore, e tale valore viene indicato il token `()`.

Il valore di `unit` tipo viene spesso utilizzato per indicare la posizione in cui è necessario un valore per la sintassi del linguaggio, ma quando nessun valore è necessario o desiderato di programmazione F #. Un esempio potrebbe essere il valore restituito di un `printf` (funzione). Poiché le azioni di importanti di `printf` operazione eseguita nella funzione, la funzione non deve restituire un valore effettivo. Pertanto, il valore restituito è di tipo `unit`.

Alcuni costrutti prevedono un `unit` valore. Ad esempio, un `do` associazione o codice al livello superiore di un modulo è previsto in modo che restituisca un `unit` valore. Il compilatore genera un avviso quando un `do` associazione o il codice nella parte superiore di un modulo produce un risultato diverso dal `unit` valore che non viene utilizzato, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Questo avviso è una caratteristica della programmazione funzionale; non è visualizzata in altri linguaggi di programmazione .NET. In un programma puramente funzionale, in cui le funzioni non hanno effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione. Pertanto, quando il risultato viene ignorato, è un possibile errore di programmazione. Sebbene F # non sia un linguaggio di programmazione puramente funzionale, è buona norma utilizza lo stile di programmazione funzionale, laddove possibile.

## <a name="see-also"></a>Vedere anche
[Primitivi](primitive-types.md)

[Riferimenti per il linguaggio F#](index.md)
