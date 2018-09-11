---
title: Funzioni inline (F#)
description: 'Informazioni su come utilizzare F # le funzioni inline che sono integrate direttamente nel codice chiamante.'
ms.date: 05/16/2016
ms.openlocfilehash: 47fca0fe34630792aeb0908b0cee02a927e2567d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264558"
---
# <a name="inline-functions"></a><span data-ttu-id="3e058-103">Funzioni inline</span><span class="sxs-lookup"><span data-stu-id="3e058-103">Inline Functions</span></span>

<span data-ttu-id="3e058-104">*Funzioni inline* sono funzioni che sono integrate direttamente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="3e058-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="3e058-105">Utilizzo delle funzioni Inline</span><span class="sxs-lookup"><span data-stu-id="3e058-105">Using Inline Functions</span></span>

<span data-ttu-id="3e058-106">Quando si usano parametri di tipo statico, qualsiasi funzione che vengono parametrizzate dai parametri di tipo devono essere inline.</span><span class="sxs-lookup"><span data-stu-id="3e058-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="3e058-107">In questo modo si garantisce che il compilatore può risolvere questi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="3e058-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="3e058-108">Quando si usano parametri di tipo generico normali, non è non implica tale restrizione.</span><span class="sxs-lookup"><span data-stu-id="3e058-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="3e058-109">Oltre che per consentire l'utilizzo di vincoli relativi ai membri, funzioni inline possono essere utili nell'ottimizzazione del codice.</span><span class="sxs-lookup"><span data-stu-id="3e058-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="3e058-110">Utilizzo eccessivo di funzioni inline, tuttavia, può causare il codice può essere meno resistente alle modifiche apportate alle ottimizzazioni del compilatore e l'implementazione delle funzioni della libreria.</span><span class="sxs-lookup"><span data-stu-id="3e058-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="3e058-111">Per questo motivo, è consigliabile evitare l'utilizzo delle funzioni inline per l'ottimizzazione a meno che non si sono provato a tutte le altre tecniche di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e058-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="3e058-112">Rendere inline una funzione o un metodo talvolta possono migliorare le prestazioni, ma non che è sempre così.</span><span class="sxs-lookup"><span data-stu-id="3e058-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="3e058-113">Pertanto, si devono inoltre utilizzare le misurazioni delle prestazioni per verificare che effettua una funzione inline in realtà hanno un effetto positivo.</span><span class="sxs-lookup"><span data-stu-id="3e058-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="3e058-114">Il `inline` modificatore può essere applicato alle funzioni di primo livello, a livello di modulo o a livello di metodo in una classe.</span><span class="sxs-lookup"><span data-stu-id="3e058-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="3e058-115">L'esempio di codice seguente illustra una funzione inline a livello superiore, un metodo di istanza inline e un metodo statico inline.</span><span class="sxs-lookup"><span data-stu-id="3e058-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="3e058-116">Le funzioni inline e l'inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="3e058-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="3e058-117">La presenza di `inline` interessa l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="3e058-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="3e058-118">Questo avviene perché le funzioni inline possono avere risolti staticamente parametri di tipo, operazione Impossibile con le funzioni non inline.</span><span class="sxs-lookup"><span data-stu-id="3e058-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="3e058-119">Esempio di codice seguente viene illustrato un caso in cui `inline` è utile perché si sta usando una funzione che ha un parametro di tipo risolti staticamente, la `float` operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="3e058-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="3e058-120">Senza il `inline` modificatore, l'inferenza del tipo impone la funzione accetti un tipo specifico, in questo caso `int`.</span><span class="sxs-lookup"><span data-stu-id="3e058-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="3e058-121">Ma con la `inline` modificatore, la funzione viene anche dedotto per avere un parametro di tipo risolti staticamente.</span><span class="sxs-lookup"><span data-stu-id="3e058-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="3e058-122">Con la `inline` modificatore, il tipo viene dedotto come quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e058-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="3e058-123">Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione **float**.</span><span class="sxs-lookup"><span data-stu-id="3e058-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e058-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e058-124">See also</span></span>

- [<span data-ttu-id="3e058-125">Funzioni</span><span class="sxs-lookup"><span data-stu-id="3e058-125">Functions</span></span>](index.md)
- [<span data-ttu-id="3e058-126">Vincoli</span><span class="sxs-lookup"><span data-stu-id="3e058-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="3e058-127">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="3e058-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
