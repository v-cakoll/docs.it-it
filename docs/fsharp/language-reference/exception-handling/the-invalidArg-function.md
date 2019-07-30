---
title: 'Eccezioni: Funzione invalidArg'
description: Informazioni sul modo F# in cui la funzione ' invalidArg ' genera un'eccezione di argomento.
ms.date: 05/16/2016
ms.openlocfilehash: 010dbfe313f539093b4ee7a19984ef54500b072d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630302"
---
# <a name="exceptions-the-invalidarg-function"></a>Eccezioni: Funzione invalidArg

La `invalidArg` funzione genera un'eccezione di argomento.

## <a name="syntax"></a>Sintassi

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Note

Il nome del parametro nella sintassi precedente è una stringa con il nome del parametro il cui argomento non è valido. *Error-Message-String* è una stringa letterale o un valore di tipo `string`. Diventa la `Message` proprietà dell'oggetto Exception.

L'eccezione generata da `invalidArg` è un' `System.ArgumentException` eccezione. Il codice seguente illustra l'uso di `invalidArg` per generare un'eccezione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

L'output è il seguente, seguito da un'analisi dello stack (non mostrata).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Tipi di eccezione](exception-types.md)
- [Eccezioni: `try...with` Espressione](the-try-with-expression.md)
- [Eccezioni: `try...finally` Espressione](the-try-finally-expression.md)
- [Eccezioni: funzione `raise`](the-raise-function.md)
- [Eccezioni: `failwith` Funzione](the-failwith-function.md)
