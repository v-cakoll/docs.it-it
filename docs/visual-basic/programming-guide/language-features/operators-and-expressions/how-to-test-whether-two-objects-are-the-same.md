---
title: 'Procedura: determinare se due oggetti sono uguali (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
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
