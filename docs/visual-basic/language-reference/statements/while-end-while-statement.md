---
title: Istruzione While...End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352743"
---
# <a name="whileend-while-statement-visual-basic"></a>Istruzione While...End While (Visual Basic)
Esegue una serie di istruzioni purché una determinata condizione sia `True`.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
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
|`condition`|Obbligatoria. espressione `Boolean`. Se `condition` è `Nothing`, Visual Basic lo considera `False`.|  
|`statements`|Facoltativa. Una o più istruzioni che seguono `While`, che vengono eseguite ogni volta che viene `True``condition`.|  
|`Continue While`|Facoltativa. Trasferisce il controllo all'iterazione successiva del blocco `While`.|  
|`Exit While`|Facoltativa. Trasferisce il controllo all'esterno del blocco `While`.|  
|`End While`|Obbligatoria. Termina la definizione del blocco `While`.|  
  
## <a name="remarks"></a>Note  
 Utilizzare una struttura `While...End While` quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, purché rimanga `True`una condizione. Se si desidera maggiore flessibilità con la posizione in cui si testa la condizione o il risultato per il test, è preferibile [eseguire... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md). Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
> [!NOTE]
> La parola chiave `While` viene utilizzata anche nell' [attività do... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Se `condition` è `True`, tutti i `statements` eseguiti fino a quando non viene rilevata l'istruzione `End While`. Il controllo viene quindi restituito all'istruzione `While` e la `condition` viene nuovamente controllata. Se `condition` è ancora `True`, il processo viene ripetuto. Se è `False`, il controllo passa all'istruzione che segue l'istruzione `End While`.  
  
 L'istruzione `While` controlla sempre la condizione prima di avviare il ciclo. Il ciclo continua finché la condizione rimane `True`. Se `condition` viene `False` quando si immette il ciclo per la prima volta, non viene eseguito neanche una volta.  
  
 Il `condition` in genere deriva da un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore [booleano di tipo di dati](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`). Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean`.  
  
 È possibile annidare `While` cicli inserendo un ciclo all'interno di un altro. È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Esci da  
 L'istruzione [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) può fornire un altro modo per uscire da un ciclo `While`. `Exit While` trasferisce immediatamente il controllo all'istruzione che segue l'istruzione `End While`.  
  
 In genere si usa `Exit While` dopo la valutazione di una determinata condizione, ad esempio in una struttura di `If...Then...Else`. Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione. È possibile utilizzare `Exit While` quando si verifica una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte molto grande o anche infinito. È quindi possibile usare `Exit While` per eseguire l'escape del ciclo.  
  
 È possibile inserire un numero qualsiasi di istruzioni di `Exit While` in qualsiasi punto del ciclo `While`.  
  
 Quando viene utilizzato all'interno di cicli di `While` annidati, `Exit While` trasferisce il controllo dal ciclo più interno al successivo livello di nidificazione.  
  
 L'istruzione `Continue While` trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando la variabile di `index` non è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo delle istruzioni `Continue While` e `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono lette tutte le righe in un file di testo. Il metodo <xref:System.IO.File.OpenText%2A> apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nella condizione `While` il <xref:System.IO.StreamReader.Peek%2A> metodo del `StreamReader` determina se il file contiene caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
