---
title: Operatore &lt;&lt;= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171793"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="41490-102">Operatore &lt;&lt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="41490-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="41490-103">Operatore di assegnazione di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="41490-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41490-104">Note</span><span class="sxs-lookup"><span data-stu-id="41490-104">Remarks</span></span>  
 <span data-ttu-id="41490-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="41490-105">An expression of the form</span></span>  
  
```csharp  
x <<= y  
```  
  
 <span data-ttu-id="41490-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="41490-106">is evaluated as</span></span>  
  
```csharp  
x = x << y  
```  
  
 <span data-ttu-id="41490-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="41490-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="41490-108">L'[operatore <<](../../../csharp/language-reference/operators/left-shift-operator.md) sposta `x` verso sinistra del numero di bit specificato da `y`.</span><span class="sxs-lookup"><span data-stu-id="41490-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="41490-109">L'operatore `<<=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="41490-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41490-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="41490-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="41490-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41490-111">See Also</span></span>  
 [<span data-ttu-id="41490-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="41490-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="41490-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="41490-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="41490-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="41490-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
