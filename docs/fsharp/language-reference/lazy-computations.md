---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # calcoli differiti possono migliorare le prestazioni delle App e librerie.'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037068"
---
# <a name="lazy-computations"></a><span data-ttu-id="f977f-103">Calcoli differiti</span><span class="sxs-lookup"><span data-stu-id="f977f-103">Lazy Computations</span></span>

<span data-ttu-id="f977f-104">*Calcoli differiti* calcoli che non vengono eseguiti immediatamente, ma solo quando il risultato è necessaria.</span><span class="sxs-lookup"><span data-stu-id="f977f-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="f977f-105">Questo può contribuire a migliorare le prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="f977f-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f977f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f977f-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="f977f-107">Note</span><span class="sxs-lookup"><span data-stu-id="f977f-107">Remarks</span></span>

<span data-ttu-id="f977f-108">Nella sintassi precedente *espressione* è il codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato.</span><span class="sxs-lookup"><span data-stu-id="f977f-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="f977f-109">Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo che viene usato per `'T` è determinato dal risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="f977f-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="f977f-110">Calcoli differiti consentono di migliorare le prestazioni, limitando l'esecuzione di un calcolo solo tali situazioni in cui è necessario un risultato.</span><span class="sxs-lookup"><span data-stu-id="f977f-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="f977f-111">Per forzare il calcolo da eseguire, si chiama il metodo `Force`.</span><span class="sxs-lookup"><span data-stu-id="f977f-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="f977f-112">`Force` Determina l'esecuzione deve essere eseguita solo una volta.</span><span class="sxs-lookup"><span data-stu-id="f977f-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="f977f-113">Le chiamate successive a `Force` restituiscono lo stesso risultato, ma non eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="f977f-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="f977f-114">Il codice seguente illustra l'utilizzo di calcolo lazy e l'uso di `Force`.</span><span class="sxs-lookup"><span data-stu-id="f977f-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="f977f-115">In questo codice, il tipo di `result` viene `Lazy<int>`e il `Force` metodo restituisce un `int`.</span><span class="sxs-lookup"><span data-stu-id="f977f-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="f977f-116">Valutazione lenta, ma non la `Lazy` digitare, viene usato anche per le sequenze.</span><span class="sxs-lookup"><span data-stu-id="f977f-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="f977f-117">Per altre informazioni, vedere [sequenze](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="f977f-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f977f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f977f-118">See also</span></span>

- [<span data-ttu-id="f977f-119">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f977f-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f977f-120">LazyExtensions (modulo)</span><span class="sxs-lookup"><span data-stu-id="f977f-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
