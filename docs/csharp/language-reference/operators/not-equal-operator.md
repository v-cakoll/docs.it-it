---
title: Operatore != (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
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
ms.openlocfilehash: 49c5c9668c6b1169220ee4fa0babf167292a9813
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="97f35-102">Operatore != (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="97f35-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="97f35-103">L'operatore di disuguaglianza (`!=`) restituisce false se gli operandi sono uguali, in caso contrario true.</span><span class="sxs-lookup"><span data-stu-id="97f35-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="97f35-104">Gli operatori di disuguaglianza sono predefiniti per tutti i tipi, inclusi string e object.</span><span class="sxs-lookup"><span data-stu-id="97f35-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="97f35-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `!=`.</span><span class="sxs-lookup"><span data-stu-id="97f35-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f35-106">Note</span><span class="sxs-lookup"><span data-stu-id="97f35-106">Remarks</span></span>  
 <span data-ttu-id="97f35-107">Per i tipi valore predefiniti, l'operatore di disuguaglianza (`!=`) restituisce true se i valori degli operandi sono diversi, in caso contrario false.</span><span class="sxs-lookup"><span data-stu-id="97f35-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="97f35-108">Per i tipi riferimento diversi da `string`, `!=` restituisce true se i due operandi fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="97f35-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="97f35-109">Per il tipo `string`, `!=` confronta i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="97f35-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="97f35-110">I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `!=` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="97f35-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="97f35-111">Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `!=` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="97f35-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="97f35-112">Se `!=` è sottoposto a overload, deve esserlo anche [==](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="97f35-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="97f35-113">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="97f35-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f35-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="97f35-114">Example</span></span>  
 <span data-ttu-id="97f35-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="97f35-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f35-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f35-116">See Also</span></span>  
 <span data-ttu-id="97f35-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="97f35-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="97f35-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="97f35-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="97f35-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="97f35-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

