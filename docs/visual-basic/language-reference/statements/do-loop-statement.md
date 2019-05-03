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
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638775"
---
# <a name="doloop-statement-visual-basic"></a>Istruzione Do...Loop (Visual Basic)
Ripete un blocco di istruzioni finché un' `Boolean` condizione `True` o fino a quando la condizione diventa `True`.  
  
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
|`Do`|Obbligatorio. Inizia la definizione del `Do` ciclo.|  
|`While`|Obbligatorio a meno che non sia usato `Until`. Ripetere il ciclo finché `condition` è `False`.|  
|`Until`|Obbligatorio a meno che non sia usato `While`. Ripetere il ciclo finché `condition` è `True`.|  
|`condition`|Facoltativo. `Boolean` espressione. Se `condition` viene `Nothing`, Visual Basic lo considera come `False`.|  
|`statements`|Facoltativo. Una o più istruzioni while o until, ripetute `condition` è `True`.|  
|`Continue Do`|Facoltativo. Trasferisce il controllo all'iterazione successiva del `Do` ciclo.|  
|`Exit Do`|Facoltativo. Trasferisce il controllo fuori il `Do` ciclo.|  
|`Loop`|Obbligatorio. Termina la definizione del `Do` ciclo.|  
  
## <a name="remarks"></a>Note  
 Usare un `Do...Loop` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte, fino a quando non viene soddisfatta una condizione. Se si desidera ripetere un determinato numero di volte, le istruzioni di [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.  
  
 È possibile usare `While` oppure `Until` per specificare `condition`, ma non entrambi.  
  
 È possibile testare `condition` solo una volta, all'inizio o fine del ciclo. Se si testano `condition` all'inizio del ciclo (nel `Do` istruzione), il ciclo potrebbe non funzionare ancora una volta. Se si verifica alla fine del ciclo (nel `Loop` istruzione), il ciclo viene sempre eseguito almeno una volta.  
  
 La condizione è dovuta in genere da un confronto tra due valori, ma può essere qualsiasi espressione che restituisce un [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`). Questo include i valori di altri tipi di dati, ad esempio tipi numerici, che sono stati convertiti in `Boolean`.  
  
 È possibile annidare `Do` cicli inserendo un ciclo all'interno di altra. È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro. Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Il `Do...Loop` struttura offre maggiore flessibilità di [mentre... L'istruzione end anche se](../../../visual-basic/language-reference/statements/while-end-while-statement.md) perché ti consente di decidere se terminare il ciclo quando `condition` diviene `True` o quando diventa `True`. Inoltre, consente di testare `condition` all'inizio o fine del ciclo.  
  
## <a name="exit-do"></a>Exit Do  
 Il [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un modo alternativo per chiudere un `Do…Loop`. `Exit Do` Trasferisce il controllo all'istruzione che segue immediatamente il `Loop` istruzione.  
  
 `Exit Do` viene spesso usato dopo che viene valutata una condizione, ad esempio in un `If...Then...Else` struttura. È possibile uscire da un ciclo se si rileva una condizione che rende inutili o impossibili da continuare a eseguire iterazioni, ad esempio un valore errato o una richiesta di terminazione. Un uso del `Exit Do` consiste nel testare una condizione che potrebbe causare un' *ciclo infinito*, che è un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. È possibile usare `Exit Do` per interrompere il ciclo.  
  
 È possibile includere un numero qualsiasi di `Exit Do` istruzioni in un punto qualsiasi in un `Do…Loop`.  
  
 Quando usata all'interno di cicli `Do` cicli, `Exit Do` trasferisce il controllo all'esterno del ciclo più interno e nel livello superiore successivo di annidamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, le istruzioni nel ciclo continuano fino a incontrare il `index` variabile è maggiore di 10. Il `Until` clausola si trova alla fine del ciclo.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' `While` clausola WITH invece di un' `Until` clausola e `condition` viene verificata all'inizio del ciclo anziché alla fine.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito `condition` Arresta il ciclo quando il `index` variabile è maggiore di 100. Il `If` istruzione del ciclo, tuttavia, provoca la `Exit Do` istruzione per interrompere il ciclo quando la variabile di indice è maggiore di 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente legge tutte le righe in un file di testo. Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri. Nel `Do...Loop` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se sono presenti eventuali caratteri aggiuntivi.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
