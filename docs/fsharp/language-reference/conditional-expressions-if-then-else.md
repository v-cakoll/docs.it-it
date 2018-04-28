---
title: 'Espressioni condizionali: if...then...else (F#)'
description: 'Informazioni su come scrivere espressioni condizionali in F # per eseguire diversi rami del codice.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="8583a-103">Espressioni condizionali: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="8583a-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="8583a-104">Il `if...then...else` espressione consente di eseguire diversi rami del codice e che restituisce un valore diverso in base all'espressione booleana specificata.</span><span class="sxs-lookup"><span data-stu-id="8583a-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="8583a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8583a-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="8583a-106">Note</span><span class="sxs-lookup"><span data-stu-id="8583a-106">Remarks</span></span>
<span data-ttu-id="8583a-107">Nella sintassi precedente, *expression1* viene eseguito quando l'espressione booleana restituisce `true`; in caso contrario, *expression2* viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="8583a-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="8583a-108">A differenza di altri linguaggi, il `if...then...else` costrutto è un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8583a-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="8583a-109">Ciò significa che viene prodotto un valore, ovvero il valore dell'ultima espressione nel ramo che viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="8583a-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="8583a-110">I tipi dei valori di prodotti in ogni ramo devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="8583a-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="8583a-111">Se è non esplicita `else` ramo, il tipo è `unit`.</span><span class="sxs-lookup"><span data-stu-id="8583a-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="8583a-112">Pertanto, se il tipo del `then` ramo è qualsiasi tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="8583a-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="8583a-113">Quando si concatenano `if...then...else` le espressioni, è possibile utilizzare la parola chiave `elif` anziché `else if`; sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="8583a-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="8583a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8583a-114">Example</span></span>
<span data-ttu-id="8583a-115">Nell'esempio seguente viene illustrato come utilizzare il `if...then...else` espressione.</span><span class="sxs-lookup"><span data-stu-id="8583a-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="8583a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8583a-116">See Also</span></span>
[<span data-ttu-id="8583a-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="8583a-117">F# Language Reference</span></span>](index.md)

