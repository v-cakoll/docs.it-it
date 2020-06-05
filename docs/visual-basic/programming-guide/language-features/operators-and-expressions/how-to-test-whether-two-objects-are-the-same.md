---
title: 'Procedura: determinare se due oggetti sono uguali'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403421"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="c4830-102">Procedura: determinare se due oggetti sono uguali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4830-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="c4830-103">Se si dispone di due variabili che fanno riferimento a oggetti, è possibile utilizzare `Is` l' `IsNot` operatore OR oppure entrambi per determinare se si riferiscono alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="c4830-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="c4830-104">Per verificare se due oggetti sono uguali</span><span class="sxs-lookup"><span data-stu-id="c4830-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="c4830-105">Usare l'operatore [is](../../../language-reference/operators/is-operator.md) o l' [operatore](../../../language-reference/operators/isnot-operator.md) non con le due variabili come operandi.</span><span class="sxs-lookup"><span data-stu-id="c4830-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="c4830-106">Potrebbe essere necessario eseguire una determinata azione a seconda che due oggetti facciano riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="c4830-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="c4830-107">Nell'esempio precedente viene confrontato `c` il controllo con il controllo attivo sul form `f` .</span><span class="sxs-lookup"><span data-stu-id="c4830-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="c4830-108">Se non è presente alcun controllo attivo o se ne esiste uno, ma non è la stessa istanza del controllo di `c` , l' `If` istruzione ha esito negativo e la procedura restituisce senza ulteriori elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="c4830-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="c4830-109">Se si usa `Is` o `IsNot` è una questione di praticità.</span><span class="sxs-lookup"><span data-stu-id="c4830-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="c4830-110">Una può essere più facile da leggere rispetto all'altra in un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="c4830-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4830-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4830-111">See also</span></span>

- [<span data-ttu-id="c4830-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4830-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
