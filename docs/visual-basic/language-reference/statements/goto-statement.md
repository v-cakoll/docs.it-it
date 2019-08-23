---
title: Istruzione GoTo (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912455"
---
# <a name="goto-statement"></a>Istruzione GoTo
Viene diramato in modo incondizionato a una riga specificata in una procedura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Richiesto. Qualsiasi etichetta di riga.  
  
## <a name="remarks"></a>Note  
 L' `GoTo` istruzione può creare un ramo solo per le righe della routine in cui viene visualizzata. La riga deve avere un'etichetta di linea `GoTo` a cui può fare riferimento. Per altre informazioni, vedere [Procedura: Istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)Label.  
  
> [!NOTE]
> `GoTo`le istruzioni possono rendere difficile la lettura e la gestione del codice. Quando possibile, usare invece una struttura di controllo. Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile usare `GoTo` un'istruzione per creare un ramo `For`dall'esterno di... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With` o`Using`... `End Using` costruzione in un'etichetta all'interno di.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e tentativi di costruzione  
 All'interno `Try`di... `Catch`... costruzione, le regole seguenti si applicano alla diramazione con l' `GoTo` istruzione. `Finally`  
  
|Blocco o area|Diramazione in dall'esterno|Diramazione dall'interno|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`blocco|Solo da un `Catch` blocco della stessa costruzione <sup>1</sup>|Solo all'esterno dell'intera costruzione|  
|`Catch`blocco|Mai consentito|Solo all'esterno dell'intera costruzione o al `Try` blocco della stessa costruzione <sup>1</sup>|  
|`Finally`blocco|Mai consentito|Mai consentito|  
  
 <sup>1</sup> se uno `Try`... `Catch`... la costruzione è annidata all'interno `Catch` di un'altra, un `Try` blocco può creare rami nel blocco al proprio livello di annidamento, `Try` ma non in un altro blocco. `Finally` Oggetto annidato `Try`... `Catch`... la costruzione deve essere completamente inclusa in `Try` un `Catch` blocco o della costruzione all'interno della quale è annidata. `Finally`  
  
 Nella figura seguente viene illustrata una `Try` costruzione annidata all'interno di un'altra. Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `GoTo` l'istruzione per creare un ramo delle etichette di riga in una procedura.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
