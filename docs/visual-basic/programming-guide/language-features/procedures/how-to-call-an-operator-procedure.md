---
title: 'Procedura: chiamare una routine di operatore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: b1dc4477daa4ceb9dfc6a9a6ab3f041e68011acd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Procedura: chiamare una routine di operatore (Visual Basic)
Utilizzare il simbolo dell'operatore in un'espressione per chiamare una routine di operatore. Nel caso di un operatore di conversione, si chiama il [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo di dati.  
  
 Routine di operatore non si chiama in modo esplicito. È sufficiente utilizzare l'operatore, o `CType` funzione in un'istruzione di assegnazione o un'espressione, esattamente come si utilizza in genere un operatore. Visual Basic effettua la chiamata di routine di operatore.  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
### <a name="to-call-an-operator-procedure"></a>Per chiamare una routine di operatore  
  
1.  Utilizzare il simbolo dell'operatore in un'espressione in modo normale.  
  
2.  Verificare che i tipi di dati gli operandi siano appropriati per l'operatore e nell'ordine corretto.  
  
3.  L'operatore contribuisce al valore dell'espressione, come previsto.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Per chiamare una routine di operatore di conversione  
  
1.  Utilizzare `CType` all'interno di un'espressione.  
  
2.  Verificare che i tipi di dati gli operandi siano appropriati per la conversione e nell'ordine corretto.  
  
3.  `CType` chiama la routine di operatore di conversione e restituisce il valore convertito.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due <xref:System.TimeSpan> strutture, li somma e archivia il risultato in un terzo <xref:System.TimeSpan> struttura. Il <xref:System.TimeSpan> struttura definisce le routine di operatore per eseguire l'overload diversi operatori standard.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Poiché <xref:System.TimeSpan> overload standard `+` operatore, nell'esempio precedente chiama una routine di operatore quando si calcola il valore di `combinedSpan`.  
  
 Per un esempio di chiamata una routine di operatore di conversione, vedere [procedura: utilizzare una classe che definisce operatori](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Assicurarsi che la classe o struttura in uso definisce l'operatore a cui che si desidera utilizzare.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine di operatore](./operator-procedures.md)  
 [Procedura: Definire un operatore](./how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)  
 [Istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
