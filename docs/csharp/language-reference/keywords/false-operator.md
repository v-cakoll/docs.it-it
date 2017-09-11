---
title: Operatore false (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e12de403ca31952837913fdaaa8b221986f0e5fe
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="false-operator-c-reference"></a><span data-ttu-id="2057a-102">Operatore false (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2057a-102">false Operator (C# Reference)</span></span>
<span data-ttu-id="2057a-103">Restituisce il valore [bool](../../../csharp/language-reference/keywords/bool.md) `true` per indicare che un operando è `false` e restituisce `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2057a-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="2057a-104">Prima di C# 2.0, gli operatori `true` e `false` erano usati per creare tipi di valore nullable definiti dall'utente compatibili con tipi quali `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="2057a-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="2057a-105">Tuttavia, il linguaggio fornisce ora supporto incorporato per tipi di valore nullable e, quando possibile, è consigliabile usarli al posto dell'overload degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="2057a-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="2057a-106">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="2057a-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="2057a-107">Con valori booleani nullable, l'espressione `a != b` non è necessariamente uguale a `!(a == b)` perché uno o entrambi i valori potrebbero essere null.</span><span class="sxs-lookup"><span data-stu-id="2057a-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="2057a-108">È necessario eseguire l'overload di entrambi gli operatori `true` e `false` separatamente per gestire correttamente i valori null nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="2057a-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="2057a-109">Nell'esempio riportato di seguito viene illustrato come eseguire l'overload e usare gli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="2057a-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 <span data-ttu-id="2057a-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2057a-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="2057a-111">Un tipo che esegue l'overload degli operatori `true` e `false` può essere usato per il controllo dell'espressione nelle istruzioni [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) e [for](../../../csharp/language-reference/keywords/for.md) e nelle [espressioni condizionali](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2057a-111">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="2057a-112">Se un tipo definisce l'operatore `false`, deve anche definire l'operatore [true](../../../csharp/language-reference/keywords/true.md).</span><span class="sxs-lookup"><span data-stu-id="2057a-112">If a type defines operator `false`, it must also define operator [true](../../../csharp/language-reference/keywords/true.md).</span></span>  
  
 <span data-ttu-id="2057a-113">Un tipo non può eseguire direttamente l'overload degli operatori logici condizionali ([ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), ma è possibile ottenere un effetto equivalente eseguendo l'overload dei normali operatori logici e degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="2057a-113">A type cannot directly overload the conditional logical operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2057a-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2057a-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2057a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2057a-115">See Also</span></span>  
 <span data-ttu-id="2057a-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2057a-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2057a-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2057a-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2057a-118">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2057a-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2057a-119">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="2057a-119">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="2057a-120">true</span><span class="sxs-lookup"><span data-stu-id="2057a-120">true</span></span>](../../../csharp/language-reference/keywords/true.md)

