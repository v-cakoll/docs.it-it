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
ms.openlocfilehash: 50054b9e32f4d49a34c1bb1a5c79129662019aee
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965905"
---
# <a name="value-comparisons-visual-basic"></a>Confronto di valori (Visual Basic)
Gli operatori di confronto sono utilizzabile per creare espressioni che confrontano i valori delle variabili numeriche. Queste espressioni restituiscono un `Boolean` valore basato sul fatto che il confronto è true o false. Esempi di un'espressione di questo tipo sono i seguenti.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La prima espressione restituisce `True`, poiché è maggiore di 26 45. Restituisce il secondo esempio `False`, perché non è superiore a 45 26.  
  
 È anche possibile confrontare espressioni numeriche in questo modo. Le espressioni che si confrontano possono essere autonomamente le espressioni complesse, come nell'esempio seguente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Espressione complessa precedente include i valori letterali, variabili e le chiamate di funzione. Le espressioni su entrambi i lati dell'operatore di confronto vengono valutate e i valori risultanti vengono confrontati utilizzando il `>=` operatore di confronto. Se il valore dell'espressione sul lato sinistro è maggiore o uguale al valore dell'espressione a destra, l'intera espressione viene valutata `True`; in caso contrario, restituisce `False`.  
  
 Le espressioni che confrontano i valori utilizzate più frequentemente `If...Then` costruzioni, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Il `=` segno è un operatore di confronto, nonché un operatore di assegnazione. Quando usato come operatore di confronto, valuta se il valore a sinistra è uguale a quello a destra, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 È anche possibile usare un'espressione di confronto in qualsiasi punto un' `Boolean` valore è necessario, ad esempio in un `If`, `While`, `Loop`, o `ElseIf` istruzione, o durante l'assegnazione o passare un valore a un `Boolean` variabile. Nell'esempio seguente, viene assegnato il valore restituito dall'espressione di confronto per un `Boolean` variabile.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Vedere anche
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Procedura: Calcolare valori numerici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
