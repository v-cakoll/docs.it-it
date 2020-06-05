---
title: Uso della varianza per i delegati generici Func e Action
ms.date: 07/20/2015
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
ms.openlocfilehash: f824d2422d67f1395d21a0863ca8c95d9f108989
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375758"
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="37400-102">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37400-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>

<span data-ttu-id="37400-103">In questi esempi viene illustrato come usare la covarianza e la controvarianza nei delegati generici `Func` e `Action` per consentire il riutilizzo dei metodi e offrire maggiore flessibilità nel codice.</span><span class="sxs-lookup"><span data-stu-id="37400-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>

<span data-ttu-id="37400-104">Per ulteriori informazioni sulla covarianza e la controvarianza, vedere [varianza nei delegati (Visual Basic)](variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="37400-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](variance-in-delegates.md).</span></span>

## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="37400-105">Uso dei delegati con parametri di tipo covariante</span><span class="sxs-lookup"><span data-stu-id="37400-105">Using Delegates with Covariant Type Parameters</span></span>

<span data-ttu-id="37400-106">L'esempio seguente illustra i vantaggi del supporto di covarianza nei delegati generici `Func`.</span><span class="sxs-lookup"><span data-stu-id="37400-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="37400-107">Il metodo `FindByTitle` accetta un parametro di tipo `String` e restituisce un oggetto di tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="37400-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="37400-108">Tuttavia, è possibile assegnare questo metodo al delegato `Func(Of String, Person)` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="37400-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class Finder
    Public Shared Function FindByTitle(
        ByVal title As String) As Employee
        ' This is a stub for a method that returns
        ' an employee that has the specified title.
        Return New Employee
    End Function

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim findEmployee As Func(Of String, Employee) =
            AddressOf FindByTitle

        ' The delegate expects a method to return Person,
        ' but you can assign it a method that returns Employee.
        Dim findPerson As Func(Of String, Person) =
            AddressOf FindByTitle

        ' You can also assign a delegate
        ' that returns a more derived type to a delegate
        ' that returns a less derived type.
        findPerson = findEmployee
    End Sub
End Class
```

## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="37400-109">Uso dei delegati con parametri di tipo controvariante</span><span class="sxs-lookup"><span data-stu-id="37400-109">Using Delegates with Contravariant Type Parameters</span></span>

<span data-ttu-id="37400-110">L'esempio seguente illustra i vantaggi del supporto di controvarianza nei delegati generici `Action`.</span><span class="sxs-lookup"><span data-stu-id="37400-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="37400-111">Il metodo `AddToContacts` accetta un parametro di tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="37400-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="37400-112">Tuttavia, è possibile assegnare questo metodo al delegato `Action(Of Employee)` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="37400-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>

```vb
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class AddressBook
    Shared Sub AddToContacts(ByVal person As Person)
        ' This method adds a Person object
        ' to a contact list.
    End Sub

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim addPersonToContacts As Action(Of Person) =
            AddressOf AddToContacts

        ' The Action delegate expects
        ' a method that has an Employee parameter,
        ' but you can assign it a method that has a Person parameter
        ' because Employee derives from Person.
        Dim addEmployeeToContacts As Action(Of Employee) =
            AddressOf AddToContacts

        ' You can also assign a delegate
        ' that accepts a less derived parameter
        ' to a delegate that accepts a more derived parameter.
        addEmployeeToContacts = addPersonToContacts
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="37400-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37400-113">See also</span></span>

- [<span data-ttu-id="37400-114">Covarianza e controvarianza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37400-114">Covariance and Contravariance (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="37400-115">Generics</span><span class="sxs-lookup"><span data-stu-id="37400-115">Generics</span></span>](../../../../standard/generics/index.md)
