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
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Procedura: richiamare un metodo delegato (Visual Basic)
In questo esempio viene illustrato come associare un delegato di un metodo e quindi richiamare il metodo tramite il delegato.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure corrispondenti  
  
1.  Crea un delegato denominato `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Dichiarare una classe che contiene un metodo con la stessa firma del delegato.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando predefinito `Invoke` metodo.  
  
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
 [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Applicazioni multithread](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
