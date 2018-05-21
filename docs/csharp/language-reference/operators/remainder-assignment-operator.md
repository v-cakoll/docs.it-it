---
title: Operatore %= (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: aadcb5ef969ff408cc1e738fc0f5b67152fdc78b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="303ee-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="303ee-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="303ee-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="303ee-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="303ee-104">Note</span><span class="sxs-lookup"><span data-stu-id="303ee-104">Remarks</span></span>  
 <span data-ttu-id="303ee-105">Un'espressione che usa l'operatore di assegnazione `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="303ee-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="303ee-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="303ee-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="303ee-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="303ee-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="303ee-108">Per i tipi numerici, l'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) è predefinito per calcolare il resto dopo una divisione.</span><span class="sxs-lookup"><span data-stu-id="303ee-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="303ee-109">L'operatore `%=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore %](../../../csharp/language-reference/operators/remainder-operator.md) (vedere [operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="303ee-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="303ee-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="303ee-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="303ee-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="303ee-111">See Also</span></span>  
 [<span data-ttu-id="303ee-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="303ee-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="303ee-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="303ee-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="303ee-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="303ee-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
