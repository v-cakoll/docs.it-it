---
title: Confronto di valori
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
ms.openlocfilehash: f766eaaada486a0f70838bafb754d25070ff4174
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346293"
---
# <a name="value-comparisons-visual-basic"></a>Confronto di valori (Visual Basic)
Gli operatori di confronto possono essere utilizzati per costruire espressioni che confrontano i valori delle variabili numeriche. Queste espressioni restituiscono un valore `Boolean` a seconda che il confronto sia true o false. Di seguito sono riportati alcuni esempi di espressioni di questo tipo.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La prima espressione restituisce `True`, perché 45 è maggiore di 26. Nel secondo esempio viene restituito `False`, perché 26 non è maggiore di 45.  
  
 È anche possibile confrontare le espressioni numeriche in questo modo. Le espressioni che si confrontano possono essere espressioni complesse, come nell'esempio seguente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 L'espressione complessa precedente include valori letterali, variabili e chiamate di funzione. Le espressioni su entrambi i lati dell'operatore di confronto vengono valutate e i valori risultanti vengono quindi confrontati tramite l'operatore di confronto `>=`. Se il valore dell'espressione sul lato sinistro è maggiore o uguale al valore dell'espressione a destra, l'intera espressione restituisce `True`; in caso contrario, restituisce `False`.  
  
 Le espressioni che confrontano i valori vengono utilizzate più di frequente nelle costruzioni `If...Then`, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Il segno di `=` è un operatore di confronto e un operatore di assegnazione. Quando viene usato come operatore di confronto, valuta se il valore a sinistra è uguale al valore a destra, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 È anche possibile usare un'espressione di confronto ovunque sia necessario un valore di `Boolean`, ad esempio in un'istruzione `If`, `While`, `Loop`o `ElseIf` oppure quando si assegna o si passa un valore a una variabile `Boolean`. Nell'esempio seguente, il valore restituito dall'espressione di confronto viene assegnato a una variabile `Boolean`.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Procedura: Calcolare valori numerici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
