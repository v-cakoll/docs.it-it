---
title: Strutture di controllo annidate
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348144"
---
# <a name="nested-control-structures-visual-basic"></a>Strutture di controllo annidate (Visual Basic)
È possibile inserire istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un blocco `If...Then...Else` all'interno di un ciclo di `For...Next`. Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo è detta *annidata*.  
  
## <a name="nesting-levels"></a>Livelli di annidamento  
 Le strutture di controllo in Visual Basic possono essere nidificate a tutti i livelli desiderati. Per rendere più leggibili le strutture annidate, è consigliabile rientrare nel corpo di ognuna di esse. Questa operazione viene eseguita automaticamente dall'editor Integrated Development Environment (IDE).  
  
 Nell'esempio seguente la procedura `sumRows` somma gli elementi positivi di ogni riga della matrice.  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 Nell'esempio precedente, la prima istruzione `Next` chiude il ciclo di `For` interno e l'ultima istruzione `Next` chiude il ciclo di `For` esterno.  
  
 Analogamente, nelle istruzioni `If` annidate, le istruzioni `End If` si applicano automaticamente all'istruzione `If` precedente più vicina. I cicli di `Do` annidati funzionano in modo simile, con l'istruzione `Loop` più interna che corrisponde all'istruzione `Do` più interna.  
  
> [!NOTE]
> Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando si fa clic su `If` in una costruzione `If...Then...Else`, vengono evidenziate tutte le istanze di `If`, `Then`, `ElseIf`, `Else`e `End If` nella costruzione. Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Annidamento di tipi diversi di strutture di controllo  
 È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo. Nell'esempio seguente viene utilizzato un blocco `With` all'interno di un ciclo di `For Each` e blocchi `If` annidati all'interno del blocco `With`.  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>Strutture di controllo sovrapposte  
 Non è possibile sovrapporre strutture di controllo. Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta nella successiva struttura più interna. La disposizione seguente, ad esempio, non è valida perché il ciclo di `For` termina prima del termine del blocco di `With` interno.  
  
 ![Diagramma che mostra un esempio di annidamento non valido.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Il compilatore Visual Basic rileva tali strutture di controllo sovrapposte e segnala un errore in fase di compilazione.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
