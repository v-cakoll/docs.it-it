---
title: 'Eccezioni: Funzione invalidArg'
description: Informazioni sul modo F# in cui la funzione ' invalidArg ' genera un'eccezione di argomento.
ms.date: 05/16/2016
ms.openlocfilehash: 6b1c5fdb5a541da336977d3a67d471302edb36b6
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083018"
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

```console
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
