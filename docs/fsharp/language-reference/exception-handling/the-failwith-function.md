---
title: 'Eccezioni: Funzione failwith'
description: Informazioni su come la funzione 'failwith' genera un F# eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: 08107966ddc2f55625347deb92d224b286df7761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641954"
---
# <a name="exceptions-the-failwith-function"></a>Eccezioni: Funzione failwith

Il `failwith` funzione genera un F# eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Note

Il *stringa di messaggio di errore* nella sintassi precedente è una stringa letterale o un valore di tipo `string`. Diventa il `Message` proprietà dell'eccezione.

L'eccezione che viene generato dal `failwith` è un `System.Exception` eccezione, ovvero un riferimento con il nome `Failure` in F# codice. Il codice seguente illustra l'uso di `failwith` per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: Il `try...with` espressione](the-try-with-expression.md)
- [Eccezioni: Il `try...finally` espressione](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
