---
title: 'Eccezioni: funzione failwith (F#)'
description: "Informazioni su come la funzione 'failwith' genera un'eccezione F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: af1e3b7dc96b3b822e2e19b7bac435940d15922f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-failwith-function"></a>Eccezioni: funzione failwith

Il `failwith` funzione genera un'eccezione F #.


## <a name="syntax"></a>Sintassi

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Note
Il *stringa di messaggio di errore* nella sintassi precedente è una stringa letterale o un valore di tipo `string`. Diventa il `Message` proprietà dell'eccezione.

L'eccezione generata da `failwith` è un `System.Exception` eccezione, che è un riferimento con il nome `Failure` nel codice F #. Il codice seguente viene illustrato l'utilizzo di `failwith` per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>Vedere anche
[Gestione delle eccezioni](index.md)

[Tipi di eccezione](exception-types.md)

[Eccezioni: espressione `try...with`](the-try-with-expression.md)

[Eccezioni: espressione `try...finally`](the-try-finally-expression.md)

[Eccezioni: funzione `raise`](the-raise-function.md)
