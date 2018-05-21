---
title: Operatore ^= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: b868f2cdbfa8a80f89a12e6194a30154481f0b07
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b0de5-102">Operatore ^= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b0de5-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="b0de5-103">Operatore di assegnazione OR esclusivo.</span><span class="sxs-lookup"><span data-stu-id="b0de5-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0de5-104">Note</span><span class="sxs-lookup"><span data-stu-id="b0de5-104">Remarks</span></span>  
 <span data-ttu-id="b0de5-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="b0de5-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="b0de5-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="b0de5-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="b0de5-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b0de5-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b0de5-108">L'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="b0de5-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="b0de5-109">L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b0de5-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0de5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0de5-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b0de5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0de5-111">See Also</span></span>  
 [<span data-ttu-id="b0de5-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b0de5-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b0de5-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b0de5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0de5-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b0de5-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
