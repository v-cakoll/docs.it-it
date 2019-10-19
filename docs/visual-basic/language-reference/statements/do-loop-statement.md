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
ms.openlocfilehash: eff5239e07ca27f40ece5af68f46c491be91cf09
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583447"
---
# <a name="doloop-statement-visual-basic"></a>Istruzione Do...Loop (Visual Basic)
Ripete un blocco di istruzioni mentre una condizione `Boolean` viene `True` o finché la condizione non viene `True`.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
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
|`Do`|Obbligatorio. Avvia la definizione del ciclo `Do`.|  
|`While`|Obbligatorio a meno che non sia usato `Until`. Ripetere il ciclo finché non viene `False` `condition`.|  
|`Until`|Obbligatorio a meno che non sia usato `While`. Ripetere il ciclo finché non viene `True` `condition`.|  
|`condition`|Parametro facoltativo. espressione `Boolean`. Se `condition` è `Nothing`, Visual Basic lo considera `False`.|  
|`statements`|Parametro facoltativo. Una o più istruzioni che vengono ripetute durante o fino a quando `condition` viene `True`.|  
|`Continue Do`|Parametro facoltativo. Trasferisce il controllo all'iterazione successiva del ciclo `Do`.|  
|`Exit Do`|Parametro facoltativo. Trasferisce il controllo all'esterno del ciclo `Do`.|  
|`Loop`|Obbligatorio. Termina la definizione del ciclo `Do`.|  
  
## <a name="remarks"></a>Note  
 Utilizzare una struttura `Do...Loop` quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, fino a quando non viene soddisfatta una condizione. Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
 È possibile utilizzare `While` o `Until` per specificare `condition`, ma non entrambi.  
  
 È possibile testare `condition` solo una volta, sia all'inizio che alla fine del ciclo. Se si testa `condition` all'inizio del ciclo (nell'istruzione `Do`), il ciclo potrebbe non essere eseguito neanche una volta. Se si esegue il test alla fine del ciclo (nell'istruzione `Loop`), il ciclo viene sempre eseguito almeno una volta.  
  
 La condizione viene in genere generata da un confronto di due valori, ma può trattarsi di qualsiasi espressione che restituisce un valore [booleano di tipo di dati](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`). Sono inclusi i valori di altri tipi di dati, ad esempio i tipi numerici, che sono stati convertiti in `Boolean`.  
  
 È possibile annidare `Do` cicli inserendo un ciclo all'interno di un altro. È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> La struttura di `Do...Loop` offre una maggiore flessibilità rispetto al [periodo di tempo... End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , perché consente di decidere se terminare il ciclo quando `condition` viene interrotto `True` o quando viene `True`to per la prima volta. Consente inoltre di testare `condition` all'inizio o alla fine del ciclo.  
  
## <a name="exit-do"></a>Esci da do  
 L'istruzione [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) può fornire un metodo alternativo per uscire da un `Do…Loop`. `Exit Do` trasferisce immediatamente il controllo all'istruzione che segue l'istruzione `Loop`.  
  
 `Exit Do` viene spesso utilizzata dopo la valutazione di una determinata condizione, ad esempio in una struttura di `If...Then...Else`. Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione. Un utilizzo di `Exit Do` consiste nel verificare la presenza di una condizione che potrebbe causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte elevato o infinito. È possibile utilizzare `Exit Do` per eseguire l'escape del ciclo.  
  
 È possibile includere un numero qualsiasi di istruzioni di `Exit Do` in qualsiasi punto di un `Do…Loop`.  
  
 Quando viene utilizzato all'interno di cicli di `Do` annidati, `Exit Do` trasferisce il controllo dal ciclo più interno al successivo livello di nidificazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando la variabile di `index` non è maggiore di 10. La clausola `Until` si trova alla fine del ciclo.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata una clausola `While` anziché una clausola `Until` e `condition` viene testato all'inizio del ciclo anziché alla fine.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente `condition` interrompe il ciclo quando la variabile `index` è maggiore di 100. L'istruzione `If` nel ciclo, tuttavia, causa l'arresto del ciclo da parte dell'istruzione `Exit Do` quando la variabile di indice è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono lette tutte le righe in un file di testo. Il metodo <xref:System.IO.File.OpenText%2A> apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nella condizione `Do...Loop` il <xref:System.IO.StreamReader.Peek%2A> metodo del `StreamReader` determina se sono presenti caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
