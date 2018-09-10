---
title: Operatore ^= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857232"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="633ae-102">Operatore ^= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="633ae-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="633ae-103">Operatore di assegnazione OR esclusivo.</span><span class="sxs-lookup"><span data-stu-id="633ae-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="633ae-104">Note</span><span class="sxs-lookup"><span data-stu-id="633ae-104">Remarks</span></span>  
 <span data-ttu-id="633ae-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="633ae-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="633ae-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="633ae-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="633ae-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="633ae-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="633ae-108">L'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="633ae-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="633ae-109">L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="633ae-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="633ae-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="633ae-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="633ae-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="633ae-111">See Also</span></span>

- [<span data-ttu-id="633ae-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="633ae-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="633ae-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="633ae-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="633ae-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="633ae-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
