---
title: Shadowing in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 489e1786b08085f229f66b2dbc434b96b06d86df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, o *shadow*, l'altro. In questo caso, l'elemento nascosto non è disponibile per riferimento; al contrario, quando il codice utilizza il nome dell'elemento, il compilatore Visual Basic risolve nell'elemento di shadowing.  
  
## <a name="purpose"></a>Scopo  
 Lo scopo principale di shadowing sia per proteggere la definizione dei membri della classe. La classe di base può essere sottoposto a una modifica che crea un elemento con lo stesso nome già definito. In questo caso, il `Shadows` modificatore impone che fa riferimento tramite la classe deve essere risolto per il membro è definito, anziché il nuovo elemento della classe base.  
  
## <a name="types-of-shadowing"></a>Tipi di Shadowing  
 Un elemento può nascondere un altro elemento in due modi diversi. L'elemento di shadowing può essere dichiarato in un'area secondaria dell'area che contiene l'elemento nascosto, in cui viene eseguito lo shadowing *mediante l'ambito*. O una classe derivata può ridefinire un membro di una classe base, in cui viene eseguito lo shadowing *tramite ereditarietà*.  
  
### <a name="shadowing-through-scope"></a>Shadowing tramite l'ambito  
 È possibile che gli elementi nella stesso modulo, classe o struttura abbiano lo stesso nome ma ambiti diversi di programmazione. Quando vengono dichiarati due elementi in questo modo, il codice fa riferimento al nome condividono l'elemento con ambito più ristretto nasconde l'altro elemento (l'ambito del blocco è ristretto).  
  
 Ad esempio, un modulo è possibile definire un `Public` variabile denominata `temp`, e una procedura all'interno del modulo è possibile dichiarare una variabile locale denominata anche `temp`. Fa riferimento alle `temp` dall'interno la procedura di accesso alla variabile locale, mentre i riferimenti a `temp` dall'esterno della routine accedono il `Public` variabile. In questo caso, la variabile della procedura `temp` nasconde la variabile di modulo `temp`.  
  
 La figura seguente mostra due variabili, entrambi denominati `temp`. La variabile locale `temp` nasconde la variabile membro `temp` quando si accede da all'interno della relativa routine `p`. Tuttavia, il `MyClass` parola chiave ignora lo shadowing e accedere alla variabile membro.  
  
 ![Diagramma grafico dello shadowing tramite ambito](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Shadowing tramite l'ambito  
  
 Per un esempio di shadowing tramite l'ambito, vedere [procedura: nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowing tramite eredità  
 Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe base, l'elemento ridefinisce nasconde l'elemento originale. È possibile nascondere qualsiasi tipo di elemento dichiarato o set di elementi in overload con qualsiasi altro tipo. Ad esempio, un `Integer` variabile può nascondere un `Function` stored procedure. Se si nasconde una routine con un'altra routine, è possibile utilizzare un elenco di parametri e un tipo restituito differente.  
  
 Nella figura seguente viene illustrata una classe base `b` e una classe derivata `d` che eredita da `b`. La classe base definisce una routine denominata `proc`, mentre la classe derivata nasconde con un'altra routine con lo stesso nome. Il primo `Call` istruzione accede lo shadowing `proc` nella classe derivata. Tuttavia, il `MyBase` parola chiave ignora lo shadowing e accedere alla routine nascosta nella classe base.  
  
 ![Diagramma grafico dello shadowing tramite eredità](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Shadowing tramite eredità  
  
 Per un esempio dello shadowing tramite eredità, vedere [procedura: nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e [procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing e livello di accesso  
 L'elemento di shadowing non è sempre accessibile dal codice utilizzando la classe derivata. Ad esempio, può essere dichiarata `Private`. In tal caso, lo shadowing viene annullato e il compilatore risolve qualsiasi riferimento allo stesso elemento avrebbe se fosse disponibile alcuna ombreggiatura. Questo elemento è l'elemento accessibile il minor numero di derivazionali passaggi precedenti dalla classe di shadowing. Se l'elemento nascosto non è una stored procedure, la risoluzione è nella versione accessibile più vicina con lo stesso nome, l'elenco dei parametri e tipo restituito.  
  
 Nell'esempio seguente viene illustrata una gerarchia di ereditarietà delle tre classi. Ogni classe definisce un `Sub` procedura `display`, e ogni classe derivata nasconde la `display` procedura nella relativa classe base.  
  
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
  
 Nell'esempio precedente, la classe derivata `secondClass` shadows `display` con un `Private` stored procedure. Quando modulo `callDisplay` chiamate `display` in `secondClass`, il codice chiamante non è compreso `secondClass` e pertanto non può accedere privato `display` stored procedure. Lo shadowing viene annullato e il compilatore risolve il riferimento alla classe di base `display` stored procedure.  
  
 Tuttavia, l'altra classe derivata `thirdClass` dichiara `display` come `Public`, pertanto il codice in `callDisplay` possano accedervi.  
  
## <a name="shadowing-and-overriding"></a>Shadowing e override  
 Non confondere shadowing e override. Entrambi vengono utilizzati quando una classe derivata eredita da una classe base ed entrambi consentono di ridefinire un elemento dichiarato con un altro. Ma esistono differenze significative tra i due. Per un confronto, vedere [le differenze tra Shadowing e verrà ignorato](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing e overload  
 Se si nasconde lo stesso elemento di classe di base con più di un elemento nella classe derivata, gli elementi di shadowing diventeranno versioni di overload di tale elemento. Per ulteriori informazioni, vedere [overload di routine](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Accesso a un elemento nascosto  
 Quando si accede a un elemento da una classe derivata, in genere avviene tramite l'istanza corrente della classe derivata, specificando il nome dell'elemento con la `Me` (parola chiave). Se la classe derivata nasconde l'elemento nella classe base, è possibile accedere all'elemento della classe base qualificandola con il `MyBase` (parola chiave).  
  
 Per un esempio di accesso a un elemento nascosto, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Dichiarazione della variabile oggetto  
 Come si crea la variabile oggetto può influire anche se la classe derivata accede a un elemento di shadowing o l'elemento nascosto. Nell'esempio seguente crea due oggetti da una classe derivata, ma è dichiarato un oggetto della classe base e l'altro come classe derivata.  
  
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
  
 Nell'esempio precedente, la variabile `basObj` viene dichiarata come classe base. L'assegnazione di un `dervCls` oggetto costituisce una conversione di ampliamento e pertanto è valida. Tuttavia, la classe di base non può accedere alla versione di shadowing della variabile `z` nella classe derivata, pertanto, il compilatore risolve `basObj.z` il valore di classe di base originale.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
