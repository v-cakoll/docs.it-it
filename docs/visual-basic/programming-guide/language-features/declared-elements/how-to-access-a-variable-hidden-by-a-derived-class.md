---
title: 'Procedura: accedere a una variabile nascosta da una classe derivata'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: c5ff802a0f6e081acd00d7cdfab4a8296b4daad9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392857"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Procedura: accedere a una variabile nascosta da una classe derivata (Visual Basic)

Quando il codice in una classe derivata accede a una variabile, il compilatore normalmente risolve il riferimento alla versione accessibile più vicina, ovvero la versione accessibile, il minor numero di passaggi derivazionali dalla classe di accesso. Se la variabile è definita nella classe derivata, il codice accede normalmente a tale definizione.

Se la variabile della classe derivata ombreggia una variabile nella classe di base, nasconde la versione della classe base. Tuttavia, è possibile accedere alla variabile della classe base qualificando la `MyBase` parola chiave.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Per accedere a una variabile della classe di base nascosta da una classe derivata

- In un'espressione o in un'istruzione di assegnazione precedere il nome della variabile con la `MyBase` parola chiave e un punto ( `.` ).

    Il compilatore risolve il riferimento alla versione della classe di base della variabile.

    Nell'esempio seguente viene illustrata l'ombreggiatura tramite ereditarietà. Crea due riferimenti, uno che accede alla variabile di shadowing e uno che ignora lo shadowing.

    ```vb
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

    Nell'esempio precedente la variabile viene dichiarata `shadowString` nella classe base e viene ombreggiata nella classe derivata. La routine `showStrings` della classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato. Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la `MyBase` parola chiave.

## <a name="robust-programming"></a>Programmazione efficiente

Per ridurre il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata, è possibile qualificare completamente tutti i riferimenti a una variabile ombreggiata. Lo shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata. Questo può aumentare il rischio di fare riferimento alla versione errata della variabile.

## <a name="see-also"></a>Vedere anche

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Differenze tra shadowing e override](differences-between-shadowing-and-overriding.md)
- [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: nascondere una variabile ereditata](how-to-hide-an-inherited-variable.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Override](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../objects-and-classes/inheritance-basics.md)
