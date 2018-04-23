---
title: Operatore %= (Riferimenti per C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="015ca-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="015ca-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="015ca-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="015ca-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="015ca-104">Note</span><span class="sxs-lookup"><span data-stu-id="015ca-104">Remarks</span></span>  
 <span data-ttu-id="015ca-105">Un'espressione che usa l'operatore di assegnazione `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="015ca-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="015ca-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="015ca-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="015ca-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="015ca-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="015ca-108">Per i tipi numerici, l'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) è predefinito per calcolare il resto dopo una divisione.</span><span class="sxs-lookup"><span data-stu-id="015ca-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="015ca-109">L'operatore `%=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) (vedere [operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="015ca-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="015ca-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="015ca-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="015ca-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="015ca-111">See Also</span></span>  
 [<span data-ttu-id="015ca-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="015ca-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="015ca-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="015ca-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="015ca-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="015ca-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
