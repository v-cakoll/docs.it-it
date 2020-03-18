---
title: '- Operatori - e -= - Riferimenti per C#'
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 2017aade92e8d7ad2af7101a107122fa8d7b9e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847651"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="558e3-102">Operatori - e -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="558e3-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="558e3-103">Gli `-` `-=` operatori e sono supportati dai tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile](../builtin-types/floating-point-numeric-types.md) incorporati e dai tipi [delegati.](../builtin-types/reference-types.md#the-delegate-type)</span><span class="sxs-lookup"><span data-stu-id="558e3-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="558e3-104">Per informazioni sull'operatore aritmetico `-`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di sottrazione -](arithmetic-operators.md#subtraction-operator--) dell'articolo [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="558e3-105">Rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="558e3-105">Delegate removal</span></span>

<span data-ttu-id="558e3-106">Per gli operandi dello stesso tipo [delegato](../builtin-types/reference-types.md#the-delegate-type), l'operatore `-` restituisce un'istanza di delegato che viene calcolata come segue:</span><span class="sxs-lookup"><span data-stu-id="558e3-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="558e3-107">Se entrambi gli operandi sono diversi da Null e l'elenco chiamate dell'operando di destra è un sottoelenco contiguo dell'elenco chiamate dell'operando di sinistra, il risultato dell'operazione è un nuovo elenco chiamate ottenuto rimuovendo le voci dell'operando di destra dall'elenco di chiamate dell'operando di sinistra.</span><span class="sxs-lookup"><span data-stu-id="558e3-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="558e3-108">Se l'elenco dell'operando di destra corrisponde a più sottoelenchi contigui nell'elenco dell'operando di sinistra, viene rimosso solo il sottoelenco corrispondente più a destra.</span><span class="sxs-lookup"><span data-stu-id="558e3-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="558e3-109">Se la rimozione restituisce un elenco vuoto, il risultato è `null`.</span><span class="sxs-lookup"><span data-stu-id="558e3-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](snippets/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="558e3-110">Se l'elenco chiamate dell'operando di destra non è un sottoelenco contiguo dell'elenco chiamate dell'operando di sinistra, il risultato dell'operazione è l'operando di sinistra.</span><span class="sxs-lookup"><span data-stu-id="558e3-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="558e3-111">La rimozione di un delegato che non fa parte del delegato multicast, ad esempio, non produce alcun risultato e il delegato multicast rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="558e3-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](snippets/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="558e3-112">L'esempio precedente dimostra anche che, durante la rimozione del delegato, vengono confrontate le istanze del delegato.</span><span class="sxs-lookup"><span data-stu-id="558e3-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="558e3-113">I delegati prodotti dalla valutazione di [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) identiche, ad esempio, non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="558e3-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="558e3-114">Per altre informazioni sull'uguaglianza dei delegati, vedere la sezione [Delegare gli operatori di uguaglianza](~/_csharplang/spec/expressions.md#delegate-equality-operators) dell'articolo [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="558e3-115">Se l'operando di sinistra è `null`, il risultato dell'operazione è `null`.</span><span class="sxs-lookup"><span data-stu-id="558e3-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="558e3-116">Se l'operando di destra è `null`, il risultato dell'operazione è l'operando di sinistra.</span><span class="sxs-lookup"><span data-stu-id="558e3-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](snippets/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="558e3-117">Per combinare i delegati, utilizzare [ `+` l'operatore](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="558e3-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="558e3-118">Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="558e3-119">Operatore di assegnazione di sottrazione -=</span><span class="sxs-lookup"><span data-stu-id="558e3-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="558e3-120">Un'espressione che usa l'operatore `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="558e3-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="558e3-121">equivale a</span><span class="sxs-lookup"><span data-stu-id="558e3-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="558e3-122">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="558e3-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="558e3-123">Nell'esempio seguente viene illustrato l'uso dell'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="558e3-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](snippets/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="558e3-124">È anche possibile usare l'operatore `-=` per specificare un metodo del gestore eventi quando si elimina la sottoscrizione a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="558e3-125">Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-125">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="558e3-126">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="558e3-126">Operator overloadability</span></span>

<span data-ttu-id="558e3-127">Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) dell'operatore `-`.</span><span class="sxs-lookup"><span data-stu-id="558e3-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="558e3-128">Quando viene eseguito l'overload di un operatore `-` binario, viene eseguito in modo implicito anche l'overload dell'operatore `-=`.</span><span class="sxs-lookup"><span data-stu-id="558e3-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="558e3-129">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `-=` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="558e3-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="558e3-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="558e3-130">C# language specification</span></span>

<span data-ttu-id="558e3-131">Per altre informazioni, vedere le sezioni [Operatore meno unario](~/_csharplang/spec/expressions.md#unary-minus-operator) e [Operatore di sottrazione](~/_csharplang/spec/expressions.md#subtraction-operator) di [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="558e3-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="558e3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="558e3-132">See also</span></span>

- [<span data-ttu-id="558e3-133">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="558e3-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="558e3-134">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="558e3-134">C# operators</span></span>](index.md)
- [<span data-ttu-id="558e3-135">Events</span><span class="sxs-lookup"><span data-stu-id="558e3-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="558e3-136">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="558e3-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="558e3-137">Operatori + e +=</span><span class="sxs-lookup"><span data-stu-id="558e3-137">+ and += operators</span></span>](addition-operator.md)
