---
title: Espressioni Lazy
description: Informazioni su come F# espressioni differite possono migliorare le prestazioni delle App e librerie.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904111"
---
# <a name="lazy-expressions"></a><span data-ttu-id="3dbee-103">Espressioni Lazy</span><span class="sxs-lookup"><span data-stu-id="3dbee-103">Lazy Expressions</span></span>

<span data-ttu-id="3dbee-104">*Le espressioni lazy* sono espressioni che non vengono eseguite immediatamente, ma solo quando il risultato è necessaria.</span><span class="sxs-lookup"><span data-stu-id="3dbee-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="3dbee-105">Questo può contribuire a migliorare le prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="3dbee-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="3dbee-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dbee-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="3dbee-107">Note</span><span class="sxs-lookup"><span data-stu-id="3dbee-107">Remarks</span></span>

<span data-ttu-id="3dbee-108">Nella sintassi precedente *espressione* è il codice che viene valutato solo quando è necessario, un risultato e *identificatore* è un valore che archivia il risultato.</span><span class="sxs-lookup"><span data-stu-id="3dbee-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="3dbee-109">Il valore è di tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in cui il tipo effettivo che viene usato per `'T` è determinato dal risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="3dbee-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="3dbee-110">Le espressioni lazy consentono di migliorare le prestazioni, limitando l'esecuzione di un espressioni solo tali situazioni in cui è necessario un risultato.</span><span class="sxs-lookup"><span data-stu-id="3dbee-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="3dbee-111">Per forzare le espressioni deve essere eseguita, si chiama il metodo `Force`.</span><span class="sxs-lookup"><span data-stu-id="3dbee-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="3dbee-112">`Force` Determina l'esecuzione deve essere eseguita solo una volta.</span><span class="sxs-lookup"><span data-stu-id="3dbee-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="3dbee-113">Le chiamate successive a `Force` restituiscono lo stesso risultato, ma non eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="3dbee-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="3dbee-114">Il codice seguente illustra l'uso delle espressioni lazy e l'utilizzo di `Force`.</span><span class="sxs-lookup"><span data-stu-id="3dbee-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="3dbee-115">In questo codice, il tipo di `result` viene `Lazy<int>`e il `Force` metodo restituisce un `int`.</span><span class="sxs-lookup"><span data-stu-id="3dbee-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="3dbee-116">Valutazione lenta, ma non la `Lazy` digitare, viene usato anche per le sequenze.</span><span class="sxs-lookup"><span data-stu-id="3dbee-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="3dbee-117">Per altre informazioni, vedere [sequenze](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="3dbee-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3dbee-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dbee-118">See also</span></span>

- [<span data-ttu-id="3dbee-119">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="3dbee-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3dbee-120">LazyExtensions (modulo)</span><span class="sxs-lookup"><span data-stu-id="3dbee-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
