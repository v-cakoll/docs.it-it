---
title: Operatore *= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 6bbf2142ca7e9e05010a29920da52e1439f6e882
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171550"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="66208-102">Operatore \*= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="66208-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="66208-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="66208-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66208-104">Note</span><span class="sxs-lookup"><span data-stu-id="66208-104">Remarks</span></span>  
 <span data-ttu-id="66208-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="66208-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="66208-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="66208-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="66208-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="66208-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="66208-108">Per i tipi numerici, l'[operatore \*](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="66208-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="66208-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="66208-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66208-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="66208-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="66208-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66208-111">See Also</span></span>  
 [<span data-ttu-id="66208-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="66208-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="66208-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="66208-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="66208-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="66208-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
