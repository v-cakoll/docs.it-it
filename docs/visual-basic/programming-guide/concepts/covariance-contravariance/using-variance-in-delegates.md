---
title: Utilizzo della varianza nei delegati (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 620fd61000e42d68f566e441d023d73a036000ae
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="37eca-102">Utilizzo della varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37eca-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="37eca-103">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="37eca-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="37eca-104">La covarianza consente a un metodo per restituire tipo più derivato da quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="37eca-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="37eca-105">La controvarianza consente a un metodo che dispone di tipi di parametro che sono meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="37eca-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="37eca-106">Esempio 1: covarianza</span><span class="sxs-lookup"><span data-stu-id="37eca-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="37eca-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37eca-107">Description</span></span>  
 <span data-ttu-id="37eca-108">In questo esempio viene illustrato come utilizzare i delegati con metodi che restituiscono tipi che derivano dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="37eca-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="37eca-109">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal `Mammals` tipo definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="37eca-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="37eca-110">Codice</span><span class="sxs-lookup"><span data-stu-id="37eca-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="37eca-111">Esempio 2: controvarianza</span><span class="sxs-lookup"><span data-stu-id="37eca-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="37eca-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37eca-112">Description</span></span>  
 <span data-ttu-id="37eca-113">In questo esempio viene illustrato come utilizzare i delegati con metodi che dispongono di un tipo di parametri che sono tipi di base del tipo di parametro di firma di delegato.</span><span class="sxs-lookup"><span data-stu-id="37eca-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="37eca-114">Con la controvarianza, è possibile utilizzare un gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="37eca-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="37eca-115">Ad esempio, è possibile creare un gestore eventi che accetta un `EventArgs` parametro di input e di utilizzarlo con un `Button.MouseClick` evento che invia un `MouseEventArgs` tipo come parametro e con un `TextBox.KeyDown` evento che invia un `KeyEventArgs` parametro.</span><span class="sxs-lookup"><span data-stu-id="37eca-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="37eca-116">Codice</span><span class="sxs-lookup"><span data-stu-id="37eca-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37eca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37eca-117">See Also</span></span>  
 <span data-ttu-id="37eca-118">[Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="37eca-118">[Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
<span data-ttu-id="37eca-119"> [Utilizzo della varianza per i delegati generici azione (Visual Basic) e Func](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="37eca-119"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
