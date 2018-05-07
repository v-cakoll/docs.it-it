---
title: Tipi di eccezione (F#)
description: 'Informazioni su come definire e utilizzare i tipi di eccezione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4462dd00ddf9524d1fd376ee1e73e81fcfd5d945
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exception-types"></a>Tipi di eccezione

Esistono due categorie di eccezioni in F #: tipi di eccezione .NET e i tipi di eccezione F #. In questo argomento viene descritto come definire e utilizzare i tipi di eccezione F #.


## <a name="syntax"></a>Sintassi

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Note
Nella sintassi precedente, *-tipo di eccezione* è il nome di un nuovo tipo, eccezione F # e *-tipo di argomento* rappresenta il tipo di un argomento che può essere fornito quando si genera un'eccezione di questo tipo. È possibile specificare più argomenti usando un tipo di tupla per *-tipo di argomento*.

Una definizione tipiche per un'eccezione F # è simile al seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

È possibile generare un'eccezione di questo tipo utilizzando il `raise` funzione, come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

È possibile utilizzare un tipo di eccezione F # direttamente nei filtri in un `try...with` espressione, come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Il tipo di eccezione definito con il `exception` la parola chiave in F # è un nuovo tipo che eredita da `System.Exception`.


## <a name="see-also"></a>Vedere anche
[Gestione delle eccezioni](index.md)

[Eccezioni: funzione `raise`](the-raise-function.md)

[Gerarchia delle eccezioni](https://msdn.microsoft.com/library/z4c5tckx.aspx)
