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
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343628"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="18c47-102">Procedura: determinare se due oggetti sono uguali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18c47-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="18c47-103">Se si dispone di due variabili che fanno riferimento a oggetti, è possibile utilizzare l'operatore `Is` o `IsNot`, o entrambi, per determinare se si riferiscono alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="18c47-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="18c47-104">Per verificare se due oggetti sono uguali</span><span class="sxs-lookup"><span data-stu-id="18c47-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="18c47-105">Usare l'operatore [is](../../../../visual-basic/language-reference/operators/is-operator.md) o l' [operatore](../../../../visual-basic/language-reference/operators/isnot-operator.md) non con le due variabili come operandi.</span><span class="sxs-lookup"><span data-stu-id="18c47-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="18c47-106">Potrebbe essere necessario eseguire una determinata azione a seconda che due oggetti facciano riferimento alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="18c47-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="18c47-107">Nell'esempio precedente il controllo `c` viene confrontato con il controllo attivo sul form `f`.</span><span class="sxs-lookup"><span data-stu-id="18c47-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="18c47-108">Se non è presente alcun controllo attivo o se ne esiste uno, ma non è la stessa istanza del controllo di `c`, l'istruzione `If` ha esito negativo e la procedura viene restituita senza ulteriori elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="18c47-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="18c47-109">Se si usa `Is` o `IsNot` è una questione di praticità.</span><span class="sxs-lookup"><span data-stu-id="18c47-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="18c47-110">Una può essere più facile da leggere rispetto all'altra in un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="18c47-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c47-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18c47-111">See also</span></span>

- [<span data-ttu-id="18c47-112">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18c47-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
