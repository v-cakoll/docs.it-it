---
title: 'Procedura: Nascondere una variabile con lo stesso nome di variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: a770167bca0dc3538c828bfcc8a8de4ef86e80c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602416"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Procedura: Nascondere una variabile con lo stesso nome di variabile (Visual Basic)
È possibile nascondere una variabile dal *shadowing* , vale a dire che ridefinirla con una variabile avente lo stesso nome. È possibile nascondere la variabile che si desidera nascondere in due modi:  
  
-   **Shadowing tramite l'ambito.** È possibile nascondere mediante l'ambito da dichiararla all'interno di un'area secondaria dell'area che contiene la variabile che si desidera nascondere.  
  
-   **Shadowing tramite eredità.** Se la variabile a cui si vuole nascondere è definita a livello di classe, è possibile nascondere lo attraverso l'ereditarietà da sovrascriverle con le [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) parola chiave in una classe derivata.  
  
## <a name="two-ways-to-hide-a-variable"></a>Due modi per nascondere una variabile  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Per nascondere una variabile per lo shadowing tramite l'ambito  
  
1.  Determinare l'area di definizione della variabile che si desidera nascondere e definire un'area secondaria in cui si desidera ridefinirla con la variabile.  
  
    |Area della variabile|Area secondaria consentita per la ridefinizione|  
    |-----------------------|-------------------------------------------|  
    |Modulo|Una classe all'interno del modulo|  
    |Classe|Sottoclasse all'interno della classe<br /><br /> Una procedura all'interno della classe|  
  
     Non è possibile ridefinire una variabile della procedura in un blocco all'interno di tale routine, ad esempio un `If`... `End If` costruzione o una `For` ciclo.  
  
2.  Se non esiste già, creare l'area secondaria.  
  
3.  In aree secondarie, scrivere un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiara la variabile ombreggiatura.  
  
     Quando il codice all'interno l'area secondaria fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile ombreggiatura.  
  
     L'esempio seguente illustra lo shadowing mediante ambito, nonché un riferimento che consente di ignorare lo shadowing.  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     Nell'esempio precedente viene dichiarata la variabile `num` a livello di modulo sia a livello di routine (nella procedura `show`). La variabile locale `num` nasconde la variabile a livello di modulo `num` all'interno di `show`, in modo che la variabile locale è impostata su 2. Tuttavia, è presente alcuna variabile locale per shadow `num` nella `useModuleLevelNum` procedure. Pertanto, `useModuleLevelNum` imposta il valore della variabile a livello di modulo su 1.  
  
     Il `MsgBox` chiamare all'interno `show` ignora il meccanismo di shadowing specificando `num` con il nome del modulo. Di conseguenza, Visualizza la variabile a livello di modulo invece la variabile locale.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Per nascondere una variabile per lo shadowing tramite eredità  
  
1.  Assicurarsi che la variabile di cui che si vuole nascondere è dichiarata in una classe e a livello di classe (all'esterno di qualsiasi routine). In caso contrario, è possibile eseguire lo shadowing tramite l'ereditarietà.  
  
2.  Definire una classe derivata dalla classe della variabile se non ne esiste già.  
  
3.  All'interno della classe derivata, scrivere un `Dim` istruzione di dichiarazione di variabile. Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.  
  
     Quando il codice della classe derivata si riferisce al nome della variabile, il compilatore risolve il riferimento alla variabile.  
  
     Nell'esempio seguente viene illustrato come shadowing tramite eredità. Rende i due riferimenti, uno che accede alla variabile di shadowing e uno che consente di ignorare lo shadowing.  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe di base e lo nasconde nella classe derivata. La procedura `showStrings` nella classe derivata, Visualizza la versione di shadowing della stringa quando il nome `shadowString` non sono qualificati. Quindi Visualizza la versione nascosta quando `shadowString` completo con il `MyBase` (parola chiave).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Shadowing presenta più di una versione di una variabile con lo stesso nome. Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione di codice e la presenza di una stringa di qualificazione. Ciò può aumentare il rischio di fare riferimento a una versione imprevista di una variabile nascosta. È possibile ridurre tale rischio in modo completo tutti i riferimenti a una variabile nascosta.  
  
## <a name="see-also"></a>Vedere anche
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Procedura: Nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Procedura: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
