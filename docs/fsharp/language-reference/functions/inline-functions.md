---
title: Funzioni inline (F#)
description: 'Informazioni sull''utilizzo di F # funzioni inline sono integrate direttamente nel codice chiamante.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="34110-104">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="34110-104">Inline Functions</span></span>

<span data-ttu-id="34110-105">*Funzioni inline* sono funzioni che vengono integrate direttamente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="34110-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="34110-106">Utilizzo delle funzioni Inline</span><span class="sxs-lookup"><span data-stu-id="34110-106">Using Inline Functions</span></span>
<span data-ttu-id="34110-107">Quando si utilizzano parametri di tipo statico, le funzioni che sono parametri dai parametri di tipo devono essere inline.</span><span class="sxs-lookup"><span data-stu-id="34110-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="34110-108">In questo modo si garantisce che il compilatore può risolvere questi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="34110-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="34110-109">Quando si utilizzano parametri di tipo generico normale, non è non implica tale restrizione.</span><span class="sxs-lookup"><span data-stu-id="34110-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="34110-110">Diverso da abilitare l'utilizzo di vincoli di membro, funzioni inline possono essere utili per l'ottimizzazione di codice.</span><span class="sxs-lookup"><span data-stu-id="34110-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="34110-111">Tuttavia, utilizzo eccessivo di funzioni inline può provocare il codice meno resistente alle modifiche apportate alle ottimizzazioni del compilatore e l'implementazione di funzioni della libreria.</span><span class="sxs-lookup"><span data-stu-id="34110-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="34110-112">Per questo motivo, è consigliabile non utilizzare le funzioni inline per l'ottimizzazione a meno che non si sono tentato di altre tecniche di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="34110-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="34110-113">Rendere inline una funzione o metodo talvolta possono migliorare le prestazioni, ma non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="34110-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="34110-114">Pertanto, si devono usare anche le misurazioni delle prestazioni per verificare che effettua una funzione inline in realtà hanno un effetto positivo.</span><span class="sxs-lookup"><span data-stu-id="34110-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="34110-115">Il `inline` modificatore può essere applicato a funzioni al livello superiore, a livello di modulo o a livello di metodo in una classe.</span><span class="sxs-lookup"><span data-stu-id="34110-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="34110-116">Esempio di codice seguente viene illustrata una funzione inline a livello superiore, un metodo di istanza inline e un metodo statico inline.</span><span class="sxs-lookup"><span data-stu-id="34110-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="34110-117">Funzioni inline e l'inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="34110-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="34110-118">La presenza di `inline` interessa l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="34110-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="34110-119">Infatti, funzioni inline possono avere risolti staticamente parametri di tipo, mentre non le funzioni non inline.</span><span class="sxs-lookup"><span data-stu-id="34110-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="34110-120">Esempio di codice seguente viene illustrato un caso in cui `inline` è utile perché si sta usando una funzione che ha un parametro di tipo risolti staticamente il `float` operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="34110-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="34110-121">Senza il `inline` modificatore, l'inferenza del tipo impone la funzione per accettare un tipo specifico, in questo caso `int`.</span><span class="sxs-lookup"><span data-stu-id="34110-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="34110-122">Ma con il `inline` modificatore, la funzione viene dedotto anche avere un parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="34110-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="34110-123">Con il `inline` modificatore, il tipo viene dedotto come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="34110-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="34110-124">Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione **float**.</span><span class="sxs-lookup"><span data-stu-id="34110-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="34110-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34110-125">See Also</span></span>
[<span data-ttu-id="34110-126">Funzioni</span><span class="sxs-lookup"><span data-stu-id="34110-126">Functions</span></span>](index.md)

[<span data-ttu-id="34110-127">Vincoli</span><span class="sxs-lookup"><span data-stu-id="34110-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="34110-128">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="34110-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
