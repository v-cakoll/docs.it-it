---
title: Sapere quando usare le parole chiave Override e New - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 0a209b9522202649765654013fdc3a468913c6b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714784"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="3930a-102">Sapere quando utilizzare le parole chiave Override e New (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3930a-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="3930a-103">Nel linguaggio C# un metodo in una classe derivata può avere lo stesso nome di un metodo in una classe di base.</span><span class="sxs-lookup"><span data-stu-id="3930a-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="3930a-104">È possibile specificare in che modo avviene l'interazione tra i metodi usando le parole chiave [new](../../language-reference/keywords/new-modifier.md) e [override](../../language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="3930a-104">You can specify how the methods interact by using the [new](../../language-reference/keywords/new-modifier.md) and [override](../../language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="3930a-105">Il modificatore `override`*estende* il metodo `virtual` della classe di base e il modificatore `new`*nasconde* il metodo della classe di base accessibile.</span><span class="sxs-lookup"><span data-stu-id="3930a-105">The `override` modifier *extends* the base class `virtual` method, and the `new` modifier *hides* an accessible base class method.</span></span> <span data-ttu-id="3930a-106">La differenza è illustrata negli esempi riportati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3930a-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="3930a-107">In un'applicazione console, dichiarare le due classi `BaseClass` e `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="3930a-108">`DerivedClass` eredita da `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 <span data-ttu-id="3930a-109">Nel metodo `Main` dichiarare le variabili `bc`, `dc` e `bcdc`.</span><span class="sxs-lookup"><span data-stu-id="3930a-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
- <span data-ttu-id="3930a-110">`bc`è di tipo `BaseClass` e il suo valore è di tipo `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
- <span data-ttu-id="3930a-111">`dc`è di tipo `DerivedClass` e il suo valore è di tipo `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
- <span data-ttu-id="3930a-112">`bcdc`è di tipo `BaseClass` e il suo valore è di tipo `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="3930a-113">Si tratta della variabile a cui prestare attenzione.</span><span class="sxs-lookup"><span data-stu-id="3930a-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="3930a-114">Poiché `bc` e `bcdc` sono di tipo `BaseClass`, possono solo accedere direttamente a `Method1`, a meno che non venga usato il cast.</span><span class="sxs-lookup"><span data-stu-id="3930a-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="3930a-115">Attraverso la variabile `dc` è possibile accedere sia a `Method1` che a `Method2`.</span><span class="sxs-lookup"><span data-stu-id="3930a-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="3930a-116">Queste relazioni sono illustrate nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3930a-116">These relationships are shown in the following code.</span></span>  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 <span data-ttu-id="3930a-117">Quindi aggiungere il metodo `Method2` seguente a `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="3930a-118">La firma di questo metodo corrisponde alla firma del metodo `Method2` in `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="3930a-119">Poiché `BaseClass` ha ora un metodo `Method2`, è possibile aggiungere una seconda istruzione di chiamata per le variabili di `BaseClass``bc` e `bcdc`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3930a-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="3930a-120">Quando si compila il progetto, l'aggiunta del metodo `Method2` in `BaseClass` genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="3930a-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="3930a-121">L'avviso indica che il metodo `Method2` in `DerivedClass` nasconde il metodo `Method2` in `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="3930a-122">Se si intende ottenere tale risultato, è consigliabile l'uso della parola chiave `new` nella definizione di `Method2`.</span><span class="sxs-lookup"><span data-stu-id="3930a-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="3930a-123">In alternativa, per risolvere il problema è possibile rinominare uno dei metodi `Method2`, ma ciò non è sempre pratico.</span><span class="sxs-lookup"><span data-stu-id="3930a-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="3930a-124">Prima di aggiungere `new`, eseguire il programma per verificare l'output prodotto da altre istruzioni di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3930a-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="3930a-125">Vengono visualizzati i risultati seguenti.</span><span class="sxs-lookup"><span data-stu-id="3930a-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="3930a-126">La parola chiave `new` mantiene le relazioni che producono l'output, ma elimina l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3930a-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="3930a-127">Le variabili di tipo `BaseClass` continuano ad accedere ai membri di `BaseClass`, mentre la variabile di tipo `DerivedClass` continua ad accedere prima ai membri in `DerivedClass` e in seguito prende in considerazione i membri ereditati da `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="3930a-128">Per eliminare l'avviso, aggiungere il modificatore `new` alla definizione di `Method2` in `DerivedClass`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3930a-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="3930a-129">Il modificatore può essere aggiunto prima o dopo l'oggetto `public`.</span><span class="sxs-lookup"><span data-stu-id="3930a-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="3930a-130">Eseguire nuovamente il programma per verificare che l'output non sia stato modificato.</span><span class="sxs-lookup"><span data-stu-id="3930a-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="3930a-131">Verificare anche che l'avviso non venga più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3930a-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="3930a-132">Usando `new` si afferma di essere informati che il membro di cui si sta eseguendo la modifica nasconde un membro ereditato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="3930a-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="3930a-133">Per altre informazioni su come viene nascosto un nome tramite ereditarietà, vedere [Modificatore new](../../language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="3930a-133">For more information about name hiding through inheritance, see [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="3930a-134">Per contrastare questo comportamento agli effetti dell'uso di `override`, aggiungere il metodo seguente a `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="3930a-135">Il modificatore `override` può essere aggiunto prima o dopo l'oggetto `public`.</span><span class="sxs-lookup"><span data-stu-id="3930a-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="3930a-136">Aggiungere il modificatore `virtual` alla definizione di `Method1` in `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="3930a-137">Il modificatore `virtual` può essere aggiunto prima o dopo l'oggetto `public`.</span><span class="sxs-lookup"><span data-stu-id="3930a-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="3930a-138">Eseguire di nuovo il progetto.</span><span class="sxs-lookup"><span data-stu-id="3930a-138">Run the project again.</span></span> <span data-ttu-id="3930a-139">Si notino soprattutto le ultime due linee dell'output riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3930a-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="3930a-140">L'uso del modificatore `override` consente a `bcdc` di accedere al metodo `Method1` definito in `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="3930a-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="3930a-141">In genere si tratta del comportamento previsto nelle gerarchie di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="3930a-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="3930a-142">Si vuole che gli oggetti dotati di valori creati dalla classe derivata usino i metodi definiti nella classe derivata stessa.</span><span class="sxs-lookup"><span data-stu-id="3930a-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="3930a-143">Si ottiene questo comportamento usando `override` per estendere il metodo della classe di base.</span><span class="sxs-lookup"><span data-stu-id="3930a-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="3930a-144">Il codice seguente contiene l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="3930a-144">The following code contains the full example.</span></span>  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending   
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="3930a-145">L'esempio riportato di seguito illustra un comportamento simile in un contesto diverso.</span><span class="sxs-lookup"><span data-stu-id="3930a-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="3930a-146">L'esempio definisce tre classi: una classe di base denominata `Car` e due classi derivate da essa, `ConvertibleCar` e `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="3930a-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="3930a-147">La classe di base contiene un metodo `DescribeCar`.</span><span class="sxs-lookup"><span data-stu-id="3930a-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="3930a-148">Il metodo visualizza una descrizione di base di un'automobile, quindi chiama l'oggetto `ShowDetails` per fornire informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3930a-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="3930a-149">Ognuna delle tre classi definisce un metodo `ShowDetails`.</span><span class="sxs-lookup"><span data-stu-id="3930a-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="3930a-150">Il modificatore `new` viene usato per definire `ShowDetails` nella classe `ConvertibleCar`.</span><span class="sxs-lookup"><span data-stu-id="3930a-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="3930a-151">Il modificatore `override` viene usato per definire `ShowDetails` nella classe `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="3930a-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 <span data-ttu-id="3930a-152">L'esempio verifica quale versione di `ShowDetails` viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="3930a-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="3930a-153">Il metodo seguente, `TestCars1`, dichiara un'istanza di ogni classe e quindi chiama `DescribeCar` per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="3930a-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.    
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 <span data-ttu-id="3930a-154">`TestCars1` produce l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="3930a-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="3930a-155">Si notino in particolare i risultati per `car2`, che probabilmente non sono quelli previsti.</span><span class="sxs-lookup"><span data-stu-id="3930a-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="3930a-156">Il tipo dell'oggetto è `ConvertibleCar`, ma `DescribeCar` non accede alla versione di `ShowDetails` definita nella classe `ConvertibleCar` perché tale metodo è dichiarato con il modificatore `new`, non con il modificatore `override`.</span><span class="sxs-lookup"><span data-stu-id="3930a-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="3930a-157">Di conseguenza, un oggetto `ConvertibleCar` visualizza la stessa descrizione di un oggetto `Car`.</span><span class="sxs-lookup"><span data-stu-id="3930a-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="3930a-158">Confrontare i risultati per `car3`, che è un oggetto `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="3930a-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="3930a-159">In questo caso, il metodo `ShowDetails` che viene dichiarato nella classe `Minivan`esegue l'override del metodo `ShowDetails` che viene dichiarato nella classe `Car` e la descrizione visualizzata descrive un furgoncino.</span><span class="sxs-lookup"><span data-stu-id="3930a-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="3930a-160">`TestCars2` determina la creazione di oggetti di tipo `Car`.</span><span class="sxs-lookup"><span data-stu-id="3930a-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="3930a-161">Le istanze dei valori degli oggetti vengono create dalle classi `Car`, `ConvertibleCar` e `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="3930a-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="3930a-162">`DescribeCar` viene chiamato per ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3930a-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="3930a-163">Il codice seguente illustra la definizione di `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="3930a-163">The following code shows the definition of `TestCars2`.</span></span>  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),   
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 <span data-ttu-id="3930a-164">Verrà visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="3930a-164">The following output is displayed.</span></span> <span data-ttu-id="3930a-165">Si noti che corrisponde all'output visualizzato da `TestCars1`.</span><span class="sxs-lookup"><span data-stu-id="3930a-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="3930a-166">Il metodo `ShowDetails` della classe `ConvertibleCar` non viene chiamato, indipendentemente dal fatto che il tipo di oggetto sia `ConvertibleCar`, come in `TestCars1` o `Car` come in `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="3930a-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="3930a-167">Al contrario, `car3` chiama il metodo `ShowDetails` della classe `Minivan` in entrambi i casi, sia se è di tipo `Minivan` che se è di tipo `Car`.</span><span class="sxs-lookup"><span data-stu-id="3930a-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="3930a-168">I metodi `TestCars3` e `TestCars4` completano l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3930a-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="3930a-169">Questi metodi chiamano direttamente `ShowDetails`, prima da oggetti dichiarati con tipo `ConvertibleCar` e `Minivan` (`TestCars3`) e quindi da oggetti dichiarati con tipo `Car` (`TestCars4`).</span><span class="sxs-lookup"><span data-stu-id="3930a-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="3930a-170">Il codice seguente definisce i due metodi.</span><span class="sxs-lookup"><span data-stu-id="3930a-170">The following code defines these two methods.</span></span>  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 <span data-ttu-id="3930a-171">I metodi producono l'output seguente, che corrisponde ai risultati del primo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3930a-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 <span data-ttu-id="3930a-172">Il codice seguente illustra l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="3930a-172">The following code shows the complete project and its output.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.    
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),   
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3930a-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3930a-173">See also</span></span>

- [<span data-ttu-id="3930a-174">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3930a-174">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3930a-175">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="3930a-175">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="3930a-176">Controllo delle versioni con le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="3930a-176">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="3930a-177">base</span><span class="sxs-lookup"><span data-stu-id="3930a-177">base</span></span>](../../language-reference/keywords/base.md)
- [<span data-ttu-id="3930a-178">abstract</span><span class="sxs-lookup"><span data-stu-id="3930a-178">abstract</span></span>](../../language-reference/keywords/abstract.md)
