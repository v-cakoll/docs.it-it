---
title: Operatore &lt; (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="452c5-102">Operatore &lt; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="452c5-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="452c5-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore di" (`<`), che restituisce `true` se il primo operando è minore del secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="452c5-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="452c5-104">Note</span><span class="sxs-lookup"><span data-stu-id="452c5-104">Remarks</span></span>  
 <span data-ttu-id="452c5-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="452c5-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="452c5-106">Se `<` è sottoposto a overload, deve esserlo anche [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="452c5-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="452c5-107">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="452c5-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="452c5-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="452c5-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="452c5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="452c5-109">See Also</span></span>  
 [<span data-ttu-id="452c5-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="452c5-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="452c5-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="452c5-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="452c5-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="452c5-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
