---
title: Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '<typename>'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 65fbba9689ae01d8156bd0b3e2efeb6b75bd79e2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625949"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="da76f-102">Gli operandi con tipi di riferimento 'Is' devono, ma questo operando ha tipo valore '\<nomeTipo >'</span><span class="sxs-lookup"><span data-stu-id="da76f-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="da76f-103">Il `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="da76f-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="da76f-104">Questo confronto non è definito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="da76f-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="da76f-105">**ID errore:** BC30020</span><span class="sxs-lookup"><span data-stu-id="da76f-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da76f-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="da76f-106">To correct this error</span></span>  
  
- <span data-ttu-id="da76f-107">Usare l'operatore di confronto aritmetico appropriato o `Like` operatore per confrontare due tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="da76f-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da76f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da76f-108">See also</span></span>

- [<span data-ttu-id="da76f-109">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="da76f-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="da76f-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="da76f-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="da76f-111">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="da76f-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
