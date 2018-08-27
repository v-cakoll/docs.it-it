---
title: Operatore |= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929914"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="699d6-102">Operatore |= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="699d6-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="699d6-103">Operatore di assegnazione OR.</span><span class="sxs-lookup"><span data-stu-id="699d6-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="699d6-104">Note</span><span class="sxs-lookup"><span data-stu-id="699d6-104">Remarks</span></span>  
 <span data-ttu-id="699d6-105">Un'espressione che usa l'operatore di assegnazione `|=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="699d6-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="699d6-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="699d6-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="699d6-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="699d6-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="699d6-108">L'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) esegue un'operazione con OR logico bit per bit su operandi integrali e un'operazione con OR logico sugli operandi bool.</span><span class="sxs-lookup"><span data-stu-id="699d6-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="699d6-109">L'operatore `|=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &#124;](../../../csharp/language-reference/operators/or-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="699d6-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="699d6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="699d6-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="699d6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="699d6-111">See Also</span></span>

- [<span data-ttu-id="699d6-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="699d6-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="699d6-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="699d6-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="699d6-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="699d6-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
