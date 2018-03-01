---
title: "L'espressione lambda non verrà rimossa da questo gestore eventi"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a4c57d1f8f41d2d9ebb645d3f2628c32a2c4e4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>L'espressione lambda non verrà rimossa da questo gestore eventi
Espressione lambda non vengono rimosse da questo gestore eventi. Assegnare l'espressione lambda a una variabile e utilizzare tale variabile per aggiungere e rimuovere l'evento.  
  
 Quando le espressioni lambda vengono utilizzate con i gestori eventi, si potrebbe non visualizzare il comportamento desiderato. Il compilatore genera un nuovo metodo per ogni definizione di espressione lambda anche se sono identici. Pertanto, il codice seguente consente di visualizzare `False`.  
  
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
  
 Quando le espressioni lambda vengono utilizzate con i gestori eventi, questo può causare risultati imprevisti. Nell'esempio seguente, l'espressione lambda aggiunta da `AddHandler` non viene rimosso dal `RemoveHandler` istruzione.  
  
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
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42326  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Per evitare l'avviso e rimuovere l'espressione lambda, assegnare l'espressione lambda a una variabile e utilizzare tale variabile in entrambi i `AddHandler` e `RemoveHandler` istruzioni, come illustrato nell'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
