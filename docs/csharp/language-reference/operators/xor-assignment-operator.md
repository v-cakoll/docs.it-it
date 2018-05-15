---
title: Operatore ^= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 0315cab66729d8169527c4b0ba7e00ab3b5ad5da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1cc52-102">Operatore ^= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1cc52-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="1cc52-103">Operatore di assegnazione OR esclusivo.</span><span class="sxs-lookup"><span data-stu-id="1cc52-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cc52-104">Note</span><span class="sxs-lookup"><span data-stu-id="1cc52-104">Remarks</span></span>  
 <span data-ttu-id="1cc52-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="1cc52-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="1cc52-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="1cc52-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="1cc52-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1cc52-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="1cc52-108">L'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="1cc52-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="1cc52-109">L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](../../../csharp/language-reference/operators/xor-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="1cc52-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cc52-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="1cc52-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc52-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc52-111">See Also</span></span>  
 [<span data-ttu-id="1cc52-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1cc52-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1cc52-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1cc52-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1cc52-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1cc52-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
