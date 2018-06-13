---
title: Espressioni booleane (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: ff5843c815658468ac69fe5d62a9ea4cac2be830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655798"
---
# <a name="boolean-expressions-visual-basic"></a>Espressioni booleane (Visual Basic)
A *espressione booleana* è un'espressione che restituisce un valore di [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` o `False`. `Boolean` le espressioni possono assumere varie forme. La più semplice è il confronto diretto del valore di un `Boolean` variabile a un `Boolean` letterale, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>Due significati del = (operatore)  
 Si noti che l'istruzione di assegnazione `newCustomer = True` sembra uguale all'espressione nell'esempio precedente, ma esegue una funzione diversa e viene utilizzato in modo diverso. Nell'esempio precedente, l'espressione `newCustomer = True` rappresenta un valore booleano e `=` segno viene interpretato come un operatore di confronto. In un'istruzione autonoma, il `=` segno viene interpretato come un operatore di assegnazione e assegna il valore a destra alla variabile a sinistra. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Per ulteriori informazioni, vedere [valore confronti](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) e [istruzioni](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Operatori di confronto  
 Gli operatori di confronto, ad esempio `=`, `<`, `>`, `<>`, `<=`, e `>=` producono espressioni booleane tramite il confronto dell'espressione sul lato sinistro dell'operatore a cui l'espressione a destra l'operatore e valutare il risultato come `True` o `False`. Questa condizione è illustrata nell'esempio seguente.  
  
 `42 < 81`  
  
 Poiché 42 è inferiore a 81, l'espressione booleana nell'esempio precedente restituisce `True`. Per ulteriori informazioni su questo tipo di espressione, vedere [valore confronti](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Operatori di confronto combinati con gli operatori logici  
 Espressioni di confronto possono essere combinate utilizzando gli operatori logici per produrre le espressioni booleane più complesse. Nell'esempio seguente viene illustrato l'utilizzo di operatori di confronto in combinazione con un operatore logico.  
  
 `x > y And x < 1000`  
  
 Nell'esempio precedente, il valore dell'espressione generale dipende dai valori delle espressioni ai lati del `And` operatore. Se entrambe le espressioni sono `True`, quindi l'espressione complessiva restituisce `True`. Se delle espressioni è `False`, quindi restituisce l'intera espressione `False`.  
  
## <a name="short-circuiting-operators"></a>Operatori di corto circuito  
 Gli operatori logici `AndAlso` e `OrElse` possono presentare un comportamento noto come *corto circuito*. Un operatore di corto circuito valuta innanzitutto l'operando sinistro. Se l'operando di sinistra determina il valore dell'intera espressione, quindi l'esecuzione del programma continua senza valutare l'espressione a destra. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 Nell'esempio precedente, l'operatore valuta l'espressione a sinistra, `45 < 12`. Poiché l'espressione a sinistra restituisce `False`, deve restituire l'intera espressione logica `False`. Esecuzione del programma salta quindi l'esecuzione del codice all'interno di `If` blocco senza valutare l'espressione a destra, `testFunction(3)`. Questo esempio non viene chiamato `testFunction()` perché l'espressione a sinistra quando falsifica l'intera espressione.  
  
 Analogamente, se l'espressione a sinistra in un'espressione logica che utilizza `OrElse` restituisce `True`, l'esecuzione procede alla riga successiva del codice senza valutare l'espressione a destra, in quanto l'espressione a sinistra ha già convalidato l'intero espressione.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Confronto con gli operatori Non Short-circuit  
 Al contrario, entrambi i lati dell'operatore logico vengono valutati quando gli operatori logici `And` e `Or` vengono utilizzati. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 Nell'esempio precedente viene chiamato `testFunction()` anche se l'espressione a sinistra di restituisce `False`.  
  
## <a name="parenthetical-expressions"></a>Espressioni tra parentesi  
 È possibile utilizzare parentesi per controllare l'ordine di valutazione di espressioni booleane. Valutata prima di espressioni racchiuse tra parentesi. Per più livelli di annidamento, precedenza viene concesso per le espressioni nidificate. All'interno delle parentesi, valutazione procede secondo le regole di precedenza degli operatori. Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Istruzioni](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
