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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351079"
---
# <a name="goto-statement"></a>Istruzione GoTo
Viene diramato in modo incondizionato a una riga specificata in una procedura.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Obbligatoria. Qualsiasi etichetta di riga.  
  
## <a name="remarks"></a>Note  
 L'istruzione `GoTo` può creare branch solo per le righe della procedura in cui viene visualizzata. La riga deve avere un'etichetta di linea a cui `GoTo` può fare riferimento. Per altre informazioni, vedere [How to: Label statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> le istruzioni `GoTo` possono rendere difficile la lettura e la gestione del codice. Quando possibile, usare invece una struttura di controllo. Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile usare un'istruzione `GoTo` per creare un ramo dall'esterno di un `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`o `Using`...`End Using` costruzione in un'etichetta all'interno di.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e tentativi di costruzione  
 All'interno di una `Try`...`Catch`...`Finally` costruzione, le regole seguenti si applicano alla diramazione con l'istruzione `GoTo`.  
  
|Blocco o area|Diramazione in dall'esterno|Diramazione dall'interno|  
|---------------------|-------------------------------|-------------------------------|  
|blocco `Try`|Solo da un blocco `Catch` della stessa costruzione <sup>1</sup>|Solo all'esterno dell'intera costruzione|  
|blocco `Catch`|Mai consentito|Solo all'esterno dell'intera costruzione o al blocco `Try` della stessa costruzione <sup>1</sup>|  
|blocco `Finally`|Mai consentito|Mai consentito|  
  
 <sup>1</sup> se una `Try`...`Catch`...`Finally` costruzione è annidata all'interno di un'altra, un blocco `Catch` può creare un ramo nel blocco `Try` al proprio livello di annidamento, ma non in un altro blocco di `Try`. Una costruzione annidata `Try`...`Catch`...`Finally` deve essere completamente inclusa in un blocco `Try` o `Catch` della costruzione all'interno della quale è annidato.  
  
 Nella figura seguente viene illustrato un `Try` costruzione annidata all'interno di un altro. Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `GoTo` per creare rami di etichette di riga in una procedura.  
  
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
