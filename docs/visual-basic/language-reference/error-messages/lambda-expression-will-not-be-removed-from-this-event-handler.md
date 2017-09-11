---
title: Espressione lambda non vengono rimosse da questo gestore eventi | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
dev_langs:
- VB
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7afe8160a25130cd92722df527d9567192912292
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="c6b8e-102">L'espressione lambda non verrà rimossa da questo gestore eventi</span><span class="sxs-lookup"><span data-stu-id="c6b8e-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="c6b8e-103">L'espressione lambda non verrà rimossa da questo gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="c6b8e-104">Assegnare l'espressione lambda a una variabile e utilizzare la variabile per aggiungere e rimuovere l'evento.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="c6b8e-105">Quando le espressioni lambda vengono utilizzate con i gestori eventi, potrebbero non essere visualizzati il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="c6b8e-106">Il compilatore genera un nuovo metodo per ogni definizione dell'espressione lambda, anche se sono identici.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="c6b8e-107">Pertanto, il codice seguente visualizza `False`.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-107">Therefore, the following code displays `False`.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 <span data-ttu-id="c6b8e-108">Quando le espressioni lambda vengono utilizzate con i gestori eventi, questo può causare risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="c6b8e-109">Nell'esempio seguente, l'espressione lambda aggiunta da `AddHandler` non viene rimosso mediante il `RemoveHandler` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c6b8e-110">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-110">By default, this message is a warning.</span></span> <span data-ttu-id="c6b8e-111">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c6b8e-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c6b8e-112">**ID errore:** BC42326</span><span class="sxs-lookup"><span data-stu-id="c6b8e-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6b8e-113">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c6b8e-113">To correct this error</span></span>  
  
-   <span data-ttu-id="c6b8e-114">Per evitare l'avviso e rimuovere l'espressione lambda, assegnare l'espressione lambda a una variabile e utilizzare tale variabile in entrambe le `AddHandler` e `RemoveHandler` istruzioni, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c6b8e-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6b8e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6b8e-115">See Also</span></span>  
 <span data-ttu-id="c6b8e-116">[Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="c6b8e-116">[Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="c6b8e-117"> [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md) </span><span class="sxs-lookup"><span data-stu-id="c6b8e-117"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md) </span></span>  
<span data-ttu-id="c6b8e-118"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="c6b8e-118"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
