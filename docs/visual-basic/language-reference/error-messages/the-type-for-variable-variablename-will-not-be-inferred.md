---
title: Il tipo della variabile '<variablename>' non verrà dedotto perché associato a un ambito di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: d7289b8ab0a141d6efdb0f4ca4b4547f15e0e182
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259241"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Il tipo della variabile '\<nomevariabile >' non riuscita perché è associato a un campo in un ambito contenitore
Il tipo della variabile '\<nomevariabile >' non riuscita perché è associato a un campo in un ambito contenitore. Modificare il nome del '\<nomevariabile >', oppure usare il nome completo (ad esempio, 'Me. variablename' o 'Variablename').  
  
 Una variabile di controllo ciclo nel codice ha lo stesso nome di un campo della classe o altri ambito contenitore. Poiché la variabile di controllo viene usata senza un `As` clausola, è associato al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile per tale né dedurne il tipo.  
  
 Nell'esempio seguente `Index`, la variabile di controllo nel `For` istruzione, è associato ai `Index` campo il `Customer` classe. Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o dedurre il tipo.  
  
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
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42110  
  
### <a name="to-address-this-warning"></a>Per risolvere questo avviso  
  
-   Rendere la variabile di controllo locale modificando il relativo nome a un identificatore che non è anche il nome di un campo della classe.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Chiarire che la variabile di controllo associata al campo della classe, facendolo precedere dalla `Me.` al nome della variabile.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Anziché basarsi sull'inferenza del tipo locale, usare un `As` clausola per specificare un tipo di variabile di controllo ciclo for.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'esempio precedente con la correzione primo posto.  
  
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
- [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Procedura: Fare riferimento all'istanza corrente di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
