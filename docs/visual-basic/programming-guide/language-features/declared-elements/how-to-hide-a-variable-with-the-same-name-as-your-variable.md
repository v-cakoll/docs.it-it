---
title: "Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)"
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
ms.openlocfilehash: a7ebc4eb44592800decd5ef943750f0cd845afb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)
È possibile nascondere una variabile da *shadowing* , vale a dire ridefinirla con una variabile con lo stesso nome. È possibile nascondere la variabile che si desidera nascondere in due modi:  
  
-   **Shadowing tramite l'ambito.** È possibile nascondere mediante l'ambito da dichiararla all'interno di un'area secondaria dell'area che contiene la variabile che si desidera nascondere.  
  
-   **Shadowing tramite eredità.** Se la variabile che si desidera nascondere è definita a livello di classe, è possibile nascondere, tramite l'ereditarietà da dichiararla nuovamente con la [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) parola chiave in una classe derivata.  
  
## <a name="two-ways-to-hide-a-variable"></a>Due modi per nascondere una variabile  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Per nascondere una variabile eseguendone lo shadowing mediante ambito  
  
1.  Determinare l'area di definizione della variabile a cui che si desidera nascondere e definire un'area secondaria in cui si desidera ridefinirla con la variabile.  
  
    |Area della variabile|Area secondaria consentita per la ridefinizione|  
    |-----------------------|-------------------------------------------|  
    |Modulo|Una classe all'interno del modulo|  
    |Classe|Una sottoclasse della classe<br /><br /> Una routine all'interno della classe|  
  
     Non è possibile ridefinire una variabile di routine in un blocco in questa procedura, ad esempio un `If`... `End If` costruzione o `For` ciclo.  
  
2.  Se non esiste già, creare l'area secondaria.  
  
3.  All'interno della sottoarea scrivere un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiara la variabile ombreggiatura.  
  
     Quando il codice all'interno di aree secondarie fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile di shadowing.  
  
     Nell'esempio seguente viene illustrato lo shadowing mediante ambito, nonché un riferimento che consente di ignorare lo shadowing.  
  
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
  
     Nell'esempio precedente viene dichiarata la variabile `num` a livello di modulo sia a livello di routine (nella procedura `show`). La variabile locale `num` nasconde la variabile a livello di modulo `num` all'interno di `show`, in modo che la variabile locale è impostata su 2. Tuttavia, è presente alcuna variabile locale a ombreggiatura `num` nel `useModuleLevelNum` stored procedure. Pertanto, `useModuleLevelNum` imposta il valore della variabile a livello di modulo su 1.  
  
     Il `MsgBox` chiamare all'interno di `show` ignora il meccanismo di shadowing specificando `num` con il nome del modulo. Di conseguenza, Visualizza la variabile a livello di modulo anziché la variabile locale.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Per nascondere una variabile eseguendone lo shadowing tramite eredità  
  
1.  Assicurarsi che la variabile che si desidera nascondere è dichiarata in una classe e a livello di classe (all'esterno di qualsiasi routine). In caso contrario è possibile eseguire lo shadowing tramite l'ereditarietà.  
  
2.  Definire una classe derivata dalla classe della variabile, se non ne esiste già.  
  
3.  All'interno della classe derivata, scrivere un `Dim` istruzione di dichiarazione della variabile. Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.  
  
     Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.  
  
     Nell'esempio seguente viene illustrato lo shadowing tramite eredità. Rende i due riferimenti, uno che accede alla variabile shadowing e uno che consente di ignorare lo shadowing.  
  
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
  
     Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe base e lo nasconde nella classe derivata. La procedura `showStrings` nella classe derivata, Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato. Verrà quindi visualizzata la versione nascosta quando `shadowString` completo con il `MyBase` (parola chiave).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione del codice e la presenza di una stringa di qualifica. Ciò può aumentare il rischio di fare riferimento a una versione di una variabile nascosta non intenzionale. È possibile ridurre tale rischio in modo completo tutti i riferimenti a una variabile nascosta.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
