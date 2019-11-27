---
title: 'Procedura: nascondere una variabile ereditata'
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
ms.openlocfilehash: c20c36b26c90c82da4e8836799f499498ccc40e4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345346"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedura: nascondere una variabile ereditata (Visual Basic)

Una classe derivata eredita tutte le definizioni della relativa classe di base. Se si vuole definire una variabile con lo stesso nome di un elemento della classe di base, è possibile nascondere, o *ombreggiare*, tale elemento della classe base quando si definisce la variabile nella classe derivata. In tal caso, il codice della classe derivata accede alla variabile a meno che non venga ignorato in modo esplicito il meccanismo di ombreggiatura.

Un altro motivo per cui potrebbe essere necessario nascondere una variabile ereditata consiste nel proteggersi dalla revisione della classe base. La classe base può subire una modifica che modifica l'elemento che si sta ereditando. In tal caso, il modificatore di `Shadows` impone la risoluzione dei riferimenti dalla classe derivata alla variabile, anziché all'elemento della classe base.

## <a name="to-hide-an-inherited-variable"></a>Per nascondere una variabile ereditata

1. Assicurarsi che la variabile che si desidera nascondere sia dichiarata a livello di classe (all'esterno di qualsiasi routine). In caso contrario, non è necessario nasconderlo.
  
2. All'interno della classe derivata scrivere un' [istruzione Dim](../../../language-reference/statements/dim-statement.md) che dichiara la variabile. Usare lo stesso nome della variabile ereditata.

3. Includere la parola chiave [Shadows](../../../language-reference/modifiers/shadows.md) nella dichiarazione.

     Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.

     Nell'esempio seguente viene illustrata l'ombreggiatura di una variabile ereditata:
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe di base e viene ombreggiata nella classe derivata. La procedura `ShowStrings` nella classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato. Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la parola chiave `MyBase`.  
  
## <a name="robust-programming"></a>Programmazione efficiente

Lo shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata. Questo può aumentare il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata. È possibile ridurre il rischio selezionando completamente tutti i riferimenti a una variabile ombreggiata.

## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Differenze tra shadowing e override](differences-between-shadowing-and-overriding.md)
- [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: accedere a una variabile nascosta da una classe derivata](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../objects-and-classes/inheritance-basics.md)
