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
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Procedura: richiamare un metodo delegato (Visual Basic)

Questo esempio illustra come associare un metodo a un delegato e quindi richiamare il metodo tramite il delegato.

### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure di corrispondenza

1. Creare un delegato denominato `MySubDelegate` .

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

- [Istruzione Delegate](../../../language-reference/statements/delegate-statement.md)
- [Delegati](index.md)
- [Events](../events/index.md)
- [Applicazioni a thread multipli](../../../../standard/threading/using-threads-and-threading.md)
