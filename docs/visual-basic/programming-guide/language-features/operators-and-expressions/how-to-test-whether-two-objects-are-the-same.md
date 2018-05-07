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
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Procedura: determinare se due oggetti sono uguali (Visual Basic)
Se si dispone di due variabili fanno riferimento agli oggetti, è possibile utilizzare il `Is` o `IsNot` operatore o entrambi, per determinare se puntano alla stessa istanza.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Per verificare se due oggetti sono uguali.  
  
-   Utilizzare il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) con le due variabili come operandi.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Si potrebbe voler eseguire un'azione di a seconda se due oggetti si riferiscono alla stessa istanza. Nell'esempio precedente viene confrontato il controllo `c` con il controllo attivo sul form `f`. Se è presente alcun controllo attivo o se è presente uno ma non è la stessa istanza di controllo di `c`, quindi il `If` istruzione ha esito negativo e la procedura restituisce senza un'ulteriore elaborazione.  
  
 Se si utilizza `Is` o `IsNot` è una questione di esigenze personali. Uno potrebbe essere più facile da leggere rispetto a altra in una determinata espressione.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
