---
title: Operatore = (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="85139-102">Operatore = (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="85139-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="85139-103">L'operatore di assegnazione (`=`) archivia il valore dell'operando a destra nella posizione di archiviazione, nella proprietà o nell'indicizzatore indicati dall'operando a sinistra e restituisce il valore come risultato.</span><span class="sxs-lookup"><span data-stu-id="85139-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="85139-104">Gli operandi devono essere dello stesso tipo (o l'operando destro deve essere convertibile in modo implicito nel tipo dell'operando a sinistra).</span><span class="sxs-lookup"><span data-stu-id="85139-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85139-105">Note</span><span class="sxs-lookup"><span data-stu-id="85139-105">Remarks</span></span>  
 <span data-ttu-id="85139-106">Non è possibile sottoporre l'operatore di assegnazione a overload.</span><span class="sxs-lookup"><span data-stu-id="85139-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="85139-107">Tuttavia, è possibile definire operatori di conversione implicita per un tipo, che consentono di usare l'operatore di assegnazione con tali tipi.</span><span class="sxs-lookup"><span data-stu-id="85139-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="85139-108">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="85139-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85139-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="85139-109">Example</span></span>  
 <span data-ttu-id="85139-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="85139-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85139-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85139-111">See Also</span></span>  
 <span data-ttu-id="85139-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="85139-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="85139-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="85139-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="85139-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="85139-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

