---
title: Operatore &lt;= (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
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
ms.openlocfilehash: 931843783888a844d9f90f273b2362d327e8ccbc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="2372b-102">Operatore &lt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2372b-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="2372b-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore o uguale a" (`<=`), che restituisce `true` se il primo operando è inferiore o uguale al secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="2372b-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2372b-104">Note</span><span class="sxs-lookup"><span data-stu-id="2372b-104">Remarks</span></span>  
 <span data-ttu-id="2372b-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="2372b-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="2372b-106">Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="2372b-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="2372b-107">Se `<=` è sottoposto a overload, deve esserlo anche [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2372b-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="2372b-108">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2372b-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2372b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2372b-109">Example</span></span>  
 <span data-ttu-id="2372b-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2372b-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2372b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2372b-111">See Also</span></span>  
 <span data-ttu-id="2372b-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2372b-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2372b-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2372b-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2372b-114">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="2372b-114">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="2372b-115">explicit</span><span class="sxs-lookup"><span data-stu-id="2372b-115">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

