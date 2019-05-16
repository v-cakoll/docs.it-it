---
title: Tipi di eccezione
description: Informazioni su come definire e usare F# tipi di eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645561"
---
# <a name="exception-types"></a>Tipi di eccezione

Esistono due categorie di eccezioni in F#: i tipi di eccezione .NET e F# tipi di eccezione. Questo argomento descrive come definire e usare F# tipi di eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Note

Nella sintassi precedente *-tipo di eccezione* è il nome di un nuovo F# tipo di eccezione, e *tipi di argomento* rappresenta il tipo di argomento che può essere fornito quando si genera un'eccezione di questo tipo. È possibile specificare più argomenti usando un tipo di tupla per *tipi di argomento*.

Una tipica definizione per un F# eccezione è simile al seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

È possibile generare un'eccezione di questo tipo usando il `raise` funzionare, come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

È possibile usare un F# tipo di eccezione direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Il tipo di eccezione definito tramite il `exception` parola chiave in F# è un nuovo tipo che eredita da `System.Exception`.

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Gerarchia delle eccezioni](https://msdn.microsoft.com/library/z4c5tckx.aspx)
