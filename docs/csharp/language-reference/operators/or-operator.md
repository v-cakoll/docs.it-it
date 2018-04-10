---
title: Operatore | (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 374adc30e6937a68d67bfae152f2546c854b829b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2fb31-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2fb31-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="2fb31-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="2fb31-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="2fb31-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="2fb31-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="2fb31-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="2fb31-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fb31-106">Note</span><span class="sxs-lookup"><span data-stu-id="2fb31-106">Remarks</span></span>  
 <span data-ttu-id="2fb31-107">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="2fb31-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fb31-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fb31-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2fb31-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fb31-109">See Also</span></span>  
 [<span data-ttu-id="2fb31-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2fb31-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2fb31-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2fb31-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2fb31-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="2fb31-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
