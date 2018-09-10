---
title: Operatore /= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 8fff048cc441181aa3f0e3c0c638d501aaf9de3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526308"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8de65-102">Operatore /= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8de65-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="8de65-103">Operatore di assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="8de65-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8de65-104">Note</span><span class="sxs-lookup"><span data-stu-id="8de65-104">Remarks</span></span>  
 <span data-ttu-id="8de65-105">Un'espressione che usa l'operatore di assegnazione `/=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="8de65-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="8de65-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="8de65-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="8de65-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8de65-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8de65-108">L'[operatore /](../../../csharp/language-reference/operators/division-operator.md) è già definito per i tipi numerici per l'esecuzione di divisioni.</span><span class="sxs-lookup"><span data-stu-id="8de65-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="8de65-109">L'operatore `/=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore /](../../../csharp/language-reference/operators/division-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8de65-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8de65-110">Su tutti gli operatori di assegnazione composti, l'overload dell'operatore binario esegue in modo implicito l'overload dell'assegnazione composta equivalente.</span><span class="sxs-lookup"><span data-stu-id="8de65-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8de65-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8de65-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8de65-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de65-112">See Also</span></span>

- [<span data-ttu-id="8de65-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8de65-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8de65-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8de65-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8de65-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8de65-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
