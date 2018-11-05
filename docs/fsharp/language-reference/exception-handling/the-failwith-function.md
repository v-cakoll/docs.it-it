---
title: 'Eccezioni: funzione failwith (F#)'
description: "Informazioni su come la funzione 'failwith' genera un'eccezione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 69a2eb69e0157d3bde8cb8884cb0ae960634dddc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863429"
---
# <a name="exceptions-the-failwith-function"></a>Eccezioni: funzione failwith

Il `failwith` funzione genera un'eccezione F #.

## <a name="syntax"></a>Sintassi

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Note

Il *stringa di messaggio di errore* nella sintassi precedente è una stringa letterale o un valore di tipo `string`. Diventa il `Message` proprietà dell'eccezione.

L'eccezione che viene generato dal `failwith` è un `System.Exception` eccezione, ovvero un riferimento con il nome `Failure` nel codice F #. Il codice seguente illustra l'uso di `failwith` per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: espressione `try...with`](the-try-with-expression.md)
- [Eccezioni: espressione `try...finally`](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
