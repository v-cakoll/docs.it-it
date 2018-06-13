---
title: 'Procedura: richiamare un metodo delegato (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: aca87dd9fa1990d44c99aab7753f2fd7d508adc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646952"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="23e6f-102">Procedura: richiamare un metodo delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e6f-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="23e6f-103">In questo esempio viene illustrato come associare un delegato di un metodo e quindi richiamare il metodo tramite il delegato.</span><span class="sxs-lookup"><span data-stu-id="23e6f-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="23e6f-104">Creare il delegato e le procedure corrispondenti</span><span class="sxs-lookup"><span data-stu-id="23e6f-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="23e6f-105">Crea un delegato denominato `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="23e6f-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="23e6f-106">Dichiarare una classe che contiene un metodo con la stessa firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="23e6f-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="23e6f-107">Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando predefinito `Invoke` metodo.</span><span class="sxs-lookup"><span data-stu-id="23e6f-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23e6f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23e6f-108">See Also</span></span>  
 [<span data-ttu-id="23e6f-109">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="23e6f-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="23e6f-110">Delegati</span><span class="sxs-lookup"><span data-stu-id="23e6f-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="23e6f-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="23e6f-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="23e6f-112">Applicazioni multithread</span><span class="sxs-lookup"><span data-stu-id="23e6f-112">Multithreaded Applications</span></span>](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
