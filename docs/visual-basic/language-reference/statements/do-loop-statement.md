---
title: Istruzione Do...Loop
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
ms.openlocfilehash: a9ec6caccbe161a39b592a642a938b81bae911a6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404784"
---
# <a name="doloop-statement-visual-basic"></a>Istruzione Do...Loop (Visual Basic)
Ripete un blocco di istruzioni mentre una `Boolean` condizione è `True` o finché la condizione non diventa `True` .  
  
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
|`Do`|Obbligatorio. Avvia la definizione del `Do` ciclo.|  
|`While`|Obbligatorio a meno che non sia usato `Until`. Ripetere il ciclo finché non `condition` è `False` .|  
|`Until`|Obbligatorio a meno che non sia usato `While`. Ripetere il ciclo finché non `condition` è `True` .|  
|`condition`|Facoltativa. Espressione `Boolean`. Se `condition` è `Nothing` , Visual Basic lo considera come `False` .|  
|`statements`|Facoltativa. Una o più istruzioni ripetute durante o fino a `condition` `True` .|  
|`Continue Do`|Facoltativa. Trasferisce il controllo all'iterazione successiva del `Do` ciclo.|  
|`Exit Do`|Facoltativa. Trasferisce il controllo all'esterno del `Do` ciclo.|  
|`Loop`|Obbligatorio. Termina la definizione del `Do` ciclo.|  
  
## <a name="remarks"></a>Commenti  
 Utilizzare una `Do...Loop` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte, fino a quando non viene soddisfatta una condizione. Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](for-next-statement.md) è in genere una scelta migliore.  
  
 È possibile utilizzare `While` o `Until` per specificare `condition` , ma non entrambi.  
  
 È possibile eseguire il test `condition` solo una volta, sia all'inizio che alla fine del ciclo. Se si verifica `condition` all'inizio del ciclo (nell' `Do` istruzione), il ciclo potrebbe non essere eseguito neanche una volta. Se si esegue il test alla fine del ciclo (nell' `Loop` istruzione), il ciclo viene sempre eseguito almeno una volta.  
  
 La condizione viene in genere generata da un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore [booleano di tipo di dati](../data-types/boolean-data-type.md) ( `True` o `False` ). Sono inclusi i valori di altri tipi di dati, ad esempio i tipi numerici, che sono stati convertiti in `Boolean` .  
  
 È possibile annidare `Do` cicli inserendo un ciclo all'interno di un altro. È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> La `Do...Loop` struttura offre una maggiore flessibilità rispetto al [tempo... End While](while-end-while-statement.md) , perché consente di decidere se terminare il ciclo quando viene `condition` interrotto `True` o quando diventa prima `True` . Consente inoltre di eseguire il test `condition` sia all'inizio che alla fine del ciclo.  
  
## <a name="exit-do"></a>Esci da do  
 L'istruzione [Exit Do](exit-statement.md) può fornire un metodo alternativo per uscire da `Do…Loop` . `Exit Do`trasferisce immediatamente il controllo all'istruzione che segue l' `Loop` istruzione.  
  
 `Exit Do`viene spesso usato dopo la valutazione di una determinata condizione, ad esempio in una `If...Then...Else` struttura. Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione. Un uso di `Exit Do` è quello di verificare la presenza di una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte elevato o infinito. È possibile utilizzare `Exit Do` per eseguire l'escape del ciclo.  
  
 È possibile includere qualsiasi numero di `Exit Do` istruzioni in un punto qualsiasi di un oggetto `Do…Loop` .  
  
 Quando viene utilizzato all'interno `Do` di cicli annidati, `Exit Do` trasferisce il controllo al di fuori del ciclo più interno e al successivo livello di nidificazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando la `index` variabile non è maggiore di 10. La `Until` clausola si trova alla fine del ciclo.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata una `While` clausola anziché una `Until` clausola e `condition` viene testato all'inizio del ciclo anziché alla fine.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `condition` Arresta il ciclo quando la `index` variabile è maggiore di 100. Nell' `If` istruzione del ciclo, tuttavia, l' `Exit Do` istruzione arresta il ciclo quando la variabile di indice è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono lette tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un oggetto <xref:System.IO.StreamReader> che legge i caratteri. Nella `Do...Loop` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo di `StreamReader` determina se sono presenti caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione For...Next](for-next-statement.md)
- [Tipo di dati Boolean](../data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](exit-statement.md)
- [Istruzione While...End While](while-end-while-statement.md)
