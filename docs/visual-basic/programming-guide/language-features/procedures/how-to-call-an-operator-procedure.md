---
title: 'Procedura: Chiamare una routine di operatore (Visual Basic)'
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
ms.openlocfilehash: d68781aa12ab7c1c717031ca252c5f3120649edc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335485"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Procedura: Chiamare una routine di operatore (Visual Basic)
Si chiama una routine di operatore usando il simbolo di operatore in un'espressione. Nel caso di un operatore di conversione, si chiama il [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo a altro.  
  
 Routine di operatore non viene chiamato in modo esplicito. È sufficiente usare l'operatore, o `CType` funzione in un'istruzione di assegnazione o un'espressione, simile a quello in cui si utilizza normalmente un operatore. Visual Basic effettua la chiamata alla routine di operatore.  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
### <a name="to-call-an-operator-procedure"></a>Per chiamare una routine di operatore  
  
1. Usare il simbolo dell'operatore in un'espressione nel modo normale.  
  
2. Assicurarsi che i tipi di dati gli operandi sono appropriati per l'operatore e nell'ordine corretto.  
  
3. L'operatore contribuisce al valore dell'espressione come previsto.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Per chiamare una routine di operatore di conversione  
  
1. Usare `CType` all'interno di un'espressione.  
  
2. Assicurarsi che i tipi di dati gli operandi sono appropriati per la conversione e nell'ordine corretto.  
  
3. `CType` chiama la routine di operatore di conversione e restituisce il valore convertito.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due <xref:System.TimeSpan> strutture, li somma e archivia il risultato in una terza <xref:System.TimeSpan> struttura. Il <xref:System.TimeSpan> struttura definisce le routine di operatore per eseguire l'overload di diversi operatori standard.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 In quanto <xref:System.TimeSpan> overloads standard `+` operatore, nell'esempio precedente chiama una routine di operatore quando si calcola il valore di `combinedSpan`.  
  
 Per un esempio di chiamata una routine di operatore di conversione, vedere [come: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Assicurarsi che la classe o struttura che si usa definisce l'operatore da usare.  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
