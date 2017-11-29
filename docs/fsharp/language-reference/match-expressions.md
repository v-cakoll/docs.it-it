---
title: Espressioni match (F#)
description: "Informazioni su come l'espressione di corrispondenza di F # offre il controllo con diramazione è basato sul confronto di un'espressione con un set di modelli."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="ae37e-104">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="ae37e-104">Match Expressions</span></span>

<span data-ttu-id="ae37e-105">Il `match` espressione fornisce un controllo con diramazione basato sul confronto di un'espressione con un set di modelli.</span><span class="sxs-lookup"><span data-stu-id="ae37e-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae37e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae37e-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ae37e-107">Note</span><span class="sxs-lookup"><span data-stu-id="ae37e-107">Remarks</span></span>

<span data-ttu-id="ae37e-108">Le espressioni di corrispondenza consentono di creazione di rami complesse in base al confronto di un'espressione di test con un set di modelli.</span><span class="sxs-lookup"><span data-stu-id="ae37e-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="ae37e-109">Nel `match` espressione, il *espressione di test* viene confrontato con ogni modello e quando viene trovata una corrispondenza, il corrispondente *espressione di risultato* viene valutata e il valore risultante è restituito come valore dell'espressione di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ae37e-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="ae37e-110">Criteri di ricerca funzione illustrato nella sintassi precedente sono un'espressione lambda in quale criterio di corrispondenza viene eseguita immediatamente per l'argomento.</span><span class="sxs-lookup"><span data-stu-id="ae37e-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="ae37e-111">Criteri di ricerca funzione illustrato nella sintassi precedente sono equivalente a quanto segue.</span><span class="sxs-lookup"><span data-stu-id="ae37e-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="ae37e-112">Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni Lambda: I `fun` parola chiave](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="ae37e-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="ae37e-113">L'intero set di modelli deve coprire tutte le corrispondenze possibili della variabile di input.</span><span class="sxs-lookup"><span data-stu-id="ae37e-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="ae37e-114">È spesso necessario utilizzare il carattere jolly (`_`) per l'ultima serie corrispondere i valori di input in precedenza non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ae37e-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="ae37e-115">Il codice seguente vengono illustrati alcuni dei modi in cui il `match` viene utilizzata l'espressione.</span><span class="sxs-lookup"><span data-stu-id="ae37e-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="ae37e-116">Per un riferimento ed esempi di tutti i possibili modelli che possono essere usati, vedere [criteri di ricerca](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="ae37e-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="ae37e-117">Guard nei modelli</span><span class="sxs-lookup"><span data-stu-id="ae37e-117">Guards on Patterns</span></span>

<span data-ttu-id="ae37e-118">È possibile utilizzare un `when` clausola per specificare una condizione aggiuntiva che la variabile deve soddisfare la corrispondenza di un modello.</span><span class="sxs-lookup"><span data-stu-id="ae37e-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="ae37e-119">Tale clausola viene considerata un *protezione*.</span><span class="sxs-lookup"><span data-stu-id="ae37e-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="ae37e-120">L'espressione che segue il `when` parola chiave non viene valutata a meno che non viene individuata una corrispondenza per il modello associato a tale guard.</span><span class="sxs-lookup"><span data-stu-id="ae37e-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="ae37e-121">Nell'esempio seguente viene illustrato l'utilizzo di una clausola guard per specificare un intervallo numerico per un modello di variabile.</span><span class="sxs-lookup"><span data-stu-id="ae37e-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="ae37e-122">Si noti che più condizioni vengono combinate tramite gli operatori booleani.</span><span class="sxs-lookup"><span data-stu-id="ae37e-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="ae37e-123">Si noti che poiché valori diversi da valori letterali non possono essere utilizzati nel modello, è necessario utilizzare un `when` clausola se è necessario confrontare una parte dell'input con un valore.</span><span class="sxs-lookup"><span data-stu-id="ae37e-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="ae37e-124">Questo comportamento viene mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ae37e-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="ae37e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae37e-125">See Also</span></span>

[<span data-ttu-id="ae37e-126">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ae37e-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ae37e-127">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="ae37e-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="ae37e-128">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="ae37e-128">Pattern Matching</span></span>](pattern-matching.md)
