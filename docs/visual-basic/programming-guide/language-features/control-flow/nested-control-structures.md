---
title: Strutture di controllo annidate (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f2c91bcdd741ef75417fe50b0c08bd0f9bd5ff80
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="nested-control-structures-visual-basic"></a>Strutture di controllo annidate (Visual Basic)
È possibile inserire le istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocco all'interno di un `For...Next` ciclo. Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo è detta *nidificata*.  
  
## <a name="nesting-levels"></a>Livelli di annidamento  
 Strutture di controllo in Visual Basic possono essere nidificate fino a un numero di livelli. È pratica comune per rendere più leggibile strutture annidate rientrare il corpo di ciascuna di esse. L'editor di sviluppo integrato (IDE) di ambiente automaticamente esegue questa operazione.  
  
 Nell'esempio seguente, la procedura `sumRows` per sommare positivo gli elementi di ogni riga della matrice.  
  
```  
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
  
 Nell'esempio precedente, il primo `Next` istruzione chiude il `For` ciclo e l'ultimo `Next` istruzione chiude esterna `For` ciclo.  
  
 Analogamente, in annidati `If` istruzioni, il `End If` istruzioni vengono applicate automaticamente al precedente più vicino `If` istruzione. Annidati `Do` cicli di lavoro in modo simile, con più interna `Loop` corrispondente alla più interna `Do` istruzione.  
  
> [!NOTE]
>  Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati. Per spostarsi alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Annidamento di tipi diversi di strutture di controllo  
 È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo. Nell'esempio seguente viene utilizzato un `With` blocco un `For Each` ciclo e nidificate `If` blocchi all'interno di `With` blocco.  
  
```  
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
  
## <a name="overlapping-control-structures"></a>Sovrapposizione di strutture di controllo  
 Non è possibile sovrapporre le strutture di controllo. Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta all'interno della successiva struttura più interna. Ad esempio, la disposizione seguente non è valida perché il `For` ciclo termina prima del `With` termina.  
  
 ![Diagramma grafico di annidamento non valida](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
Annidamento non valido di per e con strutture  
  
 Il compilatore Visual Basic rileva le strutture di controllo sovrapposte e segnala un errore in fase di compilazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
