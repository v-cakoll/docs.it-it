---
title: 'Espressioni Match (F #)'
description: "Informazioni su come l'espressione di corrispondenza di F # offre il controllo con diramazione è basato sul confronto di un'espressione con un set di modelli."
author: cartermp
ms.author: phcart
ms.date: 04/19/2018
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f6930f782384464f0d44b205ea77cbaf43898213
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="match-expressions"></a>Espressioni Match

Il `match` espressione fornisce un controllo con diramazione basato sul confronto di un'espressione con un set di modelli.

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

Le espressioni di corrispondenza consentono di creazione di rami complesse in base al confronto di un'espressione di test con un set di modelli. Nel `match` espressione, il *espressione di test* viene confrontato con ogni modello e quando viene trovata una corrispondenza, il corrispondente *espressione di risultato* viene valutata e il valore risultante è restituito come valore dell'espressione di corrispondenza.

Criteri di ricerca funzione illustrato nella sintassi precedente sono un'espressione lambda in quale criterio di corrispondenza viene eseguita immediatamente per l'argomento. Criteri di ricerca funzione illustrato nella sintassi precedente sono equivalente a quanto segue.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni Lambda: I `fun` parola chiave](functions/lambda-expressions-the-fun-keyword.md).

L'intero set di modelli deve coprire tutte le corrispondenze possibili della variabile di input. È spesso necessario utilizzare il carattere jolly (`_`) per l'ultima serie corrispondere i valori di input in precedenza non corrispondenti.

Il codice seguente vengono illustrati alcuni dei modi in cui il `match` viene utilizzata l'espressione. Per un riferimento ed esempi di tutti i possibili modelli che possono essere usati, vedere [criteri di ricerca](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Guard nei modelli

È possibile utilizzare un `when` clausola per specificare una condizione aggiuntiva che la variabile deve soddisfare la corrispondenza di un modello. Tale clausola viene considerata un *protezione*. L'espressione che segue il `when` parola chiave non viene valutata a meno che non viene individuata una corrispondenza per il modello associato a tale guard.

Nell'esempio seguente viene illustrato l'utilizzo di una clausola guard per specificare un intervallo numerico per un modello di variabile. Si noti che più condizioni vengono combinate tramite gli operatori booleani.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Si noti che poiché valori diversi da valori letterali non possono essere utilizzati nel modello, è necessario utilizzare un `when` clausola se è necessario confrontare una parte dell'input con un valore. Come illustrato nel codice seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Si noti che quando un modello unione è coperto da una clausola guard, la protezione viene applicata a **tutti** dei modelli, non solo quella più recente. Si consideri ad esempio il codice seguente, la clausola guard `when a > 12` si applica a entrambe `A a` e `B a`:

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

[Riferimenti per il linguaggio F#](index.md)  
[Criteri attivi](active-patterns.md)  
[Criteri di ricerca](pattern-matching.md)  
