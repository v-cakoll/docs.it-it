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
ms.openlocfilehash: f49bba0497f9f4f2774b01284c815bba9aaed119
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357270"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedura: nascondere una variabile ereditata (Visual Basic)

Una classe derivata eredita tutte le definizioni della relativa classe di base. Se si vuole definire una variabile con lo stesso nome di un elemento della classe di base, è possibile nascondere, o *ombreggiare*, tale elemento della classe base quando si definisce la variabile nella classe derivata. In tal caso, il codice della classe derivata accede alla variabile a meno che non venga ignorato in modo esplicito il meccanismo di ombreggiatura.

Un altro motivo per cui potrebbe essere necessario nascondere una variabile ereditata consiste nel proteggersi dalla revisione della classe base. La classe base può subire una modifica che modifica l'elemento che si sta ereditando. In tal caso, il `Shadows` modificatore impone la risoluzione dei riferimenti dalla classe derivata alla variabile, anziché all'elemento della classe base.

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
  
     Nell'esempio precedente la variabile viene dichiarata `shadowString` nella classe base e viene ombreggiata nella classe derivata. La routine `ShowStrings` della classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato. Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la `MyBase` parola chiave.  
  
## <a name="robust-programming"></a>Programmazione efficiente

Lo shadowing introduce più di una versione di una variabile con lo stesso nome. Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata. Questo può aumentare il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata. È possibile ridurre il rischio selezionando completamente tutti i riferimenti a una variabile ombreggiata.

## <a name="see-also"></a>Vedere anche

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Differenze tra shadowing e override](differences-between-shadowing-and-overriding.md)
- [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: accedere a una variabile nascosta da una classe derivata](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Override](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../objects-and-classes/inheritance-basics.md)
