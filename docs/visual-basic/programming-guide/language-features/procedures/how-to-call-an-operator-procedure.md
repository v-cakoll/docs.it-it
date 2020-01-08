---
title: 'Procedura: chiamare una routine di operatore'
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
ms.openlocfilehash: a977b17d4b2c797bbe38d289a57f3d9d31fa64fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345958"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Procedura: chiamare una routine di operatore (Visual Basic)
Una routine di operatore viene chiamata utilizzando il simbolo dell'operatore in un'espressione. Nel caso di un operatore di conversione, si chiama la [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo di dati a un altro.  
  
 Le routine dell'operatore non vengono chiamate in modo esplicito. È sufficiente utilizzare l'operatore o la funzione `CType`, in un'istruzione di assegnazione o in un'espressione, nello stesso modo in cui si utilizza normalmente un operatore. Visual Basic esegue la chiamata alla routine di operatore.  
  
 La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.  
  
### <a name="to-call-an-operator-procedure"></a>Per chiamare una routine di operatore  
  
1. Usare il simbolo dell'operatore in un'espressione nel modo normale.  
  
2. Assicurarsi che i tipi di dati degli operandi siano appropriati per l'operatore e nell'ordine corretto.  
  
3. L'operatore contribuisce al valore dell'espressione come previsto.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Per chiamare una procedura dell'operatore di conversione  
  
1. Utilizzare `CType` all'interno di un'espressione.  
  
2. Assicurarsi che i tipi di dati degli operandi siano appropriati per la conversione e nell'ordine corretto.  
  
3. `CType` chiama la routine dell'operatore di conversione e restituisce il valore convertito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono create due strutture di <xref:System.TimeSpan>, aggiunte insieme e il risultato viene archiviato in una terza struttura <xref:System.TimeSpan>. La struttura <xref:System.TimeSpan> definisce procedure di operatore per eseguire l'overload di diversi operatori standard.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Poiché <xref:System.TimeSpan> esegue l'overload dell'operatore `+` standard, nell'esempio precedente viene chiamata una routine di operatore quando viene calcolato il valore di `combinedSpan`.  
  
 Per un esempio di chiamata a una routine dell'operatore di conversazione, vedere [procedura: usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare.  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
