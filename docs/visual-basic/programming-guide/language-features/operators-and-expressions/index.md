---
title: Operatori ed espressioni in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dae47988e27ed4b1a714943ce1fbffe3b815066b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="operators-and-expressions-in-visual-basic"></a>Operatori ed espressioni in Visual Basic
Un *operatore* è un elemento di codice che esegue un'operazione su uno o più elementi di codice che contengono valori. Gli elementi di valore includono variabili, costanti, valori letterali, proprietà, espressioni e valori restituiti da procedure `Function` e `Operator`.  
  
 Un'*espressione* è una serie di elementi di valore combinati con operatori che restituisce un nuovo valore. Gli operatori agiscono sugli elementi di valore mediante l'esecuzione di calcoli, confronti o altre operazioni.  
  
## <a name="types-of-operators"></a>Tipi di operatori  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] include i tipi di operatori seguenti:  
  
-   Gli [operatori aritmetici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) eseguono calcoli comuni su valori numerici, inclusa l'inversione degli schemi di bit.  
  
-   Gli [operatori di confronto](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) confrontano due espressioni e restituiscono un valore `Boolean` che rappresenta il risultato del confronto.  
  
-   Gli [operatori di concatenamento](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) uniscono più stringhe in un'unica stringa.  
  
-   Gli [operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combinano valori `Boolean` o numerici e restituiscono un risultato con lo stesso tipo di dati dei valori.  
  
 Gli elementi di valore che vengono combinati con un operatore sono detti *operandi* di tale operatore. Gli operatori combinati con elementi di valore formano espressioni, ad eccezione dell'operatore di assegnazione che forma un'*istruzione*. Per altre informazioni, vedere [Istruzioni](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
## <a name="evaluation-of-expressions"></a>Valutazione delle espressioni  
 Il risultato finale di un'espressione rappresenta un valore, in genere espresso con un tipo di dati comune quale `Boolean`, `String` o un tipo numerico.  
  
 Di seguito sono riportati esempi di espressioni.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Più operatori possono eseguire azioni in un'unica operazione o istruzione, come illustrato nel seguente esempio.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 Nell'esempio precedente [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] esegue le operazioni nell'espressione sul lato destro dell'operatore di assegnazione (`=`), quindi assegna il valore risultante alla variabile `x` sul lato sinistro. Non esistono limiti al numero di operatori combinabili in un'espressione, ma per ottenere i risultati previsti è importante tenere presenti le regole di [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
 Per altre informazioni ed esempi, vedere [Overload di operatori in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori](../../../../visual-basic/language-reference/operators/index.md)  
 [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
