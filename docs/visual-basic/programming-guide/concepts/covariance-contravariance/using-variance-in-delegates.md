---
title: Uso della varianza nei delegati (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: ebba7e862e1b4677d9438aa301ef2b713fba3712
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169075"
---
# <a name="using-variance-in-delegates-visual-basic"></a>Uso della varianza nei delegati (Visual Basic)

Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo. La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato. La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.

## <a name="example-1-covariance"></a>Esempio 1: Covarianza

### <a name="description"></a>DESCRIZIONE

In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato. Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.

### <a name="code"></a>Codice

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a>Esempio 2: Controvarianza

### <a name="description"></a>Descrizione

Questo esempio illustra come usare i delegati con i metodi che hanno parametri i cui tipi sono tipi di base del tipo di parametro della firma del delegato. Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati. Nell'esempio seguente vengono usati due delegati:

- Delegato che definisce la firma dell'evento [Button. KeyDown.](xref:System.Windows.Forms.Control.KeyDown) <xref:System.Windows.Forms.KeyEventHandler> La firma è:

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- Delegato che definisce la firma dell'evento [Button. Click](xref:System.Windows.Forms.Control.MouseDown) -through. <xref:System.Windows.Forms.MouseEventHandler> La firma è:

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

Nell'esempio viene definito un gestore eventi con <xref:System.EventArgs> un parametro e viene utilizzato per gestire `Button.KeyDown` gli eventi `Button.MouseClick` e. Questa operazione può essere eseguita <xref:System.EventArgs> perché è un tipo di base <xref:System.Windows.Forms.KeyEventArgs> sia <xref:System.Windows.Forms.MouseEventArgs>di che di.

### <a name="code"></a>Codice

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a>Vedere anche

- [Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
