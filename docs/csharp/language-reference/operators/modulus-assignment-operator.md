---
title: Operatore %= (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="ebc3e-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ebc3e-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="ebc3e-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="ebc3e-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebc3e-104">Note</span><span class="sxs-lookup"><span data-stu-id="ebc3e-104">Remarks</span></span>  
 <span data-ttu-id="ebc3e-105">Un'espressione che usa l'operatore di assegnazione `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="ebc3e-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="ebc3e-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="ebc3e-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="ebc3e-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ebc3e-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ebc3e-108">Per i tipi numerici, l'[operatore %](../../../csharp/language-reference/operators/modulus-operator.md) è predefinito per calcolare il resto dopo una divisione.</span><span class="sxs-lookup"><span data-stu-id="ebc3e-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="ebc3e-109">L'operatore `%=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore %](../../../csharp/language-reference/operators/modulus-operator.md) (vedere [operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ebc3e-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebc3e-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebc3e-110">Example</span></span>  
 <span data-ttu-id="ebc3e-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebc3e-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc3e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebc3e-112">See Also</span></span>  
 <span data-ttu-id="ebc3e-113">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ebc3e-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ebc3e-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ebc3e-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ebc3e-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="ebc3e-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

