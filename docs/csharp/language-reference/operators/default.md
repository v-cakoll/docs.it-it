---
title: Operatore default - Riferimenti per C#
description: Usare l'operatore predefinito per produrre il valore predefinito di un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: ba4c02caa53a9d532be4012a4543a25cd41b6023
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239313"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="8f032-103">Operatore default (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8f032-103">default operator (C# reference)</span></span>

<span data-ttu-id="8f032-104">L'operatore `default` produce il [valore predefinito](../builtin-types/default-values.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="8f032-104">The `default` operator produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="8f032-105">L'argomento dell'operatore `default` deve essere il nome di un tipo o di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="8f032-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="8f032-106">L'esempio seguente illustra l'utilizzo dell'operatore `default`:</span><span class="sxs-lookup"><span data-stu-id="8f032-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/snippets/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="8f032-107">È anche possibile usare la parola chiave `default` come etichetta case predefinita all'interno di un' [istruzione`switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="8f032-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="8f032-108">valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="8f032-108">default literal</span></span>

<span data-ttu-id="8f032-109">A partire da C# 7.1, è possibile usare il valore letterale `default` per produrre il valore predefinito di un tipo quando il compilatore è in grado di dedurre il tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="8f032-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="8f032-110">L'espressione letterale `default` produce lo stesso valore dell'espressione `default(T)` in cui `T` è il tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="8f032-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="8f032-111">È possibile usare il valore letterale `default` in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="8f032-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="8f032-112">Nell'assegnazione o nell'inizializzazione di una variabile.</span><span class="sxs-lookup"><span data-stu-id="8f032-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="8f032-113">Nella dichiarazione del valore predefinito per un parametro del [metodo facoltativo](../../methods.md#optional-parameters-and-arguments).</span><span class="sxs-lookup"><span data-stu-id="8f032-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="8f032-114">In una chiamata al metodo per fornire un valore di argomento.</span><span class="sxs-lookup"><span data-stu-id="8f032-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="8f032-115">In un' [istruzione`return`](../keywords/return.md) o come espressione in un [membro con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="8f032-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="8f032-116">L'esempio seguente illustra l'utilizzo del valore letterale `default`:</span><span class="sxs-lookup"><span data-stu-id="8f032-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/snippets/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="8f032-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8f032-117">C# language specification</span></span>

<span data-ttu-id="8f032-118">Per altre informazioni, vedere la sezione [Espressioni con valore predefinito](~/_csharplang/spec/expressions.md#default-value-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8f032-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="8f032-119">Per altre informazioni sul valore letterale `default`, vedere la [nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="8f032-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f032-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f032-120">See also</span></span>

- [<span data-ttu-id="8f032-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8f032-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8f032-122">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8f032-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="8f032-123">Valori predefiniti dei C# tipi</span><span class="sxs-lookup"><span data-stu-id="8f032-123">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="8f032-124">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="8f032-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
