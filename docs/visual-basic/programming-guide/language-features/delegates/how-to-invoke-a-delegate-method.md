---
title: 'Procedura: richiamare un metodo delegato'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: f319727c007b93c7b334af0598f1b9f7c034144d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410721"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="cf8b9-102">Procedura: richiamare un metodo delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf8b9-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="cf8b9-103">Questo esempio illustra come associare un metodo a un delegato e quindi richiamare il metodo tramite il delegato.</span><span class="sxs-lookup"><span data-stu-id="cf8b9-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="cf8b9-104">Creare il delegato e le procedure di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="cf8b9-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="cf8b9-105">Creare un delegato denominato `MySubDelegate` .</span><span class="sxs-lookup"><span data-stu-id="cf8b9-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="cf8b9-106">Dichiarare una classe che contiene un metodo con la stessa firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="cf8b9-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="cf8b9-107">Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando il `Invoke` metodo incorporato.</span><span class="sxs-lookup"><span data-stu-id="cf8b9-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="cf8b9-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf8b9-108">See also</span></span>

- [<span data-ttu-id="cf8b9-109">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="cf8b9-109">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="cf8b9-110">Delegati</span><span class="sxs-lookup"><span data-stu-id="cf8b9-110">Delegates</span></span>](index.md)
- [<span data-ttu-id="cf8b9-111">Events</span><span class="sxs-lookup"><span data-stu-id="cf8b9-111">Events</span></span>](../events/index.md)
- [<span data-ttu-id="cf8b9-112">Applicazioni a thread multipli</span><span class="sxs-lookup"><span data-stu-id="cf8b9-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
