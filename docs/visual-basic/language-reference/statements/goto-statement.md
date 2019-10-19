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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581822"
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
  
## <a name="remarks"></a>Note  
 L'istruzione `GoTo` può creare branch solo per le righe della procedura in cui viene visualizzata. La riga deve avere un'etichetta di linea a cui `GoTo` può fare riferimento. Per altre informazioni, vedere [How to: Label statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> le istruzioni `GoTo` possono rendere difficile la lettura e la gestione del codice. Quando possibile, usare invece una struttura di controllo. Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile usare un'istruzione `GoTo` per creare un ramo dall'esterno di un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 o 2... 3 costruzione in un'etichetta all'interno di.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e tentativi di costruzione  
 All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano alla diramazione con l'istruzione `GoTo`.  
  
|Blocco o area|Diramazione in dall'esterno|Diramazione dall'interno|  
|---------------------|-------------------------------|-------------------------------|  
|blocco `Try`|Solo da un blocco `Catch` della stessa costruzione <sup>1</sup>|Solo all'esterno dell'intera costruzione|  
|blocco `Catch`|Mai consentito|Solo all'esterno dell'intera costruzione o al blocco `Try` della stessa costruzione <sup>1</sup>|  
|blocco `Finally`|Mai consentito|Mai consentito|  
  
 <sup>1</sup> se una `Try`... `Catch`... `Finally` costruzione è annidata all'interno di un'altra, un blocco di `Catch` può creare rami nel blocco `Try` a livello di annidamento, ma non in altri blocchi `Try`. @No__t_0 annidato... `Catch`... la costruzione di `Finally` deve essere completamente inclusa in un blocco `Try` o `Catch` della costruzione all'interno della quale è annidata.  
  
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
