---
title: Shadowing in Visual Basic
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
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839392"
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, oppure *shadow*, un altro. In questo caso, l'elemento nascosto non è disponibile per riferimento; al contrario, quando il codice usi il nome dell'elemento, il compilatore Visual Basic si risolve nell'elemento di shadowing.  
  
## <a name="purpose"></a>Scopo  
 Lo scopo principale di shadowing consiste nella protezione di definizione dei membri della classe. La classe di base potrebbe essere sottoposto a una modifica che crea un elemento con lo stesso nome di uno che già definito. In questo caso, il `Shadows` modificatore impone che fa riferimento tramite la classe deve essere risolto al membro è definito, anziché per il nuovo elemento di classe di base.  
  
## <a name="types-of-shadowing"></a>Tipi di Shadowing  
 Un elemento può nascondere un altro elemento in due modi diversi. L'elemento di shadowing può essere dichiarato all'interno di un'area secondaria dell'area che contiene l'elemento nascosto, in cui viene eseguito lo shadowing *mediante l'ambito*. O una classe derivante può ridefinire un membro di una classe base, la quale viene eseguito lo shadowing *attraverso l'ereditarietà*.  
  
### <a name="shadowing-through-scope"></a>Shadowing tramite l'ambito  
 È possibile che gli elementi nella stesso modulo, classe o struttura abbiano lo stesso nome ma un ambito diverso di programmazione. Quando vengono dichiarati due elementi in questo modo e il codice fa riferimento al nome condividono, l'elemento con l'ambito più ristretto nasconde l'altro elemento (l'ambito del blocco è il più ristretto).  
  
 Ad esempio, è possibile definire un modulo di un `Public` variabile denominata `temp`, e una procedura all'interno del modulo può dichiarare una variabile locale denominata anche `temp`. I riferimenti a `temp` dall'interno la procedura di accesso alla variabile locale, mentre i riferimenti a `temp` di fuori della routine accedono i `Public` variabile. In questo caso, la variabile della procedura `temp` nasconde la variabile del modulo `temp`.  
  
 La figura seguente illustra due variabili, entrambi denominati `temp`. La variabile locale `temp` nasconde la variabile membro `temp` quando si accede da all'interno della relativa routine `p`. Tuttavia, il `MyClass` parola chiave ignora lo shadowing e accede alla variabile membro.  
  
 ![Figura che illustra shadowing tramite l'ambito.](./media/shadowing/shadow-scope-diagram.gif)
  
 Per un esempio di shadowing tramite l'ambito, vedere [come: Nascondere una variabile con lo stesso nome di un'altra variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowing tramite eredità  
 Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe di base, l'elemento ridefinisce nasconde l'elemento originale. È possibile nascondere qualsiasi tipo di elemento dichiarato o set di elementi in overload con qualsiasi altro tipo. Ad esempio, un' `Integer` variabile può nascondere un `Function` procedure. Se si nasconde una procedura con un'altra routine, è possibile usare un elenco di parametri diversi e un tipo restituito differente.  
  
 La figura seguente mostra una classe di base `b` e una classe derivata `d` che eredita da `b`. La classe di base definisce una routine denominata `proc`, mentre la classe derivata nasconde con un'altra routine con lo stesso nome. Il primo `Call` istruzione accede allo shadowing `proc` nella classe derivata. Tuttavia, il `MyBase` parola chiave ignora lo shadowing e accedere alla routine nascosta nella classe di base.  
  
 ![Diagramma grafico dello shadowing tramite eredità](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Per un esempio dello shadowing tramite eredità, vedere [come: Nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e [come: Nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing e livello di accesso  
 L'elemento di shadowing non sempre accessibile dal codice utilizzando la classe derivata. Ad esempio, potrebbe essere dichiarato `Private`. In tal caso, lo shadowing viene annullato e il compilatore risolve qualsiasi riferimento allo stesso elemento avrebbe se fosse disponibile alcun shadowing. Questo elemento è l'elemento accessibile il minor numero di derivazionali passaggi precedente dalla classe di shadowing. Se l'elemento nascosto non è una procedura, la risoluzione è alla versione più vicina accessibile con lo stesso nome, l'elenco dei parametri e il tipo restituito.  
  
 L'esempio seguente illustra una gerarchia di ereditarietà delle tre classi. Ogni classe definisce un `Sub` procedure `display`, e ciascuna classe derivata nasconde la `display` procedure nella relativa classe base.  
  
```  
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
  
 Nell'esempio precedente, la classe derivata `secondClass` shadows `display` con un `Private` procedure. Quando modulo `callDisplay` chiamate `display` nelle `secondClass`, il codice chiamante non è compreso `secondClass` e pertanto non può accedere a privato `display` procedure. Lo shadowing viene annullato e il compilatore risolve il riferimento alla classe di base `display` procedure.  
  
 Tuttavia, l'altra classe derivata `thirdClass` dichiara `display` come `Public`, quindi il codice in `callDisplay` possano accedervi.  
  
## <a name="shadowing-and-overriding"></a>Shadowing e override  
 Non confondere shadowing e override. Entrambi vengono utilizzati quando una classe derivata eredita da una classe di base ed entrambi consentono di ridefinire un elemento dichiarato con un altro. Ma esistono differenze significative tra i due. Per un confronto, vedere [differenze tra Shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing e overload  
 Se si nasconde lo stesso elemento di classe di base con più di un elemento nella classe derivata, gli elementi di shadowing diventano le versioni di overload di quell'elemento. Per altre informazioni, vedere [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Accesso a un elemento nascosto  
 Quando si accede a un elemento da una classe derivata, in genere farlo tramite l'istanza corrente di tale classe derivata, qualificando il nome dell'elemento con la `Me` (parola chiave). Se la classe derivata nasconde l'elemento nella classe di base, è possibile accedere all'elemento della classe base per qualificarlo con il `MyBase` (parola chiave).  
  
 Per un esempio di accesso a un elemento nascosto, vedere [come: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Dichiarazione della variabile oggetto  
 Come si crea la variabile oggetto può anche determinare se la classe derivata accede a un elemento di shadowing o l'elemento nascosto. L'esempio seguente crea due oggetti da una classe derivata, ma un oggetto viene dichiarato come classe base e l'altro come la classe derivata.  
  
```  
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
  
 Nell'esempio precedente, la variabile `basObj` viene dichiarata come classe di base. Assegnazione di un `dervCls` oggetto ad esso costituisce una conversione verso un ed è pertanto valido. Tuttavia, la classe di base non può accedere alla versione di shadowing della variabile `z` nella classe derivata, pertanto, il compilatore risolve `basObj.z` il valore di classe di base originale.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
