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
ms.openlocfilehash: 01816b5730cf4fda61f1737ce3ce00ab82f57da8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403395"
---
# <a name="value-comparisons-visual-basic"></a>Confronto di valori (Visual Basic)
Gli operatori di confronto possono essere utilizzati per costruire espressioni che confrontano i valori delle variabili numeriche. Queste espressioni restituiscono un `Boolean` valore a seconda che il confronto sia true o false. Di seguito sono riportati alcuni esempi di espressioni di questo tipo.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La prima espressione restituisce `True` , perché 45 è maggiore di 26. Il secondo esempio restituisce `False` , perché 26 non è maggiore di 45.  
  
 È anche possibile confrontare le espressioni numeriche in questo modo. Le espressioni che si confrontano possono essere espressioni complesse, come nell'esempio seguente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 L'espressione complessa precedente include valori letterali, variabili e chiamate di funzione. Le espressioni su entrambi i lati dell'operatore di confronto vengono valutate e i valori risultanti vengono quindi confrontati tramite l' `>=` operatore di confronto. Se il valore dell'espressione sul lato sinistro è maggiore o uguale al valore dell'espressione a destra, l'intera espressione restituisce `True` . in caso contrario, restituisce `False` .  
  
 Le espressioni che confrontano i valori vengono utilizzate più di frequente nelle `If...Then` costruzioni, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Il `=` segno è un operatore di confronto e un operatore di assegnazione. Quando viene usato come operatore di confronto, valuta se il valore a sinistra è uguale al valore a destra, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 È anche possibile usare un'espressione di confronto in qualsiasi punto `Boolean` in cui è necessario un valore, ad esempio in un' `If` istruzione,, `While` o oppure quando si `Loop` `ElseIf` assegna o si passa un valore a una `Boolean` variabile. Nell'esempio seguente, il valore restituito dall'espressione di confronto viene assegnato a una `Boolean` variabile.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni booleane](boolean-expressions.md)
- [Operatori ed espressioni](index.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Procedura: calcolare valori numerici](how-to-calculate-numeric-values.md)
- [Precedenza tra gli operatori in Visual Basic](../../../language-reference/operators/operator-precedence.md)
