---
title: 'Procedura: utilizzare una classe che definisce gli operatori'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347884"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)
Se si usa una classe o una struttura che definisce operatori propri, è possibile accedere a tali operatori da Visual Basic.  
  
 La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene accesso alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic. Usare `CType(`*espressione stringa sql*`String)` per convertire una stringa SQL in una stringa di Visual Basic e `CType(`*Visual Basic espressione stringa*, <xref:System.Data.SqlTypes.SqlString>`)` da convertire nell'altra direzione.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 La struttura <xref:System.Data.SqlTypes.SqlString> definisce un operatore di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String`. L'istruzione che assegna `title` a `jobTitle` usa il primo operatore e la chiamata di funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> usa il secondo.  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare. Non presupporre che la classe o la struttura abbia definito ogni operatore disponibile per l'overload. Per un elenco degli operatori disponibili, vedere [istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Includere l'istruzione `Imports` appropriata per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).  
  
 Il progetto deve avere riferimenti a System. Data e System. XML.  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
