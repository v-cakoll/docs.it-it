---
title: Operatore -- (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 25f301bc0b2bc9bf51b0a44f26b2efabae00e452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288801"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="7a924-102">Operatore -- (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7a924-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="7a924-103">L'operatore di decremento (`--`) decrementa il proprio operando di 1.</span><span class="sxs-lookup"><span data-stu-id="7a924-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="7a924-104">L'operatore di decremento può apparire prima o dopo il proprio operando: `--variable` e `variable--`.</span><span class="sxs-lookup"><span data-stu-id="7a924-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="7a924-105">Il primo esempio è un'operazione di decremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="7a924-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="7a924-106">Il risultato dell'operazione è il valore dell'operando "dopo" essere stato decrementato.</span><span class="sxs-lookup"><span data-stu-id="7a924-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="7a924-107">Il secondo esempio è un'operazione di decremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="7a924-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="7a924-108">Il risultato dell'operazione è il valore dell'operando "prima" di essere decrementato.</span><span class="sxs-lookup"><span data-stu-id="7a924-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a924-109">Note</span><span class="sxs-lookup"><span data-stu-id="7a924-109">Remarks</span></span>  
 <span data-ttu-id="7a924-110">I tipi numerico e di enumerazione hanno operatori di decremento predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7a924-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="7a924-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `--` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7a924-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7a924-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7a924-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a924-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a924-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7a924-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a924-114">See Also</span></span>  
 [<span data-ttu-id="7a924-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7a924-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7a924-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7a924-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7a924-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7a924-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
