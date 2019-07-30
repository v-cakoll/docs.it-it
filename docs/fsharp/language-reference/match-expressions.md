---
title: Espressioni di corrispondenza
description: Informazioni sul modo F# in cui l'espressione di corrispondenza fornisce il controllo di diramazione basato sul confronto di un'espressione con un set di modelli.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627616"
---
# <a name="match-expressions"></a>Espressioni di corrispondenza

L' `match` espressione fornisce il controllo di diramazione basato sul confronto di un'espressione con un set di modelli.

## <a name="syntax"></a>Sintassi

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>Note

Le espressioni di criteri di ricerca consentono una diramazione complessa basata sul confronto di un'espressione di test con un set di modelli. Nell'espressione, *test-Expression* viene confrontato con ogni pattern e, quando viene trovata una corrispondenza, l' *espressione result* corrispondente viene valutata e il valore risultante viene restituito come valore dell'espressione di corrispondenza. `match`

La funzione di criteri di ricerca illustrata nella sintassi precedente è un'espressione lambda in cui i criteri di ricerca vengono eseguiti immediatamente nell'argomento. La funzione di criteri di ricerca illustrata nella sintassi precedente è equivalente alla seguente.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni lambda: `fun` Parola chiave](./functions/lambda-expressions-the-fun-keyword.md).

L'intero set di modelli dovrebbe coprire tutte le possibili corrispondenze della variabile di input. Spesso si usa il modello con caratteri jolly`_`() come ultimo criterio per trovare la corrispondenza con qualsiasi valore di input precedentemente non corrispondente.

Nel codice seguente vengono illustrati alcuni dei modi in cui viene `match` utilizzata l'espressione. Per un riferimento ed esempi di tutti i possibili modelli che è possibile usare [, vedere Criteri](pattern-matching.md)di ricerca.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Protezioni su modelli

È possibile usare una `when` clausola per specificare una condizione aggiuntiva che la variabile deve soddisfare per corrispondere a un modello. Tale clausola viene definita *Guard*. L'espressione che segue `when` la parola chiave non viene valutata a meno che non venga apportata una corrispondenza al criterio associato a tale Guard.

Nell'esempio seguente viene illustrato l'utilizzo di una Guard per specificare un intervallo numerico per un modello di variabile. Si noti che più condizioni vengono combinate tramite gli operatori booleani.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Si noti che poiché non è possibile usare valori diversi dai valori letterali nel criterio, è necessario `when` usare una clausola se è necessario confrontare una parte dell'input rispetto a un valore. Questo comportamento è illustrato nel codice seguente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Si noti che quando un modello di Unione è coperto da una protezione, la protezione si applica a **tutti** i modelli, non solo all'ultima. Dato il codice seguente, ad esempio, la protezione `when a > 12` si applica sia `A a` a `B a`che a:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Criteri attivi](active-patterns.md)
- [Criteri di ricerca](pattern-matching.md)
