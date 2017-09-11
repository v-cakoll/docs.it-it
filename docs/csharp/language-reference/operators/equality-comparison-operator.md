---
title: Operatore == (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
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
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="936f8-102">Operatore == (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="936f8-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="936f8-103">Per i tipi valore predefiniti, l'operatore di uguaglianza (`==`) restituisce true se i valori degli operandi sono uguali, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="936f8-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="936f8-104">Per i tipi riferimento diversi da [string](../../../csharp/language-reference/keywords/string.md), `==` restituisce `true` se i due operandi fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="936f8-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="936f8-105">Per il tipo `string`, `==` confronta i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="936f8-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="936f8-106">Note</span><span class="sxs-lookup"><span data-stu-id="936f8-106">Remarks</span></span>  
 <span data-ttu-id="936f8-107">I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `==` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="936f8-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="936f8-108">Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `==` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="936f8-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="936f8-109">Se `==` è sottoposto a overload, deve esserlo anche [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="936f8-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="936f8-110">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="936f8-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="936f8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="936f8-111">Example</span></span>  
 <span data-ttu-id="936f8-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="936f8-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936f8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="936f8-113">See Also</span></span>  
 <span data-ttu-id="936f8-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="936f8-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="936f8-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="936f8-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="936f8-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="936f8-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

