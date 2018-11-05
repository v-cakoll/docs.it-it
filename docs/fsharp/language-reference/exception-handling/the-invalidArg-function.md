---
title: 'Eccezioni: funzione invalidArg (F#)'
description: Informazioni su come la funzione 'invalidArg' F# genera un'eccezione di argomento.
ms.date: 05/16/2016
ms.openlocfilehash: 8bf65fae9392a88205e3cdec8b7d7a3ff42f8416
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44180319"
---
# <a name="exceptions-the-invalidarg-function"></a>Eccezioni: funzione invalidArg

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
- [Eccezioni: espressione `try...with`](the-try-with-expression.md)
- [Eccezioni: espressione `try...finally`](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Eccezioni: funzione `failwith`](the-failwith-function.md)
