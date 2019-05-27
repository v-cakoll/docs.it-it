---
title: '?: operatore - Riferimenti per C#'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: a40dd4addfaf8a505cf334876192f0b2ccf66a09
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452408"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e56cd-102">?: Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e56cd-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="e56cd-103">L'operatore condizionale `?:`, comunemente noto come operatore condizionale ternario, valuta un'espressione booleana e restituisce il risultato della valutazione di una di due espressioni, a seconda che l'espressione booleana restituisca `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e56cd-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="e56cd-104">A partire da C# 7.2, l'[espressione condizionale ref](#conditional-ref-expression) restituisce il riferimento al risultato di una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e56cd-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="e56cd-105">La sintassi dell'operatore condizionale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e56cd-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="e56cd-106">L'espressione `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e56cd-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="e56cd-107">Se `condition` restituisce `true`, viene valutata l'espressione `consequent` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e56cd-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="e56cd-108">Se `condition` restituisce `false`, viene valutata l'espressione `alternative` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e56cd-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="e56cd-109">Viene valutata solo `consequent` o solo `alternative`.</span><span class="sxs-lookup"><span data-stu-id="e56cd-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="e56cd-110">Il tipo di `consequent` e `alternative` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro.</span><span class="sxs-lookup"><span data-stu-id="e56cd-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="e56cd-111">L'operatore condizionale si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="e56cd-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="e56cd-112">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="e56cd-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="e56cd-113">Un modo per ricordarsi come funziona questo operatore consiste nel porsi questa domanda:</span><span class="sxs-lookup"><span data-stu-id="e56cd-113">A mnemonic device you can use to remember how this operator evaluates is to ask:</span></span>

```text
is this condition true ? yes : no
```

<span data-ttu-id="e56cd-114">dove la parte ?</span><span class="sxs-lookup"><span data-stu-id="e56cd-114">with the ?</span></span> <span data-ttu-id="e56cd-115">dell'operatore funge da punto interrogativo per l'affermazione precedente e la parte successiva da risposta logica alla domanda.</span><span class="sxs-lookup"><span data-stu-id="e56cd-115">part of the operator acting as a question mark for the previous statement, and the consequent acting as the logical response to this question.</span></span>

<span data-ttu-id="e56cd-116">L'esempio seguente illustra l'uso dell'operatore condizionale:</span><span class="sxs-lookup"><span data-stu-id="e56cd-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="e56cd-117">Espressione condizionale ref</span><span class="sxs-lookup"><span data-stu-id="e56cd-117">Conditional ref expression</span></span>

<span data-ttu-id="e56cd-118">A partire da C# 7.2, è possibile usare l'espressione condizionale ref per restituire il riferimento al risultato di una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e56cd-118">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="e56cd-119">È possibile assegnare tale riferimento a una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals) oppure usarlo come [valore restituito di riferimento](../keywords/ref.md#reference-return-values) o come [parametro del metodo `ref`](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="e56cd-119">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="e56cd-120">La sintassi dell'espressione condizionale ref è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e56cd-120">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="e56cd-121">Come l'operatore condizionale originale, l'espressione condizionale ref valuta solo una delle due espressioni: `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="e56cd-121">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="e56cd-122">Nel caso dell'espressione condizionale ref, il tipo di `consequent` e `alternative` deve coincidere.</span><span class="sxs-lookup"><span data-stu-id="e56cd-122">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="e56cd-123">L'esempio seguente illustra l'uso dell'espressione condizionale ref:</span><span class="sxs-lookup"><span data-stu-id="e56cd-123">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="e56cd-124">Per altre informazioni, vedere la [nota relativa alla proposta di funzionalità](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="e56cd-124">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="e56cd-125">Operatore condizionale e istruzione `if..else`</span><span class="sxs-lookup"><span data-stu-id="e56cd-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="e56cd-126">L'uso dell'operatore condizionale su un'istruzione [if-else](../keywords/if-else.md) potrebbe generare codice più conciso nel casi in cui occorre calcolare un valore in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="e56cd-126">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="e56cd-127">L'esempio seguente illustra due modi di classificare un intero come negativo o non negativo:</span><span class="sxs-lookup"><span data-stu-id="e56cd-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="e56cd-128">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="e56cd-128">Operator overloadability</span></span>

<span data-ttu-id="e56cd-129">Non è possibile eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="e56cd-129">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e56cd-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e56cd-130">C# language specification</span></span>

<span data-ttu-id="e56cd-131">Per altre informazioni, vedere la sezione [Operatore condizionale](~/_csharplang/spec/expressions.md#conditional-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e56cd-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e56cd-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e56cd-132">See also</span></span>

- [<span data-ttu-id="e56cd-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e56cd-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e56cd-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e56cd-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e56cd-135">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="e56cd-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="e56cd-136">Istruzione if-else</span><span class="sxs-lookup"><span data-stu-id="e56cd-136">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="e56cd-137">[Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="e56cd-137">[?. and ?[] Operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="e56cd-138">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="e56cd-138">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="e56cd-139">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="e56cd-139">ref keyword</span></span>](../keywords/ref.md)
