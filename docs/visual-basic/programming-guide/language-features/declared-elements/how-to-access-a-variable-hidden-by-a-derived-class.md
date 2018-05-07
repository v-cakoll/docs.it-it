---
title: 'Procedura: accedere a una variabile nascosta da una classe derivata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Procedura: accedere a una variabile nascosta da una classe derivata (Visual Basic)
Quando il codice in una classe derivata accede a una variabile, il compilatore risolve in genere il riferimento alla versione accessibile più vicino, vale a dire la versione accessibile i minor numero di passaggi di derivazione con le versioni precedenti dalla classe. Se la variabile è definita nella classe derivata, il codice accede normalmente tale definizione.  
  
 Se la variabile di classe derivata nasconde una variabile nella classe base, in quanto viene nascosta la versione della classe base. Tuttavia, è possibile accedere alla variabile della classe base qualificandola con il `MyBase` (parola chiave).  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Per accedere a una variabile di classe base nascosta da una classe derivata  
  
-   In un'espressione o istruzione di assegnazione, far precedere il nome della variabile con il `MyBase` (parola chiave) e un periodo (`.`).  
  
     Il compilatore risolve il riferimento alla versione della classe base della variabile.  
  
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
 Per ridurre il rischio di fare riferimento a una versione di una variabile nascosta indesiderata, è possibile qualificare completamente tutti i riferimenti a una variabile nascosta. Shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione del codice e la presenza di una stringa di qualifica. Ciò può aumentare il rischio di fare riferimento alla versione errata della variabile.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
