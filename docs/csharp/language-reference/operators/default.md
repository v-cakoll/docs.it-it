---
title: Operatore default - Riferimenti per C#
description: Utilizzare l'operatore predefinito per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399483"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="c1eba-103">Operatore default (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c1eba-103">default operator (C# reference)</span></span>

<span data-ttu-id="c1eba-104">L'operatore `default` produce il [valore predefinito](../builtin-types/default-values.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="c1eba-104">The `default` operator produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="c1eba-105">L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="c1eba-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="c1eba-106">L'esempio seguente illustra l'utilizzo dell'operatore `default`:</span><span class="sxs-lookup"><span data-stu-id="c1eba-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="c1eba-107">È inoltre `default` possibile utilizzare la parola chiave come etichetta case predefinita all'interno di un'istruzione [ `switch` ](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="c1eba-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="c1eba-108">valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="c1eba-108">default literal</span></span>

<span data-ttu-id="c1eba-109">A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="c1eba-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="c1eba-110">L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="c1eba-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="c1eba-111">È possibile usare il valore letterale `default` in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="c1eba-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="c1eba-112">Nell'assegnazione o nell'inizializzazione di una variabile.</span><span class="sxs-lookup"><span data-stu-id="c1eba-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="c1eba-113">Nella dichiarazione del valore predefinito per un [parametro di metodo facoltativo.](../../methods.md#optional-parameters-and-arguments)</span><span class="sxs-lookup"><span data-stu-id="c1eba-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="c1eba-114">In una chiamata al metodo per fornire un valore di argomento.</span><span class="sxs-lookup"><span data-stu-id="c1eba-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="c1eba-115">In [ `return` un'istruzione](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="c1eba-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="c1eba-116">L'esempio seguente illustra l'utilizzo del valore letterale `default`:</span><span class="sxs-lookup"><span data-stu-id="c1eba-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="c1eba-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c1eba-117">C# language specification</span></span>

<span data-ttu-id="c1eba-118">Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c1eba-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="c1eba-119">Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="c1eba-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1eba-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1eba-120">See also</span></span>

- [<span data-ttu-id="c1eba-121">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="c1eba-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c1eba-122">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c1eba-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="c1eba-123">Valori predefiniti dei tipi c'è</span><span class="sxs-lookup"><span data-stu-id="c1eba-123">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="c1eba-124">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="c1eba-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
