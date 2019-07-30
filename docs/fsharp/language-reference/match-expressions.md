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
# <a name="match-expressions"></a><span data-ttu-id="d3771-103">Espressioni di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="d3771-103">Match expressions</span></span>

<span data-ttu-id="d3771-104">L' `match` espressione fornisce il controllo di diramazione basato sul confronto di un'espressione con un set di modelli.</span><span class="sxs-lookup"><span data-stu-id="d3771-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3771-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3771-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d3771-106">Note</span><span class="sxs-lookup"><span data-stu-id="d3771-106">Remarks</span></span>

<span data-ttu-id="d3771-107">Le espressioni di criteri di ricerca consentono una diramazione complessa basata sul confronto di un'espressione di test con un set di modelli.</span><span class="sxs-lookup"><span data-stu-id="d3771-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="d3771-108">Nell'espressione, *test-Expression* viene confrontato con ogni pattern e, quando viene trovata una corrispondenza, l' *espressione result* corrispondente viene valutata e il valore risultante viene restituito come valore dell'espressione di corrispondenza. `match`</span><span class="sxs-lookup"><span data-stu-id="d3771-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="d3771-109">La funzione di criteri di ricerca illustrata nella sintassi precedente è un'espressione lambda in cui i criteri di ricerca vengono eseguiti immediatamente nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="d3771-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="d3771-110">La funzione di criteri di ricerca illustrata nella sintassi precedente è equivalente alla seguente.</span><span class="sxs-lookup"><span data-stu-id="d3771-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="d3771-111">Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni lambda: `fun` Parola chiave](./functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="d3771-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="d3771-112">L'intero set di modelli dovrebbe coprire tutte le possibili corrispondenze della variabile di input.</span><span class="sxs-lookup"><span data-stu-id="d3771-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="d3771-113">Spesso si usa il modello con caratteri jolly`_`() come ultimo criterio per trovare la corrispondenza con qualsiasi valore di input precedentemente non corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d3771-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="d3771-114">Nel codice seguente vengono illustrati alcuni dei modi in cui viene `match` utilizzata l'espressione.</span><span class="sxs-lookup"><span data-stu-id="d3771-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="d3771-115">Per un riferimento ed esempi di tutti i possibili modelli che è possibile usare [, vedere Criteri](pattern-matching.md)di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d3771-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="d3771-116">Protezioni su modelli</span><span class="sxs-lookup"><span data-stu-id="d3771-116">Guards on patterns</span></span>

<span data-ttu-id="d3771-117">È possibile usare una `when` clausola per specificare una condizione aggiuntiva che la variabile deve soddisfare per corrispondere a un modello.</span><span class="sxs-lookup"><span data-stu-id="d3771-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="d3771-118">Tale clausola viene definita *Guard*.</span><span class="sxs-lookup"><span data-stu-id="d3771-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="d3771-119">L'espressione che segue `when` la parola chiave non viene valutata a meno che non venga apportata una corrispondenza al criterio associato a tale Guard.</span><span class="sxs-lookup"><span data-stu-id="d3771-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="d3771-120">Nell'esempio seguente viene illustrato l'utilizzo di una Guard per specificare un intervallo numerico per un modello di variabile.</span><span class="sxs-lookup"><span data-stu-id="d3771-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="d3771-121">Si noti che più condizioni vengono combinate tramite gli operatori booleani.</span><span class="sxs-lookup"><span data-stu-id="d3771-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="d3771-122">Si noti che poiché non è possibile usare valori diversi dai valori letterali nel criterio, è necessario `when` usare una clausola se è necessario confrontare una parte dell'input rispetto a un valore.</span><span class="sxs-lookup"><span data-stu-id="d3771-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="d3771-123">Questo comportamento è illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d3771-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="d3771-124">Si noti che quando un modello di Unione è coperto da una protezione, la protezione si applica a **tutti** i modelli, non solo all'ultima.</span><span class="sxs-lookup"><span data-stu-id="d3771-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="d3771-125">Dato il codice seguente, ad esempio, la protezione `when a > 12` si applica sia `A a` a `B a`che a:</span><span class="sxs-lookup"><span data-stu-id="d3771-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d3771-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3771-126">See also</span></span>

- [<span data-ttu-id="d3771-127">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="d3771-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d3771-128">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="d3771-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="d3771-129">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="d3771-129">Pattern Matching</span></span>](pattern-matching.md)
