---
title: 'Eccezioni: funzione failwith (F#)'
description: 'Informazioni su come la funzione ''failwith'' genera un''eccezione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2017
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
