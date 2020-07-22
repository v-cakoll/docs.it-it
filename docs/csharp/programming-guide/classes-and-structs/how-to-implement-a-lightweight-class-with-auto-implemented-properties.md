---
title: Come implementare una classe Lightweight con proprietà implementate automaticamente (Guida per programmatori C#)
description: Informazioni su come creare una classe leggera non modificabile in C# che incapsula le proprietà implementate automaticamente. Esistono due approcci di implementazione.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: de9034772bad1f28e27abe01595309dd84ddc3e7
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864566"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="906bb-104">Come implementare una classe Lightweight con proprietà implementate automaticamente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="906bb-104">How to implement a lightweight class with auto-implemented properties (C# Programming Guide)</span></span>

<span data-ttu-id="906bb-105">Questo esempio mostra come creare una classe leggera non modificabile che serve solo a incapsulare un set di proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="906bb-105">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="906bb-106">Usare questo genere di costrutto invece di una struct quando è necessario usare la semantica del tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="906bb-106">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="906bb-107">È possibile creare una proprietà non modificabile in due modi:</span><span class="sxs-lookup"><span data-stu-id="906bb-107">You can make an immutable property in two ways:</span></span>

- <span data-ttu-id="906bb-108">È possibile dichiarare la funzione di accesso [set](../../language-reference/keywords/set.md) come [privata](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="906bb-108">You can declare the [set](../../language-reference/keywords/set.md) accessor to be [private](../../language-reference/keywords/private.md).</span></span>  <span data-ttu-id="906bb-109">La proprietà è impostabile solo all'interno del tipo è, ma non è modificabile per i consumer.</span><span class="sxs-lookup"><span data-stu-id="906bb-109">The property is only settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="906bb-110">Quando si dichiara una funzione di accesso `set` privata, non è possibile usare un inizializzatore di oggetto per inizializzare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="906bb-110">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="906bb-111">È necessario usare un costruttore o un metodo factory.</span><span class="sxs-lookup"><span data-stu-id="906bb-111">You must use a constructor or a factory method.</span></span>
- <span data-ttu-id="906bb-112">È possibile dichiarare solo la funzione di accesso [Get](../../language-reference/keywords/get.md) , che rende la proprietà non modificabile ovunque tranne che nel costruttore del tipo.</span><span class="sxs-lookup"><span data-stu-id="906bb-112">You can declare only the [get](../../language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type's constructor.</span></span>

<span data-ttu-id="906bb-113">Nell'esempio seguente viene illustrato il modo in cui una proprietà con solo la funzione di accesso get è diversa da una con Get e private set.</span><span class="sxs-lookup"><span data-stu-id="906bb-113">The following example shows how a property with only get accessor differs than one with get and private set.</span></span>

```csharp
class Contact
{
    public string Name { get; }
    public string Address { get; private set; }

    public Contact(string contactName, string contactAddress)
    {
        // Both properties are accessible in the constructor.
        Name = contactName;
        Address = contactAddress;
    }

    // Name isn't assignable here. This will generate a compile error.
    //public void ChangeName(string newName) => Name = newName;

    // Address is assignable here.
    public void ChangeAddress(string newAddress) => Address = newAddress
}
```

## <a name="example"></a><span data-ttu-id="906bb-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="906bb-114">Example</span></span>

<span data-ttu-id="906bb-115">Il seguente esempio mostra due modi per implementare una classe non modificabile con proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="906bb-115">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="906bb-116">Ogni modo dichiara una delle proprietà con una funzione di accesso `set` privata e una delle proprietà solo con `get`.</span><span class="sxs-lookup"><span data-stu-id="906bb-116">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="906bb-117">La prima classe usa un costruttore solo per inizializzare le proprietà e la seconda classe usa un metodo factory statico che chiama un costruttore.</span><span class="sxs-lookup"><span data-stu-id="906bb-117">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only property.
    public string Name { get; }

    // Read-write property with a private set accessor.
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-write property with a private set accessor.
    public string Name { get; private set; }

    // Read-only property.
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

<span data-ttu-id="906bb-118">Il compilatore crea campi sottostanti per ogni proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="906bb-118">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="906bb-119">I campi non sono accessibili direttamente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="906bb-119">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="906bb-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="906bb-120">See also</span></span>

- [<span data-ttu-id="906bb-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="906bb-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="906bb-122">struct</span><span class="sxs-lookup"><span data-stu-id="906bb-122">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="906bb-123">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="906bb-123">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
