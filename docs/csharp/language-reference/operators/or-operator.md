---
title: Operatore | (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 7b62af53f0d8b7cba29f4496887717f1726eabf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265687"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="78097-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="78097-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="78097-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="78097-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="78097-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="78097-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="78097-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="78097-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78097-106">Note</span><span class="sxs-lookup"><span data-stu-id="78097-106">Remarks</span></span>  
 <span data-ttu-id="78097-107">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="78097-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78097-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="78097-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="78097-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78097-109">See Also</span></span>  
 [<span data-ttu-id="78097-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="78097-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="78097-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="78097-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="78097-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="78097-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
