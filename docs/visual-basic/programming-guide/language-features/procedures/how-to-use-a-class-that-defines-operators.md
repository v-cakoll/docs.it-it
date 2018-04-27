---
title: 'Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e0bcfaeca638dfabb841a9e935b872f76fdf957
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)
Se si utilizza una classe o struttura che definisce i propri operatori, è possibile accedere a tali operatori da Visual Basic.  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di accedere alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic. Uso `CType(` *espressione stringa SQL*, `String)` per convertire una stringa SQL in una stringa in Visual Basic, e `CType(` *espressione stringa Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` da convertire in altra direzione.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Il <xref:System.Data.SqlTypes.SqlString> struttura definisce un operatore di conversione ([CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String`. L'istruzione che assegna `title` a `jobTitle` utilizza il primo operatore e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata di funzione utilizza il secondo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Assicurarsi che la classe o struttura in uso definisce l'operatore a cui che si desidera utilizzare. Non presupporre che la classe o struttura sia definito tutti gli operatori disponibili per l'overload. Per un elenco di operatori disponibili, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Includere appropriata `Imports` istruzione per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).  
  
 Il progetto deve includere riferimenti a System. Data e System. Xml.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine di operatore](./operator-procedures.md)  
 [Procedura: Definire un operatore](./how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)  
 [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
