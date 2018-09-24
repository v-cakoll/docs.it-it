---
title: Operatore false (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46578726"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="db801-102">Operatore false (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="db801-102">false operator (C# Reference)</span></span>

<span data-ttu-id="db801-103">Restituisce il valore [bool](bool.md) `true` per indicare che un operando è `false` e restituisce `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="db801-103">Returns the [bool](bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>

<span data-ttu-id="db801-104">Prima di C# 2.0, gli operatori `true` e `false` erano usati per creare tipi di valore nullable definiti dall'utente compatibili con tipi quali `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="db801-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="db801-105">Tuttavia, il linguaggio fornisce ora supporto incorporato per tipi di valore nullable e, quando possibile, è consigliabile usarli al posto dell'overload degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="db801-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="db801-106">Per altre informazioni, vedere [Tipi nullable](../../programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="db801-106">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="db801-107">Con valori booleani nullable, l'espressione `a != b` non è necessariamente uguale a `!(a == b)` perché uno o entrambi i valori potrebbero essere null.</span><span class="sxs-lookup"><span data-stu-id="db801-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="db801-108">È necessario eseguire l'overload di entrambi gli operatori `true` e `false` separatamente per gestire correttamente i valori null nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="db801-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="db801-109">Nell'esempio riportato di seguito viene illustrato come eseguire l'overload e usare gli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="db801-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

<span data-ttu-id="db801-110">Un tipo che esegue l'overload degli operatori `true` e `false` può essere usato per il controllo dell'espressione nelle istruzioni [if](if-else.md), [do](do.md), [while](while.md) e [for](for.md) e nelle [espressioni condizionali](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="db801-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in [conditional expressions](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="db801-111">Se un tipo definisce l'operatore `false`, deve anche definire l'operatore [true](true.md).</span><span class="sxs-lookup"><span data-stu-id="db801-111">If a type defines operator `false`, it must also define operator [true](true.md).</span></span>

<span data-ttu-id="db801-112">Un tipo non può eseguire direttamente l'overload degli operatori logici condizionali ([ && ](../operators/conditional-and-operator.md) e [&#124;&#124;](../operators/conditional-or-operator.md)), ma è possibile ottenere un effetto equivalente eseguendo l'overload dei normali operatori logici e degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="db801-112">A type cannot directly overload the conditional logical operators [&&](../operators/conditional-and-operator.md) and [&#124;&#124;](../operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="db801-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="db801-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="db801-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db801-114">See also</span></span>

- [<span data-ttu-id="db801-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="db801-115">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="db801-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="db801-116">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="db801-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="db801-117">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="db801-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="db801-118">C# Operators</span></span>](../operators/index.md)  
- [<span data-ttu-id="db801-119">true</span><span class="sxs-lookup"><span data-stu-id="db801-119">true</span></span>](true.md)  