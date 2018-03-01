---
title: Operatore &amp; (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="69e91-102">Operatore &amp; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="69e91-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="69e91-103">L'operatore & ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="69e91-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e91-104">Note</span><span class="sxs-lookup"><span data-stu-id="69e91-104">Remarks</span></span>  
 <span data-ttu-id="69e91-105">L'operatore unario & restituisce l'indirizzo del relativo operando (richiede il contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="69e91-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="69e91-106">Gli operatori & binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="69e91-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="69e91-107">Per i tipi integrali, & calcola l'operatore AND logico bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="69e91-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="69e91-108">Per gli operandi `bool`, & calcola l'operatore AND logico dei relativi operandi, ovvero, il risultato è `true` se e solo se entrambi gli operandi sono `true`.</span><span class="sxs-lookup"><span data-stu-id="69e91-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="69e91-109">L'operatore `&` valuta entrambi gli operatori indipendentemente dal valore del primo.</span><span class="sxs-lookup"><span data-stu-id="69e91-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="69e91-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="69e91-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="69e91-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `&` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="69e91-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="69e91-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="69e91-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="69e91-113">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="69e91-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69e91-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="69e91-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="69e91-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69e91-115">See Also</span></span>  
 [<span data-ttu-id="69e91-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="69e91-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="69e91-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="69e91-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="69e91-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="69e91-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
