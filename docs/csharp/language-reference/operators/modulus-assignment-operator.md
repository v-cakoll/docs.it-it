---
title: Operatore %= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%=_CSharpKeyword'
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9bafd0078153e29fbf923948d9b380d4795c3d35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e7168-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e7168-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="e7168-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="e7168-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7168-104">Note</span><span class="sxs-lookup"><span data-stu-id="e7168-104">Remarks</span></span>  
 <span data-ttu-id="e7168-105">Un'espressione che usa l'operatore di assegnazione `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="e7168-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="e7168-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="e7168-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="e7168-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e7168-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e7168-108">Per i tipi numerici, l'[operatore %](../../../csharp/language-reference/operators/modulus-operator.md) è predefinito per calcolare il resto dopo una divisione.</span><span class="sxs-lookup"><span data-stu-id="e7168-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="e7168-109">L'operatore `%=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore %](../../../csharp/language-reference/operators/modulus-operator.md) (vedere [operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e7168-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7168-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7168-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e7168-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7168-111">See Also</span></span>  
 [<span data-ttu-id="e7168-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e7168-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e7168-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e7168-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e7168-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="e7168-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
