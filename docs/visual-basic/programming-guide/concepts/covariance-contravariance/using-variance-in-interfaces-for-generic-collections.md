---
title: Utilizzo della varianza nelle interfacce per le raccolte generiche (Visual Basic) | Documenti di Microsoft
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
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="5717f-102">Utilizzo della varianza nelle interfacce per le raccolte generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5717f-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>
<span data-ttu-id="5717f-103">Un'interfaccia covariante consente ai metodi restituire più tipi derivati da quelle specificate nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5717f-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="5717f-104">Un'interfaccia controvariante consente ai metodi di accettare parametri di tipi meno derivati di quelli specificati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5717f-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="5717f-105">In .NET Framework 4, diverse interfacce esistenti diventano covarianti e controvarianti.</span><span class="sxs-lookup"><span data-stu-id="5717f-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="5717f-106">Sono inclusi <xref:System.Collections.Generic.IEnumerable%601>e <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5717f-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="5717f-107">In questo modo è possibile riutilizzare i metodi che operano con raccolte generiche di tipi di base per le raccolte di tipi derivati.</span><span class="sxs-lookup"><span data-stu-id="5717f-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="5717f-108">Per un elenco di interfacce variant in .NET Framework, vedere [varianza nelle interfacce generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="5717f-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="5717f-109">Conversione di raccolte generiche</span><span class="sxs-lookup"><span data-stu-id="5717f-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="5717f-110">L'esempio seguente illustra i vantaggi del supporto di covarianza nel <xref:System.Collections.Generic.IEnumerable%601>interfaccia.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5717f-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="5717f-111">Il `PrintFullName` metodo accetta una raccolta del `IEnumerable(Of Person)` tipo come parametro.</span><span class="sxs-lookup"><span data-stu-id="5717f-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="5717f-112">Tuttavia, è possibile riutilizzarlo per una raccolta di `IEnumerable(Of Person)` tipo perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="5717f-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>  
  
<span data-ttu-id="5717f-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5717f-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="comparing-generic-collections"></a><span data-ttu-id="5717f-114">Confronto di raccolte generiche</span><span class="sxs-lookup"><span data-stu-id="5717f-114">Comparing Generic Collections</span></span>  
 <span data-ttu-id="5717f-115">L'esempio seguente illustra i vantaggi del supporto della controvarianza nella <xref:System.Collections.Generic.IComparer%601>interfaccia.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="5717f-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="5717f-116">La classe `PersonComparer` implementa l'interfaccia `IComparer(Of Person)`.</span><span class="sxs-lookup"><span data-stu-id="5717f-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="5717f-117">Tuttavia, è possibile riutilizzare questa classe per una sequenza di oggetti di confrontare il `Employee` tipo perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="5717f-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```vb  
' Simple hierarhcy of classes.  
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
  
## <a name="see-also"></a><span data-ttu-id="5717f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5717f-118">See Also</span></span>  
 [<span data-ttu-id="5717f-119">Varianza nelle interfacce generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5717f-119">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
