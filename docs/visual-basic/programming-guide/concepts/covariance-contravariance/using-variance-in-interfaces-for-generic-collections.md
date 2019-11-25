---
title: Utilizzo della varianza nelle interfacce per le raccolte generiche
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 6ee133dfd61d7d7a88243ca592642ff21e0c2223
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349015"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Using Variance in Interfaces for Generic Collections (Visual Basic)

Un'interfaccia covariante consente ai propri metodi di restituire più tipi derivati rispetto a quelli specificati nell'interfaccia. Un'interfaccia controvariante consente ai propri metodi di accettare parametri di meno tipi derivati rispetto a quelli specificati nell'interfaccia.

In .NET Framework 4 diverse interfacce già esistenti sono diventate covarianti e controvarianti. Tra queste sono inclusi i tipi  <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601>. In questo modo è possibile riutilizzare i metodi che funzionano con raccolte generiche di tipi di base per le raccolte di tipi derivati.

For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).

## <a name="converting-generic-collections"></a>Convertire le raccolte generiche

L'esempio seguente illustra i vantaggi del supporto di covarianza nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>. Il metodo `PrintFullName` accetta una raccolta del tipo `IEnumerable(Of Person)` come parametro. Tuttavia, è possibile riutilizzarlo per una raccolta del tipo `IEnumerable(Of Person)` perché `Employee` eredita `Person`.

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a>Confrontare le raccolte generiche

L'esempio seguente illustra i vantaggi del supporto di controvarianza nell'interfaccia <xref:System.Collections.Generic.IComparer%601>. La classe `PersonComparer` implementa l'interfaccia `IComparer(Of Person)`. Tuttavia, è possibile riutilizzare questa classe per confrontare una sequenza di oggetti del tipo `Employee` perché `Employee` eredita `Person`.

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class
' The custom comparer for the Person type
' with standard implementations of Equals()
' and GetHashCode() methods.
Class PersonComparer
    Implements IEqualityComparer(Of Person)

    Public Function Equals1(
        ByVal x As Person,
        ByVal y As Person) As Boolean _
        Implements IEqualityComparer(Of Person).Equals

        If x Is y Then Return True
        If x Is Nothing OrElse y Is Nothing Then Return False
        Return (x.FirstName = y.FirstName) AndAlso
            (x.LastName = y.LastName)
    End Function
    Public Function GetHashCode1(
        ByVal person As Person) As Integer _
        Implements IEqualityComparer(Of Person).GetHashCode

        If person Is Nothing Then Return 0
        Dim hashFirstName =
            If(person.FirstName Is Nothing,
            0, person.FirstName.GetHashCode())
        Dim hashLastName = person.LastName.GetHashCode()
        Return hashFirstName Xor hashLastName
    End Function
End Class

Sub Main()
    Dim employees = New List(Of Employee) From {
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}
    }

    ' You can pass PersonComparer,
    ' which implements IEqualityComparer(Of Person),
    ' although the method expects IEqualityComparer(Of Employee)

    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())

    For Each employee In noduplicates
        Console.WriteLine(employee.FirstName & " " & employee.LastName)
    Next
End Sub
```

## <a name="see-also"></a>Vedere anche

- [Varianza nelle interfacce generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
