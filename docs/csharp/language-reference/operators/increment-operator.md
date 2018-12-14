---
title: Operatore ++ (Riferimenti per C#)
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030470"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="09bed-102">Operatore ++ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="09bed-102">++ Operator (C# Reference)</span></span>

<span data-ttu-id="09bed-103">L'operatore di incremento unario `++` incrementa il suo operando di 1.</span><span class="sxs-lookup"><span data-stu-id="09bed-103">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="09bed-104">È supportato in due forme: l'operatore di incremento suffisso, `x++`, e l'operatore di incremento prefisso, `++x`.</span><span class="sxs-lookup"><span data-stu-id="09bed-104">It's supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

## <a name="postfix-increment-operator"></a><span data-ttu-id="09bed-105">Operatore di incremento suffisso</span><span class="sxs-lookup"><span data-stu-id="09bed-105">Postfix increment operator</span></span>

<span data-ttu-id="09bed-106">Il risultato di `x++` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="09bed-106">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a><span data-ttu-id="09bed-107">Operatore di incremento prefisso</span><span class="sxs-lookup"><span data-stu-id="09bed-107">Prefix increment operator</span></span>

<span data-ttu-id="09bed-108">Il risultato di `++x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="09bed-108">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a><span data-ttu-id="09bed-109">Note</span><span class="sxs-lookup"><span data-stu-id="09bed-109">Remarks</span></span>

<span data-ttu-id="09bed-110">L'operatore di incremento è predefinito per tutti i [tipi integrali](../keywords/integral-types-table.md) (incluso il tipo [char](../keywords/char.md)), i [tipi a virgola mobile](../keywords/floating-point-types-table.md) e i tipi [enumerazione](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="09bed-110">The increment operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="09bed-111">Un operando dell'operatore di incremento deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="09bed-111">An operand of the increment operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="09bed-112">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="09bed-112">Operator overloadability</span></span>

<span data-ttu-id="09bed-113">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `++`.</span><span class="sxs-lookup"><span data-stu-id="09bed-113">User-defined types can [overload](../keywords/operator.md) the `++` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09bed-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="09bed-114">C# language specification</span></span>

<span data-ttu-id="09bed-115">Per altre informazioni, vedere le sezioni [Operatori di incremento e decremento in forma suffissa](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) e [Operatori di incremento e decremento in forma prefissa](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="09bed-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09bed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09bed-116">See also</span></span>

- [<span data-ttu-id="09bed-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="09bed-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="09bed-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="09bed-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="09bed-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="09bed-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="09bed-120">Operatore --</span><span class="sxs-lookup"><span data-stu-id="09bed-120">-- Operator</span></span>](decrement-operator.md)
- [<span data-ttu-id="09bed-121">Procedura: incrementare e decrementare i puntatori</span><span class="sxs-lookup"><span data-stu-id="09bed-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
