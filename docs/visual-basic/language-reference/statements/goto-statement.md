---
title: Istruzione GoTo
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
ms.openlocfilehash: eb6f48d04b7d14591003e340464451da7df45cd6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404615"
---
# <a name="goto-statement"></a>Istruzione GoTo
Viene diramato in modo incondizionato a una riga specificata in una procedura.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Obbligatorio. Qualsiasi etichetta di riga.  
  
## <a name="remarks"></a>Commenti  
 L' `GoTo` istruzione può creare un ramo solo per le righe della routine in cui viene visualizzata. La riga deve avere un'etichetta di linea `GoTo` a cui può fare riferimento. Per altre informazioni, vedere [How to: Label statements](../../programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo`le istruzioni possono rendere difficile la lettura e la gestione del codice. Quando possibile, usare invece una struttura di controllo. Per altre informazioni, vedere [Flusso di controllo](../../programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile usare un' `GoTo` istruzione per creare un ramo dall'esterno di `For` ... `Next` , `For Each` ... `Next` ,. `SyncLock` .. `End SyncLock` , `Try` .. `Catch` . ... `Finally` , `With` ... `End With` o `Using` ... `End Using` costruzione in un'etichetta all'interno di.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e tentativi di costruzione  
 All'interno di `Try` .. `Catch` . ...`Finally` costruzione, le regole seguenti si applicano alla diramazione con l' `GoTo` istruzione.  
  
|Blocco o area|Diramazione in dall'esterno|Diramazione dall'interno|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`blocco|Solo da un `Catch` blocco della stessa costruzione <sup>1</sup>|Solo all'esterno dell'intera costruzione|  
|`Catch`blocco|Mai consentito|Solo all'esterno dell'intera costruzione o al `Try` blocco della stessa costruzione <sup>1</sup>|  
|`Finally`blocco|Mai consentito|Mai consentito|  
  
 <sup>1</sup> se uno `Try` ... `Catch` ...`Finally` la costruzione è annidata all'interno di un'altra, un `Catch` blocco può creare rami nel `Try` blocco al proprio livello di annidamento, ma non in un altro `Try` blocco. Oggetto annidato `Try` ... `Catch` ...`Finally` la costruzione deve essere completamente inclusa in `Try` un `Catch` blocco o della costruzione all'interno della quale è annidata.  
  
 Nella figura seguente viene illustrata una `Try` costruzione annidata all'interno di un'altra. Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `GoTo` istruzione per creare un ramo delle etichette di riga in una procedura.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](do-loop-statement.md)
- [Istruzione For...Next](for-next-statement.md)
- [Istruzione For Each...Next](for-each-next-statement.md)
- [Istruzione If...Then...Else](if-then-else-statement.md)
- [Istruzione Select...Case](select-case-statement.md)
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
- [Istruzione While...End While](while-end-while-statement.md)
- [Istruzione With...End With](with-end-with-statement.md)
