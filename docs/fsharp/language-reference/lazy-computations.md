---
title: Calcoli differiti (F#)
description: 'Informazioni su come F # differiti possono migliorare le prestazioni delle App e librerie.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="6a566-104">Calcoli differiti</span><span class="sxs-lookup"><span data-stu-id="6a566-104">Lazy Computations</span></span>

<span data-ttu-id="6a566-105">*Calcoli differiti* sono calcoli che non vengono valutati immediatamente, ma solo quando il risultato è necessario.</span><span class="sxs-lookup"><span data-stu-id="6a566-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="6a566-106">Questo può contribuire a migliorare le prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="6a566-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a566-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a566-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="6a566-108">Note</span><span class="sxs-lookup"><span data-stu-id="6a566-108">Remarks</span></span>

<span data-ttu-id="6a566-109">Nella sintassi precedente, *espressione* è codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato.</span><span class="sxs-lookup"><span data-stu-id="6a566-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="6a566-110">Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo utilizzato per `'T` è determinato dal risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="6a566-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="6a566-111">Calcoli differiti consentono di migliorare le prestazioni limitando l'esecuzione di un calcolo in solo nelle situazioni in cui è necessario un risultato.</span><span class="sxs-lookup"><span data-stu-id="6a566-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="6a566-112">Per forzare il calcolo da eseguire, chiamare il metodo `Force`.</span><span class="sxs-lookup"><span data-stu-id="6a566-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="6a566-113">`Force`Determina l'esecuzione a essere eseguita solo una volta.</span><span class="sxs-lookup"><span data-stu-id="6a566-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="6a566-114">Le chiamate successive a `Force` restituire lo stesso risultato, ma non eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="6a566-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="6a566-115">Il codice seguente viene illustrato l'utilizzo di calcolo lazy e l'utilizzo di `Force`.</span><span class="sxs-lookup"><span data-stu-id="6a566-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="6a566-116">In questo codice, il tipo di `result` è `Lazy<int>`e `Force` metodo restituisce un `int`.</span><span class="sxs-lookup"><span data-stu-id="6a566-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="6a566-117">Valutazione lenta, ma non il `Lazy` digitare, viene usato anche per le sequenze.</span><span class="sxs-lookup"><span data-stu-id="6a566-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="6a566-118">Per ulteriori informazioni, vedere [sequenze](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="6a566-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a566-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a566-119">See Also</span></span>

[<span data-ttu-id="6a566-120">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="6a566-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6a566-121">LazyExtensions (modulo)</span><span class="sxs-lookup"><span data-stu-id="6a566-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
