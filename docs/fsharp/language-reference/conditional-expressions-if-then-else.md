---
title: 'Espressioni condizionali: If... quindi... altro'
description: Informazioni su come scrivere espressioni condizionali F# in per eseguire rami di codice diversi.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083027"
---
# <a name="conditional-expressions-ifthenelse"></a>Espressioni condizionali:`if...then...else`

L' `if...then...else` espressione esegue diversi rami di codice e restituisce anche un valore diverso a seconda dell'espressione booleana specificata.

## <a name="syntax"></a>Sintassi

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *expression1* viene eseguito quando l'espressione booleana restituisce `true`. in caso contrario, viene eseguito *expression2* .

Diversamente da altri linguaggi, il `if...then...else` costrutto è un'espressione, non un'istruzione. Ciò significa che produce un valore, ovvero il valore dell'ultima espressione nel ramo eseguito. I tipi dei valori prodotti in ogni ramo devono corrispondere. Se non è presente alcun `else` ramo esplicito, il `unit`relativo tipo è. Pertanto, se il tipo del `then` ramo è un tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito. Quando si concatenano `if...then...else` espressioni, è possibile usare la `elif` parola chiave `else if`invece di. sono equivalenti.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare l' `if...then...else` espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
