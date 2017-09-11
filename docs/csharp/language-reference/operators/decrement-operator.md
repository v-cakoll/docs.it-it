---
title: Operatore -- (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="db0cb-102">Operatore -- (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="db0cb-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="db0cb-103">L'operatore di decremento (`--`) decrementa il proprio operando di 1.</span><span class="sxs-lookup"><span data-stu-id="db0cb-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="db0cb-104">L'operatore di decremento può apparire prima o dopo il proprio operando: `--variable` e `variable--`.</span><span class="sxs-lookup"><span data-stu-id="db0cb-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="db0cb-105">Il primo esempio è un'operazione di decremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="db0cb-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="db0cb-106">Il risultato dell'operazione è il valore dell'operando "dopo" essere stato decrementato.</span><span class="sxs-lookup"><span data-stu-id="db0cb-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="db0cb-107">Il secondo esempio è un'operazione di decremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="db0cb-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="db0cb-108">Il risultato dell'operazione è il valore dell'operando "prima" di essere decrementato.</span><span class="sxs-lookup"><span data-stu-id="db0cb-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db0cb-109">Note</span><span class="sxs-lookup"><span data-stu-id="db0cb-109">Remarks</span></span>  
 <span data-ttu-id="db0cb-110">I tipi numerico e di enumerazione hanno operatori di decremento predefiniti.</span><span class="sxs-lookup"><span data-stu-id="db0cb-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="db0cb-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `--` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="db0cb-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="db0cb-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="db0cb-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db0cb-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="db0cb-113">Example</span></span>  
 <span data-ttu-id="db0cb-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="db0cb-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db0cb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db0cb-115">See Also</span></span>  
 <span data-ttu-id="db0cb-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="db0cb-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="db0cb-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="db0cb-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="db0cb-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="db0cb-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

