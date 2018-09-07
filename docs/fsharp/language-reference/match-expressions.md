---
title: 'Espressioni Match (F #)'
description: "Informazioni su come l'espressione di ricerca di F # offre controllo del branching basato sul confronto di un'espressione con un set di modelli."
ms.date: 04/19/2018
ms.openlocfilehash: e4cb82f20fe82bff562736557c2346562c557f59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44047675"
---
# <a name="match-expressions"></a>Espressioni Match

Il `match` espressione fornisce controllo del branching basato sul confronto di un'espressione con un set di modelli.

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

Le espressioni di corrispondenza consentono l'implicazione complesso basato sul confronto di un'espressione di test con un set di modelli. Nel `match` espressione, il *test-expression* viene confrontato con ogni modello, a sua volta, e quando viene trovata una corrispondenza, il corrispondente *espressione di risultato* viene valutata e il valore risultante è restituire come valore dell'espressione di corrispondenza.

I criteri di ricerca di funzione illustrato nella sintassi precedente sono un'espressione lambda in quale criterio di corrispondenza viene eseguita immediatamente in base all'argomento. I criteri di ricerca di funzione illustrato nella sintassi precedente sono equivalente alla seguente.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Per altre informazioni sulle espressioni lambda, vedere [espressioni Lambda: I `fun` parola chiave](functions/lambda-expressions-the-fun-keyword.md).

L'intero set di modelli devono coprire tutte le corrispondenze possibili della variabile di input. Spesso utilizzare il modello carattere jolly (`_`) come l'ultimo modello in modo che corrispondano eventuali valori di input in precedenza non corrispondenti.

Il codice seguente illustra alcuni dei modi in cui il `match` espressione viene usata. Per un riferimento ed esempi di tutti i possibili modelli utilizzabili, vedere [criteri di ricerca](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Guard nei modelli

È possibile usare un `when` clausola per specificare una condizione aggiuntiva che la variabile deve soddisfare corrisponda a un modello. Questa clausola viene definita un' *guard*. L'espressione che segue il `when` parola chiave non viene valutato solo se viene individuata una corrispondenza per il modello associato a tale protezione.

Nell'esempio seguente viene illustrato l'utilizzo di una clausola guard per specificare un intervallo numerico per un modello variabile. Si noti che più condizioni vengono unite tramite operatori booleani.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Si noti che poiché valori diversi da valori letterali non possono essere usati nel modello, è necessario utilizzare un `when` clausola se è necessario confrontare una parte dell'input rispetto a un valore. Questa operazione è illustrata nel codice seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Si noti che quando un modello di unione è coperto da una clausola guard, la protezione si applica a **tutti** degli schemi, non solo quello precedente. Si consideri ad esempio il codice seguente, la clausola guard `when a > 12` si applica a entrambe `A a` e `B a`:

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
