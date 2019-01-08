---
title: Operatore &lt;= - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 30f42de68667756a8233fef4241bfd74ed4eff2a
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656089"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="14d47-102">Operatore &lt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="14d47-102">&lt;= Operator (C# Reference)</span></span>

<span data-ttu-id="14d47-103">L'operatore relazionale "minore o uguale a" `<=` restituisce `true` se il primo operando è minore o uguale al secondo operando, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="14d47-103">The "less than or equal" relational operator `<=` returns `true` if its first operand is less than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="14d47-104">Tutti i tipi numerici e di enumerazione supportano l'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="14d47-104">All numeric and enumeration types support the `<=` operator.</span></span> <span data-ttu-id="14d47-105">Per gli operandi dello stesso tipo [enum](../keywords/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="14d47-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="14d47-106">Per gli operatori relazionali `==`, `>`, `<` `>=`, e `<=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="14d47-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="14d47-107">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`).</span><span class="sxs-lookup"><span data-stu-id="14d47-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="14d47-108">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14d47-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="14d47-109">Nell'esempio seguente viene illustrato l'uso dell'operatore `<=`:</span><span class="sxs-lookup"><span data-stu-id="14d47-109">The following example demonstrates the usage of the `<=` operator:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="14d47-110">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="14d47-110">Operator overloadability</span></span>

<span data-ttu-id="14d47-111">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="14d47-111">User-defined types can [overload](../keywords/operator.md) the `<=` operator.</span></span> <span data-ttu-id="14d47-112">Se un tipo esegue l'overload dell'operatore "minore o uguale a" `<=`, deve anche eseguire l'overload dell'[operatore "maggiore o uguale a"](greater-than-equal-operator.md) `>=`.</span><span class="sxs-lookup"><span data-stu-id="14d47-112">If a type overloads the "less than or equal" operator `<=`, it must also overload the ["greater than or equal" operator](greater-than-equal-operator.md) `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="14d47-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="14d47-113">C# language specification</span></span>

<span data-ttu-id="14d47-114">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="14d47-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14d47-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14d47-115">See also</span></span>

- [<span data-ttu-id="14d47-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="14d47-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="14d47-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="14d47-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="14d47-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="14d47-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="14d47-119">Operatore <</span><span class="sxs-lookup"><span data-stu-id="14d47-119">< Operator</span></span>](less-than-operator.md)
- [<span data-ttu-id="14d47-120">Operatore ==</span><span class="sxs-lookup"><span data-stu-id="14d47-120">== Operator</span></span>](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
