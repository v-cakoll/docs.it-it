---
title: 'Espressioni condizionali: if... then... else'
description: Informazioni su come scrivere espressioni condizionali F# per l'esecuzione di diversi rami del codice.
ms.date: 05/16/2016
ms.openlocfilehash: db2d5ce5b75ecda171f2623c986878dcee1cf4d9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641982"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="84473-103">Espressioni condizionali: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="84473-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="84473-104">Il `if...then...else` espressione esegue diversi rami del codice e restituisce un valore diverso in base all'espressione booleana specificata.</span><span class="sxs-lookup"><span data-stu-id="84473-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="84473-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84473-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="84473-106">Note</span><span class="sxs-lookup"><span data-stu-id="84473-106">Remarks</span></span>

<span data-ttu-id="84473-107">Nella sintassi precedente *expression1* viene eseguita quando l'espressione booleana restituisce `true`; in caso contrario, *expression2* viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="84473-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="84473-108">A differenza di altri linguaggi, la `if...then...else` costrutto è un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="84473-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="84473-109">Ciò significa che produce un valore, ovvero il valore dell'ultima espressione nel ramo che esegue.</span><span class="sxs-lookup"><span data-stu-id="84473-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="84473-110">I tipi di valori prodotti in ogni ramo devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="84473-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="84473-111">Se è presente non espliciti `else` branch, il tipo è `unit`.</span><span class="sxs-lookup"><span data-stu-id="84473-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="84473-112">Pertanto, se il tipo del `then` ramo è qualsiasi tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="84473-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="84473-113">Quando si concatenano `if...then...else` le espressioni, è possibile usare la parola chiave `elif` invece di `else if`; sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="84473-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="84473-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="84473-114">Example</span></span>

<span data-ttu-id="84473-115">L'esempio seguente illustra come usare il `if...then...else` espressione.</span><span class="sxs-lookup"><span data-stu-id="84473-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="84473-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84473-116">See also</span></span>

- [<span data-ttu-id="84473-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="84473-117">F# Language Reference</span></span>](index.md)
