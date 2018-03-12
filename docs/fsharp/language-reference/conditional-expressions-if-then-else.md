---
title: 'Espressioni condizionali: if...then...else (F#)'
description: 'Informazioni su come scrivere espressioni condizionali in F # per eseguire diversi rami del codice.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 5823e46cd13053fcd31f94f2d79d1f7470ca5118
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2018
---
# <a name="conditional-expressions-ifthenelse"></a>Espressioni condizionali: `if...then...else`

Il `if...then...else` espressione consente di eseguire diversi rami del codice e che restituisce un valore diverso in base all'espressione booleana specificata.


## <a name="syntax"></a>Sintassi

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Note
Nella sintassi precedente, *expression1* viene eseguito quando l'espressione booleana restituisce `true`; in caso contrario, *expression2* viene eseguito.

A differenza di altri linguaggi, il `if...then...else` costrutto è un'espressione, non un'istruzione. Ciò significa che viene prodotto un valore, ovvero il valore dell'ultima espressione nel ramo che viene eseguita. I tipi dei valori di prodotti in ogni ramo devono corrispondere. Se è non esplicita `else` ramo, il tipo è `unit`. Pertanto, se il tipo del `then` ramo è qualsiasi tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito. Quando si concatenano `if...then...else` le espressioni, è possibile utilizzare la parola chiave `elif` anziché `else if`; sono equivalenti.

## <a name="example"></a>Esempio
Nell'esempio seguente viene illustrato come utilizzare il `if...then...else` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

