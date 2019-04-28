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
ms.openlocfilehash: ce9146791935a488108d110134e9273507b0da6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864667"
---
# <a name="boolean-expressions-visual-basic"></a>Espressioni booleane (Visual Basic)
Oggetto *espressione booleana* è un'espressione che restituisce un valore delle [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` o `False`. `Boolean` le espressioni possono assumere forme diverse. È la più semplice il confronto diretto del valore di una `Boolean` variabile in un `Boolean` letterale, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Due significati del = (operatore)  
 Si noti che l'istruzione di assegnazione `newCustomer = True` è simile a espressione nell'esempio precedente, ma esegue una funzione diversa e viene usato in modo diverso. Nell'esempio precedente, l'espressione `newCustomer = True` rappresenta un valore booleano e il `=` segno viene interpretato come operatore di confronto. In un'istruzione autonoma, il `=` segno viene interpretato come operatore di assegnazione e assegna il valore a destra per la variabile a sinistra. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Per altre informazioni, vedere [confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) e [istruzioni](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Operatori di confronto  
 Gli operatori di confronto, ad esempio `=`, `<`, `>`, `<>`, `<=`, e `>=` produrre le espressioni booleane, confrontando l'espressione a sinistra dell'operatore a cui l'espressione a destra l'operatore e valutare il risultato come `True` o `False`. Questa condizione è illustrata nell'esempio seguente.  
  
 `42 < 81`  
  
 Poiché 42 è minore di 81, l'espressione booleana dell'esempio precedente restituisce `True`. Per altre informazioni su questo tipo di espressione, vedere [confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Operatori di confronto combinati con gli operatori logici  
 Espressioni di confronto possono essere combinate utilizzando gli operatori logici per produrre le espressioni booleane più complesse. Nell'esempio seguente viene illustrato l'utilizzo di operatori di confronto in combinazione con un operatore logico.  
  
 `x > y And x < 1000`  
  
 Nell'esempio precedente, il valore dell'espressione globale dipende dai valori delle espressioni ai lati del `And` operatore. Se entrambe le espressioni sono `True`, quindi restituisce l'espressione complessivo `True`. Se è delle espressioni `False`, quindi restituisce l'intera espressione `False`.  
  
## <a name="short-circuiting-operators"></a>Operatori di corto circuiti  
 Gli operatori logici `AndAlso` e `OrElse` un comportamento noto come *corto circuito*. Un operatore di corto circuito valuta innanzitutto l'operando sinistro. Se il secondo operando determina il valore dell'intera espressione, l'esecuzione del programma procede senza la valutazione dell'espressione a destra. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 Nell'esempio precedente, l'operatore valuta l'espressione a sinistra, `45 < 12`. Poiché restituisce l'espressione a sinistra `False`, deve restituire l'intera espressione logica `False`. L'esecuzione del programma salta quindi l'esecuzione del codice all'interno di `If` blocco senza la valutazione dell'espressione a destra, `testFunction(3)`. In questo esempio non chiama `testFunction()` perché l'espressione a sinistra quando falsifica l'intera espressione.  
  
 Analogamente, se l'espressione a sinistra in un'espressione logica che utilizza `OrElse` restituisca `True`, l'esecuzione procede alla riga successiva del codice senza la valutazione dell'espressione a destra, perché l'espressione a sinistra è già convalidato l'intero espressione.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Confronto con operatori Non Short-circuit  
 Al contrario, vengono valutati entrambi i lati dell'operatore logico quando gli operatori logici `And` e `Or` vengono usati. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 Nell'esempio precedente viene chiamato `testFunction()` anche se l'espressione a sinistra restituisce `False`.  
  
## <a name="parenthetical-expressions"></a>Espressioni tra parentesi  
 È possibile utilizzare parentesi per controllare l'ordine di valutazione di espressioni booleane. Prima di tutto valutazione di espressioni racchiuse tra parentesi. Per più livelli di annidamento, viene concessa la precedenza sulle espressioni maggiormente annidata. All'interno delle parentesi, la valutazione procede secondo le regole di precedenza degli operatori. Per altre informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Istruzioni](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
