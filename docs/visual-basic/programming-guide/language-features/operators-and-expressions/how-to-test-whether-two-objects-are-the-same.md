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
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Procedura: determinare se due oggetti sono uguali (Visual Basic)
Se si dispone di due variabili che fanno riferimento a oggetti, è possibile utilizzare l'operatore `Is` o `IsNot`, o entrambi, per determinare se si riferiscono alla stessa istanza.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Per verificare se due oggetti sono uguali  
  
- Usare l'operatore [is](../../../../visual-basic/language-reference/operators/is-operator.md) o l' [operatore](../../../../visual-basic/language-reference/operators/isnot-operator.md) non con le due variabili come operandi.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Potrebbe essere necessario eseguire una determinata azione a seconda che due oggetti facciano riferimento alla stessa istanza. Nell'esempio precedente il controllo `c` viene confrontato con il controllo attivo sul form `f`. Se non è presente alcun controllo attivo o se ne esiste uno, ma non è la stessa istanza del controllo di `c`, l'istruzione `If` ha esito negativo e la procedura viene restituita senza ulteriori elaborazioni.  
  
 Se si usa `Is` o `IsNot` è una questione di praticità. Una può essere più facile da leggere rispetto all'altra in un'espressione specificata.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
