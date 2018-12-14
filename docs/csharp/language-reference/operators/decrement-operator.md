---
title: Operatore -- (Riferimenti per C#)
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 0858321d6fe192a55bc548f169c558542238a981
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153337"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="12eaa-102">Operatore -- (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="12eaa-102">-- Operator (C# Reference)</span></span>

<span data-ttu-id="12eaa-103">L'operatore di decremento unario `--` decrementa il proprio operando di 1.</span><span class="sxs-lookup"><span data-stu-id="12eaa-103">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="12eaa-104">È supportato in due forme: l'operatore di decremento suffisso, `x--`, e l'operatore di decremento prefisso, `--x`.</span><span class="sxs-lookup"><span data-stu-id="12eaa-104">It's supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

## <a name="postfix-decrement-operator"></a><span data-ttu-id="12eaa-105">Operatore di decremento suffisso</span><span class="sxs-lookup"><span data-stu-id="12eaa-105">Postfix decrement operator</span></span>

<span data-ttu-id="12eaa-106">Il risultato di `x--` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="12eaa-106">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a><span data-ttu-id="12eaa-107">Operatore di decremento prefisso</span><span class="sxs-lookup"><span data-stu-id="12eaa-107">Prefix decrement operator</span></span>

<span data-ttu-id="12eaa-108">Il risultato di `--x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="12eaa-108">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a><span data-ttu-id="12eaa-109">Note</span><span class="sxs-lookup"><span data-stu-id="12eaa-109">Remarks</span></span>

<span data-ttu-id="12eaa-110">L'operatore di decremento è predefinito per tutti i [tipi integrali](../keywords/integral-types-table.md) (incluso il tipo [char](../keywords/char.md)), i [tipi a virgola mobile](../keywords/floating-point-types-table.md) e i tipi [enumerazione](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="12eaa-110">The decrement operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="12eaa-111">Un operando dell'operatore di decremento deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="12eaa-111">An operand of the decrement operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="12eaa-112">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="12eaa-112">Operator overloadability</span></span>

<span data-ttu-id="12eaa-113">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `--`.</span><span class="sxs-lookup"><span data-stu-id="12eaa-113">User-defined types can [overload](../keywords/operator.md) the `--` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12eaa-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="12eaa-114">C# language specification</span></span>

<span data-ttu-id="12eaa-115">Per altre informazioni, vedere le sezioni [Operatori di incremento e decremento in forma suffissa](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) e [Operatori di incremento e decremento in forma prefissa](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="12eaa-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12eaa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12eaa-116">See also</span></span>

- [<span data-ttu-id="12eaa-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="12eaa-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12eaa-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="12eaa-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12eaa-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="12eaa-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="12eaa-120">Operatore ++</span><span class="sxs-lookup"><span data-stu-id="12eaa-120">++ Operator</span></span>](increment-operator.md)
- [<span data-ttu-id="12eaa-121">Procedura: Incrementare e decrementare i puntatori</span><span class="sxs-lookup"><span data-stu-id="12eaa-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
