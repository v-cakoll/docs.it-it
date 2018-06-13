---
title: Operatore |= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: 18246d013275c8d6c8ad7e05409387457afc3442
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171517"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fd463-102">Operatore |= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fd463-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="fd463-103">Operatore di assegnazione OR.</span><span class="sxs-lookup"><span data-stu-id="fd463-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd463-104">Note</span><span class="sxs-lookup"><span data-stu-id="fd463-104">Remarks</span></span>  
 <span data-ttu-id="fd463-105">Un'espressione che usa l'operatore di assegnazione `|=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="fd463-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="fd463-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="fd463-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="fd463-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="fd463-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="fd463-108">L'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) esegue un'operazione con OR logico bit per bit su operandi integrali e un'operazione con OR logico sugli operandi bool.</span><span class="sxs-lookup"><span data-stu-id="fd463-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="fd463-109">L'operatore `|=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fd463-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd463-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd463-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fd463-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd463-111">See Also</span></span>  
 [<span data-ttu-id="fd463-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fd463-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fd463-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fd463-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fd463-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="fd463-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
