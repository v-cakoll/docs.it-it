---
title: Operatore () - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758105"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="36262-102">Operatore () (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="36262-102">() operator (C# Reference)</span></span>

<span data-ttu-id="36262-103">Le parentesi `()` vengono in genere usate per la chiamata di un metodo o un delegato o nelle espressioni cast.</span><span class="sxs-lookup"><span data-stu-id="36262-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="36262-104">È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="36262-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="36262-105">Per altre informazioni, vedere la sezione [Aggiunta di parentesi](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) dell'articolo [Operatori](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="36262-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="36262-106">Per l'elenco degli operatori ordinati in base al livello di precedenza, vedere [ Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="36262-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="36262-107">Chiamata del metodo</span><span class="sxs-lookup"><span data-stu-id="36262-107">Method invocation</span></span>

<span data-ttu-id="36262-108">L'esempio seguente illustra come richiamare un metodo (con o senza argomenti) e un delegato:</span><span class="sxs-lookup"><span data-stu-id="36262-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="36262-109">Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con un operatore [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="36262-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="36262-110">Per altre informazioni sui metodi, vedere [Metodi](../../programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="36262-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="36262-111">Per altre informazioni sui delegati, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="36262-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="36262-112">Espressione cast</span><span class="sxs-lookup"><span data-stu-id="36262-112">Cast expression</span></span>

<span data-ttu-id="36262-113">Un'espressione cast con formato `(T)E` richiama un operatore di conversione per convertire il valore dell'espressione `E` nel tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="36262-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="36262-114">Se non esiste alcuna conversione esplicita dal tipo `E` al tipo `T`, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="36262-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="36262-115">Per informazioni su come definire un operatore di conversione, vedere gli articoli sulle parole chiave [explicit](../keywords/explicit.md) e [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="36262-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="36262-116">L'esempio seguente illustra la conversione di tipi tra tipi numerici:</span><span class="sxs-lookup"><span data-stu-id="36262-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="36262-117">Per altre informazioni sulle conversioni esplicite predefinite tra tipi numerici, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="36262-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="36262-118">Per altre informazioni, vedere [Cast e conversioni di tipi](../../programming-guide/types/casting-and-type-conversions.md) e [Operatori di conversione](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="36262-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="36262-119">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="36262-119">Operator overloadability</span></span>

<span data-ttu-id="36262-120">Non è possibile sottoporre a overload l'operatore `()`.</span><span class="sxs-lookup"><span data-stu-id="36262-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="36262-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="36262-121">C# language specification</span></span>

<span data-ttu-id="36262-122">Per altre informazioni, vedere le sezioni [Espressioni di chiamata](~/_csharplang/spec/expressions.md#invocation-expressions) e [Espressioni cast](~/_csharplang/spec/expressions.md#cast-expressions) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="36262-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36262-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36262-123">See also</span></span>

- [<span data-ttu-id="36262-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="36262-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="36262-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="36262-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="36262-126">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="36262-126">C# Operators</span></span>](index.md)
