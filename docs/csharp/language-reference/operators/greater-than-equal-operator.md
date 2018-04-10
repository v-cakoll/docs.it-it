---
title: Operatore &gt;= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020c2bd8756899908681ab72cac7aa2a203c6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="b5d45-102">Operatore &gt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b5d45-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="b5d45-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "maggiore o uguale a", `>=`, che restituisce `true` se il primo operando è maggiore o uguale al secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="b5d45-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5d45-104">Note</span><span class="sxs-lookup"><span data-stu-id="b5d45-104">Remarks</span></span>  
 <span data-ttu-id="b5d45-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>=`.</span><span class="sxs-lookup"><span data-stu-id="b5d45-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="b5d45-106">Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="b5d45-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="b5d45-107">Se `>=` è sottoposto a overload, deve esserlo anche [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b5d45-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="b5d45-108">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b5d45-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d45-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5d45-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b5d45-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5d45-110">See Also</span></span>  
 [<span data-ttu-id="b5d45-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b5d45-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b5d45-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b5d45-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b5d45-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b5d45-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
