---
title: Operatore *= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517168"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e8777-102">Operatore \*= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e8777-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="e8777-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="e8777-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8777-104">Note</span><span class="sxs-lookup"><span data-stu-id="e8777-104">Remarks</span></span>  
 <span data-ttu-id="e8777-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="e8777-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="e8777-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="e8777-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="e8777-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e8777-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e8777-108">Per i tipi numerici, l'[operatore \*](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8777-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="e8777-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore \*](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e8777-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8777-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8777-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e8777-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8777-111">See Also</span></span>

- [<span data-ttu-id="e8777-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e8777-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e8777-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e8777-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e8777-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="e8777-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
