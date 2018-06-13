---
title: 'Procedura: nascondere una variabile ereditata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: c59fdd8c6c6d2444b8d687c78c61f4e0d4bf9a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649139"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedura: nascondere una variabile ereditata (Visual Basic)
Una classe derivata eredita tutte le definizioni della relativa classe base. Se si desidera definire una variabile utilizzando lo stesso nome di un elemento della classe di base, è possibile nascondere o *shadow*, tale elemento quando si definisce la variabile nella classe derivata della classe base. In questo caso, il codice nella classe derivata accede alla variabile a meno che non venga esplicitamente ignorato il meccanismo di shadowing.  
  
 Un altro motivo, che è possibile nascondere una variabile ereditata è evitare revisione della classe base. La classe di base può essere sottoposto a una modifica che consente di modificare l'elemento che sta ereditando. In questo caso, il `Shadows` modificatore impone riferimenti dalla classe derivata vengano risolti alla variabile, anziché l'elemento della classe base.  
  
### <a name="to-hide-an-inherited-variable"></a>Per nascondere una variabile ereditata  
  
1.  Assicurarsi che la variabile che si desidera nascondere è dichiarata a livello di classe (all'esterno di qualsiasi routine). In caso contrario non è necessario per nasconderlo.  
  
2.  All'interno della classe derivata, scrivere un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiarare la variabile. Utilizzare lo stesso nome della variabile ereditata.  
  
3.  Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.  
  
     Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.  
  
     Nell'esempio seguente viene illustrato lo shadowing di una variabile ereditata.  
  
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
 [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
