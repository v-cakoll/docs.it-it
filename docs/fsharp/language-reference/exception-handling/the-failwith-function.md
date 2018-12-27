---
title: 'Eccezioni: Funzione failwith'
description: Informazioni su come la funzione 'failwith' genera un F# eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: 05d385ddfc98a910779a6f59949a7187c38f0812
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610112"
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