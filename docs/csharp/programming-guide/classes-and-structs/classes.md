---
title: Classi - Guida per programmatori C#
description: Informazioni sui tipi di classe e su come crearli
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: d726ab3a882d2e6913fa69c7b82f1d6db78dd47d
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102047"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="1b431-103">Classi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1b431-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="1b431-104">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="1b431-104">Reference types</span></span>  
<span data-ttu-id="1b431-105">Un tipo definito come [classe](../../language-reference/keywords/class.md) è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="1b431-105">A type that is defined as a [class](../../language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="1b431-106">In fase di esecuzione, quando si dichiara una variabile di un tipo riferimento, la variabile contiene il valore [Null](../../language-reference/keywords/null.md) fino a quando non si crea in modo esplicito un'istanza della classe usando l'operatore [new](../../language-reference/operators/new-operator.md) o fino a quando non le viene assegnato un oggetto di un tipo compatibile creato altrove, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1b431-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../language-reference/operators/new-operator.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="1b431-107">Quando viene creato l'oggetto, una quantità di memoria sufficiente viene allocata nell'heap gestito per l'oggetto specifico e la variabile mantiene solo un riferimento al percorso dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b431-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="1b431-108">I tipi nell'heap gestito richiedono un overhead quando vengono allocati e recuperati dalla funzionalità di gestione automatica della memoria di CLR, nota come *Garbage Collection*.</span><span class="sxs-lookup"><span data-stu-id="1b431-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="1b431-109">La Garbage Collection, tuttavia, è anche altamente ottimizzata e, nella maggior parte degli scenari, non genera un problema di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1b431-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="1b431-110">Per altre informazioni sulla Garbage Collection, vedere [Gestione automatica della memoria e Garbage Collection](../../../standard/garbage-collection/fundamentals.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/fundamentals.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="1b431-111">Dichiarazione di classi</span><span class="sxs-lookup"><span data-stu-id="1b431-111">Declaring Classes</span></span>

 <span data-ttu-id="1b431-112">Le classi vengono dichiarate usando la parola chiave [class](../../language-reference/keywords/class.md) seguita da un identificatore univoco, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1b431-112">Classes are declared by using the [class](../../language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="1b431-113">La parola chiave `class` è preceduta dal livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="1b431-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="1b431-114">Poiché in questo caso viene usata la parola chiave [public](../../language-reference/keywords/public.md), chiunque può creare istanze di questa classe.</span><span class="sxs-lookup"><span data-stu-id="1b431-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="1b431-115">Il nome della classe segue la parola chiave `class`.</span><span class="sxs-lookup"><span data-stu-id="1b431-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="1b431-116">Il nome della classe deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.</span><span class="sxs-lookup"><span data-stu-id="1b431-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="1b431-117">Il resto della definizione è il corpo della classe, in cui vengono definiti il comportamento e i dati.</span><span class="sxs-lookup"><span data-stu-id="1b431-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="1b431-118">I campi, le proprietà, i metodi e gli eventi in una classe vengono collettivamente definiti *membri della classe*.</span><span class="sxs-lookup"><span data-stu-id="1b431-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="1b431-119">Creazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="1b431-119">Creating objects</span></span>

<span data-ttu-id="1b431-120">Anche se vengono talvolta usati in modo intercambiabile, una classe e un oggetto sono elementi diversi.</span><span class="sxs-lookup"><span data-stu-id="1b431-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="1b431-121">Una classe definisce un tipo di oggetto, ma non è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b431-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="1b431-122">Un oggetto è un'entità concreta ed è basato su una classe. Talvolta si fa riferimento all'oggetto come istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="1b431-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="1b431-123">Gli oggetti possono essere creati tramite la parola chiave [new](../../language-reference/operators/new-operator.md) seguita dal nome della classe su cui si baserà l'oggetto, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b431-123">Objects can be created by using the [new](../../language-reference/operators/new-operator.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="1b431-124">Quando viene creata un'istanza di una classe, viene passato al programmatore un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b431-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="1b431-125">Nell'esempio precedente, `object1` è un riferimento a un oggetto basato su `Customer`.</span><span class="sxs-lookup"><span data-stu-id="1b431-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="1b431-126">Questo riferimento indica il nuovo oggetto, ma non contiene i dati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b431-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="1b431-127">Infatti, è possibile creare un riferimento all'oggetto senza creare un oggetto:</span><span class="sxs-lookup"><span data-stu-id="1b431-127">In fact, you can create an object reference without creating an object at all:</span></span>  

```csharp
 Customer object2;
```

 <span data-ttu-id="1b431-128">Non è consigliabile creare riferimenti a oggetti come questo che non fanno riferimento a un oggetto reale perché il tentativo di accedere a un oggetto tramite tale riferimento avrà esito negativo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1b431-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="1b431-129">Tuttavia, tale riferimento può essere creato per fare riferimento a un oggetto, creando un nuovo oggetto oppure assegnandolo a un oggetto esistente, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1b431-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="1b431-130">Questo codice crea due riferimenti a oggetti che fanno entrambi riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b431-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="1b431-131">Tutte le modifiche effettuate all'oggetto tramite `object3` si riflettono tuttavia nei successivi usi di `object4`.</span><span class="sxs-lookup"><span data-stu-id="1b431-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="1b431-132">Poiché gli oggetti che si basano su classi vengono indicati tramite riferimenti, le classi sono note come tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1b431-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="1b431-133">Ereditarietà delle classi</span><span class="sxs-lookup"><span data-stu-id="1b431-133">Class inheritance</span></span>  

<span data-ttu-id="1b431-134">Le classi supportano completamente l'*ereditarietà*, una caratteristica fondamentale nella programmazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="1b431-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="1b431-135">Quando si crea una classe, è possibile ereditare da qualsiasi altra interfaccia o classe non definita come [sealed](../../language-reference/keywords/sealed.md) e le altre classi possono ereditare dalla classe appena creata ed eseguire l'override dei metodi virtuali della classe.</span><span class="sxs-lookup"><span data-stu-id="1b431-135">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

<span data-ttu-id="1b431-136">L'ereditarietà si ottiene usando una *derivazione*, vale a dire che una classe viene dichiarata usando una *classe di base* da cui eredita dati e comportamento.</span><span class="sxs-lookup"><span data-stu-id="1b431-136">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="1b431-137">Una classe di base viene specificata tramite l'aggiunta di due punti e il nome della classe di base dopo il nome della classe derivata, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b431-137">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="1b431-138">Quando una classe dichiara una classe di base, eredita tutti i membri della classe di base, a eccezione dei costruttori.</span><span class="sxs-lookup"><span data-stu-id="1b431-138">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="1b431-139">Per altre informazioni, vedere [Ereditarietà](inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-139">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="1b431-140">Diversamente da C++, una classe di C# può ereditare direttamente solo da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="1b431-140">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="1b431-141">Tuttavia, poiché una classe di base può ereditare da un'altra classe, una classe può ereditare indirettamente più classi di base.</span><span class="sxs-lookup"><span data-stu-id="1b431-141">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="1b431-142">Una classe può anche implementare direttamente più di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1b431-142">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="1b431-143">Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-143">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="1b431-144">Una classe può essere dichiarata come [astratta](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-144">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="1b431-145">Una classe astratta contiene metodi astratti che hanno una definizione di firma, ma senza implementazione.</span><span class="sxs-lookup"><span data-stu-id="1b431-145">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="1b431-146">Non è possibile creare un'istanza di classi astratte.</span><span class="sxs-lookup"><span data-stu-id="1b431-146">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="1b431-147">Le classi astratte possono essere usate solo tramite classi derivate che implementano i metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="1b431-147">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="1b431-148">Al contrario, una classe [sealed](../../language-reference/keywords/sealed.md) non consente ad altre classi di derivare da tale classe.</span><span class="sxs-lookup"><span data-stu-id="1b431-148">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="1b431-149">Per altre informazioni, vedere [classi e membri delle classi astratte e sealed](abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-149">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="1b431-150">Le definizioni di classe possono essere suddivise tra file di origine diversa.</span><span class="sxs-lookup"><span data-stu-id="1b431-150">Class definitions can be split between different source files.</span></span> <span data-ttu-id="1b431-151">Per altre informazioni, vedere [Classi e metodi parziali](partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-151">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b431-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b431-152">Example</span></span>

<span data-ttu-id="1b431-153">L'esempio seguente definisce una classe pubblica che contiene una [proprietà implementata automaticamente](auto-implemented-properties.md), un metodo e un metodo speciale denominato costruttore.</span><span class="sxs-lookup"><span data-stu-id="1b431-153">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="1b431-154">Per altre informazioni, vedere gli argomenti [Proprietà](properties.md), [Metodi](methods.md) e [Costruttori](constructors.md).</span><span class="sxs-lookup"><span data-stu-id="1b431-154">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="1b431-155">Le istanze della classe vengono quindi create con la parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="1b431-155">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="1b431-156">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1b431-156">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b431-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b431-157">See also</span></span>

- [<span data-ttu-id="1b431-158">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1b431-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1b431-159">Programmazione orientata ad oggetti</span><span class="sxs-lookup"><span data-stu-id="1b431-159">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)
- [<span data-ttu-id="1b431-160">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="1b431-160">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="1b431-161">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="1b431-161">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="1b431-162">Membri</span><span class="sxs-lookup"><span data-stu-id="1b431-162">Members</span></span>](members.md)
- [<span data-ttu-id="1b431-163">Metodi</span><span class="sxs-lookup"><span data-stu-id="1b431-163">Methods</span></span>](methods.md)
- [<span data-ttu-id="1b431-164">Costruttori</span><span class="sxs-lookup"><span data-stu-id="1b431-164">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="1b431-165">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="1b431-165">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="1b431-166">Oggetti</span><span class="sxs-lookup"><span data-stu-id="1b431-166">Objects</span></span>](objects.md)
