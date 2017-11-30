---
title: Istruzione If...Then...Else (Visual Basic) |
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a>Istruzione If...Then...Else (Visual Basic) |
Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
' Multiple-line syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  
  
## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. Espressione. Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.  
  
 Se l'espressione è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisce [nulla](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione non è `True`e `Else` blocco eseguito.  
  
 `Then`  
 Richiesto nella sintassi a riga singola; facoltativo per la sintassi di più righe.  
  
 `statements`  
 Parametro facoltativo. Uno o più istruzioni che seguono `If`... `Then` che vengono eseguite se `condition` restituisce `True`.  
  
 `elseifcondition`  
 Obbligatorio se `ElseIf` è presente. Espressione. Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.  
  
 `elseifstatements`  
 Parametro facoltativo. Uno o più istruzioni che seguono `ElseIf`... `Then` che vengono eseguite se `elseifcondition` restituisce `True`.  
  
 `elsestatements`  
 Parametro facoltativo. Una o più istruzioni eseguite se non precedente `condition` o `elseifcondition` espressione viene valutata `True`.  
  
 `End If`  
 Termina il `If`... `Then`... `Else` blocco.  
  
## <a name="remarks"></a>Note  
  
## <a name="multiple-line-syntax"></a>Sintassi di più righe  
 Quando un `If`... `Then`... `Else` viene rilevata l'istruzione, `condition` viene eseguito il test. Se `condition` è `True`, le istruzioni che seguono `Then` vengono eseguite. Se `condition` è `False`, ogni `ElseIf` istruzione (se presenti) viene considerata nell'ordine. Quando un `True``elseifcondition` viene trovato, le istruzioni che seguono immediatamente associato `ElseIf` vengono eseguite. Se non `elseifcondition` restituisce `True`, o se non esistono alcun `ElseIf` istruzioni, le istruzioni che seguono `Else` vengono eseguite. Dopo l'esecuzione di istruzioni che seguono `Then`, `ElseIf`, o `Else`, l'esecuzione continua con la seguente istruzione `End If`.  
  
 Il `ElseIf` e `Else` clausole sono entrambi facoltativi. È possibile specificare qualsiasi numero `ElseIf` clausole come si desidera che un `If`... `Then`... `Else` istruzione, ma non `ElseIf` clausola può comparire dopo un `Else` clausola. `If`... `Then`... `Else` possono essere annidate all'interno di altro.  
  
 Nella sintassi di più righe, il `If` istruzione deve essere l'unica istruzione nella prima riga. Il `ElseIf`, `Else`, e `End If` istruzioni possono essere precedute solo da un'etichetta di riga. Il `If`... `Then`... `Else` blocco deve terminare con un `End If` istruzione.  
  
> [!TIP]
>  Il [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) potrebbero essere più utili quando si valuta una singola espressione che dispone di più valori.  
  
## <a name="single-line-syntax"></a>Sintassi a riga singola  
 Per eseguire test breve e semplice, è possibile utilizzare la sintassi a riga singola. Tuttavia, la sintassi di più righe offre maggiore flessibilità e struttura e viene in genere più facile leggere, gestione e debug.  
  
 Di seguito il `Then` parola chiave viene esaminato per determinare se un'istruzione è una riga singola `If`. Se diverso da un commento viene visualizzato dopo `Then` sulla stessa riga, l'istruzione viene considerato come una riga singola `If` istruzione. Se `Then` è assente, deve essere l'inizio di una riga di più `If`... `Then`... `Else`.  
  
 Nella sintassi a riga singola, è possibile inserire più istruzioni eseguite come risultato di un `If`... `Then` delle decisioni. Tutte le istruzioni devono essere nella stessa riga e di essere separate da virgola.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo della sintassi di più righe di `If`... `Then`... `Else` istruzione.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene nidificata `If`... `Then`... `Else` istruzioni.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Strutture decisionali](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
