---
title: Istruzione While...End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965805"
---
# <a name="whileend-while-statement-visual-basic"></a>Istruzione While...End While (Visual Basic)
Esegue una serie di istruzioni purché una determinata condizione sia `True`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`condition`|Richiesto. `Boolean`espressione. Se `condition` `False`è `Nothing`, Visual Basic lo considera come.|  
|`statements`|facoltativo. Una o più istruzioni che `While`seguono, che vengono eseguite `condition` ogni `True`volta è.|  
|`Continue While`|facoltativo. Trasferisce il controllo all'iterazione successiva `While` del blocco.|  
|`Exit While`|facoltativo. Trasferisce il controllo all' `While` esterno del blocco.|  
|`End While`|Richiesto. Termina la definizione del blocco `While`.|  
  
## <a name="remarks"></a>Note  
 Utilizzare una `While...End While` struttura quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, purché rimanga `True`una condizione. Se si desidera maggiore flessibilità con la posizione in cui si testa la condizione o il risultato per il test, è preferibile [eseguire... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md). Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
> [!NOTE]
> La `While` parola chiave viene usata anche nel. [.. Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Se `condition` `statements` `End While` è `True`, tutto l'esecuzione fino a quando non viene rilevata l'istruzione. Il `While` controllo viene quindi restituito all'istruzione e `condition` viene di nuovo controllata. Se `condition` è ancora `True`, il processo viene ripetuto. Se è `False`, il controllo passa all'istruzione che segue l' `End While` istruzione.  
  
 L' `While` istruzione controlla sempre la condizione prima di avviare il ciclo. Il ciclo continua finché la condizione rimane `True`. Se `condition` è`False` la prima volta che si immette il ciclo, non viene eseguito neanche una volta.  
  
 Il `condition` risultato è in genere dovuto a un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore di [tipo di dati booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`). Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato `Boolean`convertito in.  
  
 È possibile annidare `While` i cicli inserendo un ciclo all'interno di un altro. È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Esci da  
 L'istruzione [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) può fornire un altro modo per uscire `While` da un ciclo. `Exit While`trasferisce immediatamente il controllo all'istruzione che segue `End While` l'istruzione.  
  
 In genere si `Exit While` USA dopo la valutazione di una determinata condizione, ad esempio `If...Then...Else` in una struttura. Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione. È possibile usare `Exit While` quando si esegue il test di una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte molto grande o addirittura infinito. È quindi possibile usare `Exit While` per eseguire l'escape del ciclo.  
  
 È possibile inserire un numero qualsiasi `Exit While` di istruzioni `While` in qualsiasi punto del ciclo.  
  
 Quando viene utilizzato all' `While` interno di `Exit While` cicli annidati, trasferisce il controllo al di fuori del ciclo più interno e al successivo livello di nidificazione.  
  
 L' `Continue While` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando `index` la variabile non è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo delle `Continue While` istruzioni e. `Exit While`  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono lette tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> oggetto che legge i caratteri. Nella condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo di `StreamReader` determina se il file contiene caratteri aggiuntivi. `While`  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
