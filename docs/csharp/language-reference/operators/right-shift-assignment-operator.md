---
title: Operatore &gt;&gt;= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: aebc92ffb007db7b4950313874ebc2bf3c40615f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239446"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="f309c-102">Operatore &gt;&gt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f309c-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="f309c-103">Operatore di assegnazione di spostamento a destra.</span><span class="sxs-lookup"><span data-stu-id="f309c-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f309c-104">Note</span><span class="sxs-lookup"><span data-stu-id="f309c-104">Remarks</span></span>  
 <span data-ttu-id="f309c-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="f309c-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="f309c-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="f309c-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="f309c-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="f309c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f309c-108">L'[operatore >>](../../../csharp/language-reference/operators/right-shift-operator.md) sposta `x` verso destra di una quantità specificata da `y`.</span><span class="sxs-lookup"><span data-stu-id="f309c-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="f309c-109">L'operatore >>= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="f309c-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f309c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="f309c-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f309c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f309c-111">See Also</span></span>

- [<span data-ttu-id="f309c-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f309c-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f309c-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f309c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f309c-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f309c-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
