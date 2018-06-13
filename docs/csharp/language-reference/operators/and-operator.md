---
title: Operatore &amp; (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267880"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="b0d06-102">Operatore &amp; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b0d06-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="b0d06-103">L'operatore `&` ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="b0d06-103">The `&` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0d06-104">Note</span><span class="sxs-lookup"><span data-stu-id="b0d06-104">Remarks</span></span>  
 <span data-ttu-id="b0d06-105">L'operatore unario `&` restituisce l'indirizzo del relativo operando (richiede il contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="b0d06-105">The unary `&` operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="b0d06-106">Gli operatori `&` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="b0d06-106">Binary `&` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="b0d06-107">Per i tipi integrali, & calcola l'operatore AND logico bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="b0d06-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="b0d06-108">Per gli operandi `bool`, & calcola l'operatore AND logico dei relativi operandi, ovvero, il risultato è `true` se e solo se entrambi gli operandi sono `true`.</span><span class="sxs-lookup"><span data-stu-id="b0d06-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="b0d06-109">L'operatore binario `&` valuta entrambi gli operatori indipendentemente dal valore dal primo, diversamente dall'[operatore AND condizionale](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span><span class="sxs-lookup"><span data-stu-id="b0d06-109">The binary `&` operator evaluates both operators regardless of the first one's value, in contrast to the [conditional AND operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span></span> <span data-ttu-id="b0d06-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0d06-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="b0d06-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `&` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b0d06-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b0d06-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b0d06-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="b0d06-113">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="b0d06-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d06-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0d06-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b0d06-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0d06-115">See Also</span></span>  
 [<span data-ttu-id="b0d06-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b0d06-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b0d06-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b0d06-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0d06-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b0d06-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
