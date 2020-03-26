---
title: Espressioni di valore predefinito - Riferimento in C
description: Utilizzare le espressioni di valore predefinito per ottenere il valore predefinito di un tipo
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 2adfd8d24066e9dad50c3c18407d3ade71b4b68e
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507178"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="0a614-103">Espressioni di valore predefinito (riferimenti in C</span><span class="sxs-lookup"><span data-stu-id="0a614-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="0a614-104">Un'espressione di valore predefinito produce il [valore predefinito](../builtin-types/default-values.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="0a614-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="0a614-105">Esistono due tipi di espressioni di valore predefinito: la chiamata [all'operatore predefinito](#default-operator) e un [valore letterale predefinito](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="0a614-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="0a614-106">È inoltre `default` possibile utilizzare la parola chiave come etichetta case predefinita all'interno di un'istruzione [ `switch` ](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="0a614-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="0a614-107">operatore default</span><span class="sxs-lookup"><span data-stu-id="0a614-107">default operator</span></span>

<span data-ttu-id="0a614-108">L'argomento dell'operatore `default` deve essere il nome o il parametro di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0a614-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="0a614-109">valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="0a614-109">default literal</span></span>

<span data-ttu-id="0a614-110">A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="0a614-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="0a614-111">L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="0a614-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="0a614-112">È possibile usare il valore letterale `default` in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="0a614-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="0a614-113">Nell'assegnazione o nell'inizializzazione di una variabile.</span><span class="sxs-lookup"><span data-stu-id="0a614-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="0a614-114">Nella dichiarazione del valore predefinito per un [parametro di metodo facoltativo.](../../methods.md#optional-parameters-and-arguments)</span><span class="sxs-lookup"><span data-stu-id="0a614-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="0a614-115">In una chiamata al metodo per fornire un valore di argomento.</span><span class="sxs-lookup"><span data-stu-id="0a614-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="0a614-116">In [ `return` un'istruzione](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="0a614-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="0a614-117">L'esempio seguente illustra l'utilizzo del valore letterale `default`:</span><span class="sxs-lookup"><span data-stu-id="0a614-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="0a614-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0a614-118">C# language specification</span></span>

<span data-ttu-id="0a614-119">Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0a614-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0a614-120">Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="0a614-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a614-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a614-121">See also</span></span>

- [<span data-ttu-id="0a614-122">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="0a614-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0a614-123">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0a614-123">C# operators</span></span>](index.md)
- [<span data-ttu-id="0a614-124">Valori predefiniti dei tipi c'è</span><span class="sxs-lookup"><span data-stu-id="0a614-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="0a614-125">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="0a614-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
