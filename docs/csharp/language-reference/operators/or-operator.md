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
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085705"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2817-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a2817-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="a2817-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="a2817-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="a2817-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="a2817-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="a2817-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="a2817-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2817-106">Note</span><span class="sxs-lookup"><span data-stu-id="a2817-106">Remarks</span></span>  
 <span data-ttu-id="a2817-107">L'operatore binario `|` valuta entrambi gli operandi indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale] (conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="a2817-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator]     (conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="a2817-108">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a2817-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2817-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2817-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2817-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2817-110">See Also</span></span>

- [<span data-ttu-id="a2817-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a2817-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a2817-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a2817-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2817-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a2817-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
