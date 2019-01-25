---
title: 'Procedura: Richiamare un metodo delegato (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 42d56fca7e1d33c071db2e7e38935aa00caa5b7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676211"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="02de5-102">Procedura: Richiamare un metodo delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02de5-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="02de5-103">In questo esempio viene illustrato come associare un metodo con un delegato e quindi richiamare tale metodo tramite il delegato.</span><span class="sxs-lookup"><span data-stu-id="02de5-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="02de5-104">Creare il delegato e le procedure corrispondente</span><span class="sxs-lookup"><span data-stu-id="02de5-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="02de5-105">Creare un delegato denominato `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="02de5-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="02de5-106">Dichiarare una classe che contiene un metodo con la stessa firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="02de5-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="02de5-107">Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando predefiniti `Invoke` (metodo).</span><span class="sxs-lookup"><span data-stu-id="02de5-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="02de5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02de5-108">See also</span></span>

- [<span data-ttu-id="02de5-109">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="02de5-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="02de5-110">Delegati</span><span class="sxs-lookup"><span data-stu-id="02de5-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="02de5-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="02de5-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="02de5-112">Applicazioni multithread</span><span class="sxs-lookup"><span data-stu-id="02de5-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
