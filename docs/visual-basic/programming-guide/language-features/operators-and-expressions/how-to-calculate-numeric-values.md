---
title: 'Procedura: Calcolare valori numerici (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 7bbc3bcadb318203688a3b8ecae18e723e82c8ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560740"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Procedura: Calcolare valori numerici (Visual Basic)
È possibile calcolare valori numerici tramite l'utilizzo di espressioni numeriche. Oggetto *espressione numerica* è un'espressione che contiene i valori letterali, costanti e variabili che rappresentano valori numerici e operatori che agiscono su quei valori.  
  
## <a name="calculating-numeric-values"></a>Calcolo dei valori numerici  
  
#### <a name="to-calculate-a-numeric-value"></a>Per calcolare un valore numerico  
  
-   Combinare uno o più valori letterali, costanti e variabili in un'espressione numerica. Nell'esempio seguente mostra alcune espressioni numerici validi.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Le prime tre righe mostrano un valore letterale, una costante e una variabile. Ognuno di essi costituisce un'espressione numerica valida da solo. L'ultima riga mostra una combinazione di una variabile con due valori letterali.  
  
     Si noti che un'espressione numerica non formano un'istruzione completa di Visual Basic da solo. È necessario utilizzare l'espressione come parte di un'istruzione completa.  
  
#### <a name="to-store-a-numeric-value"></a>Per archiviare un valore numerico  
  
-   È possibile usare un'istruzione di assegnazione per assegnare il valore rappresentato da un'espressione numerica per una variabile, come illustrato nell'esempio seguente.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     Nell'esempio precedente, il valore dell'espressione sul lato destro dell'operatore uguale (`=`) viene assegnato alla variabile `j` sul lato sinistro dell'operatore, in modo `j` 276 viene valutata.  
  
     Per altre informazioni, vedere [Istruzioni](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Più operatori  
 Se l'espressione numerica contiene più di un operatore, l'ordine in cui vengono valutati è determinato dalle regole di precedenza degli operatori. Per ignorare le regole di precedenza degli operatori, racchiudere le espressioni tra parentesi, come illustrato nell'esempio riportato sopra; le espressioni racchiuse tra parentesi vengono valutate per primi.  
  
#### <a name="to-override-normal-operator-precedence"></a>Eseguire l'override di precedenza degli operatori normale  
  
-   Utilizzare le parentesi per racchiudere le operazioni che si desidera venga eseguita per prima. Nell'esempio seguente mostra due risultati diversi con gli stessi operandi e operatori.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     Nell'esempio precedente, il calcolo `j` esegue l'operatore di addizione (`+`) prima perché le parentesi che racchiudono `(67 + i)` esegue l'override della precedenza normale e il valore assegnato a `j` è 276 (4 tentativi 69). Il calcolo `k` esegue gli operatori nella relativa priorità normale (`*` prima `+`) e il valore assegnato a `k` 270 (268 + 2).  
  
     Per altre informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vedere anche
- [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operatori aritmetici](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
