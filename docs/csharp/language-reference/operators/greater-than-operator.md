---
title: Operatore &gt; (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273498"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="df66a-102">Operatore &gt; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="df66a-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="df66a-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "maggiore di", `>`, che restituisce `true` se il primo operando è maggiore del secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="df66a-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df66a-104">Note</span><span class="sxs-lookup"><span data-stu-id="df66a-104">Remarks</span></span>  
 <span data-ttu-id="df66a-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="df66a-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="df66a-106">Se `>` è sottoposto a overload, deve esserlo anche [<](../../../csharp/language-reference/operators/less-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="df66a-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="df66a-107">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="df66a-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df66a-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="df66a-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="df66a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df66a-109">See Also</span></span>  
 [<span data-ttu-id="df66a-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="df66a-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="df66a-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="df66a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="df66a-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="df66a-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="df66a-113">explicit</span><span class="sxs-lookup"><span data-stu-id="df66a-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
