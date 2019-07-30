---
title: Funzioni inline
description: Informazioni su come usare F# le funzioni inline integrate direttamente nel codice chiamante.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630674"
---
# <a name="inline-functions"></a><span data-ttu-id="7584f-103">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="7584f-103">Inline Functions</span></span>

<span data-ttu-id="7584f-104">Le *funzioni inline* sono funzioni integrate direttamente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7584f-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="7584f-105">Uso di funzioni inline</span><span class="sxs-lookup"><span data-stu-id="7584f-105">Using Inline Functions</span></span>

<span data-ttu-id="7584f-106">Quando si usano parametri di tipo statici, le funzioni parametrizzate dai parametri di tipo devono essere inline.</span><span class="sxs-lookup"><span data-stu-id="7584f-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="7584f-107">Ciò garantisce che il compilatore possa risolvere questi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="7584f-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="7584f-108">Quando si usano i normali parametri di tipo generico, non esiste alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="7584f-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="7584f-109">Oltre ad abilitare l'utilizzo di vincoli dei membri, le funzioni inline possono essere utili per l'ottimizzazione del codice.</span><span class="sxs-lookup"><span data-stu-id="7584f-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="7584f-110">Tuttavia, l'utilizzo eccessivo delle funzioni inline può causare una minore resistenza del codice alle modifiche apportate alle ottimizzazioni del compilatore e all'implementazione delle funzioni della libreria.</span><span class="sxs-lookup"><span data-stu-id="7584f-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="7584f-111">Per questo motivo, è consigliabile evitare di utilizzare le funzioni inline per l'ottimizzazione, a meno che non siano state tentate tutte le altre tecniche di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="7584f-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="7584f-112">L'esecuzione inline di una funzione o di un metodo può talvolta migliorare le prestazioni, ma questo non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="7584f-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="7584f-113">Pertanto, è necessario utilizzare anche le misurazioni delle prestazioni per verificare che l'esecuzione inline di una determinata funzione abbia effetti positivi.</span><span class="sxs-lookup"><span data-stu-id="7584f-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="7584f-114">Il `inline` modificatore può essere applicato a funzioni a livello superiore, a livello di modulo o a livello di metodo in una classe.</span><span class="sxs-lookup"><span data-stu-id="7584f-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="7584f-115">Nell'esempio di codice seguente viene illustrata una funzione inline al livello principale, un metodo di istanza inline e un metodo statico inline.</span><span class="sxs-lookup"><span data-stu-id="7584f-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="7584f-116">Funzioni inline e inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="7584f-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="7584f-117">La presenza di `inline` influiscono sull'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="7584f-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="7584f-118">Ciò è dovuto al fatto che le funzioni inline possono avere parametri di tipo risolti staticamente, mentre le funzioni non inline non possono.</span><span class="sxs-lookup"><span data-stu-id="7584f-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="7584f-119">Nell'esempio di codice riportato di seguito viene `inline` illustrato un caso in cui è utile perché si utilizza una funzione con un parametro di tipo risolto `float` in modo statico, l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="7584f-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="7584f-120">Senza il `inline` modificatore, l'inferenza del tipo impone che la funzione prenda un tipo specifico `int`, in questo caso.</span><span class="sxs-lookup"><span data-stu-id="7584f-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="7584f-121">Ma con il `inline` modificatore, la funzione viene anche dedotta per avere un parametro di tipo risolto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="7584f-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="7584f-122">Con il `inline` modificatore, il tipo viene dedotto come il seguente:</span><span class="sxs-lookup"><span data-stu-id="7584f-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="7584f-123">Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione in **float**.</span><span class="sxs-lookup"><span data-stu-id="7584f-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7584f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7584f-124">See also</span></span>

- [<span data-ttu-id="7584f-125">Funzioni</span><span class="sxs-lookup"><span data-stu-id="7584f-125">Functions</span></span>](index.md)
- [<span data-ttu-id="7584f-126">Vincoli</span><span class="sxs-lookup"><span data-stu-id="7584f-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="7584f-127">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="7584f-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
