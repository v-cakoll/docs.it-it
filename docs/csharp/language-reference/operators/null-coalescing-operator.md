---
title: ?? \- operatore - Riferimenti per C#
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816016"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="32e3a-103">??</span><span class="sxs-lookup"><span data-stu-id="32e3a-103">??</span></span> <span data-ttu-id="32e3a-104">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="32e3a-104">operator (C# Reference)</span></span>

<span data-ttu-id="32e3a-105">L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="32e3a-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="32e3a-106">L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.</span><span class="sxs-lookup"><span data-stu-id="32e3a-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="32e3a-107">L'operatore null-coalescing si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="32e3a-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="32e3a-108">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="32e3a-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="32e3a-109">L'operatore `??` può essere utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="32e3a-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="32e3a-110">Nelle espressioni con gli [operatori condizionali null ?. e ?[]](member-access-operators.md#null-conditional-operators--and-), è possibile usare l'operatore null-coalescing per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione con operazioni condizionali Null sia `null`:</span><span class="sxs-lookup"><span data-stu-id="32e3a-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="32e3a-111">Se si usano [tipi di valori nullable](../../programming-guide/nullable-types/index.md) e si deve specificare un valore di un tipo sottostante, usare l'operatore null-coalescing per specificare il valore da fornire nel caso in cui un valore di tipo nullable sia `null`:</span><span class="sxs-lookup"><span data-stu-id="32e3a-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="32e3a-112">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="32e3a-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="32e3a-113">A partire da C# 7.0, è possibile usare un'[espressione `throw`](../keywords/throw.md#the-throw-expression) come operando destro dell'operatore null-coalescing per rendere più conciso il codice il controllo degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="32e3a-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="32e3a-114">L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.</span><span class="sxs-lookup"><span data-stu-id="32e3a-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="32e3a-115">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="32e3a-115">Operator overloadability</span></span>

<span data-ttu-id="32e3a-116">Non è possibile sottoporre a overload l'operatore null-coalescing.</span><span class="sxs-lookup"><span data-stu-id="32e3a-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="32e3a-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="32e3a-117">C# language specification</span></span>

<span data-ttu-id="32e3a-118">Per altre informazioni, vedere la sezione [ null coalescing](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="32e3a-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32e3a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e3a-119">See also</span></span>

- [<span data-ttu-id="32e3a-120">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="32e3a-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="32e3a-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="32e3a-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32e3a-122">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="32e3a-122">C# operators</span></span>](index.md)
- <span data-ttu-id="32e3a-123">[Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="32e3a-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="32e3a-124">Operatore ?:</span><span class="sxs-lookup"><span data-stu-id="32e3a-124">?: operator</span></span>](conditional-operator.md)
