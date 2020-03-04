---
title: 'Operatore ?: - Riferimenti per C#'
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 6e8fde8c210b2c33cc514167be7face657cbb618
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239379"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="15ff4-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="15ff4-102">?: operator (C# reference)</span></span>

<span data-ttu-id="15ff4-103">L'operatore condizionale `?:`, noto anche come operatore condizionale ternario, valuta un'espressione booleana e restituisce il risultato di una delle due espressioni, a seconda che l'espressione booleana restituisca `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="15ff4-103">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="15ff4-104">A partire da C# 7.2, l'[espressione condizionale ref](#conditional-ref-expression) restituisce il riferimento al risultato di una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="15ff4-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="15ff4-105">La sintassi dell'operatore condizionale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="15ff4-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="15ff4-106">L'espressione `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="15ff4-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="15ff4-107">Se `condition` restituisce `true`, viene valutata l'espressione `consequent` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="15ff4-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="15ff4-108">Se `condition` restituisce `false`, viene valutata l'espressione `alternative` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="15ff4-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="15ff4-109">Viene valutata solo `consequent` o solo `alternative`.</span><span class="sxs-lookup"><span data-stu-id="15ff4-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="15ff4-110">Il tipo di `consequent` e `alternative` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro.</span><span class="sxs-lookup"><span data-stu-id="15ff4-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="15ff4-111">L'operatore condizionale si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="15ff4-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="15ff4-112">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="15ff4-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="15ff4-113">Un modo per ricordarsi che cosa restituisce questo operatore è il seguente:</span><span class="sxs-lookup"><span data-stu-id="15ff4-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="15ff4-114">L'esempio seguente illustra l'uso dell'operatore condizionale:</span><span class="sxs-lookup"><span data-stu-id="15ff4-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="15ff4-115">Espressione condizionale ref</span><span class="sxs-lookup"><span data-stu-id="15ff4-115">Conditional ref expression</span></span>

<span data-ttu-id="15ff4-116">A partire da C# 7.2, è possibile usare l'espressione condizionale ref per restituire il riferimento al risultato di una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="15ff4-116">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="15ff4-117">È possibile assegnare tale riferimento a una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals) oppure usarlo come [valore restituito di riferimento](../keywords/ref.md#reference-return-values) o come [parametro del metodo `ref`](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="15ff4-117">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="15ff4-118">La sintassi dell'espressione condizionale ref è la seguente:</span><span class="sxs-lookup"><span data-stu-id="15ff4-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="15ff4-119">Come l'operatore condizionale originale, l'espressione condizionale ref valuta solo una delle due espressioni: `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="15ff4-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="15ff4-120">Nel caso dell'espressione condizionale ref, il tipo di `consequent` e `alternative` deve coincidere.</span><span class="sxs-lookup"><span data-stu-id="15ff4-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="15ff4-121">L'esempio seguente illustra l'uso dell'espressione condizionale ref:</span><span class="sxs-lookup"><span data-stu-id="15ff4-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="15ff4-122">Operatore condizionale e istruzione `if..else`</span><span class="sxs-lookup"><span data-stu-id="15ff4-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="15ff4-123">L'uso dell'operatore condizionale anziché di un'istruzione [if-else](../keywords/if-else.md) potrebbe produrre codice più conciso nei casi in cui è necessario calcolare un valore in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="15ff4-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="15ff4-124">L'esempio seguente illustra due modi di classificare un intero come negativo o non negativo:</span><span class="sxs-lookup"><span data-stu-id="15ff4-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="15ff4-125">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="15ff4-125">Operator overloadability</span></span>

<span data-ttu-id="15ff4-126">Un tipo definito dall'utente non può eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="15ff4-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="15ff4-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="15ff4-127">C# language specification</span></span>

<span data-ttu-id="15ff4-128">Per altre informazioni, vedere la sezione [Operatore condizionale](~/_csharplang/spec/expressions.md#conditional-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="15ff4-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="15ff4-129">Per ulteriori informazioni sull'espressione di riferimento condizionale, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="15ff4-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15ff4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15ff4-130">See also</span></span>

- [<span data-ttu-id="15ff4-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="15ff4-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="15ff4-132">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="15ff4-132">C# operators</span></span>](index.md)
- [<span data-ttu-id="15ff4-133">Istruzione if-else</span><span class="sxs-lookup"><span data-stu-id="15ff4-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="15ff4-134">[Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="15ff4-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="15ff4-135">?? e? = operatori</span><span class="sxs-lookup"><span data-stu-id="15ff4-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="15ff4-136">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="15ff4-136">ref keyword</span></span>](../keywords/ref.md)
