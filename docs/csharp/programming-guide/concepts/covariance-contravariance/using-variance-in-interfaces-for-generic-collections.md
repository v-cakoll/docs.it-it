---
title: Uso della varianza nelle interfacce per le raccolte generiche (C#)
description: Informazioni su come usare le interfacce covariante e controvariante per le raccolte generiche. Vedere esempi di conversione e confronto di raccolte generiche.
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: c2ce849e32520cb91422ff36173e418a010476bd
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105665"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="51a80-104">Uso della varianza nelle interfacce per le raccolte generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="51a80-104">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="51a80-105">Un'interfaccia covariante consente ai propri metodi di restituire più tipi derivati rispetto a quelli specificati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="51a80-105">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="51a80-106">Un'interfaccia controvariante consente ai propri metodi di accettare parametri di meno tipi derivati rispetto a quelli specificati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="51a80-106">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="51a80-107">In .NET Framework 4 diverse interfacce già esistenti sono diventate covarianti e controvarianti.</span><span class="sxs-lookup"><span data-stu-id="51a80-107">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="51a80-108">Tra queste sono inclusi i tipi  <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="51a80-108">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="51a80-109">In questo modo è possibile riutilizzare i metodi che funzionano con raccolte generiche di tipi di base per le raccolte di tipi derivati.</span><span class="sxs-lookup"><span data-stu-id="51a80-109">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="51a80-110">Per un elenco di interfacce variant in .NET, vedere [varianza nelle interfacce generiche (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="51a80-110">For a list of variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="51a80-111">Convertire le raccolte generiche</span><span class="sxs-lookup"><span data-stu-id="51a80-111">Converting Generic Collections</span></span>  
 <span data-ttu-id="51a80-112">L'esempio seguente illustra i vantaggi del supporto di covarianza nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="51a80-112">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="51a80-113">Il metodo `PrintFullName` accetta una raccolta del tipo `IEnumerable<Person>` come parametro.</span><span class="sxs-lookup"><span data-stu-id="51a80-113">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="51a80-114">Tuttavia, è possibile riutilizzarlo per una raccolta del tipo `IEnumerable<Employee>` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="51a80-114">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="51a80-115">Confrontare le raccolte generiche</span><span class="sxs-lookup"><span data-stu-id="51a80-115">Comparing Generic Collections</span></span>  
 <span data-ttu-id="51a80-116">L'esempio seguente illustra i vantaggi del supporto di controvarianza nell'interfaccia <xref:System.Collections.Generic.IComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="51a80-116">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="51a80-117">La classe `PersonComparer` implementa l'interfaccia `IComparer<Person>`.</span><span class="sxs-lookup"><span data-stu-id="51a80-117">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="51a80-118">Tuttavia, è possibile riutilizzare questa classe per confrontare una sequenza di oggetti del tipo `Employee` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="51a80-118">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="51a80-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51a80-119">See also</span></span>

- [<span data-ttu-id="51a80-120">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="51a80-120">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
