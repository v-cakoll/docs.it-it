---
title: Operatore ^ (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3f57e-102">Operatore ^ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3f57e-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="3f57e-103">Gli operatori `^` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="3f57e-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="3f57e-104">Per i tipi integrali, `^` calcola l'operazione di OR esclusivo bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="3f57e-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="3f57e-105">Per gli operandi `bool`, `^` calcola l'operazione di OR esclusivo logico dei relativi operandi, ovvero, il risultato è `true` se e solo se esattamente uno degli operandi è `true`.</span><span class="sxs-lookup"><span data-stu-id="3f57e-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f57e-106">Note</span><span class="sxs-lookup"><span data-stu-id="3f57e-106">Remarks</span></span>  
 <span data-ttu-id="3f57e-107">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `^` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3f57e-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3f57e-108">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f57e-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f57e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f57e-109">Example</span></span>  
 <span data-ttu-id="3f57e-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f57e-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="3f57e-111">Il calcolo di `0xf8 ^ 0x3f` nell'esempio precedente esegue un'operazione di OR esclusivo bit per bit dei due valori binari seguenti, che corrispondono ai valori esadecimali F8 e 3F:</span><span class="sxs-lookup"><span data-stu-id="3f57e-111">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="3f57e-112">Il risultato dell'operazione di OR esclusivo è `1100 0111`, ovvero C7 in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="3f57e-112">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f57e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f57e-113">See Also</span></span>  
 <span data-ttu-id="3f57e-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f57e-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3f57e-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f57e-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3f57e-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3f57e-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

