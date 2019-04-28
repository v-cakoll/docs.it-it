---
title: Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '<typename>'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: b828de196a12128a9f34ee1f9ff1e57fee22c687
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799190"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="1d04b-102">Gli operandi con tipi di riferimento 'Is' devono, ma questo operando ha tipo valore '\<nomeTipo >'</span><span class="sxs-lookup"><span data-stu-id="1d04b-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="1d04b-103">Il `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="1d04b-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="1d04b-104">Questo confronto non è definito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="1d04b-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="1d04b-105">**ID errore:** BC30020</span><span class="sxs-lookup"><span data-stu-id="1d04b-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d04b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1d04b-106">To correct this error</span></span>  
  
- <span data-ttu-id="1d04b-107">Usare l'operatore di confronto aritmetico appropriato o `Like` operatore per confrontare due tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="1d04b-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d04b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d04b-108">See also</span></span>

- [<span data-ttu-id="1d04b-109">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="1d04b-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="1d04b-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="1d04b-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="1d04b-111">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="1d04b-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
