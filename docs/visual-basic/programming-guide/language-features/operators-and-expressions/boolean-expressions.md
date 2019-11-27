---
title: Espressioni booleane
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
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350817"
---
# <a name="boolean-expressions-visual-basic"></a>Espressioni booleane (Visual Basic)
Un' *espressione booleana* è un'espressione che restituisce un valore del tipo di [dati booleano](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` o `False`. `Boolean` espressioni possono assumere diverse forme. Il più semplice è il confronto diretto del valore di una variabile di `Boolean` a un valore letterale `Boolean`, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Due significati dell'operatore =  
 Si noti che l'istruzione di assegnazione `newCustomer = True` sembra uguale all'espressione nell'esempio precedente, ma esegue una funzione diversa e viene usata in modo diverso. Nell'esempio precedente, l'espressione `newCustomer = True` rappresenta un valore booleano e il segno di `=` viene interpretato come operatore di confronto. In un'istruzione autonoma, il segno di `=` viene interpretato come un operatore di assegnazione e assegna il valore a destra alla variabile a sinistra. Ciò è illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Per ulteriori informazioni, vedere [confronti di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) e [istruzioni](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Operatori di confronto  
 Gli operatori di confronto, ad esempio `=`, `<`, `>`, `<>`, `<=`e `>=` producono espressioni booleane confrontando l'espressione sul lato sinistro dell'operatore con l'espressione a destra dell'operatore e valutando il risultato come `True` o `False`. Ciò è illustrato nell'esempio seguente.  
  
 `42 < 81`  
  
 Poiché 42 è minore di 81, l'espressione booleana nell'esempio precedente restituisce `True`. Per altre informazioni su questo tipo di espressione, vedere [confronti di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Operatori di confronto combinati con operatori logici  
 Le espressioni di confronto possono essere combinate utilizzando operatori logici per produrre espressioni booleane più complesse. Nell'esempio seguente viene illustrato l'utilizzo di operatori di confronto in combinazione con un operatore logico.  
  
 `x > y And x < 1000`  
  
 Nell'esempio precedente, il valore dell'espressione complessiva dipende dai valori delle espressioni su ogni lato dell'operatore `And`. Se entrambe le espressioni sono `True`, l'espressione complessiva restituisce `True`. Se una delle due espressioni è `False`, l'intera espressione restituisce `False`.  
  
## <a name="short-circuiting-operators"></a>Operatori di corto circuito  
 Gli operatori logici `AndAlso` e `OrElse` presentano un comportamento noto come *corto circuito*. Un operatore di corto circuito valuta prima l'operando sinistro. Se l'operando sinistro determina il valore dell'intera espressione, l'esecuzione del programma procede senza valutare l'espressione a destra. Ciò è illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 Nell'esempio precedente, l'operatore valuta l'espressione a sinistra, `45 < 12`. Poiché l'espressione a sinistra restituisce `False`, l'intera espressione logica deve restituire `False`. L'esecuzione del programma ignora quindi l'esecuzione del codice all'interno del blocco `If` senza valutare l'espressione a destra, `testFunction(3)`. In questo esempio non viene chiamato `testFunction()` perché l'espressione a sinistra falsifica l'intera espressione.  
  
 Analogamente, se l'espressione a sinistra in un'espressione logica che usa `OrElse` restituisce `True`, l'esecuzione procede alla riga di codice successiva senza valutare l'espressione a destra, perché l'espressione a sinistra ha già convalidato l'intera espressione.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Confronto con operatori non di cortocircuito  
 Al contrario, entrambi i lati dell'operatore logico vengono valutati quando vengono utilizzati gli operatori logici `And` e `Or`. Ciò è illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 Nell'esempio precedente viene chiamato `testFunction()` anche se l'espressione a sinistra restituisce `False`.  
  
## <a name="parenthetical-expressions"></a>Espressioni parentesi  
 È possibile utilizzare le parentesi per controllare l'ordine di valutazione delle espressioni booleane. Le espressioni racchiuse tra parentesi vengono valutate per prime. Per più livelli di annidamento, viene concessa la precedenza alle espressioni annidate più profondamente. Tra parentesi, la valutazione continua in base alle regole di precedenza degli operatori. Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Istruzioni](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
