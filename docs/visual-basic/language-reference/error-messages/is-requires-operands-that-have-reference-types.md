---
title: '&#39;È&#39; richiede operandi che hanno tipi di riferimento, ma questo operando ha tipo valore &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 0b3f80e98087e455ec730dea8c57478528e9259c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722920"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="06c29-102">&#39;È&#39; richiede operandi che hanno tipi di riferimento, ma questo operando ha tipo valore &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="06c29-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="06c29-103">Il `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="06c29-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="06c29-104">Questo confronto non è definito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="06c29-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="06c29-105">**ID errore:** BC30020</span><span class="sxs-lookup"><span data-stu-id="06c29-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06c29-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="06c29-106">To correct this error</span></span>  
  
-   <span data-ttu-id="06c29-107">Usare l'operatore di confronto aritmetico appropriato o `Like` operatore per confrontare due tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="06c29-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c29-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06c29-108">See also</span></span>
- [<span data-ttu-id="06c29-109">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="06c29-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="06c29-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="06c29-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="06c29-111">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="06c29-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
