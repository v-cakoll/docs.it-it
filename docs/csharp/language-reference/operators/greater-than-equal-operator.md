---
title: Operatore &gt;= (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
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
ms.openlocfilehash: 59b134ce1e1169b0a5f4583374148d39ceb8326a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="89ef6-102">Operatore &gt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="89ef6-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="89ef6-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "maggiore o uguale a", `>=`, che restituisce `true` se il primo operando è maggiore o uguale al secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="89ef6-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89ef6-104">Note</span><span class="sxs-lookup"><span data-stu-id="89ef6-104">Remarks</span></span>  
 <span data-ttu-id="89ef6-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>=`.</span><span class="sxs-lookup"><span data-stu-id="89ef6-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="89ef6-106">Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="89ef6-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="89ef6-107">Se `>=` è sottoposto a overload, deve esserlo anche [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="89ef6-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="89ef6-108">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="89ef6-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89ef6-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="89ef6-109">Example</span></span>  
 <span data-ttu-id="89ef6-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="89ef6-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ef6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89ef6-111">See Also</span></span>  
 <span data-ttu-id="89ef6-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="89ef6-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="89ef6-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="89ef6-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="89ef6-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="89ef6-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

