---
title: 'Procedura: Richiamare un metodo delegato (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c2bdb65c9d060e854db3319e4aa5b2e93b9681af
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629585"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Procedura: Richiamare un metodo delegato (Visual Basic)

Questo esempio illustra come associare un metodo a un delegato e quindi richiamare il metodo tramite il delegato.

### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure di corrispondenza

1. Creare un delegato denominato `MySubDelegate`.

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. Dichiarare una classe che contiene un metodo con la stessa firma del delegato.

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. Definire un metodo che crea un'istanza del delegato e richiama il metodo associato al delegato chiamando il `Invoke` metodo incorporato.

    ```vb
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
