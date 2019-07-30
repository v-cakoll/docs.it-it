---
title: 'Espressione Loops: for...in'
description: Vedere come il F# ... nel costrutto di ciclo di espressioni viene usato per eseguire l'iterazione delle corrispondenze di un modello in una raccolta enumerabile.
ms.date: 05/16/2016
ms.openlocfilehash: 640b0f91f6c641f3b49a99dc67abe7e4c31911ea
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630723"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="a3321-103">Espressione Loops: for...in</span><span class="sxs-lookup"><span data-stu-id="a3321-103">Loops: for...in Expression</span></span>

<span data-ttu-id="a3321-104">Questo costrutto di ciclo viene usato per eseguire l'iterazione delle corrispondenze di un modello in una raccolta enumerabile, ad esempio un'espressione di intervallo, una sequenza, un elenco, una matrice o un altro costrutto che supporta l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a3321-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="a3321-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3321-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="a3321-106">Note</span><span class="sxs-lookup"><span data-stu-id="a3321-106">Remarks</span></span>

<span data-ttu-id="a3321-107">L' `for...in` espressione può essere confrontata `for each` con l'istruzione in altri linguaggi .NET perché viene utilizzata per eseguire il ciclo sui valori in una raccolta enumerabile.</span><span class="sxs-lookup"><span data-stu-id="a3321-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="a3321-108">Tuttavia, `for...in` supporta anche criteri di ricerca sulla raccolta anziché semplicemente iterazione sull'intera raccolta.</span><span class="sxs-lookup"><span data-stu-id="a3321-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="a3321-109">L'espressione enumerabile può essere specificata come raccolta enumerabile o, usando l' `..` operatore, come intervallo in un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="a3321-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="a3321-110">Le raccolte enumerabili includono elenchi, sequenze, matrici, set, mappe e così via.</span><span class="sxs-lookup"><span data-stu-id="a3321-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="a3321-111">È possibile utilizzare qualsiasi `System.Collections.IEnumerable` tipo che implementa.</span><span class="sxs-lookup"><span data-stu-id="a3321-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="a3321-112">Quando si esprime un intervallo usando l' `..` operatore, è possibile usare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="a3321-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="a3321-113">*Avvia* ...</span><span class="sxs-lookup"><span data-stu-id="a3321-113">*start* ..</span></span> <span data-ttu-id="a3321-114">*finish*</span><span class="sxs-lookup"><span data-stu-id="a3321-114">*finish*</span></span>

<span data-ttu-id="a3321-115">È anche possibile usare una versione che include un incremento denominato *Skip*, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a3321-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="a3321-116">*Avvia* ...</span><span class="sxs-lookup"><span data-stu-id="a3321-116">*start* ..</span></span> <span data-ttu-id="a3321-117">*Ignora* .</span><span class="sxs-lookup"><span data-stu-id="a3321-117">*skip* ..</span></span> <span data-ttu-id="a3321-118">*finish*</span><span class="sxs-lookup"><span data-stu-id="a3321-118">*finish*</span></span>

<span data-ttu-id="a3321-119">Quando si usano intervalli integrali e una semplice variabile contatore come modello, il comportamento tipico consiste nell'incrementare la variabile contatore di 1 per ogni iterazione, ma se l'intervallo include un valore skip, il contatore viene incrementato in base al valore skip.</span><span class="sxs-lookup"><span data-stu-id="a3321-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="a3321-120">È anche possibile usare i valori corrispondenti nel criterio nell'espressione Body.</span><span class="sxs-lookup"><span data-stu-id="a3321-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="a3321-121">Negli esempi di codice seguenti viene illustrato l'utilizzo dell' `for...in` espressione.</span><span class="sxs-lookup"><span data-stu-id="a3321-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="a3321-122">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a3321-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="a3321-123">Nell'esempio seguente viene illustrato come eseguire il ciclo su una sequenza e come utilizzare un modello di tupla anziché una variabile semplice.</span><span class="sxs-lookup"><span data-stu-id="a3321-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="a3321-124">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a3321-124">The output is as follows.</span></span>

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

<span data-ttu-id="a3321-125">Nell'esempio seguente viene illustrato come eseguire il ciclo su un intervallo di valori integer semplici.</span><span class="sxs-lookup"><span data-stu-id="a3321-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="a3321-126">L'output di funzione1 è il seguente.</span><span class="sxs-lookup"><span data-stu-id="a3321-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="a3321-127">Nell'esempio seguente viene illustrato come eseguire il ciclo su un intervallo con un valore skip di 2, che include tutti gli altri elementi dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="a3321-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="a3321-128">Di seguito è `function2` riportato l'output di.</span><span class="sxs-lookup"><span data-stu-id="a3321-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="a3321-129">Nell'esempio seguente viene illustrato come utilizzare un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="a3321-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="a3321-130">Di seguito è `function3` riportato l'output di.</span><span class="sxs-lookup"><span data-stu-id="a3321-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="a3321-131">Nell'esempio seguente viene illustrato come utilizzare un valore skip negativo per un'iterazione inversa.</span><span class="sxs-lookup"><span data-stu-id="a3321-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="a3321-132">Di seguito è `function4` riportato l'output di.</span><span class="sxs-lookup"><span data-stu-id="a3321-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="a3321-133">L'inizio e la fine dell'intervallo possono anche essere espressioni, ad esempio funzioni, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a3321-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="a3321-134">Di seguito è `function5` riportato l'output di con questo input.</span><span class="sxs-lookup"><span data-stu-id="a3321-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="a3321-135">Nell'esempio seguente viene illustrato l'utilizzo di un carattere jolly\_() quando l'elemento non è necessario nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="a3321-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="a3321-136">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a3321-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="a3321-137">`Note`È possibile utilizzare `for...in` nelle espressioni di sequenza e in altre espressioni `for...in` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="a3321-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="a3321-138">Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di calcolo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a3321-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3321-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3321-139">See also</span></span>

- [<span data-ttu-id="a3321-140">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="a3321-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a3321-141">Cicli `for...to`Espressione</span><span class="sxs-lookup"><span data-stu-id="a3321-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="a3321-142">Cicli `while...do`Espressione</span><span class="sxs-lookup"><span data-stu-id="a3321-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
