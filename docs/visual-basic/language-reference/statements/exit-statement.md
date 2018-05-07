---
title: Istruzione Exit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 05a65dd84a00478f52c8cd7d8b46341644512718
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exit-statement-visual-basic"></a>Istruzione Exit (Visual Basic)
Esce da una routine o il blocco e trasferisce immediatamente il controllo all'istruzione che segue la chiamata di routine o la definizione di blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Istruzioni  
 `Exit Do`  
 Chiude immediatamente il `Do` ciclo in cui compare. L'esecuzione continua con l'istruzione che segue il `Loop` istruzione. `Exit Do` può essere utilizzato solo all'interno di un `Do` ciclo. Se utilizzato all'interno di cicli `Do` cicli, `Exit Do` esce dal ciclo più interno e trasferisce il controllo del successivo livello superiore di annidamento.  
  
 `Exit For`  
 Chiude immediatamente il `For` ciclo in cui compare. L'esecuzione continua con l'istruzione che segue il `Next` istruzione. `Exit For` può essere utilizzato solo all'interno di un `For`... `Next` o `For Each`... `Next` ciclo. Se utilizzato all'interno di cicli `For` cicli, `Exit For` esce dal ciclo più interno e trasferisce il controllo del successivo livello superiore di annidamento.  
  
 `Exit Function`  
 Chiude immediatamente il `Function` procedure in cui è presente. L'esecuzione continua con l'istruzione successiva all'istruzione che ha chiamato la `Function` procedura. `Exit Function` può essere utilizzato solo all'interno di un `Function` stored procedure.  
  
 Per specificare un valore restituito, è possibile assegnare il valore per il nome della funzione in una riga prima di `Exit Function` istruzione. Per assegnare il valore restituito e chiudere la funzione in un'unica istruzione, è possibile utilizzare invece il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Chiude immediatamente il `Property` procedure in cui è presente. L'esecuzione continua con l'istruzione che ha chiamato la `Property` procedura, vale a dire, con l'istruzione che richiede o imposta il valore della proprietà. `Exit Property` può essere utilizzato solo all'interno di una proprietà `Get` o `Set` stored procedure.  
  
 Per specificare un valore restituito in un `Get` procedura, è possibile assegnare il valore per il nome della funzione in una riga prima di `Exit Property` istruzione. Per assegnare il valore restituito e uscita di `Get` procedure in un'unica istruzione, è possibile utilizzare invece il `Return` istruzione.  
  
 In un `Set` procedure, il `Exit Property` equivale all'istruzione il `Return` istruzione.  
  
 `Exit Select`  
 Chiude immediatamente il `Select Case` blocco in cui compare. L'esecuzione continua con l'istruzione che segue il `End Select` istruzione. `Exit Select` può essere utilizzato solo all'interno di un `Select Case` istruzione.  
  
 `Exit Sub`  
 Chiude immediatamente il `Sub` procedure in cui è presente. L'esecuzione continua con l'istruzione successiva all'istruzione che ha chiamato la `Sub` procedura. `Exit Sub` può essere utilizzato solo all'interno di un `Sub` stored procedure.  
  
 In un `Sub` procedure, il `Exit Sub` equivale all'istruzione il `Return` istruzione.  
  
 `Exit Try`  
 Chiude immediatamente il `Try` o `Catch` blocco in cui compare. L'esecuzione continua con la `Finally` blocco se è presente, o con l'istruzione che segue il `End Try` istruzione in caso contrario. `Exit Try` può essere utilizzato solo all'interno di un `Try` oppure `Catch` blocco e non all'interno un `Finally` blocco.  
  
 `Exit While`  
 Chiude immediatamente il `While` ciclo in cui compare. L'esecuzione continua con l'istruzione che segue il `End While` istruzione. `Exit While` può essere utilizzato solo all'interno di un `While` ciclo. Se utilizzato all'interno di cicli `While` cicli, `Exit While` trasferisce il controllo al ciclo nidificato al livello immediatamente superiore al ciclo in cui `Exit While` si verifica.  
  
## <a name="remarks"></a>Note  
 Non confondere `Exit` istruzioni con `End` istruzioni. `Exit` definisce la fine di un'istruzione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, la condizione di ciclo viene arrestato il ciclo quando il `index` variabile è maggiore di 100. Il `If` istruzione nel ciclo, tuttavia, comporta la `Exit Do` istruzione per interrompere il ciclo quando la variabile di indice è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene assegnato il valore restituito per il nome della funzione `myFunction`e quindi utilizza `Exit Function` da restituire dalla funzione.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) per assegnare il valore restituito e uscire dalla funzione.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Istruzione Stop](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
