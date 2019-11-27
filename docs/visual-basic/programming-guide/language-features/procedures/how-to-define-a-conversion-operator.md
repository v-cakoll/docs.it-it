---
title: 'Procedura: definire un operatore di conversione'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344891"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Procedura: definire un operatore di conversione (Visual Basic)
Se è stata definita una classe o una struttura, è possibile definire un operatore di conversione dei tipi tra il tipo della classe o della struttura e un altro tipo di dati (ad esempio `Integer`, `Double`o `String`).  
  
 Definire la conversione del tipo come routine della [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) all'interno della classe o della struttura. Tutte le procedure di conversione devono essere `Public Shared`te, ognuna delle quali deve specificare un valore [crescente](../../../../visual-basic/language-reference/modifiers/widening.md) o più [piccolo](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono definiti gli operatori di conversione tra una struttura denominata `digit` e una `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 È possibile testare la struttura `digit` con il codice seguente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
