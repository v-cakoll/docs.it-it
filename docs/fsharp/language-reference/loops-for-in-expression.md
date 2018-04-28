---
title: 'Cicli: espressioni for...in (F#)'
description: "Vedere come il ciclo for di F #... nell'espressione costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: eaf0f4fc6419d8e0bff46795120ee5e42c4efe1d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forin-expression"></a><span data-ttu-id="8e78b-103">Espressione Loops: for...in</span><span class="sxs-lookup"><span data-stu-id="8e78b-103">Loops: for...in Expression</span></span>

<span data-ttu-id="8e78b-104">Questo costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile, ad esempio un'espressione di intervallo, sequenza, elenco, matrice o un altro costrutto che supporta l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="8e78b-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="8e78b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e78b-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="8e78b-106">Note</span><span class="sxs-lookup"><span data-stu-id="8e78b-106">Remarks</span></span>
<span data-ttu-id="8e78b-107">Il `for...in` espressione può essere confrontata con il `for each` istruzione in altri linguaggi .NET perché è utilizzato per eseguire il ciclo i valori di una raccolta enumerabile.</span><span class="sxs-lookup"><span data-stu-id="8e78b-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="8e78b-108">Tuttavia, `for...in` supporta anche i criteri di ricerca della raccolta anziché solo l'iterazione nell'intera raccolta.</span><span class="sxs-lookup"><span data-stu-id="8e78b-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="8e78b-109">L'espressione enumerabile può essere specificata come una raccolta enumerabile o, tramite il `..` (operatore), come un intervallo in un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="8e78b-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="8e78b-110">Raccolte enumerabili includono elenchi, sequenze, matrici, set, mappe e così via.</span><span class="sxs-lookup"><span data-stu-id="8e78b-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="8e78b-111">Qualsiasi tipo che implementa `System.Collections.IEnumerable` può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8e78b-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="8e78b-112">Quando si esprime un intervallo mediante la `..` operatore, è possibile utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="8e78b-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="8e78b-113">*Avviare* ...</span><span class="sxs-lookup"><span data-stu-id="8e78b-113">*start* ..</span></span> <span data-ttu-id="8e78b-114">*Fine*</span><span class="sxs-lookup"><span data-stu-id="8e78b-114">*finish*</span></span>

<span data-ttu-id="8e78b-115">È inoltre possibile utilizzare una versione che include un incremento, detto di *ignorare*, come nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="8e78b-116">*Avviare* ...</span><span class="sxs-lookup"><span data-stu-id="8e78b-116">*start* ..</span></span> <span data-ttu-id="8e78b-117">*ignorare* ...</span><span class="sxs-lookup"><span data-stu-id="8e78b-117">*skip* ..</span></span> <span data-ttu-id="8e78b-118">*Fine*</span><span class="sxs-lookup"><span data-stu-id="8e78b-118">*finish*</span></span>

<span data-ttu-id="8e78b-119">Quando si utilizza intervalli integrali e a una variabile contatore semplice come modello, il comportamento tipico consiste nell'incrementare la variabile contatore di 1 a ogni iterazione, ma se l'intervallo include un valore di salto, il contatore viene incrementato invece del valore di salto.</span><span class="sxs-lookup"><span data-stu-id="8e78b-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="8e78b-120">I valori corrispondenti nel modello utilizzabile anche nell'espressione del corpo.</span><span class="sxs-lookup"><span data-stu-id="8e78b-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="8e78b-121">Gli esempi di codice seguente viene illustrato l'utilizzo del `for...in` espressione.</span><span class="sxs-lookup"><span data-stu-id="8e78b-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="8e78b-122">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="8e78b-123">Nell'esempio seguente viene illustrato come eseguire un ciclo in una sequenza e come usare un tupla (modello) anziché una variabile semplice.</span><span class="sxs-lookup"><span data-stu-id="8e78b-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="8e78b-124">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="8e78b-125">Nell'esempio seguente viene illustrato come eseguire un ciclo su un intervallo di numeri interi semplice.</span><span class="sxs-lookup"><span data-stu-id="8e78b-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="8e78b-126">L'output di function1 è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="8e78b-127">Nell'esempio seguente viene illustrato come eseguire un ciclo su un intervallo con un skip 2, che include ogni altro elemento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="8e78b-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="8e78b-128">L'output di `function2` è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="8e78b-129">Nell'esempio seguente viene illustrato come utilizzare un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="8e78b-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="8e78b-130">L'output di `function3` è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="8e78b-131">Nell'esempio seguente viene illustrato come utilizzare un valore negativo skip per un'iterazione inversa.</span><span class="sxs-lookup"><span data-stu-id="8e78b-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="8e78b-132">L'output di `function4` è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="8e78b-133">Inizio e alla fine dell'intervallo possono anche essere espressioni, ad esempio funzioni, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8e78b-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="8e78b-134">L'output di `function5` con questo input è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="8e78b-135">Nell'esempio successivo viene illustrato l'utilizzo di un carattere jolly (_) quando l'elemento non è necessario nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="8e78b-135">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="8e78b-136">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e78b-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="8e78b-137">`Note` È possibile utilizzare `for...in` in espressioni sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `for...in` viene utilizzata l'espressione.</span><span class="sxs-lookup"><span data-stu-id="8e78b-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="8e78b-138">Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8e78b-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8e78b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e78b-139">See Also</span></span>
[<span data-ttu-id="8e78b-140">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="8e78b-140">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8e78b-141">Cicli: espressione `for...to`</span><span class="sxs-lookup"><span data-stu-id="8e78b-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="8e78b-142">Cicli: espressione `while...do`</span><span class="sxs-lookup"><span data-stu-id="8e78b-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
