---
title: Istruzione Do...Loop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: e12cdc1ae405b877d4d27d1947c98dcb51938ba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="doloop-statement-visual-basic"></a>Istruzione Do...Loop (Visual Basic)
Ripete un blocco di istruzioni finché una `Boolean` condizione è `True` o fino a quando la condizione non diventa `True`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`Do`|Obbligatorio. Inizia la definizione di `Do` ciclo.|  
|`While`|Obbligatorio a meno che non sia usato `Until`. Ripetere il ciclo finché `condition` è `False`.|  
|`Until`|Obbligatorio a meno che non sia usato `While`. Ripetere il ciclo finché `condition` è `True`.|  
|`condition`|Facoltativo. `Boolean` Espressione. Se `condition` è `Nothing`, Visual Basic lo considera come `False`.|  
|`statements`|Facoltativo. Una o più istruzioni che vengono ripetute durante o fino a quando `condition` è `True`.|  
|`Continue Do`|Facoltativo. Trasferisce il controllo all'iterazione successiva di `Do` ciclo.|  
|`Exit Do`|Facoltativo. Trasferisce il controllo fuori il `Do` ciclo.|  
|`Loop`|Obbligatorio. Termina la definizione di `Do` ciclo.|  
  
## <a name="remarks"></a>Note  
 Utilizzare un `Do...Loop` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte, fino a quando non viene soddisfatta una condizione. Se si desidera ripetere le istruzioni di un numero di volte, il [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
 È possibile utilizzare `While` o `Until` per specificare `condition`, ma non entrambi.  
  
 È possibile testare `condition` solo una volta, all'inizio o fine del ciclo. Se si prova `condition` all'inizio del ciclo (nel `Do` istruzione), il ciclo potrebbe non essere eseguito anche una sola volta. Se si verifica alla fine del ciclo (nel `Loop` istruzione), il ciclo viene eseguito sempre almeno una volta.  
  
 La condizione in genere il risultato un confronto tra due valori, ma può essere qualsiasi espressione che restituisce un [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`). Sono inclusi i valori di altri tipi di dati, ad esempio tipi numerici, che sono stati convertiti in `Boolean`.  
  
 È possibile annidare `Do` cicli inserendo un ciclo all'interno di un altro. È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro. Per ulteriori informazioni, vedere [strutture di controllo nidificate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Il `Do...Loop` struttura offre maggiore flessibilità di [mentre... Istruzione While fine](../../../visual-basic/language-reference/statements/while-end-while-statement.md) perché ti consente di decidere se terminare il ciclo quando `condition` diviene `True` o quando diventa `True`. Inoltre, consente di testare `condition` all'inizio o fine del ciclo.  
  
## <a name="exit-do"></a>Exit Do  
 Il [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un modo alternativo per uscire da un `Do…Loop`. `Exit Do` Trasferisce il controllo all'istruzione che segue immediatamente il `Loop` istruzione.  
  
 `Exit Do` spesso viene utilizzata dopo una condizione viene valutata, ad esempio in un `If...Then...Else` struttura. È possibile uscire da un ciclo se si rileva una condizione che rende Impossibile continuare la ripetizione, ad esempio una richiesta di terminazione o di un valore errato o non necessarie. Un utilizzo di `Exit Do` consiste nel verificare la presenza di una condizione che potrebbe causare un *ciclo infinito*, ovvero un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. È possibile utilizzare `Exit Do` per interrompere il ciclo.  
  
 È possibile includere un numero qualsiasi di `Exit Do` le istruzioni in un punto qualsiasi in un `Do…Loop`.  
  
 Se utilizzato all'interno di cicli `Do` cicli, `Exit Do` trasferisce il controllo all'esterno del ciclo più interno e del successivo livello superiore di annidamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni nel ciclo di continuano l'esecuzione fino a quando il `index` variabile è maggiore di 10. Il `Until` clausola è alla fine del ciclo.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un `While` clausola anziché un `Until` clausola e `condition` viene verificata all'inizio del ciclo anziché alla fine.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `condition` il ciclo viene interrotto quando il `index` variabile è maggiore di 100. Il `If` istruzione nel ciclo, tuttavia, comporta la `Exit Do` istruzione per interrompere il ciclo quando la variabile di indice è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente legge tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nel `Do...Loop` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se sono presenti eventuali caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
