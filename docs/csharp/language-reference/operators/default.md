---
title: Operatore default - Riferimenti per C#
description: Usare l'operatore predefinito per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 744bdf1ec683ef32bba508c260590c0ed4c6e987
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712715"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="aefb9-103">Operatore default (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="aefb9-103">default operator (C# reference)</span></span>

<span data-ttu-id="aefb9-104">L'operatore `default` produce il [valore predefinito](../keywords/default-values-table.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="aefb9-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="aefb9-105">L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="aefb9-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="aefb9-106">L'esempio seguente illustra l'utilizzo dell'operatore `default`:</span><span class="sxs-lookup"><span data-stu-id="aefb9-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="aefb9-107">È anche possibile usare la parola chiave `default` come etichetta case predefinita all'interno di un' [istruzione`switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="aefb9-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="aefb9-108">valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="aefb9-108">default literal</span></span>

<span data-ttu-id="aefb9-109">A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="aefb9-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="aefb9-110">L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="aefb9-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="aefb9-111">È possibile usare il valore letterale `default` in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="aefb9-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="aefb9-112">Nell'assegnazione o nell'inizializzazione di una variabile.</span><span class="sxs-lookup"><span data-stu-id="aefb9-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="aefb9-113">Nella dichiarazione del valore predefinito per un parametro del [metodo facoltativo](../../methods.md#optional-parameters-and-arguments).</span><span class="sxs-lookup"><span data-stu-id="aefb9-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="aefb9-114">In una chiamata al metodo per fornire un valore di argomento.</span><span class="sxs-lookup"><span data-stu-id="aefb9-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="aefb9-115">In un' [istruzione`return`](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="aefb9-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="aefb9-116">L'esempio seguente illustra l'utilizzo del valore letterale `default`:</span><span class="sxs-lookup"><span data-stu-id="aefb9-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="aefb9-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="aefb9-117">C# language specification</span></span>

<span data-ttu-id="aefb9-118">Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="aefb9-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="aefb9-119">Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="aefb9-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aefb9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aefb9-120">See also</span></span>

- [<span data-ttu-id="aefb9-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="aefb9-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="aefb9-122">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="aefb9-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="aefb9-123">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="aefb9-123">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="aefb9-124">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="aefb9-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
