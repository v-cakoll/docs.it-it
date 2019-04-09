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
ms.openlocfilehash: 80c9a77494be95365899c6a25435fcfc5d2a7293
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175019"
---
# <a name="operator-procedures-visual-basic"></a>Routine di operatore (Visual Basic)
Una routine di operatore è una serie di istruzioni di Visual Basic che definiscono il comportamento di un operatore standard (ad esempio `*`, `<>`, o `And`) in una classe o struttura definita. Questo è l'acronimo *overload degli operatori*.  
  
## <a name="when-to-define-operator-procedures"></a>Quando definire le routine di operatore  
 Dopo aver definito una classe o struttura, è possibile dichiarare variabili sia del tipo di quella classe o struttura. In alcuni casi tale variabile deve far parte di un'operazione come parte di un'espressione. A tale scopo, deve essere un operando di un operatore.  
  
 Visual Basic definisce gli operatori solo sui tipi di dati più importanti. È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono del tipo di classe o struttura.  
  
 Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Tipi di routine di operatore  
 Una routine di operatore può essere uno dei tipi seguenti:  
  
-   Una definizione di un operatore unario dove l'argomento è del tipo di classe o struttura.  
  
-   Una definizione di un operatore binario in cui almeno uno degli argomenti è del tipo di classe o struttura.  
  
-   Una definizione di un operatore di conversione in cui l'argomento è del tipo di classe o struttura.  
  
-   Una definizione di un operatore di conversione che restituisce il tipo di classe o struttura.  
  
 Gli operatori di conversione sono sempre unario e utilizzare sempre `CType` dell'operatore a cui si sta definendo.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare una routine di operatore è come segue:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *simbolooperatore* `(` *operand1*`[,`*operand2* `]) As` *datatype*   
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Si utilizza il `Widening` o `Narrowing` parola chiave solo su un operatore di conversione di tipi. Il simbolo dell'operatore è sempre [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) per un operatore di conversione di tipi.  
  
 Si dichiarano due operandi per definire un operatore binario, e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione di tipi. Tutti gli operandi devono essere dichiarati `ByVal`.  
  
 Si dichiara ogni operando simile a quello dichiarare i parametri per [Sub (routine)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Poiché si sta definendo un operatore in una classe o struttura definita, almeno uno degli operandi deve essere del tipo di dati di tale classe o struttura. Per un operatore di conversione di tipi, l'operando o il tipo restituito deve essere del tipo di dati della classe o struttura.  
  
 Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Una routine di operatore è richiamare in modo implicito usando il simbolo di operatore in un'espressione. Gli operandi vengono forniti la stessa procedura valida per gli operatori predefiniti.  
  
 La sintassi per una chiamata implicita a una routine di operatore è come segue:  
  
 `Dim testStruct As`  *nomestruttura*  
  
 `Dim testNewStruct As`  *nomestruttura*`= testStruct`*simbolooperatore*   `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e di chiamata  
 La struttura seguente archivia un valore intero con segno a 128 bit come le parti costituenti alto e basso. Definisce i `+` operaa a add due `veryLong` i valori e generare una risultante `veryLong` valore.  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata per il `+` operatore definito in `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine di proprietà](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Procedura: Definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
