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
ms.openlocfilehash: 9f43a863de69122e251204668af2ea989fcc993c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300081"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="d14e8-102">Operatori - e -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d14e8-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="d14e8-103">L'operatore `-` è supportato dai tipi numerici predefiniti e i tipi [delegato](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="d14e8-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="d14e8-104">Per informazioni sull'operatore aritmetico `-`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di sottrazione -](arithmetic-operators.md#subtraction-operator--) dell'articolo [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d14e8-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="d14e8-105">Rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="d14e8-105">Delegate removal</span></span>

<span data-ttu-id="d14e8-106">Per gli operandi dello stesso tipo [delegato](../keywords/delegate.md), l'operatore `-` restituisce un'istanza di delegato che viene calcolata come segue:</span><span class="sxs-lookup"><span data-stu-id="d14e8-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="d14e8-107">Se entrambi gli operandi sono diversi da Null e l'elenco chiamate del secondo operando è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è un nuovo elenco chiamate ottenuto rimuovendo le voci del secondo operando dall'elenco di chiamate del primo operando.</span><span class="sxs-lookup"><span data-stu-id="d14e8-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="d14e8-108">Se l'elenco del secondo operando corrisponde a più sottoelenchi contigui nell'elenco del primo operando, viene rimosso solo il sottoelenco corrispondente più a destra.</span><span class="sxs-lookup"><span data-stu-id="d14e8-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="d14e8-109">Se la rimozione restituisce un elenco vuoto, il risultato è `null`.</span><span class="sxs-lookup"><span data-stu-id="d14e8-109">If removal results in an empty list, the result is `null`.</span></span>
- <span data-ttu-id="d14e8-110">Se l'elenco chiamate del secondo operando non è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è il primo operando.</span><span class="sxs-lookup"><span data-stu-id="d14e8-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span>
- <span data-ttu-id="d14e8-111">Se il primo operando è `null`, il risultato dell'operazione è `null`.</span><span class="sxs-lookup"><span data-stu-id="d14e8-111">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="d14e8-112">Se il secondo operando è `null`, il risultato dell'operazione è il primo operando.</span><span class="sxs-lookup"><span data-stu-id="d14e8-112">If the second operand is `null`, the result of the operation is the first operand.</span></span>

<span data-ttu-id="d14e8-113">L'esempio seguente illustra come l'operazione `-` esegue la rimozione dei delegati:</span><span class="sxs-lookup"><span data-stu-id="d14e8-113">The following example shows how the `-` operation performs delegate removal:</span></span>

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="d14e8-114">Operatore di assegnazione di sottrazione -=</span><span class="sxs-lookup"><span data-stu-id="d14e8-114">Subtraction assignment operator -=</span></span>

<span data-ttu-id="d14e8-115">Un'espressione che usa l'operatore `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d14e8-115">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="d14e8-116">equivale a</span><span class="sxs-lookup"><span data-stu-id="d14e8-116">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="d14e8-117">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d14e8-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="d14e8-118">Nell'esempio seguente viene illustrato l'uso dell'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="d14e8-118">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="d14e8-119">È anche possibile usare l'operatore `-=` per specificare un metodo del gestore eventi quando si elimina la sottoscrizione a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="d14e8-119">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="d14e8-120">Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="d14e8-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d14e8-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="d14e8-121">Operator overloadability</span></span>

<span data-ttu-id="d14e8-122">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) dell'operatore `-`.</span><span class="sxs-lookup"><span data-stu-id="d14e8-122">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="d14e8-123">Quando viene eseguito l'overload di un operatore `-` binario, viene eseguito in modo implicito anche l'overload dell'operatore `-=`.</span><span class="sxs-lookup"><span data-stu-id="d14e8-123">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="d14e8-124">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `-=` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d14e8-124">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d14e8-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d14e8-125">C# language specification</span></span>

<span data-ttu-id="d14e8-126">Per altre informazioni, vedere le sezioni [Operatore meno unario](~/_csharplang/spec/expressions.md#unary-minus-operator) e [Operatore di sottrazione](~/_csharplang/spec/expressions.md#subtraction-operator) di [Specifiche del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d14e8-126">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d14e8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14e8-127">See also</span></span>

- [<span data-ttu-id="d14e8-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d14e8-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d14e8-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d14e8-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d14e8-130">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d14e8-130">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d14e8-131">Delegati</span><span class="sxs-lookup"><span data-stu-id="d14e8-131">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="d14e8-132">Eventi</span><span class="sxs-lookup"><span data-stu-id="d14e8-132">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="d14e8-133">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="d14e8-133">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="d14e8-134">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="d14e8-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="d14e8-135">Operatori + e +=</span><span class="sxs-lookup"><span data-stu-id="d14e8-135">+ and += operators</span></span>](addition-operator.md)
