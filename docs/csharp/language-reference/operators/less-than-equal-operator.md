---
title: Operatore &lt;= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 24bf274bfcb0a8e19a79aafb3bd7920054044be0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271162"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="7ddf4-102">Operatore &lt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7ddf4-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="7ddf4-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore o uguale a" (`<=`), che restituisce `true` se il primo operando è inferiore o uguale al secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="7ddf4-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ddf4-104">Note</span><span class="sxs-lookup"><span data-stu-id="7ddf4-104">Remarks</span></span>  
 <span data-ttu-id="7ddf4-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<=`.</span><span class="sxs-lookup"><span data-stu-id="7ddf4-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="7ddf4-106">Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ddf4-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="7ddf4-107">Se `<=` è sottoposto a overload, deve esserlo anche [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ddf4-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="7ddf4-108">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7ddf4-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ddf4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ddf4-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7ddf4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ddf4-110">See Also</span></span>  
 [<span data-ttu-id="7ddf4-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7ddf4-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7ddf4-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7ddf4-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7ddf4-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7ddf4-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="7ddf4-114">explicit</span><span class="sxs-lookup"><span data-stu-id="7ddf4-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
