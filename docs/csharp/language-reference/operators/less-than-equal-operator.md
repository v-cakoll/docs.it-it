---
title: Operatore <= - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 54c8300ad883e81cfb3d4886881984fd5a0ebdb3
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545377"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2a3b8-102">Operatore \<= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2a3b8-102">\<= Operator (C# Reference)</span></span>

<span data-ttu-id="2a3b8-103">L'operatore relazionale "minore o uguale a" `<=` restituisce `true` se il primo operando è minore o uguale al secondo operando, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-103">The "less than or equal" relational operator `<=` returns `true` if its first operand is less than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="2a3b8-104">Tutti i tipi numerici e di enumerazione supportano l'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-104">All numeric and enumeration types support the `<=` operator.</span></span> <span data-ttu-id="2a3b8-105">Per gli operandi dello stesso tipo [enum](../keywords/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="2a3b8-106">Per gli operatori relazionali `==`, `>`, `<` `>=`, e `<=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="2a3b8-107">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`).</span><span class="sxs-lookup"><span data-stu-id="2a3b8-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="2a3b8-108">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="2a3b8-109">Nell'esempio seguente viene illustrato l'uso dell'operatore `<=`:</span><span class="sxs-lookup"><span data-stu-id="2a3b8-109">The following example demonstrates the usage of the `<=` operator:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="2a3b8-110">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="2a3b8-110">Operator overloadability</span></span>

<span data-ttu-id="2a3b8-111">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-111">User-defined types can [overload](../keywords/operator.md) the `<=` operator.</span></span> <span data-ttu-id="2a3b8-112">Se un tipo esegue l'overload dell'operatore "minore o uguale a" `<=`, deve anche eseguire l'overload dell'[operatore "maggiore o uguale a"](greater-than-equal-operator.md) `>=`.</span><span class="sxs-lookup"><span data-stu-id="2a3b8-112">If a type overloads the "less than or equal" operator `<=`, it must also overload the ["greater than or equal" operator](greater-than-equal-operator.md) `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2a3b8-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2a3b8-113">C# language specification</span></span>

<span data-ttu-id="2a3b8-114">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2a3b8-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a3b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a3b8-115">See also</span></span>

- [<span data-ttu-id="2a3b8-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2a3b8-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2a3b8-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2a3b8-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2a3b8-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="2a3b8-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2a3b8-119">Operatore <</span><span class="sxs-lookup"><span data-stu-id="2a3b8-119">< Operator</span></span>](less-than-operator.md)
- [<span data-ttu-id="2a3b8-120">Operatore ==</span><span class="sxs-lookup"><span data-stu-id="2a3b8-120">== Operator</span></span>](equality-operators.md#equality-operator-)
- <xref:System.IComparable%601?displayProperty=nameWithType>
