---
title: Tipi di eccezione (F#)
description: 'Informazioni su come definire e usare i tipi di eccezione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858821"
---
# <a name="exception-types"></a>Tipi di eccezione

Esistono due categorie di eccezioni in F #: tipi di eccezione .NET e i tipi di eccezione F #. Questo argomento descrive come definire e usare i tipi di eccezione F #.

## <a name="syntax"></a>Sintassi

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Note

Nella sintassi precedente *-tipo di eccezione* è il nome di un nuovo tipo, eccezione F # e *tipi di argomento* rappresenta il tipo di argomento che può essere fornito quando si genera un'eccezione di questo tipo. È possibile specificare più argomenti usando un tipo di tupla per *tipi di argomento*.

Una tipica definizione per un'eccezione F # è simile al seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

È possibile generare un'eccezione di questo tipo usando il `raise` funzionare, come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

È possibile usare un tipo di eccezione F # direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Il tipo di eccezione definito tramite il `exception` parola chiave in F # è un nuovo tipo che eredita da `System.Exception`.

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Gerarchia delle eccezioni](https://msdn.microsoft.com/library/z4c5tckx.aspx)
