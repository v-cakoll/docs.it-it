---
title: Uso della varianza nei delegati (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: e0b0df354c6c31eed41ead2bb0b2a1aaa4ac9922
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690826"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="2a810-102">Uso della varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a810-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="2a810-103">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="2a810-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="2a810-104">La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="2a810-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="2a810-105">La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="2a810-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="2a810-106">Esempio 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="2a810-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="2a810-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a810-107">Description</span></span>  
 <span data-ttu-id="2a810-108">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="2a810-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="2a810-109">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="2a810-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a810-110">Codice</span><span class="sxs-lookup"><span data-stu-id="2a810-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="2a810-111">Esempio 2: Controvarianza</span><span class="sxs-lookup"><span data-stu-id="2a810-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="2a810-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a810-112">Description</span></span>  
 <span data-ttu-id="2a810-113">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri di un tipo che rappresentano tipi di base del tipo di parametro della firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="2a810-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="2a810-114">Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="2a810-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="2a810-115">Ad esempio, è possibile creare un gestore eventi che accetta un parametro di input `EventArgs` e usarlo con un evento `Button.MouseClick` che invia un tipo `MouseEventArgs` come parametro e anche con un evento `TextBox.KeyDown` che invia un parametro `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="2a810-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a810-116">Codice</span><span class="sxs-lookup"><span data-stu-id="2a810-116">Code</span></span>  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
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
  
## <a name="see-also"></a><span data-ttu-id="2a810-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a810-117">See also</span></span>
- [<span data-ttu-id="2a810-118">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a810-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="2a810-119">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a810-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
