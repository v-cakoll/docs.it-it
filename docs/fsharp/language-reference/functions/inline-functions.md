---
title: Funzioni inline (F#)
description: "Informazioni sull'utilizzo di F # funzioni inline sono integrate direttamente nel codice chiamante."
ms.date: 05/16/2016
ms.openlocfilehash: d265f9b4e828946c510bd8e84b14d5236ab511fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563508"
---
# <a name="inline-functions"></a><span data-ttu-id="acd16-103">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="acd16-103">Inline Functions</span></span>

<span data-ttu-id="acd16-104">*Funzioni inline* sono funzioni che sono integrate direttamente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="acd16-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="acd16-105">Utilizzo delle funzioni Inline</span><span class="sxs-lookup"><span data-stu-id="acd16-105">Using Inline Functions</span></span>
<span data-ttu-id="acd16-106">Quando si utilizzano parametri di tipo statico, le funzioni che sono parametri dai parametri di tipo devono essere inline.</span><span class="sxs-lookup"><span data-stu-id="acd16-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="acd16-107">In questo modo si garantisce che il compilatore può risolvere questi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="acd16-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="acd16-108">Quando si utilizzano parametri di tipo generico normale, non è non implica tale restrizione.</span><span class="sxs-lookup"><span data-stu-id="acd16-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="acd16-109">Diverso da abilitare l'utilizzo di vincoli di membro, funzioni inline possono essere utili per l'ottimizzazione di codice.</span><span class="sxs-lookup"><span data-stu-id="acd16-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="acd16-110">Tuttavia, utilizzo eccessivo di funzioni inline può provocare il codice meno resistente alle modifiche apportate alle ottimizzazioni del compilatore e l'implementazione di funzioni della libreria.</span><span class="sxs-lookup"><span data-stu-id="acd16-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="acd16-111">Per questo motivo, è consigliabile non utilizzare le funzioni inline per l'ottimizzazione a meno che non si sono tentato di altre tecniche di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="acd16-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="acd16-112">Rendere inline una funzione o metodo talvolta possono migliorare le prestazioni, ma non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="acd16-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="acd16-113">Pertanto, si devono usare anche le misurazioni delle prestazioni per verificare che effettua una funzione inline in realtà hanno un effetto positivo.</span><span class="sxs-lookup"><span data-stu-id="acd16-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="acd16-114">Il `inline` modificatore può essere applicato a funzioni al livello superiore, a livello di modulo o a livello di metodo in una classe.</span><span class="sxs-lookup"><span data-stu-id="acd16-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="acd16-115">Esempio di codice seguente viene illustrata una funzione inline a livello superiore, un metodo di istanza inline e un metodo statico inline.</span><span class="sxs-lookup"><span data-stu-id="acd16-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="acd16-116">Funzioni inline e l'inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="acd16-116">Inline Functions and Type Inference</span></span>
<span data-ttu-id="acd16-117">La presenza di `inline` interessa l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="acd16-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="acd16-118">Infatti, funzioni inline possono avere risolti staticamente parametri di tipo, mentre non le funzioni non inline.</span><span class="sxs-lookup"><span data-stu-id="acd16-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="acd16-119">Esempio di codice seguente viene illustrato un caso in cui `inline` è utile perché si sta usando una funzione che ha un parametro di tipo risolti staticamente il `float` operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="acd16-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="acd16-120">Senza il `inline` modificatore, l'inferenza del tipo impone la funzione per accettare un tipo specifico, in questo caso `int`.</span><span class="sxs-lookup"><span data-stu-id="acd16-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="acd16-121">Ma con il `inline` modificatore, la funzione viene dedotto anche avere un parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="acd16-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="acd16-122">Con il `inline` modificatore, il tipo viene dedotto come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="acd16-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="acd16-123">Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione **float**.</span><span class="sxs-lookup"><span data-stu-id="acd16-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="acd16-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acd16-124">See Also</span></span>
[<span data-ttu-id="acd16-125">Funzioni</span><span class="sxs-lookup"><span data-stu-id="acd16-125">Functions</span></span>](index.md)

[<span data-ttu-id="acd16-126">Vincoli</span><span class="sxs-lookup"><span data-stu-id="acd16-126">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="acd16-127">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="acd16-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
