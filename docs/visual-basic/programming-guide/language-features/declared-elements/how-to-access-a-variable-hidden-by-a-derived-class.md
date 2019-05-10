---
title: 'Procedura: Accedere a una variabile nascosta da una classe derivata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 43f7af1a1b540dd630cc2f228f1e5a6018d7c5d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610464"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Procedura: Accedere a una variabile nascosta da una classe derivata (Visual Basic)
Quando il codice in una classe derivata accede a una variabile, il compilatore risolve in genere il riferimento alla versione accessibile più vicino, vale a dire, la versione accessibile i minor numero di passaggi di derivazione con le versioni precedenti dalla classe. Se la variabile viene definita nella classe derivata, il codice accede in genere tale definizione.  
  
 Se la variabile di classe derivata nasconde una variabile nella classe di base, questa nasconderà la versione della classe base. Tuttavia, è possibile accedere alla variabile della classe base per qualificarlo con il `MyBase` (parola chiave).  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Per accedere a una variabile di classe di base nascosta da una classe derivata  
  
- In un'espressione o istruzione di assegnazione, far precedere il nome della variabile con il `MyBase` parola chiave e un periodo (`.`).  
  
     Il compilatore risolve il riferimento alla versione della classe base della variabile.  
  
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
 Per ridurre il rischio di fare riferimento a una versione imprevista di una variabile nascosta, è possibile qualificare completamente tutti i riferimenti a una variabile nascosta. Shadowing presenta più di una versione di una variabile con lo stesso nome. Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione di codice e la presenza di una stringa di qualificazione. Ciò può aumentare il rischio di fare riferimento alla versione errata della variabile.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Procedura: Nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: Nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
