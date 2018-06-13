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
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604731"
---
# <a name="whileend-while-statement-visual-basic"></a>Istruzione While...End While (Visual Basic)
Esegue una serie di istruzioni purché una determinata condizione è `True`.  
  
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
|`condition`|Obbligatorio. `Boolean` Espressione. Se `condition` è `Nothing`, Visual Basic lo considera come `False`.|  
|`statements`|Facoltativo. Uno o più istruzioni che seguono `While`, che ogni fase di esecuzione `condition` è `True`.|  
|`Continue While`|Facoltativo. Trasferisce il controllo all'iterazione successiva del `While` blocco.|  
|`Exit While`|Facoltativo. Trasferisce il controllo fuori il `While` blocco.|  
|`End While`|Obbligatorio. Termina la definizione del blocco `While`.|  
  
## <a name="remarks"></a>Note  
 Utilizzare un `While...End While` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte, fino a quando una condizione non `True`. Se si desidera maggiore flessibilità su dove la condizione di test o per quale risultato si esegue il test, potrebbe preferire il [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md). Se si desidera ripetere le istruzioni di un numero di volte, il [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
> [!NOTE]
>  Il `While` (parola chiave) viene usato anche nel [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md), [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Se `condition` è `True`tutti del `statements` esecuzione fino a quando il `End While` viene rilevata un'istruzione. Il controllo ritorna quindi per il `While` istruzione e `condition` viene nuovamente verificata. Se `condition` è ancora `True`, il processo viene ripetuto. Se dispone di `False`, il controllo passa all'istruzione che segue il `End While` istruzione.  
  
 Il `While` sempre istruzione verifica la condizione prima di avviare il ciclo. Ciclo continua finché la condizione rimane `True`. Se `condition` è `False` quando si inizia il ciclo, non eseguire ancora una volta.  
  
 Il `condition` in genere i risultati di un confronto di due valori, ma possono essere qualsiasi espressione che restituisce un [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`). Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean`.  
  
 È possibile annidare `While` inserendo un ciclo all'interno di altra. È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di un altro. Per ulteriori informazioni, vedere [strutture di controllo nidificate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Uscita durante  
 Il [uscire mentre](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un altro modo per uscire da un `While` ciclo. `Exit While` Trasferisce immediatamente il controllo all'istruzione che segue il `End While` istruzione.  
  
 In genere si usa `Exit While` dopo la valutazione di alcune condizioni (ad esempio, in un `If...Then...Else` struttura). È possibile uscire da un ciclo se si rileva una condizione che rende Impossibile continuare la ripetizione, ad esempio una richiesta di terminazione o di un valore errato o non necessarie. È possibile utilizzare `Exit While` quando si testa una condizione che potrebbe causare un *ciclo infinito*, ovvero un ciclo che è stato possibile eseguire un numero estremamente elevato o persino infinito di volte. È quindi possibile utilizzare `Exit While` per interrompere il ciclo.  
  
 È possibile inserire un numero qualsiasi di `Exit While` istruzioni in un punto qualsiasi di `While` ciclo.  
  
 Se utilizzato all'interno di cicli `While` cicli, `Exit While` trasferisce il controllo all'esterno del ciclo più interno e del successivo livello superiore di annidamento.  
  
 Il `Continue While` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni nel ciclo di continuano l'esecuzione fino a quando il `index` variabile è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo del `Continue While` e `Exit While` istruzioni.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente legge tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nel `While` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se il file contiene caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
