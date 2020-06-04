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
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="cd555-102">Uso della varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd555-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="cd555-103">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="cd555-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="cd555-104">La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="cd555-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="cd555-105">La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="cd555-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="cd555-106">Esempio 1: covarianza</span><span class="sxs-lookup"><span data-stu-id="cd555-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="cd555-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd555-107">Description</span></span>

<span data-ttu-id="cd555-108">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="cd555-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="cd555-109">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="cd555-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="cd555-110">Codice</span><span class="sxs-lookup"><span data-stu-id="cd555-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="cd555-111">Esempio 2: controvarianza</span><span class="sxs-lookup"><span data-stu-id="cd555-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="cd555-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd555-112">Description</span></span>

<span data-ttu-id="cd555-113">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri i cui tipi rappresentano tipi di base del tipo di parametro della firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="cd555-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="cd555-114">Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="cd555-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="cd555-115">Nell'esempio seguente vengono usati due delegati:</span><span class="sxs-lookup"><span data-stu-id="cd555-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="cd555-116">Un delegato <xref:System.Windows.Forms.KeyEventHandler> che definisce la firma dell'evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="cd555-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="cd555-117">La firma è:</span><span class="sxs-lookup"><span data-stu-id="cd555-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="cd555-118">Un delegato <xref:System.Windows.Forms.MouseEventHandler> che definisce la firma dell'evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="cd555-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="cd555-119">La firma è:</span><span class="sxs-lookup"><span data-stu-id="cd555-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="cd555-120">Nell'esempio viene definito un gestore eventi con un parametro <xref:System.EventArgs> e viene usato per gestire entrambi gli eventi `Button.KeyDown` e `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="cd555-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="cd555-121">Ciò è possibile perché <xref:System.EventArgs> è un tipo di base sia di <xref:System.Windows.Forms.KeyEventArgs> che di <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd555-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="cd555-122">Codice</span><span class="sxs-lookup"><span data-stu-id="cd555-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cd555-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd555-123">See also</span></span>

- [<span data-ttu-id="cd555-124">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd555-124">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
- [<span data-ttu-id="cd555-125">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd555-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
