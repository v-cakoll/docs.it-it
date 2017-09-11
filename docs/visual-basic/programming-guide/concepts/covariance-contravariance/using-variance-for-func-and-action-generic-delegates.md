---
title: Utilizzo della varianza per i delegati generici Func e Action (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b4dc4a162d3562b218a448653cb51473fff4165a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="183f0-102">Utilizzo della varianza per i delegati generici azione (Visual Basic) e Func</span><span class="sxs-lookup"><span data-stu-id="183f0-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>
<span data-ttu-id="183f0-103">In questi esempi viene illustrato come utilizzare la covarianza e controvarianza nel `Func` e `Action` delegati generici per consentire di riutilizzare i metodi e fornire una maggiore flessibilità nel codice.</span><span class="sxs-lookup"><span data-stu-id="183f0-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="183f0-104">Per ulteriori informazioni sulla covarianza e controvarianza, vedere [varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="183f0-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="183f0-105">Utilizzo di delegati con parametri di tipo covariante</span><span class="sxs-lookup"><span data-stu-id="183f0-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="183f0-106">L'esempio seguente illustra i vantaggi del supporto di covarianza nell'interfaccia generica `Func` delegati.</span><span class="sxs-lookup"><span data-stu-id="183f0-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="183f0-107">Il `FindByTitle` metodo accetta un parametro di `String` tipo e restituisce un oggetto del `Employee` tipo.</span><span class="sxs-lookup"><span data-stu-id="183f0-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="183f0-108">Tuttavia, è possibile assegnare questo metodo per la `Func(Of String, Person)` delegato perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="183f0-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="183f0-109">Utilizzo di delegati con parametri di tipo controvariante</span><span class="sxs-lookup"><span data-stu-id="183f0-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="183f0-110">L'esempio seguente illustra i vantaggi del supporto della controvarianza nell'interfaccia generica `Action` delegati.</span><span class="sxs-lookup"><span data-stu-id="183f0-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="183f0-111">Il `AddToContacts` metodo accetta un parametro di `Person` tipo.</span><span class="sxs-lookup"><span data-stu-id="183f0-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="183f0-112">Tuttavia, è possibile assegnare questo metodo per la `Action(Of Employee)` delegato perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="183f0-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="183f0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="183f0-113">See Also</span></span>  
 <span data-ttu-id="183f0-114">[Covarianza e controvarianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md) </span><span class="sxs-lookup"><span data-stu-id="183f0-114">[Covariance and Contravariance (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md) </span></span>  
<span data-ttu-id="183f0-115"> [Generics](https://msdn.microsoft.com/library/ms172192)</span><span class="sxs-lookup"><span data-stu-id="183f0-115"> [Generics](https://msdn.microsoft.com/library/ms172192)</span></span>
