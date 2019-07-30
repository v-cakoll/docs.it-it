---
title: Espressioni lazy
description: Informazioni su F# come le espressioni Lazy possono migliorare le prestazioni delle app e delle librerie.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630743"
---
# <a name="lazy-expressions"></a><span data-ttu-id="7ccd6-103">Espressioni lazy</span><span class="sxs-lookup"><span data-stu-id="7ccd6-103">Lazy Expressions</span></span>

<span data-ttu-id="7ccd6-104">Le *espressioni Lazy* sono espressioni che non vengono valutate immediatamente, ma vengono invece valutate quando il risultato è necessario.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="7ccd6-105">Questo può contribuire a migliorare le prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ccd6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ccd6-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="7ccd6-107">Note</span><span class="sxs-lookup"><span data-stu-id="7ccd6-107">Remarks</span></span>

<span data-ttu-id="7ccd6-108">Nella sintassi precedente, *Expression* è il codice che viene valutato solo quando è necessario un risultato e *Identifier* è un valore che archivia il risultato.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="7ccd6-109">Il valore è di tipo [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo usato per `'T` è determinato dal risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="7ccd6-110">Le espressioni Lazy consentono di migliorare le prestazioni limitando l'esecuzione di espressioni solo alle situazioni in cui è necessario un risultato.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="7ccd6-111">Per forzare l'esecuzione delle espressioni, chiamare il metodo `Force`.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="7ccd6-112">`Force`fa in modo che l'esecuzione venga eseguita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="7ccd6-113">Le chiamate successive `Force` a restituiscono lo stesso risultato, ma non eseguono alcun codice.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="7ccd6-114">Nel codice seguente viene illustrato l'utilizzo di espressioni Lazy e l'utilizzo di `Force`.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="7ccd6-115">In questo codice, il tipo di `result` è `Lazy<int>` `int`e il `Force` metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="7ccd6-116">La valutazione lazy, ma non `Lazy` il tipo, viene usata anche per le sequenze.</span><span class="sxs-lookup"><span data-stu-id="7ccd6-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="7ccd6-117">Per ulteriori informazioni, vedere [sequences](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="7ccd6-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ccd6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ccd6-118">See also</span></span>

- [<span data-ttu-id="7ccd6-119">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="7ccd6-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7ccd6-120">Modulo LazyExtensions</span><span class="sxs-lookup"><span data-stu-id="7ccd6-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
