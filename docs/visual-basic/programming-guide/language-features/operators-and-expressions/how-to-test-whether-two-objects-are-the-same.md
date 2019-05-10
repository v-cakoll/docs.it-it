---
title: 'Procedura: Verificare se due oggetti sono la stessa (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 6301228d786fe55e8851b6207dd84819671656f4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649686"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="bc52a-102">Procedura: Verificare se due oggetti sono la stessa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc52a-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="bc52a-103">Se si dispone di due variabili fanno riferimento agli oggetti, è possibile usare la `Is` o `IsNot` operatore o entrambi, per determinare se si riferiscono alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="bc52a-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="bc52a-104">Per verificare se due oggetti sono uguali.</span><span class="sxs-lookup"><span data-stu-id="bc52a-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="bc52a-105">Usare la [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) o nella [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) con le due variabili come operandi.</span><span class="sxs-lookup"><span data-stu-id="bc52a-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="bc52a-106">È possibile eseguire una determinata azione a seconda del fatto che due oggetti si riferiscono alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="bc52a-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="bc52a-107">Nell'esempio precedente viene confrontato il controllo `c` con il controllo attivo sul form `f`.</span><span class="sxs-lookup"><span data-stu-id="bc52a-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="bc52a-108">Se non è disponibile alcun controllo attivo o se è presente uno ma non è la stessa istanza di controllo come `c`, quindi il `If` istruzione ha esito negativo e la procedura restituisce senza ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="bc52a-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="bc52a-109">Se si utilizza `Is` o `IsNot` è una questione di praticità aggiuntivo personale all'utente.</span><span class="sxs-lookup"><span data-stu-id="bc52a-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="bc52a-110">Uno potrebbe essere più facile da leggere rispetto a altro in una determinata espressione.</span><span class="sxs-lookup"><span data-stu-id="bc52a-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc52a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc52a-111">See also</span></span>

- [<span data-ttu-id="bc52a-112">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc52a-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
