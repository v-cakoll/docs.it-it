---
title: 'Procedura: Usare una classe che definisce gli operatori (Visual Basic)'
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
ms.openlocfilehash: 372d3f663109597fc2d25c5d75a9efa6b3648682
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640678"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Procedura: Usare una classe che definisce gli operatori (Visual Basic)
Se si usa una classe o struttura che definisca i propri operatori, è possibile accedere a questi ultimi da Visual Basic.  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di accedere alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic. Uso `CType(` *espressione stringa SQL*, `String)` per convertire una stringa SQL in una stringa di Visual Basic, e `CType(` *espressione Visual Basic stringa*, <xref:System.Data.SqlTypes.SqlString> `)` da convertire in altra direzione.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Il <xref:System.Data.SqlTypes.SqlString> struttura definisce un operatore di conversione ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) dal `String` a <xref:System.Data.SqlTypes.SqlString> e l'altro da <xref:System.Data.SqlTypes.SqlString> a `String`. L'istruzione che assegna `title` al `jobTitle` Usa il primo operatore e il <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata di funzione utilizzerà il secondo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Assicurarsi che la classe o struttura che si usa definisce l'operatore da usare. Non presupporre che la classe o struttura è definita tutti gli operatori disponibili per eseguire l'overload. Per un elenco di operatori disponibili, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Includere appropriato `Imports` istruzione per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).  
  
 Il progetto deve disporre di riferimenti a System. Data e System. Xml.  
  
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
