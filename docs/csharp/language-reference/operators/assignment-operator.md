---
title: Operatore = - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 40dc844f2a4b6411ea82aa2f029b36d7dd8f6e5a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716316"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d051e-102">Operatore = (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d051e-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="d051e-103">L'operatore di assegnazione `=` assegna il valore dell'operando a destra a una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un elemento [indicizzatore](../../../csharp/programming-guide/indexers/index.md) indicato dall'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d051e-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="d051e-104">Il risultato di un'espressione di assegnazione è il valore assegnato all'operando a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d051e-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="d051e-105">Il tipo dell'operando destro deve corrispondere al tipo dell'operando sinistro o essere convertibile in modo implicito in esso.</span><span class="sxs-lookup"><span data-stu-id="d051e-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="d051e-106">L'operatore di assegnazione si associa all'operando a destra, che significa che un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="d051e-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="d051e-107">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="d051e-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="d051e-108">L'esempio seguente illustra l'utilizzo dell'operatore di assegnazione per assegnare valori a una variabile locale, una proprietà e un elemento indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="d051e-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="d051e-109">Operatore di assegnazione ref</span><span class="sxs-lookup"><span data-stu-id="d051e-109">ref assignment operator</span></span>

<span data-ttu-id="d051e-110">A partire da C# 7.3, è possibile usare l'operatore di assegnazione ref `= ref` per riassegnare una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="d051e-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="d051e-111">L'esempio seguente illustra l'uso dell'operatore di assegnazione ref:</span><span class="sxs-lookup"><span data-stu-id="d051e-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="d051e-112">Nel caso dell'operatore di assegnazione ref, il tipo dell'operando sinistro deve corrispondere al tipo dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="d051e-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="d051e-113">Per altre informazioni, vedere la [nota relativa alla proposta di funzionalità](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="d051e-113">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d051e-114">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="d051e-114">Operator overloadability</span></span>

<span data-ttu-id="d051e-115">Un tipo definito dall'utente non può eseguire l'overload dell'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d051e-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="d051e-116">Tuttavia, un tipo definito dall'utente può definire una conversione implicita in un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="d051e-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="d051e-117">In questo modo il valore di un tipo definito dall'utente può essere assegnato a una variabile, una proprietà o un elemento indicizzatore di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="d051e-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="d051e-118">Per altre informazioni, vedere l'articolo relativo alla parola chiave [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="d051e-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d051e-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d051e-119">C# language specification</span></span>

<span data-ttu-id="d051e-120">Per altre informazioni, vedere la sezione [Assegnazione semplice](~/_csharplang/spec/expressions.md#simple-assignment) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d051e-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d051e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d051e-121">See also</span></span>

- [<span data-ttu-id="d051e-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d051e-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d051e-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d051e-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d051e-124">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d051e-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d051e-125">ref (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="d051e-125">ref keyword</span></span>](../keywords/ref.md)
