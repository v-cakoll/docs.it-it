---
title: Operatore *= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc2201f78e1e05bd0ccdea04522896c00294bdd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bf44b-102">Operatore *= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bf44b-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="bf44b-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="bf44b-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf44b-104">Note</span><span class="sxs-lookup"><span data-stu-id="bf44b-104">Remarks</span></span>  
 <span data-ttu-id="bf44b-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="bf44b-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="bf44b-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="bf44b-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="bf44b-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="bf44b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="bf44b-108">Per i tipi numerici, l'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="bf44b-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="bf44b-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bf44b-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf44b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf44b-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bf44b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf44b-111">See Also</span></span>  
 [<span data-ttu-id="bf44b-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bf44b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bf44b-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bf44b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bf44b-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="bf44b-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
