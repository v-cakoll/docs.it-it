---
title: 'Procedura: determinare se due oggetti sono uguali (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 005c91e6f4ec556a7e1bf255b47c8276a5d3d185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647605"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="0abf9-102">Procedura: determinare se due oggetti sono uguali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0abf9-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="0abf9-103">Se si dispone di due variabili fanno riferimento agli oggetti, è possibile utilizzare il `Is` o `IsNot` operatore o entrambi, per determinare se puntano alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="0abf9-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="0abf9-104">Per verificare se due oggetti sono uguali.</span><span class="sxs-lookup"><span data-stu-id="0abf9-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="0abf9-105">Utilizzare il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) con le due variabili come operandi.</span><span class="sxs-lookup"><span data-stu-id="0abf9-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="0abf9-106">Si potrebbe voler eseguire un'azione di a seconda se due oggetti si riferiscono alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="0abf9-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="0abf9-107">Nell'esempio precedente viene confrontato il controllo `c` con il controllo attivo sul form `f`.</span><span class="sxs-lookup"><span data-stu-id="0abf9-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="0abf9-108">Se è presente alcun controllo attivo o se è presente uno ma non è la stessa istanza di controllo di `c`, quindi il `If` istruzione ha esito negativo e la procedura restituisce senza un'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="0abf9-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="0abf9-109">Se si utilizza `Is` o `IsNot` è una questione di esigenze personali.</span><span class="sxs-lookup"><span data-stu-id="0abf9-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="0abf9-110">Uno potrebbe essere più facile da leggere rispetto a altra in una determinata espressione.</span><span class="sxs-lookup"><span data-stu-id="0abf9-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abf9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0abf9-111">See Also</span></span>  
 [<span data-ttu-id="0abf9-112">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0abf9-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
