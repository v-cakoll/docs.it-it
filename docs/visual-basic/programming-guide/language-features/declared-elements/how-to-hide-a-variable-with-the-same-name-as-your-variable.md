---
title: "Procedura: nascondere una variabile con lo stesso nome di un'altra variabile"
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
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345363"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)

Per nascondere una variabile, è possibile *ombreggiarla* , ovvero ridefinerla con una variabile con lo stesso nome. È possibile ombreggiare la variabile che si desidera nascondere in due modi:

- **Shadowing tramite ambito.** È possibile ombreggiarlo tramite l'ambito ridichiarando il contenuto in una regione secondaria dell'area contenente la variabile che si desidera nascondere.

- **Shadowing tramite ereditarietà.** Se la variabile che si desidera nascondere è definita a livello di classe, è possibile ombreggiarla tramite ereditarietà ridichiarando la parola chiave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) in una classe derivata.

## <a name="two-ways-to-hide-a-variable"></a>Due modi per nascondere una variabile

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Per nascondere una variabile ombreggiando l'ambito

1. Determinare l'area che definisce la variabile che si desidera nascondere e determinare un'area secondaria in cui ridefinirla con la variabile.

    |Area della variabile|Area secondaria consentita per la ridefinizione|
    |-----------------------|-------------------------------------------|
    |Modulo|Una classe all'interno del modulo|
    |Classe|Sottoclasse all'interno della classe<br /><br /> Una routine all'interno della classe|

    Non è possibile ridefinire una variabile di routine in un blocco all'interno di tale procedura, ad esempio in una costruzione `If`...`End If` o un ciclo di `For`.

2. Creare l'area secondaria, se non esiste già.

3. All'interno dell'area secondaria scrivere un' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) che dichiara la variabile di ombreggiatura.

    Quando il codice all'interno dell'area secondaria fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile di ombreggiatura.

    Nell'esempio seguente viene illustrata l'ombreggiatura tramite l'ambito, nonché un riferimento che ignora lo shadowing.

    ```vb
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

    Nell'esempio precedente viene dichiarata la variabile `num` a livello di modulo e a livello di routine (nella procedura `show`). La variabile locale `num` nasconde la variabile a livello di modulo `num` all'interno `show`, quindi la variabile locale è impostata su 2. Tuttavia, non esiste alcuna variabile locale per nascondere `num` nella procedura di `useModuleLevelNum`. Pertanto, `useModuleLevelNum` imposta su 1 il valore della variabile a livello di modulo.

    La chiamata `MsgBox` all'interno di `show` ignora il meccanismo di shadowing qualificando `num` con il nome del modulo. Quindi, Visualizza la variabile a livello di modulo invece della variabile locale.

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Per nascondere una variabile mediante lo shadowing tramite ereditarietà

1. Assicurarsi che la variabile che si desidera nascondere sia dichiarata in una classe e a livello di classe (all'esterno di qualsiasi routine). In caso contrario, non sarà possibile nasconderlo tramite l'ereditarietà.

2. Definire una classe derivata dalla classe della variabile se non ne esiste già una.

3. All'interno della classe derivata scrivere un'istruzione `Dim` che dichiara la variabile. Includere la parola chiave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.

    Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.

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

    Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe di base e viene ombreggiata nella classe derivata. La procedura `showStrings` nella classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato. Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la parola chiave `MyBase`.

## <a name="robust-programming"></a>Programmazione efficiente

Lo shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata. Questo può aumentare il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata. È possibile ridurre il rischio selezionando completamente tutti i riferimenti a una variabile ombreggiata.

## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
