---
title: Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '<typename>'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: e5acc94a3738fca3a43740bdba727fc843132aa1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402811"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="49339-102">Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '\<typename>'</span><span class="sxs-lookup"><span data-stu-id="49339-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="49339-103">L' `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="49339-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="49339-104">Questo confronto non è definito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="49339-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="49339-105">**ID errore:** BC30020</span><span class="sxs-lookup"><span data-stu-id="49339-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="49339-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="49339-106">To correct this error</span></span>  
  
- <span data-ttu-id="49339-107">Utilizzare l'operatore di confronto aritmetico appropriato o l' `Like` operatore per confrontare due tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="49339-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49339-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49339-108">See also</span></span>

- [<span data-ttu-id="49339-109">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="49339-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="49339-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="49339-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="49339-111">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="49339-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
