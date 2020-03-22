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
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266924"
---
# <a name="nested-control-structures-visual-basic"></a>Strutture di controllo annidate (Visual Basic)
È possibile inserire istruzioni di controllo all'interno `If...Then...Else` di `For...Next` altre istruzioni di controllo, ad esempio un blocco all'interno di un ciclo. Un'istruzione di controllo inserita all'interno di un'altra istruzione di controllo viene detta *annidata.*  
  
## <a name="nesting-levels"></a>Livelli di nidificazione  
 Le strutture di controllo in Visual Basic possono essere annidate a tutti i livelli desiderati. È pratica comune rendere le strutture annidate più leggibili applicando un rientro al corpo di ognuna di esse. L'editor dell'ambiente di sviluppo integrato (IDE) esegue automaticamente questa operazione.  
  
 Nell'esempio seguente la `sumRows` routine somma gli elementi positivi di ogni riga della matrice.  
  
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
  
 Nell'esempio precedente, la `Next` prima istruzione `For` chiude il `Next` ciclo interno e `For` l'ultima istruzione chiude il ciclo esterno.  
  
 Analogamente, `If` nelle istruzioni `End If` annidate, le istruzioni `If` si applicano automaticamente all'istruzione precedente più vicina. I `Do` cicli annidati funzionano in modo `Loop` simile, con `Do` l'istruzione più interna corrispondente all'istruzione più interna.  
  
> [!NOTE]
> Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando `If` si `If...Then...Else` fa clic `If`in `Then` `ElseIf`una `Else`costruzione, tutte le istanze di , , , e `End If` nella costruzione vengono evidenziate. Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL-MAIUSC-FRECCIA GIU' o CTRL-MAIUSC-FRECCIA SU.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Nidificazione di diversi tipi di strutture di controllo  
 È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo. L'esempio seguente `With` usa `For Each` un blocco `If` all'interno di un ciclo e blocchi annidati all'interno del `With` blocco.  
  
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
 Non è possibile sovrapporre strutture di controllo. Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta all'interno della struttura più interna successiva. Ad esempio, la disposizione `For` seguente non è `With` valida perché il ciclo termina prima che il blocco interno termini.  
  
 ![Diagramma che mostra un esempio di annidamento non valido.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Il compilatore Visual Basic rileva tali strutture di controllo sovrapposte e segnala un errore in fase di compilazione.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
