---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # differiti possono migliorare le prestazioni delle App e librerie.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563932"
---
# <a name="lazy-computations"></a><span data-ttu-id="060f4-103">Calcoli differiti</span><span class="sxs-lookup"><span data-stu-id="060f4-103">Lazy Computations</span></span>

<span data-ttu-id="060f4-104">*Calcoli differiti* sono calcoli che non vengono valutati immediatamente, ma solo quando è necessario il risultato.</span><span class="sxs-lookup"><span data-stu-id="060f4-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="060f4-105">Questo può contribuire a migliorare le prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="060f4-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="060f4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="060f4-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="060f4-107">Note</span><span class="sxs-lookup"><span data-stu-id="060f4-107">Remarks</span></span>

<span data-ttu-id="060f4-108">Nella sintassi precedente, *espressione* è codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato.</span><span class="sxs-lookup"><span data-stu-id="060f4-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="060f4-109">Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo utilizzato per `'T` è determinato dal risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="060f4-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="060f4-110">Calcoli differiti consentono di migliorare le prestazioni limitando l'esecuzione di un calcolo in solo nelle situazioni in cui è necessario un risultato.</span><span class="sxs-lookup"><span data-stu-id="060f4-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="060f4-111">Per forzare il calcolo da eseguire, chiamare il metodo `Force`.</span><span class="sxs-lookup"><span data-stu-id="060f4-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="060f4-112">`Force` Determina l'esecuzione deve essere eseguita solo una volta.</span><span class="sxs-lookup"><span data-stu-id="060f4-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="060f4-113">Le chiamate successive a `Force` restituire lo stesso risultato, ma non eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="060f4-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="060f4-114">Il codice seguente viene illustrato l'utilizzo di calcolo lazy e l'utilizzo di `Force`.</span><span class="sxs-lookup"><span data-stu-id="060f4-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="060f4-115">In questo codice, il tipo di `result` è `Lazy<int>`e `Force` metodo restituisce un `int`.</span><span class="sxs-lookup"><span data-stu-id="060f4-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="060f4-116">Valutazione lenta, ma non il `Lazy` digitare, viene usato anche per le sequenze.</span><span class="sxs-lookup"><span data-stu-id="060f4-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="060f4-117">Per ulteriori informazioni, vedere [sequenze](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="060f4-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="060f4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="060f4-118">See Also</span></span>

[<span data-ttu-id="060f4-119">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="060f4-119">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="060f4-120">LazyExtensions (modulo)</span><span class="sxs-lookup"><span data-stu-id="060f4-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
