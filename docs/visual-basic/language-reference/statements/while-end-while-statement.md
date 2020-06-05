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
ms.openlocfilehash: d9eb8cb95d46e860aa127954d7b44e37991d4a13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391586"
---
# <a name="whileend-while-statement-visual-basic"></a>Istruzione While...End While (Visual Basic)
Esegue una serie di istruzioni purché una determinata condizione sia `True` .  
  
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
|`condition`|Obbligatorio. Espressione `Boolean`. Se `condition` è `Nothing` , Visual Basic lo considera come `False` .|  
|`statements`|Facoltativa. Una o più istruzioni `While` che seguono, che vengono eseguite ogni volta `condition` è `True` .|  
|`Continue While`|Facoltativa. Trasferisce il controllo all'iterazione successiva del `While` blocco.|  
|`Exit While`|Facoltativa. Trasferisce il controllo all'esterno del `While` blocco.|  
|`End While`|Obbligatorio. Termina la definizione del blocco `While`.|  
  
## <a name="remarks"></a>Commenti  
 Utilizzare una `While...End While` struttura quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, purché rimanga una condizione `True` . Se si desidera maggiore flessibilità con la posizione in cui si testa la condizione o il risultato per il test, è preferibile [eseguire... Istruzione Loop](do-loop-statement.md). Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](for-next-statement.md) è in genere una scelta migliore.  
  
> [!NOTE]
> La `While` parola chiave viene usata anche nel. [.. Istruzione Loop](do-loop-statement.md), [clausola Skip While](../queries/skip-while-clause.md) e [clausola Take While](../queries/take-while-clause.md).  
  
 Se `condition` è `True` , tutto l' `statements` esecuzione fino a quando non `End While` viene rilevata l'istruzione. Il controllo viene quindi restituito all' `While` istruzione e `condition` viene di nuovo controllata. Se `condition` è ancora `True` , il processo viene ripetuto. Se è `False` , il controllo passa all'istruzione che segue l' `End While` istruzione.  
  
 L' `While` istruzione controlla sempre la condizione prima di avviare il ciclo. Il ciclo continua finché la condizione rimane `True` . Se `condition` è `False` la prima volta che si immette il ciclo, non viene eseguito neanche una volta.  
  
 Il `condition` risultato è in genere dovuto a un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore di [tipo di dati booleano](../data-types/boolean-data-type.md) ( `True` o `False` ). Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean` .  
  
 È possibile annidare i `While` cicli inserendo un ciclo all'interno di un altro. È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Esci da  
 L'istruzione [Exit While](exit-statement.md) può fornire un altro modo per uscire da un `While` ciclo. `Exit While`trasferisce immediatamente il controllo all'istruzione che segue l' `End While` istruzione.  
  
 In genere si usa `Exit While` dopo la valutazione di una determinata condizione, ad esempio in una `If...Then...Else` struttura. Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione. È possibile usare `Exit While` quando si esegue il test di una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte molto grande o addirittura infinito. È quindi possibile usare `Exit While` per eseguire l'escape del ciclo.  
  
 È possibile inserire un numero qualsiasi di `Exit While` istruzioni in qualsiasi punto del `While` ciclo.  
  
 Quando viene utilizzato all'interno `While` di cicli annidati, `Exit While` trasferisce il controllo al di fuori del ciclo più interno e al successivo livello di nidificazione.  
  
 L' `Continue While` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](continue-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando la `index` variabile non è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo delle `Continue While` istruzioni e `Exit While` .  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono lette tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un oggetto <xref:System.IO.StreamReader> che legge i caratteri. Nella `While` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo di `StreamReader` determina se il file contiene caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione Do...Loop](do-loop-statement.md)
- [Istruzione For...Next](for-next-statement.md)
- [Tipo di dati Boolean](../data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](exit-statement.md)
- [Istruzione continue](continue-statement.md)
