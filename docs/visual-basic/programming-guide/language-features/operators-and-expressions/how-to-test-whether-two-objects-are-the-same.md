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
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Procedura: determinare se due oggetti sono uguali (Visual Basic)
Se si dispone di due variabili che fanno riferimento a oggetti, è possibile utilizzare `Is` l' `IsNot` operatore OR oppure entrambi per determinare se si riferiscono alla stessa istanza.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Per verificare se due oggetti sono uguali  
  
- Usare l'operatore [is](../../../language-reference/operators/is-operator.md) o l' [operatore](../../../language-reference/operators/isnot-operator.md) non con le due variabili come operandi.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Potrebbe essere necessario eseguire una determinata azione a seconda che due oggetti facciano riferimento alla stessa istanza. Nell'esempio precedente viene confrontato `c` il controllo con il controllo attivo sul form `f` . Se non è presente alcun controllo attivo o se ne esiste uno, ma non è la stessa istanza del controllo di `c` , l' `If` istruzione ha esito negativo e la procedura restituisce senza ulteriori elaborazioni.  
  
 Se si usa `Is` o `IsNot` è una questione di praticità. Una può essere più facile da leggere rispetto all'altra in un'espressione specificata.  
  
## <a name="see-also"></a>Vedere anche

- [Comparison Operators in Visual Basic](comparison-operators.md)
