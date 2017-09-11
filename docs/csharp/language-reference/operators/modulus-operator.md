---
title: Operatore % (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
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
ms.openlocfilehash: 658b04f4bee952a20a7b0a740aa931fe4fad9cdf
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="50531-102">Operatore % (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="50531-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="50531-103">L'operatore `%` calcola il resto dopo aver diviso il primo operando per il secondo.</span><span class="sxs-lookup"><span data-stu-id="50531-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="50531-104">Tutti i tipi numerici hanno operatori di resto predefiniti.</span><span class="sxs-lookup"><span data-stu-id="50531-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50531-105">Note</span><span class="sxs-lookup"><span data-stu-id="50531-105">Remarks</span></span>  
 <span data-ttu-id="50531-106">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `%` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="50531-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="50531-107">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="50531-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50531-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="50531-108">Example</span></span>  
 <span data-ttu-id="50531-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="50531-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="50531-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="50531-110">Comments</span></span>  
 <span data-ttu-id="50531-111">Osservare gli errori di arrotondamento associati al tipo double.</span><span class="sxs-lookup"><span data-stu-id="50531-111">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50531-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50531-112">See Also</span></span>  
 <span data-ttu-id="50531-113">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="50531-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="50531-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="50531-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="50531-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="50531-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

