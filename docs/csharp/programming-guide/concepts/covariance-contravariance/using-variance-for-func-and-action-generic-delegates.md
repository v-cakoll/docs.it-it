---
title: Uso della varianza per i delegati generici Func e Action (C#)
description: Informazioni sull'uso della covarianza e della controvarianza nei delegati generici Func e Action per offrire una maggiore flessibilità nel codice.
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: d7174b0f734d10ab69d0936cb5ca4aa2f4fafdf7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105715"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="0e13e-103">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="0e13e-103">Using Variance for Func and Action Generic Delegates (C#)</span></span>
<span data-ttu-id="0e13e-104">In questi esempi viene illustrato come usare la covarianza e la controvarianza nei delegati generici `Func` e `Action` per consentire il riutilizzo dei metodi e offrire maggiore flessibilità nel codice.</span><span class="sxs-lookup"><span data-stu-id="0e13e-104">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="0e13e-105">Per altre informazioni sulla covarianza e la controvarianza, vedere [Varianza nei delegati (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0e13e-105">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="0e13e-106">Uso dei delegati con parametri di tipo covariante</span><span class="sxs-lookup"><span data-stu-id="0e13e-106">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="0e13e-107">L'esempio seguente illustra i vantaggi del supporto di covarianza nei delegati generici `Func`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-107">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="0e13e-108">Il metodo `FindByTitle` accetta un parametro di tipo `String` e restituisce un oggetto di tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-108">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="0e13e-109">Tuttavia, è possibile assegnare questo metodo al delegato `Func<String, Person>` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-109">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="0e13e-110">Uso dei delegati con parametri di tipo controvariante</span><span class="sxs-lookup"><span data-stu-id="0e13e-110">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="0e13e-111">L'esempio seguente illustra i vantaggi del supporto di controvarianza nei delegati generici `Action`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-111">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="0e13e-112">Il metodo `AddToContacts` accetta un parametro di tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-112">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="0e13e-113">Tuttavia, è possibile assegnare questo metodo al delegato `Action<Employee>` perché `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="0e13e-113">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e13e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e13e-114">See also</span></span>

- [<span data-ttu-id="0e13e-115">Covarianza e controvarianza (C#)</span><span class="sxs-lookup"><span data-stu-id="0e13e-115">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="0e13e-116">Generics</span><span class="sxs-lookup"><span data-stu-id="0e13e-116">Generics</span></span>](../../../../standard/generics/index.md)
