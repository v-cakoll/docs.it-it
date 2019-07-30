---
title: 'Espressioni condizionali: If... quindi... altro'
description: Informazioni su come scrivere espressioni condizionali F# in per eseguire rami di codice diversi.
ms.date: 05/16/2016
ms.openlocfilehash: 825149bf296eded3cc2b4d8847ba4d82bea40cdc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630387"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="efb59-103">Espressioni condizionali:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="efb59-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="efb59-104">L' `if...then...else` espressione esegue diversi rami di codice e restituisce anche un valore diverso a seconda dell'espressione booleana specificata.</span><span class="sxs-lookup"><span data-stu-id="efb59-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="efb59-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efb59-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="efb59-106">Note</span><span class="sxs-lookup"><span data-stu-id="efb59-106">Remarks</span></span>

<span data-ttu-id="efb59-107">Nella sintassi precedente, *expression1* viene eseguito quando l'espressione booleana restituisce `true`. in caso contrario, viene eseguito *expression2* .</span><span class="sxs-lookup"><span data-stu-id="efb59-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="efb59-108">Diversamente da altri linguaggi, il `if...then...else` costrutto è un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="efb59-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="efb59-109">Ciò significa che produce un valore, ovvero il valore dell'ultima espressione nel ramo eseguito.</span><span class="sxs-lookup"><span data-stu-id="efb59-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="efb59-110">I tipi dei valori prodotti in ogni ramo devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="efb59-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="efb59-111">Se non è presente alcun `else` ramo esplicito, il `unit`relativo tipo è.</span><span class="sxs-lookup"><span data-stu-id="efb59-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="efb59-112">Pertanto, se il tipo del `then` ramo è un tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="efb59-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="efb59-113">Quando si concatenano `if...then...else` espressioni, è possibile usare la `elif` parola chiave `else if`invece di. sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="efb59-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="efb59-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="efb59-114">Example</span></span>

<span data-ttu-id="efb59-115">Nell'esempio seguente viene illustrato come utilizzare l' `if...then...else` espressione.</span><span class="sxs-lookup"><span data-stu-id="efb59-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="efb59-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efb59-116">See also</span></span>

- [<span data-ttu-id="efb59-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="efb59-117">F# Language Reference</span></span>](index.md)
