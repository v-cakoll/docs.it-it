---
title: Impossibile convertire il tipo anonimo in un albero delle espressioni. Il tipo anonimo contiene un campo usato nell'inizializzazione di un altro campo.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: d43f6ef19591af326d06a4ce21194d8f9fa58c2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585476"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Impossibile convertire il tipo anonimo in un albero delle espressioni. Il tipo anonimo contiene un campo usato nell'inizializzazione di un altro campo.
Il compilatore non accetta la conversione di un tipo anonimo in un albero delle espressioni quando una proprietà di tipo anonimo viene utilizzata per inizializzare un'altra proprietà di tipo anonimo. Ad esempio, nel codice seguente, `Prop1` viene dichiarato nell'elenco di inizializzazione e quindi utilizzato come valore iniziale per `Prop2`.  
  
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
  
-   Assegnare il valore iniziale per `Prop1` a una variabile locale. Assegnare la variabile sia `Prop1` e `Prop2`, come illustrato nel codice seguente.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Alberi delle espressioni](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [Procedura: Usare alberi delle espressioni per la compilazione di query dinamiche](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
