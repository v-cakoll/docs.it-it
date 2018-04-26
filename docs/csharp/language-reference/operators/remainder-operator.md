---
title: Operatore % (Riferimenti per C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c4302-102">Operatore % (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c4302-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="c4302-103">L'operatore di resto (`%`) calcola il resto dopo aver diviso il primo operando per il secondo.</span><span class="sxs-lookup"><span data-stu-id="c4302-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="c4302-104">Tutti i tipi numerici hanno operatori di resto predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c4302-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c4302-105">Note</span><span class="sxs-lookup"><span data-stu-id="c4302-105">Remarks</span></span>  
 <span data-ttu-id="c4302-106">La formula `a % b` restituirà sempre un valore nell'intervallo `(-b, b)`, esclusi (non può mai restituire `b` o `-b`), mantenendo il segno del dividendo.</span><span class="sxs-lookup"><span data-stu-id="c4302-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="c4302-107">Per la divisione di interi, l'operatore di resto soddisfa la regola `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="c4302-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="c4302-108">Questa operazione non deve essere confusa con il modulo canonico, che soddisfa una regola simile ma con una divisione con arrotondamento all'intero più grande (floor) e restituisce valori nell'intervallo `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="c4302-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="c4302-109">C# non include un operatore per il modulo canonico.</span><span class="sxs-lookup"><span data-stu-id="c4302-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="c4302-110">Tuttavia, il comportamento è lo stesso per i dividendi positivi.</span><span class="sxs-lookup"><span data-stu-id="c4302-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="c4302-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `%` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c4302-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c4302-112">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="c4302-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4302-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4302-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="c4302-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="c4302-114">Comments</span></span>  
 <span data-ttu-id="c4302-115">Osservare gli errori di arrotondamento associati al tipo double.</span><span class="sxs-lookup"><span data-stu-id="c4302-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4302-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4302-116">See Also</span></span>  
 [<span data-ttu-id="c4302-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c4302-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c4302-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c4302-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c4302-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c4302-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
