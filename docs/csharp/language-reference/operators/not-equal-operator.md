---
title: Operatore != (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: e974ffb1b25944e24fca23864dc7e932ec1876d5
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45597095"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c80fb-102">Operatore != (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c80fb-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="c80fb-103">L'operatore di disuguaglianza (`!=`) restituisce false se gli operandi sono uguali, in caso contrario true.</span><span class="sxs-lookup"><span data-stu-id="c80fb-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="c80fb-104">Gli operatori di disuguaglianza sono predefiniti per tutti i tipi, inclusi string e object.</span><span class="sxs-lookup"><span data-stu-id="c80fb-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="c80fb-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `!=`.</span><span class="sxs-lookup"><span data-stu-id="c80fb-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c80fb-106">Note</span><span class="sxs-lookup"><span data-stu-id="c80fb-106">Remarks</span></span>  
 <span data-ttu-id="c80fb-107">Per i tipi valore predefiniti, l'operatore di disuguaglianza (`!=`) restituisce true se i valori degli operandi sono diversi, in caso contrario false.</span><span class="sxs-lookup"><span data-stu-id="c80fb-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="c80fb-108">Per i tipi riferimento diversi da `string`, `!=` restituisce true se i due operandi fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="c80fb-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="c80fb-109">Per il tipo `string`, `!=` confronta i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="c80fb-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="c80fb-110">I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `!=` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c80fb-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c80fb-111">Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `!=` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c80fb-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="c80fb-112">Se `!=` è sottoposto a overload, deve esserlo anche [==](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c80fb-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="c80fb-113">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c80fb-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c80fb-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="c80fb-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c80fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c80fb-115">See Also</span></span>

- [<span data-ttu-id="c80fb-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c80fb-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c80fb-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c80fb-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c80fb-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c80fb-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
