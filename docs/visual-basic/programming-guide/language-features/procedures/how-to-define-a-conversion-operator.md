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
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388089"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Procedura: definire un operatore di conversione (Visual Basic)
Se è stata definita una classe o una struttura, è possibile definire un operatore di conversione dei tipi tra il tipo della classe o della struttura e un altro tipo di dati, ad esempio `Integer` , `Double` o `String` .  
  
 Definire la conversione del tipo come routine della [funzione CType](../../../language-reference/functions/ctype-function.md) all'interno della classe o della struttura. Tutte le procedure di conversione devono essere `Public Shared` e ognuna di esse deve specificare un valore [crescente](../../../language-reference/modifiers/widening.md) o più [piccolo](../../../language-reference/modifiers/narrowing.md).  
  
 La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono definiti gli operatori di conversione tra una struttura denominata `digit` e un oggetto `Byte` .  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 È possibile testare la struttura `digit` con il codice seguente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: definire un operatore](./how-to-define-an-operator.md)
- [Procedura: chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Procedura: utilizzare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Istruzione Structure](../../../language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
