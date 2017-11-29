---
title: Operatore % (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="32d5d-102">Operatore % (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="32d5d-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="32d5d-103">L'operatore `%` calcola il resto dopo aver diviso il primo operando per il secondo.</span><span class="sxs-lookup"><span data-stu-id="32d5d-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="32d5d-104">Tutti i tipi numerici hanno operatori di resto predefiniti.</span><span class="sxs-lookup"><span data-stu-id="32d5d-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32d5d-105">Note</span><span class="sxs-lookup"><span data-stu-id="32d5d-105">Remarks</span></span>  
 <span data-ttu-id="32d5d-106">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `%` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="32d5d-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="32d5d-107">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="32d5d-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32d5d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="32d5d-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="32d5d-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="32d5d-109">Comments</span></span>  
 <span data-ttu-id="32d5d-110">Osservare gli errori di arrotondamento associati al tipo double.</span><span class="sxs-lookup"><span data-stu-id="32d5d-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d5d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32d5d-111">See Also</span></span>  
 [<span data-ttu-id="32d5d-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="32d5d-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="32d5d-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="32d5d-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="32d5d-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="32d5d-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
