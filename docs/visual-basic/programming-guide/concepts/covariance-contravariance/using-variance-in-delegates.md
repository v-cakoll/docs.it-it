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
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="f6256-102">Uso della varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6256-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="f6256-103">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="f6256-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="f6256-104">La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="f6256-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="f6256-105">La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="f6256-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="f6256-106">Esempio 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="f6256-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="f6256-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f6256-107">Description</span></span>

<span data-ttu-id="f6256-108">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="f6256-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="f6256-109">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="f6256-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="f6256-110">Codice</span><span class="sxs-lookup"><span data-stu-id="f6256-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="f6256-111">Esempio 2: Controvarianza</span><span class="sxs-lookup"><span data-stu-id="f6256-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="f6256-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6256-112">Description</span></span>

<span data-ttu-id="f6256-113">Questo esempio illustra come usare i delegati con i metodi che hanno parametri i cui tipi sono tipi di base del tipo di parametro della firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="f6256-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="f6256-114">Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="f6256-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="f6256-115">Nell'esempio seguente vengono usati due delegati:</span><span class="sxs-lookup"><span data-stu-id="f6256-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="f6256-116">Delegato che definisce la firma dell'evento [Button. KeyDown.](xref:System.Windows.Forms.Control.KeyDown) <xref:System.Windows.Forms.KeyEventHandler></span><span class="sxs-lookup"><span data-stu-id="f6256-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="f6256-117">La firma è:</span><span class="sxs-lookup"><span data-stu-id="f6256-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="f6256-118">Delegato che definisce la firma dell'evento [Button. Click](xref:System.Windows.Forms.Control.MouseDown) -through. <xref:System.Windows.Forms.MouseEventHandler></span><span class="sxs-lookup"><span data-stu-id="f6256-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="f6256-119">La firma è:</span><span class="sxs-lookup"><span data-stu-id="f6256-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="f6256-120">Nell'esempio viene definito un gestore eventi con <xref:System.EventArgs> un parametro e viene utilizzato per gestire `Button.KeyDown` gli eventi `Button.MouseClick` e.</span><span class="sxs-lookup"><span data-stu-id="f6256-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="f6256-121">Questa operazione può essere eseguita <xref:System.EventArgs> perché è un tipo di base <xref:System.Windows.Forms.KeyEventArgs> sia <xref:System.Windows.Forms.MouseEventArgs>di che di.</span><span class="sxs-lookup"><span data-stu-id="f6256-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="f6256-122">Codice</span><span class="sxs-lookup"><span data-stu-id="f6256-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f6256-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6256-123">See also</span></span>

- [<span data-ttu-id="f6256-124">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6256-124">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="f6256-125">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6256-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
