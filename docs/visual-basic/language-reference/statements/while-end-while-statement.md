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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843710"
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
|`condition`|Obbligatorio. `Boolean` espressione. Se `condition` viene `Nothing`, Visual Basic lo considera come `False`.|  
|`statements`|Facoltativo. Uno o più istruzioni che seguono `While`, che ogni fase di esecuzione `condition` è `True`.|  
|`Continue While`|Facoltativo. Trasferisce il controllo all'iterazione successiva del `While` blocco.|  
|`Exit While`|Facoltativo. Trasferisce il controllo fuori il `While` blocco.|  
|`End While`|Obbligatorio. Termina la definizione del blocco `While`.|  
  
## <a name="remarks"></a>Note  
 Usare un `While...End While` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte in cui, purché una condizione resta `True`. Se si desidera maggiore flessibilità su dove la condizione di test o per quale risultato si esegue il test, si potrebbe preferire il [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md). Se si desidera ripetere un determinato numero di volte, le istruzioni di [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
> [!NOTE]
>  Il `While` parola chiave viene usata anche nel [è... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md), il [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e il [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Se `condition` è `True`, tutti i del `statements` esecuzione finché il `End While` viene rilevata l'istruzione. Il controllo ritorna quindi per la `While` istruzione e `condition` viene nuovamente verificata. Se `condition` resta `True`, il processo viene ripetuto. In caso affermativo `False`, il controllo passa all'istruzione che segue il `End While` istruzione.  
  
 Il `While` sempre istruzione verifica la condizione prima che venga avviato il ciclo. Esecuzione del ciclo continua finché la condizione rimane `True`. Se `condition` è `False` quando si immissione prima di tutto il ciclo, non viene eseguito neppure una volta.  
  
 Il `condition` generalmente i risultati da un confronto di due valori, ma possono essere qualsiasi espressione che restituisce un [tipo di dati booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`). Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean`.  
  
 È possibile annidare `While` inserendo un ciclo all'interno di altra. È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di loro. Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Uscita durante  
 Il [uscire mentre](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un altro modo per chiudere un `While` ciclo. `Exit While` Trasferisce il controllo all'istruzione che segue immediatamente il `End While` istruzione.  
  
 In genere si usa `Exit While` dopo che viene valutata una condizione (ad esempio, in un `If...Then...Else` struttura). È possibile uscire da un ciclo se si rileva una condizione che rende inutili o impossibili da continuare a eseguire iterazioni, ad esempio un valore errato o una richiesta di terminazione. È possibile usare `Exit While` quando si testa una condizione che potrebbe causare un' *ciclo infinito*, ovvero un ciclo che è stato possibile eseguire un numero estremamente grande o infinito di volte. È quindi possibile usare `Exit While` per interrompere il ciclo.  
  
 È possibile inserire un numero qualsiasi di `Exit While` istruzioni in qualsiasi punto nel `While` ciclo.  
  
 Quando usata all'interno di cicli `While` cicli, `Exit While` trasferisce il controllo all'esterno del ciclo più interno e nel livello superiore successivo di annidamento.  
  
 Il `Continue While` istruzione immediatamente trasferisce il controllo all'iterazione successiva del ciclo. Per altre informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni nel ciclo continuano fino a incontrare il `index` variabile è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo dei `Continue While` e `Exit While` istruzioni.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente legge tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nel `While` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se il file contiene caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
