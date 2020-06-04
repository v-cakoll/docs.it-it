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
ms.openlocfilehash: fe15e976e6a5469f2a9d1b3521a70a3e1860fdd3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414350"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)
Se si usa una classe o una struttura che definisce operatori propri, è possibile accedere a tali operatori da Visual Basic.  
  
 La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita la connessione alla struttura SQL <xref:System.Data.SqlTypes.SqlString> , che definisce gli operatori di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic. Usare `CType(` l' *espressione stringa SQL*, `String)` per convertire una stringa SQL in una stringa di Visual Basic e `CType(` *Visual Basic espressione stringa*, <xref:System.Data.SqlTypes.SqlString> `)` per eseguire la conversione nell'altra direzione.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 La <xref:System.Data.SqlTypes.SqlString> struttura definisce un operatore di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String` . L'istruzione che assegna `title` a `jobTitle` utilizza il primo operatore e la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata di funzione utilizza la seconda.  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare. Non presupporre che la classe o la struttura abbia definito ogni operatore disponibile per l'overload. Per un elenco degli operatori disponibili, vedere [istruzione Operator](../../../language-reference/statements/operator-statement.md).  
  
 Includere l' `Imports` istruzione appropriata per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes> ).  
  
 Il progetto deve avere riferimenti a System. Data e System. XML.  
  
## <a name="see-also"></a>Vedere anche

- [Routine di operatore](./operator-procedures.md)
- [Procedura: definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Procedura: chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Istruzione Structure](../../../language-reference/statements/structure-statement.md)
- [Procedura: Dichiarare una struttura](../data-types/how-to-declare-a-structure.md)
- [Conversioni implicite ed esplicite](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
