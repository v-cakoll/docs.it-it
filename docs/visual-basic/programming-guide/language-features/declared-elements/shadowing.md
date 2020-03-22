---
title: Shadowing
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266885"
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Quando due elementi di programmazione condividono lo stesso nome, uno di essi può nascondere, o *ombreggiare*, l'altro. In una situazione di questo tipo, l'elemento nascosto non è disponibile come riferimento; al contrario, quando il codice utilizza il nome dell'elemento, il compilatore Visual Basic lo risolve nell'elemento di shadowing.  
  
## <a name="purpose"></a>Scopo  
 Lo scopo principale dello shadowing è proteggere la definizione dei membri della classe. La classe base potrebbe subire una modifica che crea un elemento con lo stesso nome di uno già definito. In questo caso, il `Shadows` modificatore forza i riferimenti tramite la classe da risolvere per il membro definito, anziché per il nuovo elemento della classe base.  
  
## <a name="types-of-shadowing"></a>Tipi di ombreggiatura  
 Un elemento può nascondere un altro elemento in due modi diversi. L'elemento di shadowing può essere dichiarato all'interno di una sottoarea dell'area contenente l'elemento nascosto, nel qual caso lo shadowing viene eseguito *tramite l'ambito*. In alternativa, una classe di derivazione può ridefinire un membro di una classe base, nel qual caso lo shadowing viene eseguito *tramite l'ereditarietà*.  
  
### <a name="shadowing-through-scope"></a>Shadowing attraverso l'ambito  
 È possibile che la programmazione di elementi nello stesso modulo, classe o struttura abbia lo stesso nome ma ambito diverso. Quando due elementi vengono dichiarati in questo modo e il codice fa riferimento al nome che condividono, l'elemento con l'ambito più stretto nasconde l'altro elemento (l'ambito del blocco è il più stretto).  
  
 Ad esempio, un modulo `Public` può `temp`definire una variabile denominata , e `temp`una routine all'interno del modulo può dichiarare anche una variabile locale denominata . I `temp` riferimenti a dall'interno della routine `temp` accedono alla variabile `Public` locale, mentre i riferimenti all'esterno della routine accedono alla variabile. In questo caso, `temp` la variabile `temp`di routine nasconde la variabile di modulo .  
  
 Nella figura seguente vengono illustrate `temp`due variabili, entrambe denominate . La variabile `temp` locale nasconde `temp` la variabile membro `p`quando si accede dall'interno della propria routine . Tuttavia, `MyClass` la parola chiave ignora lo shadowing e accede alla variabile membro.  
  
 ![Immagine che mostra lo shadowing attraverso l'ambito.](./media/shadowing/shadow-scope-diagram.gif)
  
 Per un esempio di shadowing nell'ambito, vedere [Procedura: nascondere una variabile con lo stesso nome della variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowing tramite ereditarietà  
 Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe base, l'elemento di ridefinizione nasconde l'elemento originale. È possibile nascondere qualsiasi tipo di elemento dichiarato, o set di elementi di overload, con qualsiasi altro tipo. Ad esempio, `Integer` una variabile `Function` può eseguire lo shadowing di una routine. Se si nasconde una routine con un'altra routine, è possibile utilizzare un elenco di parametri diverso e un tipo restituito diverso.  
  
 Nella figura seguente vengono `b` illustrate una `d` classe base `b`e una classe derivata che eredita da . La classe base definisce `proc`una routine denominata e la classe derivata la nasconde con un'altra routine con lo stesso nome. La `Call` prima istruzione accede allo `proc` shadowing nella classe derivata. Tuttavia, `MyBase` la parola chiave ignora lo shadowing e accede alla routine sottoposta a shadowing nella classe base.  
  
 ![Diagramma grafico dello shadowing tramite eredità](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Per un esempio di shadowing tramite ereditarietà, vedere [How to: Nascondere una variabile con lo stesso nome della variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e Procedura: nascondere una variabile [ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing e livello di accesso  
 L'elemento di shadowing non è sempre accessibile dal codice tramite la classe derivata. Ad esempio, potrebbe `Private`essere dichiarato . In tal caso, lo shadowing viene annullato e il compilatore risolve qualsiasi riferimento allo stesso elemento che avrebbe se non ci fosse stato lo shadowing. Questo elemento è l'elemento accessibile il minor numero di passaggi derivati-indietro dalla classe di shadowing. Se l'elemento nascosto è una routine, la risoluzione è alla versione accessibile più vicina con lo stesso nome, elenco di parametri e tipo restituito.  
  
 Nell'esempio seguente viene illustrata una gerarchia di ereditarietà di tre classi. Ogni classe definisce una `Sub` routine `display`, `display` mentre ogni classe derivata nasconde la routine nella relativa classe base.  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 Nell'esempio precedente, le `secondClass` ombre `display` della `Private` classe derivata con una routine. Quando `callDisplay` il `display` `secondClass`modulo chiama in `secondClass` , il codice `display` chiamante è esterno e pertanto non può accedere alla routine privata. Lo shadowing viene sconfitto e il compilatore `display` risolve il riferimento alla routine della classe base.  
  
 Tuttavia, l'altra `thirdClass` classe derivata dichiara `display` come `Public`, in modo che il codice in `callDisplay` possa accedervi.  
  
## <a name="shadowing-and-overriding"></a>Shadowing e override  
 Non confondere lo shadowing con l'override. Entrambi vengono utilizzati quando una classe derivata eredita da una classe base ed entrambi ridefiniscono un elemento dichiarato con un altro. Ma ci sono differenze significative tra i due. Per un confronto, vedere [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing e Sovraccarico  
 Se si nasconde lo stesso elemento della classe base con più di un elemento nella classe derivata, gli elementi di shadowing diventano versioni di overload di tale elemento. Per altre informazioni, vedere [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Accesso a un elemento ombreggiatoAccessing a Shadowed Element  
 Quando si accede a un elemento da una classe derivata, in genere si esegue questa `Me` operazione tramite l'istanza corrente di tale classe derivata, qualificando il nome dell'elemento con la parola chiave . Se la classe derivata nasconde l'elemento nella classe base, è possibile `MyBase` accedere all'elemento della classe base qualificandolo con la parola chiave .  
  
 Per un esempio di accesso a un elemento nascosto, vedere [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Dichiarazione della variabile oggetto  
 La modalità di creazione della variabile oggetto può anche influire sulla possibilità che la classe derivata acceda a un elemento di shadowing o all'elemento ombreggiato. Nell'esempio seguente vengono creati due oggetti da una classe derivata, ma un oggetto viene dichiarato come classe base e l'altro come classe derivata.  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 Nell'esempio precedente, la `basObj` variabile viene dichiarata come classe base. L'assegnazione di un `dervCls` oggetto ad esso costituisce una conversione di ampliamento ed è quindi valido. Tuttavia, la classe base non può `z` accedere alla versione di shadowing `basObj.z` della variabile nella classe derivata, pertanto il compilatore viene risolto nel valore della classe base originale.  
  
## <a name="see-also"></a>Vedere anche

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Esegue l' override](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
