---
title: 'Procedura: Nascondere una variabile ereditata (Visual Basic)'
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
ms.openlocfilehash: ee147ecd00b88b538ace32844c42ac9c5022b2ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794693"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedura: Nascondere una variabile ereditata (Visual Basic)
Una classe derivata eredita tutte le definizioni della relativa classe base. Se si desidera definire una variabile utilizzando lo stesso nome di un elemento della classe di base, è possibile nascondere, oppure *shadow*, tale elemento di classe di base quando si definisce la variabile nella classe derivata. In questo caso, il codice nella classe derivata accede la variabile a meno che non venga esplicitamente ignorato il meccanismo di shadowing.  
  
 Un altro motivo, che è possibile nascondere una variabile ereditata consiste nella protezione rispetto alla revisione di classe di base. La classe di base potrebbe subire una modifica che consente di modificare l'elemento che si eredita. In questo caso, il `Shadows` modificatore forza riferimenti dalla classe derivata da risolvere alla variabile, anziché per l'elemento della classe base.  
  
### <a name="to-hide-an-inherited-variable"></a>Per nascondere una variabile ereditata  
  
1. Assicurarsi che la variabile di cui che si vuole nascondere è dichiarata a livello di classe (all'esterno di qualsiasi routine). In caso contrario, non è necessaria per nasconderlo.  
  
2. All'interno della classe derivata, scrivere un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiarazione di variabile. Usare lo stesso nome della variabile ereditata.  
  
3. Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.  
  
     Quando il codice della classe derivata si riferisce al nome della variabile, il compilatore risolve il riferimento alla variabile.  
  
     Nell'esempio seguente viene illustrato come shadowing di una variabile ereditata.  
  
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
- [Procedura: Nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
