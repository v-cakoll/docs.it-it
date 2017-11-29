---
title: 'Eccezioni: funzione invalidArg (F#)'
description: 'Informazioni su come la funzione ''invalidArg'' F # genera un''eccezione di argomento.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: 107bef361a6bd034e3d6a2227e18cf64b1b04576
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-invalidarg-function"></a>Eccezioni: funzione invalidArg

Il `invalidArg` funzione genera un'eccezione di argomento.


## <a name="syntax"></a>Sintassi

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Note
Il nome di parametro nella sintassi precedente è una stringa con il nome del parametro il cui argomento non valido. Il *stringa di messaggio di errore* è una stringa letterale o un valore di tipo `string`. Diventa il `Message` proprietà dell'oggetto eccezione.

L'eccezione generata dal `invalidArg` è un `System.ArgumentException` eccezione. Il codice seguente viene illustrato l'utilizzo di `invalidArg` per generare un'eccezione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

L'output è il seguente, seguito da una traccia dello stack (non illustrata).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vedere anche
[Gestione delle eccezioni](index.md)

[Tipi di eccezione](exception-types.md)

[Eccezioni: espressione `try...with`](the-try-with-expression.md)

[Eccezioni: espressione `try...finally`](the-try-finally-expression.md)

[Eccezioni: funzione `raise`](the-raise-function.md)

[Eccezioni: funzione `failwith`](the-failwith-function.md)
