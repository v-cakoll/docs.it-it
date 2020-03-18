---
title: Uso della varianza per i delegati generici Func e Action (C#)
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 17f55d594ad4364fd29c8f6e41bd6ad2445b0986
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169792"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a>Uso della varianza per i delegati generici Func e Action (C#)
In questi esempi viene illustrato come usare la covarianza e la controvarianza nei delegati generici `Func` e `Action` per consentire il riutilizzo dei metodi e offrire maggiore flessibilità nel codice.  
  
 Per altre informazioni sulla covarianza e la controvarianza, vedere [Varianza nei delegati (C#)](./variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Uso dei delegati con parametri di tipo covariante  
 L'esempio seguente illustra i vantaggi del supporto di covarianza nei delegati generici `Func`. Il metodo `FindByTitle` accetta un parametro di tipo `String` e restituisce un oggetto di tipo `Employee`. Tuttavia, è possibile assegnare questo metodo al delegato `Func<String, Person>` perché `Employee` eredita `Person`.  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Uso dei delegati con parametri di tipo controvariante  
 L'esempio seguente illustra i vantaggi del supporto di controvarianza nei delegati generici `Action`. Il metodo `AddToContacts` accetta un parametro di tipo `Person`. Tuttavia, è possibile assegnare questo metodo al delegato `Action<Employee>` perché `Employee` eredita `Person`.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Covarianza e controvarianza (C#)](./index.md)
- [Generics](../../../../standard/generics/index.md)
