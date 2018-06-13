---
title: '&#39;È&#39; richiede operandi che hanno tipi di riferimento, ma questo operando ha tipo di valore &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 07838e62bd6b180f7dece79355ea7aa1d6c4527a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585580"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="b00ff-102">&#39;È&#39; richiede operandi che hanno tipi di riferimento, ma questo operando ha tipo di valore &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="b00ff-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="b00ff-103">Il `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b00ff-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="b00ff-104">Questo confronto non è definito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="b00ff-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="b00ff-105">**ID errore:** BC30020</span><span class="sxs-lookup"><span data-stu-id="b00ff-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b00ff-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b00ff-106">To correct this error</span></span>  
  
-   <span data-ttu-id="b00ff-107">Usare l'operatore di confronto aritmetico appropriato o `Like` l'operatore per confrontare due tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="b00ff-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00ff-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b00ff-108">See Also</span></span>  
 [<span data-ttu-id="b00ff-109">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="b00ff-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="b00ff-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="b00ff-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="b00ff-111">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="b00ff-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
