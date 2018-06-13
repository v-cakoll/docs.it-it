---
title: Operatore /= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171621"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c699d-102">Operatore /= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c699d-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="c699d-103">Operatore di assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="c699d-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c699d-104">Note</span><span class="sxs-lookup"><span data-stu-id="c699d-104">Remarks</span></span>  
 <span data-ttu-id="c699d-105">Un'espressione che usa l'operatore di assegnazione `/=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="c699d-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="c699d-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="c699d-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="c699d-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="c699d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="c699d-108">L'[operatore /](../../../csharp/language-reference/operators/division-operator.md) è già definito per i tipi numerici per l'esecuzione di divisioni.</span><span class="sxs-lookup"><span data-stu-id="c699d-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="c699d-109">L'operatore `/=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore /](../../../csharp/language-reference/operators/division-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c699d-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c699d-110">Su tutti gli operatori di assegnazione composti, l'overload dell'operatore binario esegue in modo implicito l'overload dell'assegnazione composta equivalente.</span><span class="sxs-lookup"><span data-stu-id="c699d-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c699d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c699d-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c699d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c699d-112">See Also</span></span>  
 [<span data-ttu-id="c699d-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c699d-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c699d-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c699d-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c699d-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c699d-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
