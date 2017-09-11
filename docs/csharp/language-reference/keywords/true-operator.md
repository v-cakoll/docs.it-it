---
title: Operatore true (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 19
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
ms.openlocfilehash: c74fdc8091013ce7793c0591fc17ece80fd6d76d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="true-operator-c-reference"></a><span data-ttu-id="c314b-102">Operatore true (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c314b-102">true Operator (C# Reference)</span></span>
<span data-ttu-id="c314b-103">Restituisce il valore [bool](../../../csharp/language-reference/keywords/bool.md) `true` per indicare che un operando è true e, in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="c314b-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is true and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="c314b-104">Prima di C# 2.0, gli operatori `true` e `false` erano usati per creare tipi di valore nullable definiti dall'utente compatibili con tipi quali `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="c314b-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="c314b-105">Tuttavia, il linguaggio fornisce ora supporto incorporato per tipi di valore nullable e, quando possibile, è consigliabile usarli al posto dell'overload degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="c314b-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="c314b-106">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="c314b-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="c314b-107">Con valori booleani nullable, l'espressione `a != b` non è necessariamente uguale a `!(a == b)` perché uno o entrambi i valori potrebbero essere null.</span><span class="sxs-lookup"><span data-stu-id="c314b-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="c314b-108">È necessario eseguire l'overload di entrambi gli operatori `true` e `false` separatamente per identificare correttamente i valori null nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="c314b-108">You need to overload both the `true` and `false` operators separately to correctly identify the null values in the expression.</span></span> <span data-ttu-id="c314b-109">Nell'esempio riportato di seguito viene illustrato come eseguire l'overload e usare gli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="c314b-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 <span data-ttu-id="c314b-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c314b-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="c314b-111">Un tipo che esegue l'overload degli operatori `true` e `false` può essere usato per il controllo dell'espressione nelle istruzioni [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) e [for](../../../csharp/language-reference/keywords/for.md) e nelle [espressioni condizionali](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c314b-111">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="c314b-112">Se un tipo definisce l'operatore `true`, deve anche definire l'operatore [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="c314b-112">If a type defines operator `true`, it must also define operator [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
 <span data-ttu-id="c314b-113">Un tipo non può eseguire direttamente l'overload degli operatori logici condizionali ([ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), ma è possibile ottenere un effetto equivalente eseguendo l'overload dei normali operatori logici e degli operatori `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="c314b-113">A type cannot directly overload the conditional logical operators ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c314b-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c314b-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c314b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c314b-115">See Also</span></span>  
 <span data-ttu-id="c314b-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c314b-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c314b-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c314b-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c314b-118">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c314b-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c314b-119">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c314b-119">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="c314b-120">false</span><span class="sxs-lookup"><span data-stu-id="c314b-120">false</span></span>](../../../csharp/language-reference/keywords/false.md)

