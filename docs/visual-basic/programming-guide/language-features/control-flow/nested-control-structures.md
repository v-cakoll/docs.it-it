---
title: Strutture di controllo annidate (Visual Basic)
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
ms.openlocfilehash: 13e2c5c8d818a09ec5e77ec47fe8a2c83b675d82
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409796"
---
# <a name="nested-control-structures-visual-basic"></a>Strutture di controllo annidate (Visual Basic)
È possibile inserire le istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocchi all'interno di un `For...Next` ciclo. Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo viene detto *nidificata*.  
  
## <a name="nesting-levels"></a>Livelli di annidamento  
 Strutture di controllo in Visual Basic possono essere annidate a tutti i livelli desiderato. È pratica comune per rendere più leggibile strutture annidate rientrando il corpo della ognuno di essi. L'editor di sviluppo integrato (IDE) di ambiente automaticamente esegue questa operazione.  
  
 Nell'esempio seguente, la procedura `sumRows` somma tra gli elementi positivi di ogni riga della matrice.  
  
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
  
 Nell'esempio precedente, il primo `Next` istruzione chiude interna `For` ciclo e l'ultima `Next` istruzione chiude esterna `For` ciclo.  
  
 Allo stesso modo, in annidati `If` (istruzioni), il `End If` istruzioni si applicano automaticamente per il più vicino prima `If` istruzione. Annidato `Do` cicli funzionano in modo analogo, con più interna `Loop` istruzione corrispondente più interna `Do` istruzione.  
  
> [!NOTE]
>  Per molte strutture di controllo, quando si fa clic su una parola chiave, sono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione di strutture vengono evidenziati. Per spostare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Nidificazione di diversi tipi di strutture di controllo  
 È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo. L'esempio seguente usa una `With` blocchi all'interno di un `For Each` ciclo e nidificate `If` blocca all'interno del `With` blocco.  
  
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
  
## <a name="overlapping-control-structures"></a>La sovrapposizione di strutture di controllo  
 Non è possibile sovrapporre le strutture di controllo. Ciò significa che qualsiasi struttura annidata debba essere completamente contenuta all'interno della successiva struttura più interna. Ad esempio, la disposizione seguente non è valida perché il `For` ciclo termina prima del `With` blocco termina.  
  
 ![Diagramma che mostra un esempio di annidamento non valida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Il compilatore Visual Basic rileva le strutture di controllo sovrapposte e segnala un errore in fase di compilazione.  
  
## <a name="see-also"></a>Vedere anche
- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
