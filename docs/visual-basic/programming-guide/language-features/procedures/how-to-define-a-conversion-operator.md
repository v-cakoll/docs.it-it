---
title: 'Procedura: Definire un operatore di conversione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829226"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Procedura: Definire un operatore di conversione (Visual Basic)
Se è stato definito una classe o struttura, è possibile definire un operatore di conversione di tipi tra il tipo di classe o struttura e un altro tipo di dati (ad esempio `Integer`, `Double`, o `String`).  
  
 Definire la conversione del tipo come un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure all'interno della classe o struttura. Tutte le routine di conversione devono essere `Public Shared`, e ognuno di essi è necessario specificare [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) oppure [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce gli operatori di conversione tra una struttura definita `digit` e un `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 È possibile testare la struttura `digit` con il codice seguente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
- [Istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
