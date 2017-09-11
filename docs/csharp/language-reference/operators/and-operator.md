---
title: Operatore &amp; (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="12464-102">Operatore &amp; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="12464-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="12464-103">L'operatore & ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="12464-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12464-104">Note</span><span class="sxs-lookup"><span data-stu-id="12464-104">Remarks</span></span>  
 <span data-ttu-id="12464-105">L'operatore unario & restituisce l'indirizzo del relativo operando (richiede il contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="12464-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="12464-106">Gli operatori & binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="12464-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="12464-107">Per i tipi integrali, & calcola l'operatore AND logico bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="12464-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="12464-108">Per gli operandi `bool`, & calcola l'operatore AND logico dei relativi operandi, ovvero, il risultato è `true` se e solo se entrambi gli operandi sono `true`.</span><span class="sxs-lookup"><span data-stu-id="12464-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="12464-109">L'operatore `&` valuta entrambi gli operatori indipendentemente dal valore del primo.</span><span class="sxs-lookup"><span data-stu-id="12464-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="12464-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="12464-110">For example:</span></span>  
  
 <span data-ttu-id="12464-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="12464-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="12464-112">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `&` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="12464-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="12464-113">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="12464-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="12464-114">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="12464-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12464-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="12464-115">Example</span></span>  
 <span data-ttu-id="12464-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="12464-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12464-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12464-117">See Also</span></span>  
 <span data-ttu-id="12464-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="12464-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="12464-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="12464-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="12464-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="12464-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

