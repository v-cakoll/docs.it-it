---
title: Routine di operatore (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 5b4641ce8509e3111a11ed803d36194d5a301bce
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805711"
---
# <a name="operator-procedures-visual-basic"></a>Routine di operatore (Visual Basic)
Una routine di operatore è una serie di istruzioni di Visual Basic che definiscono il comportamento di un operatore (ad esempio `*`, `<>`, o `And`) in una classe o struttura definita. Questo è l'acronimo *l'overload degli operatori*.  
  
## <a name="when-to-define-operator-procedures"></a>Quando definire una routine di operatore  
 Dopo aver definito una classe o struttura, è possibile dichiarare variabili di tipo di quella classe o struttura. In alcuni casi tale variabile deve far parte di un'operazione come parte di un'espressione. A tale scopo, deve essere un operando di un operatore.  
  
 Visual Basic definisce gli operatori solo sui tipi di dati più importanti. È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono del tipo di classe o struttura.  
  
 Per ulteriori informazioni, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Tipi di routine di operatore  
 Una routine di operatore può essere uno dei seguenti tipi:  
  
-   Una definizione di un operatore unario in cui l'argomento è del tipo di classe o struttura.  
  
-   Una definizione di un operatore binario in cui almeno uno degli argomenti è del tipo di classe o struttura.  
  
-   Definizione di un operatore di conversione in cui l'argomento è del tipo di classe o struttura.  
  
-   Definizione di un operatore di conversione che restituisce il tipo di classe o struttura.  
  
 Gli operatori di conversione sono sempre unari e utilizzare sempre `CType` come l'operatore che si sta definendo.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare una routine di operatore è come segue:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *simbolooperatore* `(` *operand1*`[,`*operand2* `]) As` *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Utilizzare il `Widening` o `Narrowing` parola chiave solo su un operatore di conversione del tipo. Il simbolo dell'operatore è sempre [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per un operatore di conversione del tipo.  
  
 È necessario dichiarare due operandi per definire un operatore binario e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione del tipo. Tutti gli operandi devono essere dichiarati `ByVal`.  
  
 Dichiarare ogni operando esattamente dichiarare i parametri per [Sub (routine)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Poiché si sta definendo un operatore in una classe o struttura definita, almeno uno degli operandi deve essere del tipo di dati di quella classe o struttura. Per un operatore di conversione del tipo, l'operando o il tipo restituito deve essere del tipo di dati della classe o struttura.  
  
 Per ulteriori informazioni, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Richiamare una routine di operatore in modo implicito tramite il simbolo dell'operatore in un'espressione. Gli operandi vengono forniti la stessa procedura utilizzata per gli operatori predefiniti.  
  
 La sintassi per una chiamata implicita a una routine di operatore è come segue:  
  
 `Dim testStruct As`  *nomestruttura*  
  
 `Dim testNewStruct As`  *nomestruttura*`= testStruct`*simbolooperatore*  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e chiamata  
 La struttura seguente archivia un valore intero con segno a 128 bit come le parti costitutive alto e basso. Definisce il `+` operatore per aggiungere due `veryLong` valori e generare una risultante `veryLong` valore.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata per il `+` operatore definito in `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Per altre informazioni ed esempi, vedere [Overload di operatori in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Procedura: Definire un operatore](./how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)  
 [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)  
 [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
