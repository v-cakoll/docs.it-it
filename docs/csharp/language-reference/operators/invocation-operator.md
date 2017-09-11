---
title: Operatore () (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e44c8-102">Operatore () (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e44c8-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="e44c8-103">Oltre a specificare l'ordine in cui devono essere eseguite le operazioni di un'espressione, le parentesi vengono usate per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e44c8-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="e44c8-104">Specificare i cast, ovvero le conversioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="e44c8-104">Specify casts, or type conversions.</span></span>  
  
     <span data-ttu-id="e44c8-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e44c8-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span></span>  
  
2.  <span data-ttu-id="e44c8-106">Richiamare metodi o delegati.</span><span class="sxs-lookup"><span data-stu-id="e44c8-106">Invoke methods or delegates.</span></span>  
  
     <span data-ttu-id="e44c8-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e44c8-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e44c8-108">Note</span><span class="sxs-lookup"><span data-stu-id="e44c8-108">Remarks</span></span>  
 <span data-ttu-id="e44c8-109">Un cast richiama l'operatore di conversione in modo esplicito da un tipo a un altro. Se tale operatore di conversione non viene definito, il cast non sarà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e44c8-109">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="e44c8-110">Per informazioni sulla definizione di un operatore di conversione, vedere [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="e44c8-110">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="e44c8-111">Non è possibile sottoporre l'operatore `()` a overload.</span><span class="sxs-lookup"><span data-stu-id="e44c8-111">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="e44c8-112">Per altre informazioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="e44c8-112">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="e44c8-113">Un'espressione cast può determinare una sintassi ambigua.</span><span class="sxs-lookup"><span data-stu-id="e44c8-113">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="e44c8-114">Ad esempio, l'espressione `(x)–y` potrebbe essere interpretata come espressione cast (un cast di -y sul tipo x) oppure come espressione di addizione combinata con un'espressione tra parentesi che calcola il valore x - y.</span><span class="sxs-lookup"><span data-stu-id="e44c8-114">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="e44c8-115">Per altre informazioni sulla chiamata al metodo, vedere [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="e44c8-115">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e44c8-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e44c8-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e44c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e44c8-117">See Also</span></span>  
 <span data-ttu-id="e44c8-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e44c8-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e44c8-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e44c8-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e44c8-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="e44c8-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

