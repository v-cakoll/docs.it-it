---
title: Uso della varianza nei delegati
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 842392a1342f7d3689d4d1f2a2adb7470eeda05e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375784"
---
# <a name="using-variance-in-delegates-visual-basic"></a>Uso della varianza nei delegati (Visual Basic)

Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo. La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato. La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.

## <a name="example-1-covariance"></a>Esempio 1: covarianza

### <a name="description"></a>Descrizione

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

## <a name="example-2-contravariance"></a>Esempio 2: controvarianza

### <a name="description"></a>Descrizione

In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri i cui tipi rappresentano tipi di base del tipo di parametro della firma del delegato. Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati. Nell'esempio seguente vengono usati due delegati:

- Un delegato <xref:System.Windows.Forms.KeyEventHandler> che definisce la firma dell'evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown). La firma è:

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- Un delegato <xref:System.Windows.Forms.MouseEventHandler> che definisce la firma dell'evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown). La firma è:

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

Nell'esempio viene definito un gestore eventi con un parametro <xref:System.EventArgs> e viene usato per gestire entrambi gli eventi `Button.KeyDown` e `Button.MouseClick`. Ciò è possibile perché <xref:System.EventArgs> è un tipo di base sia di <xref:System.Windows.Forms.KeyEventArgs> che di <xref:System.Windows.Forms.MouseEventArgs>.

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

- [Varianza nei delegati (Visual Basic)](variance-in-delegates.md)
- [Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)
