---
title: Confronto di valori (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="value-comparisons-visual-basic"></a>Confronto di valori (Visual Basic)
Gli operatori di confronto consente di creare espressioni che confrontano i valori di variabili numeriche. Queste espressioni restituiscono un `Boolean` valore a seconda che il confronto sia true o false. Esempi di un'espressione di questo tipo sono i seguenti.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Restituisce la prima espressione `True`, in quanto 45 è maggiore di 26. Restituisce il secondo esempio `False`, in quanto 26 è maggiore di 45.  
  
 È inoltre possibile confrontare le espressioni numeriche in questo modo. Le espressioni che confronto possono essere autonomamente le espressioni complesse, come nell'esempio seguente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 L'espressione complessa precedente include valori letterali, variabili e chiamate di funzione. Le espressioni su entrambi i lati dell'operatore di confronto vengono valutate e i valori risultanti vengono confrontati utilizzando il `>=` operatore di confronto. Se il valore dell'espressione a sinistra è maggiore o uguale al valore dell'espressione a destra, l'intera espressione restituisce `True`; in caso contrario, restituisce `False`.  
  
 Le espressioni di confronto di valori utilizzate più frequentemente `If...Then` costruzioni, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 Il `=` segno è un operatore di confronto, nonché un operatore di assegnazione. Quando usato come operatore di confronto, valuta se il valore a sinistra è uguale al valore a destra, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 È inoltre possibile utilizzare un'espressione di confronto in qualsiasi punto un `Boolean` valore è necessario, ad esempio in un `If`, `While`, `Loop`, o `ElseIf` istruzione, o durante l'assegnazione o passare un valore a un `Boolean` variabile. Nell'esempio seguente, viene assegnato il valore restituito dall'espressione di confronto per un `Boolean` variabile.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Procedura: Calcolare valori numerici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
