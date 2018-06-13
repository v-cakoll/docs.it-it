---
title: 'Eccezioni: funzione failwith (F#)'
description: "Informazioni su come la funzione 'failwith' genera un'eccezione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 59f7129faf38668dd7390790e22d25f37c129750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563328"
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
