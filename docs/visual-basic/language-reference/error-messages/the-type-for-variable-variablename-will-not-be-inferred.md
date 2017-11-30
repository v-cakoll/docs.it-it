---
title: "Il tipo di variabile &#39; &lt;variablename&gt;&#39; non riuscita perché è associato a un campo in un ambito contenitore"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords: BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39968407f4de5436df324320c99dede4d72e2808
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Il tipo di variabile &#39; &lt;variablename&gt;&#39; non riuscita perché è associato a un campo in un ambito contenitore
Il tipo di variabile '\<variablename >' non verrà dedotto perché associato a un campo in un ambito contenitore. Modificare il nome di '\<variablename >', oppure utilizzare il nome completo (ad esempio, 'Variablename' o 'MyBase').  
  
 Una variabile di controllo del ciclo nel codice ha lo stesso nome di un campo della classe o altro ambito di inclusione. Poiché la variabile di controllo viene utilizzata senza un `As` clausola, è associato al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile per tale né dedurre il tipo.  
  
 Nell'esempio seguente, `Index`, la variabile di controllo nel `For` istruzione, è associato al `Index` campo la `Customer` classe. Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o dedurre il tipo.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42110  
  
### <a name="to-address-this-warning"></a>Per risolvere questo avviso  
  
-   Rendere la variabile di controllo locale modificando il nome a un identificatore che non sia anche il nome di un campo della classe.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Chiarire che la variabile di controllo è associata al campo della classe anteponendo `Me.` al nome della variabile.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Anziché basarsi sull'inferenza del tipo locale, utilizzare un `As` clausola per specificare un tipo per la variabile di controllo.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato l'esempio precedente con la correzione prima sul posto.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Procedura: fare riferimento all'istanza corrente di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
