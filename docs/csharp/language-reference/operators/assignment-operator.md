---
title: Operatori di assegnazione - Riferimento in C
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 420b41f586a6980d40cf1171eef00dad37bf5abf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399252"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="0e690-102">Operatori di assegnazione (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="0e690-102">Assignment operators (C# reference)</span></span>

<span data-ttu-id="0e690-103">L'operatore di assegnazione `=` assegna il valore dell'operando a destra a una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un elemento [indicizzatore](../../programming-guide/indexers/index.md) indicato dall'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0e690-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="0e690-104">Il risultato di un'espressione di assegnazione è il valore assegnato all'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0e690-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="0e690-105">Il tipo dell'operando destro deve corrispondere al tipo dell'operando sinistro o essere convertibile in modo implicito in esso.</span><span class="sxs-lookup"><span data-stu-id="0e690-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="0e690-106">L'operatore di assegnazione `=` è associativo a destra, ovvero un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="0e690-106">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="0e690-107">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="0e690-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="0e690-108">L'esempio seguente illustra l'utilizzo dell'operatore di assegnazione con una variabile locale, una proprietà e un elemento indicizzatore come operando sul lato sinistro:</span><span class="sxs-lookup"><span data-stu-id="0e690-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="0e690-109">Operatore di assegnazione ref</span><span class="sxs-lookup"><span data-stu-id="0e690-109">ref assignment operator</span></span>

<span data-ttu-id="0e690-110">A partire da C# 7.3, è possibile usare l'operatore di assegnazione ref `= ref` per riassegnare una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="0e690-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="0e690-111">L'esempio seguente illustra l'uso dell'operatore di assegnazione ref:</span><span class="sxs-lookup"><span data-stu-id="0e690-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="0e690-112">Nel caso dell'operatore di assegnazione ref, entrambi gli operandi devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="0e690-112">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="0e690-113">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="0e690-113">Compound assignment</span></span>

<span data-ttu-id="0e690-114">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="0e690-114">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="0e690-115">equivale a</span><span class="sxs-lookup"><span data-stu-id="0e690-115">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="0e690-116">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0e690-116">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="0e690-117">L'assegnazione composta è supportata da operatori [aritmetici](arithmetic-operators.md#compound-assignment), [logici booleani](boolean-logical-operators.md#compound-assignment) e [logici bit per bit e shift](bitwise-and-shift-operators.md#compound-assignment).</span><span class="sxs-lookup"><span data-stu-id="0e690-117">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="0e690-118">Assegnazione di valori Null</span><span class="sxs-lookup"><span data-stu-id="0e690-118">Null-coalescing assignment</span></span>

<span data-ttu-id="0e690-119">A partire dalla versione 8.0 di C, è possibile `??=` utilizzare l'operatore di assegnazione null-coalescing per assegnare il valore del relativo operando di destra al relativo operando di sinistra solo se l'operando di sinistra restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="0e690-119">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="0e690-120">Per ulteriori informazioni, vedere il [?? e ?? :](null-coalescing-operator.md) articolo degli operatori.</span><span class="sxs-lookup"><span data-stu-id="0e690-120">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0e690-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="0e690-121">Operator overloadability</span></span>

<span data-ttu-id="0e690-122">Un tipo definito dall'utente non può [eseguire l'overload](operator-overloading.md) dell'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0e690-122">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="0e690-123">Tuttavia, un tipo definito dall'utente può definire una conversione implicita in un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="0e690-123">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="0e690-124">In questo modo il valore di un tipo definito dall'utente può essere assegnato a una variabile, una proprietà o un elemento indicizzatore di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="0e690-124">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="0e690-125">Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0e690-125">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="0e690-126">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="0e690-126">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="0e690-127">Tuttavia, se un tipo definito dall'utente esegue l'overload di un operatore `op`binario , anche l'operatore, `op=` se esistente, viene sottoposto a overload in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="0e690-127">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0e690-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0e690-128">C# language specification</span></span>

<span data-ttu-id="0e690-129">Per altre informazioni, vedere la sezione [Operatori di assegnazione](~/_csharplang/spec/expressions.md#assignment-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0e690-129">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0e690-130">Per ulteriori informazioni sull'operatore `= ref`di assegnazione dei riferimenti , vedere la [nota](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)della proposta di funzionalità .</span><span class="sxs-lookup"><span data-stu-id="0e690-130">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e690-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e690-131">See also</span></span>

- [<span data-ttu-id="0e690-132">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="0e690-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0e690-133">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0e690-133">C# operators</span></span>](index.md)
- [<span data-ttu-id="0e690-134">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="0e690-134">ref keyword</span></span>](../keywords/ref.md)
