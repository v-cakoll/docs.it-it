---
title: 'Procedura: definire un operatore di conversione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0f9e63ba039a48226186fa4ce118d3e47b5673e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Procedura: definire un operatore di conversione (Visual Basic)
Se è stato definito una classe o struttura, è possibile definire un operatore di conversione di tipi tra il tipo di classe o struttura e un altro tipo di dati (ad esempio `Integer`, `Double`, o `String`).  
  
 Definire la conversione del tipo come un [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) routine all'interno della classe o struttura. Tutte le routine di conversione devono essere `Public Shared`, e ognuno di essi è necessario specificare [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) o [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce gli operatori di conversione tra una struttura denominata `digit` e `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 È possibile testare la struttura `digit` con il codice seguente.  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine di operatore](./operator-procedures.md)  
 [Procedura: Definire un operatore](./how-to-define-an-operator.md)  
 [Procedura: Chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)  
 [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)  
 [Istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
