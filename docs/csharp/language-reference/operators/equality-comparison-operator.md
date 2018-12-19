---
title: Operatore == - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239014"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ab043-102">Operatore == (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ab043-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="ab043-103">Per i tipi valore predefiniti, l'operatore di uguaglianza (`==`) restituisce true se i valori degli operandi sono uguali, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="ab043-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="ab043-104">Per i tipi riferimento diversi da [string](../../../csharp/language-reference/keywords/string.md), `==` restituisce `true` se i due operandi fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="ab043-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="ab043-105">Per il tipo `string`, `==` confronta i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="ab043-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab043-106">Note</span><span class="sxs-lookup"><span data-stu-id="ab043-106">Remarks</span></span>  
 <span data-ttu-id="ab043-107">I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `==` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ab043-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="ab043-108">Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `==` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ab043-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="ab043-109">Se `==` è sottoposto a overload, deve esserlo anche [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab043-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="ab043-110">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ab043-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab043-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab043-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ab043-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab043-112">See Also</span></span>

- [<span data-ttu-id="ab043-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ab043-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ab043-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ab043-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ab043-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="ab043-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
