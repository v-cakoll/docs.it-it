---
title: 'Eccezioni: Funzione invalidArg'
description: Informazioni su come il F# funzione 'invalidArg' genera un'eccezione di argomento.
ms.date: 05/16/2016
ms.openlocfilehash: 1f0cbc9b7e805822544d6d54bc1fc69adf82967a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645472"
---
# <a name="exceptions-the-invalidarg-function"></a>Eccezioni: Funzione invalidArg

Il `invalidArg` funzione genera un'eccezione di argomento.

## <a name="syntax"></a>Sintassi

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Note

Il nome di parametro nella sintassi precedente è una stringa con il nome del parametro il cui argomento non è valido. Il *stringa di messaggio di errore* è una stringa letterale o un valore di tipo `string`. Diventa il `Message` proprietà dell'oggetto eccezione.

L'eccezione generata dal `invalidArg` è un `System.ArgumentException` eccezione. Il codice seguente illustra l'uso di `invalidArg` per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

L'output è il comando seguente, seguito da una traccia dello stack (non illustrata).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: Il `try...with` espressione](the-try-with-expression.md)
- [Eccezioni: Il `try...finally` espressione](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Eccezioni: Il `failwith` (funzione)](the-failwith-function.md)
