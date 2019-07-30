---
title: Tipi di eccezione
description: Informazioni su come definire e usare F# i tipi di eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630320"
---
# <a name="exception-types"></a>Tipi di eccezione

Esistono due categorie di eccezioni in F#: tipi di eccezione .NET e F# tipi di eccezione. In questo argomento viene descritto come definire e F# utilizzare i tipi di eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il *tipo di eccezione* è il nome di un nuovo F# tipo di eccezione e *argument-type* rappresenta il tipo di un argomento che può essere fornito quando si genera un'eccezione di questo tipo. È possibile specificare più argomenti usando un tipo di tupla per *argument-type*.

Una definizione tipica per un' F# eccezione è simile alla seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

È possibile generare un'eccezione di questo tipo utilizzando la `raise` funzione, come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

È possibile utilizzare un F# tipo di eccezione direttamente nei filtri in un' `try...with` espressione, come illustrato nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Il tipo di eccezione definito con la `exception` parola chiave in F# è un nuovo tipo che eredita da `System.Exception`.

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Gerarchia delle eccezioni](https://msdn.microsoft.com/library/z4c5tckx.aspx)
