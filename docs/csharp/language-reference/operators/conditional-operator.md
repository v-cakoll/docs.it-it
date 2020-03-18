---
title: 'Operatore ?: - Riferimenti per C#'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1a17ba092d4228ba909c8774a2f7e15c2c50cfdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399518"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ee4f1-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ee4f1-102">?: operator (C# reference)</span></span>

<span data-ttu-id="ee4f1-103">L'operatore `?:`condizionale , noto anche come operatore condizionale ternario, valuta un'espressione booleana e restituisce `true` `false`il risultato di una delle due espressioni, a seconda che l'espressione booleana restituisca o .</span><span class="sxs-lookup"><span data-stu-id="ee4f1-103">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="ee4f1-104">La sintassi dell'operatore condizionale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-104">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="ee4f1-105">L'espressione `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-105">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="ee4f1-106">Se `condition` restituisce `true`, viene valutata l'espressione `consequent` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-106">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="ee4f1-107">Se `condition` restituisce `false`, viene valutata l'espressione `alternative` e il suo risultato diventa il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-107">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="ee4f1-108">Viene valutata solo `consequent` o solo `alternative`.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-108">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="ee4f1-109">Il tipo di `consequent` e `alternative` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-109">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="ee4f1-110">L'operatore condizionale si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="ee4f1-110">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="ee4f1-111">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="ee4f1-111">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="ee4f1-112">Un modo per ricordarsi che cosa restituisce questo operatore è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-112">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="ee4f1-113">L'esempio seguente illustra l'uso dell'operatore condizionale:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="ee4f1-114">Espressione condizionale ref</span><span class="sxs-lookup"><span data-stu-id="ee4f1-114">Conditional ref expression</span></span>

<span data-ttu-id="ee4f1-115">A partire dalla versione 7.2, una variabile locale [ref](../keywords/ref.md#ref-locals) o [ref readonly](../keywords/ref.md#ref-readonly-locals) può essere assegnata in modo condizionale con l'espressione di riferimento condizionale.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-115">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="ee4f1-116">È inoltre possibile utilizzare l'espressione di riferimento condizionale come [valore restituito](../keywords/ref.md#reference-return-values) di riferimento o come argomento del [ `ref` metodo](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="ee4f1-116">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="ee4f1-117">La sintassi dell'espressione condizionale ref è la seguente:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="ee4f1-118">Come l'operatore condizionale originale, l'espressione condizionale ref valuta solo una delle due espressioni: `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="ee4f1-119">Nel caso dell'espressione condizionale ref, il tipo di `consequent` e `alternative` deve coincidere.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-119">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="ee4f1-120">L'esempio seguente illustra l'uso dell'espressione condizionale ref:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="ee4f1-121">Operatore condizionale e istruzione `if..else`</span><span class="sxs-lookup"><span data-stu-id="ee4f1-121">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="ee4f1-122">L'uso dell'operatore condizionale invece di un'istruzione [if-else](../keywords/if-else.md) potrebbe comportare codice più conciso nei casi in cui è necessario in modo condizionale calcolare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-122">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="ee4f1-123">L'esempio seguente illustra due modi di classificare un intero come negativo o non negativo:</span><span class="sxs-lookup"><span data-stu-id="ee4f1-123">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="ee4f1-124">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="ee4f1-124">Operator overloadability</span></span>

<span data-ttu-id="ee4f1-125">Un tipo definito dall'utente non può eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="ee4f1-125">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ee4f1-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ee4f1-126">C# language specification</span></span>

<span data-ttu-id="ee4f1-127">Per altre informazioni, vedere la sezione [Operatore condizionale](~/_csharplang/spec/expressions.md#conditional-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ee4f1-127">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="ee4f1-128">Per ulteriori informazioni sull'espressione di riferimento condizionale, vedere la [nota](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)della proposta di feature .</span><span class="sxs-lookup"><span data-stu-id="ee4f1-128">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee4f1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4f1-129">See also</span></span>

- [<span data-ttu-id="ee4f1-130">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="ee4f1-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ee4f1-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="ee4f1-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="ee4f1-132">Istruzione if-else</span><span class="sxs-lookup"><span data-stu-id="ee4f1-132">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="ee4f1-133">[?. E? [] operatori](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="ee4f1-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="ee4f1-134">?? E?? Operatori di operatore</span><span class="sxs-lookup"><span data-stu-id="ee4f1-134">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="ee4f1-135">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="ee4f1-135">ref keyword</span></span>](../keywords/ref.md)
