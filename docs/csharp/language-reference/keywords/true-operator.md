---
title: Operatore true (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96ab7679862959f3c99e31beac0bd5514228bd8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="true-operator-c-reference"></a><span data-ttu-id="1c652-102">Operatore true (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1c652-102">true Operator (C# Reference)</span></span>
<span data-ttu-id="1c652-103">Restituisce il valore [bool](../../../csharp/language-reference/keywords/bool.md) `true` per indicare che un operando è true e, in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="1c652-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is true and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="1c652-104">Prima di C# 2.0, gli operatori `true` e `false` erano usati per creare tipi di valore nullable definiti dall'utente compatibili con tipi quali `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="1c652-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="1c652-105">Tuttavia, il linguaggio fornisce ora supporto incorporato per tipi di valore nullable e, quando possibile, è consigliabile usarli al posto dell'overload degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="1c652-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="1c652-106">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c652-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="1c652-107">Con valori booleani nullable, l'espressione `a != b` non è necessariamente uguale a `!(a == b)` perché uno o entrambi i valori potrebbero essere null.</span><span class="sxs-lookup"><span data-stu-id="1c652-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="1c652-108">È necessario eseguire l'overload di entrambi gli operatori `true` e `false` separatamente per identificare correttamente i valori null nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="1c652-108">You need to overload both the `true` and `false` operators separately to correctly identify the null values in the expression.</span></span> <span data-ttu-id="1c652-109">Nell'esempio riportato di seguito viene illustrato come eseguire l'overload e usare gli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="1c652-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 <span data-ttu-id="1c652-110">Un tipo che esegue l'overload degli operatori `true` e `false` può essere usato per il controllo dell'espressione nelle istruzioni [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) e [for](../../../csharp/language-reference/keywords/for.md) e nelle [espressioni condizionali](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1c652-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="1c652-111">Se un tipo definisce l'operatore `true`, deve anche definire l'operatore [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="1c652-111">If a type defines operator `true`, it must also define operator [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
 <span data-ttu-id="1c652-112">Un tipo non può eseguire direttamente l'overload degli operatori logici condizionali ([ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), ma è possibile ottenere un effetto equivalente eseguendo l'overload dei normali operatori logici e degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="1c652-112">A type cannot directly overload the conditional logical operators ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1c652-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1c652-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c652-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c652-114">See Also</span></span>  
 [<span data-ttu-id="1c652-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1c652-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1c652-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1c652-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1c652-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1c652-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1c652-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1c652-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="1c652-119">false</span><span class="sxs-lookup"><span data-stu-id="1c652-119">false</span></span>](../../../csharp/language-reference/keywords/false.md)
