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
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028177"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bde72-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bde72-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="bde72-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="bde72-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="bde72-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="bde72-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="bde72-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="bde72-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bde72-106">Note</span><span class="sxs-lookup"><span data-stu-id="bde72-106">Remarks</span></span>  
 <span data-ttu-id="bde72-107">L'operatore binario `|` valuta i due operatori indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale](conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="bde72-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="bde72-108">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bde72-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde72-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bde72-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bde72-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bde72-110">See Also</span></span>

- [<span data-ttu-id="bde72-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bde72-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bde72-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bde72-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bde72-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="bde72-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
