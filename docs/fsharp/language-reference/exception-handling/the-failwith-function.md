---
title: 'Eccezioni: Funzione failwith'
description: Informazioni sul modo in cui la funzione ' failwith F# ' genera un'eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: f2c86362d5bdde7bab55751f019965a5f4ca6236
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630334"
---
# <a name="exceptions-the-failwith-function"></a>Eccezioni: Funzione failwith

La `failwith` funzione genera un' F# eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Note

La *stringa di messaggio di errore* nella sintassi precedente è una stringa letterale o un valore di tipo `string`. Diventa la `Message` proprietà dell'eccezione.

L' `failwith` eccezione generata da è un' `System.Exception` eccezione, ovvero un riferimento con il nome `Failure` nel F# codice. Il codice seguente illustra l'uso di `failwith` per generare un'eccezione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: `try...with` Espressione](the-try-with-expression.md)
- [Eccezioni: `try...finally` Espressione](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
