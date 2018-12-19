---
title: Operatore *= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: f8604cdadeda14a5761bc923bd966186fd258a6d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245350"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d0b0c-102">Operatore \*= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d0b0c-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="d0b0c-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b0c-104">Note</span><span class="sxs-lookup"><span data-stu-id="d0b0c-104">Remarks</span></span>  
 <span data-ttu-id="d0b0c-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d0b0c-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="d0b0c-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="d0b0c-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="d0b0c-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d0b0c-108">Per i tipi numerici, l'[operatore \*](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="d0b0c-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore \*](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="d0b0c-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0b0c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0b0c-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d0b0c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0b0c-111">See Also</span></span>

- [<span data-ttu-id="d0b0c-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d0b0c-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d0b0c-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d0b0c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d0b0c-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d0b0c-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
