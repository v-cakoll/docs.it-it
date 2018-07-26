---
title: Impossibile convertire il tipo anonimo in un albero delle espressioni. Il tipo anonimo contiene un campo usato nell'inizializzazione di un altro campo.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 2f97a0de74428ce42a088644580a78bf8fd99945
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936802"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Impossibile convertire il tipo anonimo in un albero delle espressioni. Il tipo anonimo contiene un campo usato nell'inizializzazione di un altro campo.
Il compilatore non accetta la conversione di un tipo anonimo in un albero delle espressioni quando una proprietà del tipo anonimo viene usata per inizializzare un'altra proprietà del tipo anonimo. Ad esempio, nel codice seguente, `Prop1` viene dichiarato nell'elenco di inizializzazione e quindi utilizzato come valore iniziale per `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **ID errore:** BC36548  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assegnare il valore iniziale per `Prop1` a una variabile locale. Assegnare la variabile a entrambe `Prop1` e `Prop2`, come illustrato nel codice seguente.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

[Tipi anonimi (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
[Alberi delle espressioni (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)  
[Procedura: usare alberi delle espressioni per compilare query dinamiche (Visual Basic)](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)  