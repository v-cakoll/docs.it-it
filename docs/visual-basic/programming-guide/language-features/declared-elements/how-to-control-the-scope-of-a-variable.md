---
title: "Procedura: Controllare l'ambito di una variabile (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324318"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Procedura: Controllare l'ambito di una variabile (Visual Basic)
In genere, una variabile si trova nel *ambito*, o visibile per riferimento, l'area in cui è stato dichiarato. In dell'alcuni casi, la variabile *livello di accesso* possono influenzare il relativo ambito.  
  
 Per altre informazioni, vedere [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Ambito a livello di routine o di blocco  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Per rendere visibili solo all'interno di un blocco di una variabile  
  
-   Sul posto il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile tra l'avvio e terminazione istruzioni di dichiarazione di tale blocco, ad esempio tra il `For` e `Next` istruzioni di un `For` ciclo.  
  
     È possibile fare riferimento alla variabile solo dall'interno del blocco.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Per rendere visibili solo all'interno di una routine di una variabile  
  
-   Sul posto di `Dim` istruzione per la variabile all'interno della routine, ma all'esterno di qualsiasi blocco (ad esempio un `With`... `End With` blocco).  
  
     È possibile fare riferimento alla variabile solo dall'interno della routine, inclusi gli eventuali blocchi contenute nella procedura.  
  
## <a name="scope-at-module-or-namespace-level"></a>Ambito livello di modulo o Namespace  
 Per praticità, il termine singolo *a livello di modulo* si applica equamente a moduli, le classi e strutture. Il livello di accesso di una variabile a livello di modulo determina il relativo ambito. Lo spazio dei nomi che contiene il modulo, classe o struttura influisce anche sull'ambito.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Per rendere visibile in un modulo, classe o struttura di una variabile  
  
1. Posizione di `Dim` istruzione per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere il [privati](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.  
  
3. È possibile fare riferimento alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non da al suo esterno.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Per rendere visibile in uno spazio dei nomi una variabile  
  
1. Posizione di `Dim` istruzione per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [pubblici](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.  
  
3. È possibile fare riferimento alla variabile da qualsiasi posizione all'interno dello spazio dei nomi che contiene il modulo, classe o struttura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarata una variabile a livello di modulo e consente di limitare la visibilità al codice all'interno del modulo.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 Nell'esempio precedente, tutte le procedure definite nel modulo `demonstrateScope` può fare riferimento al `String` variabile `strMsg`. Quando la `usePrivateVariable` routine viene chiamata, viene visualizzato il contenuto della variabile di stringa `strMsg` in una finestra di dialogo.  
  
 Con la modifica seguente all'esempio precedente, la variabile stringa `strMsg` può essere indicato dal codice in qualsiasi punto nello spazio dei nomi della relativa dichiarazione.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Più ristretto ambito di una variabile, i meno le possibilità di fare riferimento a esso accidentalmente al posto di un'altra variabile con lo stesso nome. È anche possibile ridurre al minimo i problemi di riferimento corrispondenti.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Più ristretto ambito di una variabile, utilizzare minori saranno le probabilità che codice dannoso può rendere non corretta di esso.  
  
## <a name="see-also"></a>Vedere anche

- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
