---
title: Operatore = (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c7188abe54cb69678720b4dbbf4dbdea1be4abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2306c-102">Operatore = (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2306c-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="2306c-103">L'operatore di assegnazione (`=`) archivia il valore dell'operando a destra nella posizione di archiviazione, nella proprietà o nell'indicizzatore indicati dall'operando a sinistra e restituisce il valore come risultato.</span><span class="sxs-lookup"><span data-stu-id="2306c-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="2306c-104">Gli operandi devono essere dello stesso tipo (o l'operando destro deve essere convertibile in modo implicito nel tipo dell'operando a sinistra).</span><span class="sxs-lookup"><span data-stu-id="2306c-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2306c-105">Note</span><span class="sxs-lookup"><span data-stu-id="2306c-105">Remarks</span></span>  
 <span data-ttu-id="2306c-106">Non è possibile sottoporre l'operatore di assegnazione a overload.</span><span class="sxs-lookup"><span data-stu-id="2306c-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="2306c-107">Tuttavia, è possibile definire operatori di conversione implicita per un tipo, che consentono di usare l'operatore di assegnazione con tali tipi.</span><span class="sxs-lookup"><span data-stu-id="2306c-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="2306c-108">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="2306c-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2306c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2306c-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2306c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2306c-110">See Also</span></span>  
 [<span data-ttu-id="2306c-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2306c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2306c-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2306c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2306c-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="2306c-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
