---
title: '- Operatori - e -= (Riferimenti per C#)'
ms.custom: seodec18
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
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816077"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="3c768-102">Operatori - e -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3c768-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="3c768-103">L'operatore `-` è supportato dai tipi numerici predefiniti e i tipi [delegato](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="3c768-104">Per informazioni sull'operatore aritmetico `-`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di sottrazione -](arithmetic-operators.md#subtraction-operator--) dell'articolo [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="3c768-105">Rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="3c768-105">Delegate removal</span></span>

<span data-ttu-id="3c768-106">Per gli operandi dello stesso tipo [delegato](../keywords/delegate.md), l'operatore `-` restituisce un'istanza di delegato che viene calcolata come segue:</span><span class="sxs-lookup"><span data-stu-id="3c768-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="3c768-107">Se entrambi gli operandi sono diversi da Null e l'elenco chiamate del secondo operando è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è un nuovo elenco chiamate ottenuto rimuovendo le voci del secondo operando dall'elenco di chiamate del primo operando.</span><span class="sxs-lookup"><span data-stu-id="3c768-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="3c768-108">Se l'elenco del secondo operando corrisponde a più sottoelenchi contigui nell'elenco del primo operando, viene rimosso solo il sottoelenco corrispondente più a destra.</span><span class="sxs-lookup"><span data-stu-id="3c768-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="3c768-109">Se la rimozione restituisce un elenco vuoto, il risultato è `null`.</span><span class="sxs-lookup"><span data-stu-id="3c768-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="3c768-110">Se l'elenco chiamate del secondo operando non è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è il primo operando.</span><span class="sxs-lookup"><span data-stu-id="3c768-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span> <span data-ttu-id="3c768-111">Ad esempio, la rimozione di un delegato che non fa parte del delegato multicast non esegue alcuna operazione e restituisce il delegato multicast invariato.</span><span class="sxs-lookup"><span data-stu-id="3c768-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="3c768-112">L'esempio precedente dimostra anche che, durante il delegato vengono confrontate le istanze dei delegati per la rimozione.</span><span class="sxs-lookup"><span data-stu-id="3c768-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="3c768-113">Ad esempio, i delegati che sono state prodotte dalla versione di valutazione di identici [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="3c768-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="3c768-114">Per altre informazioni sull'uguaglianza di delegato, vedere la [delegare gli operatori di uguaglianza](~/_csharplang/spec/expressions.md#delegate-equality-operators) sezione il [ C# specifica del linguaggio](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

- <span data-ttu-id="3c768-115">Se il primo operando è `null`, il risultato dell'operazione è `null`.</span><span class="sxs-lookup"><span data-stu-id="3c768-115">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="3c768-116">Se il secondo operando è `null`, il risultato dell'operazione è il primo operando.</span><span class="sxs-lookup"><span data-stu-id="3c768-116">If the second operand is `null`, the result of the operation is the first operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="3c768-117">Per combinare i delegati, usare il [ `+` operatore](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="3c768-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="3c768-118">Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="3c768-119">Operatore di assegnazione di sottrazione -=</span><span class="sxs-lookup"><span data-stu-id="3c768-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="3c768-120">Un'espressione che usa l'operatore `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="3c768-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="3c768-121">equivale a</span><span class="sxs-lookup"><span data-stu-id="3c768-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="3c768-122">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="3c768-122">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="3c768-123">Nell'esempio seguente viene illustrato l'uso dell'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="3c768-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="3c768-124">È anche possibile usare l'operatore `-=` per specificare un metodo del gestore eventi quando si elimina la sottoscrizione a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="3c768-125">Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-125">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3c768-126">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="3c768-126">Operator overloadability</span></span>

<span data-ttu-id="3c768-127">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) dell'operatore `-`.</span><span class="sxs-lookup"><span data-stu-id="3c768-127">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="3c768-128">Quando viene eseguito l'overload di un operatore `-` binario, viene eseguito in modo implicito anche l'overload dell'operatore `-=`.</span><span class="sxs-lookup"><span data-stu-id="3c768-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="3c768-129">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `-=` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3c768-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3c768-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3c768-130">C# language specification</span></span>

<span data-ttu-id="3c768-131">Per altre informazioni, vedere le sezioni [Operatore meno unario](~/_csharplang/spec/expressions.md#unary-minus-operator) e [Operatore di sottrazione](~/_csharplang/spec/expressions.md#subtraction-operator) di [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c768-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c768-132">See also</span></span>

- [<span data-ttu-id="3c768-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3c768-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3c768-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3c768-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3c768-135">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3c768-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3c768-136">Delegati</span><span class="sxs-lookup"><span data-stu-id="3c768-136">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="3c768-137">Eventi</span><span class="sxs-lookup"><span data-stu-id="3c768-137">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="3c768-138">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="3c768-138">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="3c768-139">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="3c768-139">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="3c768-140">Operatori + e +=</span><span class="sxs-lookup"><span data-stu-id="3c768-140">+ and += operators</span></span>](addition-operator.md)
