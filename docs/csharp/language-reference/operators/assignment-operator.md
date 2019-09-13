---
title: Operatore = - Riferimenti per C#
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: a450a55524f33f4f06ed077aba864e8f641a458d
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924664"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="54967-102">Operatore = (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="54967-102">= operator (C# reference)</span></span>

<span data-ttu-id="54967-103">L'operatore di assegnazione `=` assegna il valore dell'operando a destra a una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un elemento [indicizzatore](../../programming-guide/indexers/index.md) indicato dall'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="54967-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="54967-104">Il risultato di un'espressione di assegnazione è il valore assegnato all'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="54967-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="54967-105">Il tipo dell'operando destro deve corrispondere al tipo dell'operando sinistro o essere convertibile in modo implicito in esso.</span><span class="sxs-lookup"><span data-stu-id="54967-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="54967-106">L'operatore di assegnazione si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="54967-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="54967-107">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="54967-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="54967-108">L'esempio seguente illustra l'utilizzo dell'operatore di assegnazione con una variabile locale, una proprietà e un elemento indicizzatore come operando sul lato sinistro:</span><span class="sxs-lookup"><span data-stu-id="54967-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="54967-109">Operatore di assegnazione ref</span><span class="sxs-lookup"><span data-stu-id="54967-109">ref assignment operator</span></span>

<span data-ttu-id="54967-110">A partire da C# 7.3, è possibile usare l'operatore di assegnazione ref `= ref` per riassegnare una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="54967-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="54967-111">L'esempio seguente illustra l'uso dell'operatore di assegnazione ref:</span><span class="sxs-lookup"><span data-stu-id="54967-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="54967-112">Nel caso dell'operatore di assegnazione ref, il tipo dell'operando sinistro deve corrispondere a quello dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="54967-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="54967-113">Per altre informazioni, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="54967-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="54967-114">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="54967-114">Compound assignment</span></span>

<span data-ttu-id="54967-115">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="54967-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="54967-116">equivale a</span><span class="sxs-lookup"><span data-stu-id="54967-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="54967-117">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="54967-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="54967-118">L'assegnazione composta è supportata da operatori [aritmetici](arithmetic-operators.md#compound-assignment), [logici booleani](boolean-logical-operators.md#compound-assignment) e [logici bit per bit e shift](bitwise-and-shift-operators.md#compound-assignment).</span><span class="sxs-lookup"><span data-stu-id="54967-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="54967-119">Assegnazione di Unione null</span><span class="sxs-lookup"><span data-stu-id="54967-119">Null-coalescing assignment</span></span>

<span data-ttu-id="54967-120">A partire C# da 8,0, è possibile usare l'operatore `??=` di assegnazione di Unione null per assegnare il valore dell'operando destro all'operando sinistro solo se l' `null`operando sinistro restituisce.</span><span class="sxs-lookup"><span data-stu-id="54967-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="54967-121">Per ulteriori informazioni, vedere [?? e?? = articolo Operators](null-coalescing-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="54967-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="54967-122">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="54967-122">Operator overloadability</span></span>

<span data-ttu-id="54967-123">Un tipo definito dall'utente non può eseguire l'overload dell'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="54967-123">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="54967-124">Tuttavia, un tipo definito dall'utente può definire una conversione implicita in un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="54967-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="54967-125">In questo modo il valore di un tipo definito dall'utente può essere assegnato a una variabile, una proprietà o un elemento indicizzatore di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="54967-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="54967-126">Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="54967-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="54967-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="54967-127">C# language specification</span></span>

<span data-ttu-id="54967-128">Per altre informazioni, vedere la sezione [Operatori di assegnazione](~/_csharplang/spec/expressions.md#assignment-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="54967-128">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54967-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54967-129">See also</span></span>

- [<span data-ttu-id="54967-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="54967-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="54967-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="54967-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="54967-132">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="54967-132">ref keyword</span></span>](../keywords/ref.md)
