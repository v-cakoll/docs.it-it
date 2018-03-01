---
title: Operatore == (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0f5b8-102">Operatore == (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0f5b8-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="0f5b8-103">Per i tipi valore predefiniti, l'operatore di uguaglianza (`==`) restituisce true se i valori degli operandi sono uguali, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="0f5b8-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="0f5b8-104">Per i tipi riferimento diversi da [string](../../../csharp/language-reference/keywords/string.md), `==` restituisce `true` se i due operandi fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="0f5b8-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="0f5b8-105">Per il tipo `string`, `==` confronta i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="0f5b8-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f5b8-106">Note</span><span class="sxs-lookup"><span data-stu-id="0f5b8-106">Remarks</span></span>  
 <span data-ttu-id="0f5b8-107">I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `==` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0f5b8-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="0f5b8-108">Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `==` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0f5b8-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="0f5b8-109">Se `==` è sottoposto a overload, deve esserlo anche [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0f5b8-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="0f5b8-110">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0f5b8-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f5b8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f5b8-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0f5b8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f5b8-112">See Also</span></span>  
 [<span data-ttu-id="0f5b8-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0f5b8-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0f5b8-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0f5b8-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0f5b8-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0f5b8-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
