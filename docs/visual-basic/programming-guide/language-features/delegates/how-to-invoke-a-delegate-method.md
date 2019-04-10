---
title: 'Procedura: Richiamare un metodo delegato (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: ac3e32010e7c20ba76e39915d694b11ab3a65d40
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319612"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Procedura: Richiamare un metodo delegato (Visual Basic)
In questo esempio viene illustrato come associare un metodo con un delegato e quindi richiamare tale metodo tramite il delegato.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure corrispondente  
  
1. Creare un delegato denominato `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2. Dichiarare una classe che contiene un metodo con la stessa firma del delegato.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3. Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando predefiniti `Invoke` (metodo).  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Applicazioni multithread](../../../../standard/threading/using-threads-and-threading.md)
