---
title: Programmazione orientata a oggetti (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 1de150f6eb4be893ca1afce6bd16afde5752c986
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711826"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="fc178-102">Programmazione orientata a oggetti (C#)</span><span class="sxs-lookup"><span data-stu-id="fc178-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="fc178-103">C# offre un supporto completo per la programmazione orientata a oggetti che include incapsulamento, ereditarietà e polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="fc178-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="fc178-104">L'*incapsulamento* indica che un gruppo di proprietà, metodi e altri membri correlati vengono considerati come una singola unità o un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="fc178-105">L'*ereditarietà* indica la capacità di creare nuove classi sulla base di una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="fc178-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="fc178-106">Il *polimorfismo* indica la capacità di usare più classi in modo intercambiabile, anche se in ognuna di esse le stesse proprietà o gli stessi metodi sono implementati in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="fc178-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="fc178-107">In questa sezione vengono descritti i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc178-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="fc178-108">Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="fc178-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="fc178-109">Membri di classi</span><span class="sxs-lookup"><span data-stu-id="fc178-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="fc178-110">Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="fc178-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="fc178-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="fc178-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="fc178-112">Costruttori</span><span class="sxs-lookup"><span data-stu-id="fc178-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="fc178-113">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="fc178-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="fc178-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="fc178-114">Events</span></span>](#Events)

    - [<span data-ttu-id="fc178-115">Classi annidate</span><span class="sxs-lookup"><span data-stu-id="fc178-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="fc178-116">Modificatori di accesso e livelli di accesso</span><span class="sxs-lookup"><span data-stu-id="fc178-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="fc178-117">Creazione di istanze di classi</span><span class="sxs-lookup"><span data-stu-id="fc178-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="fc178-118">Classi e membri statici</span><span class="sxs-lookup"><span data-stu-id="fc178-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="fc178-119">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="fc178-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="fc178-120">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="fc178-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="fc178-121">Override di membri</span><span class="sxs-lookup"><span data-stu-id="fc178-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="fc178-122">Interfacce</span><span class="sxs-lookup"><span data-stu-id="fc178-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="fc178-123">Generics</span><span class="sxs-lookup"><span data-stu-id="fc178-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="fc178-124">Delegati</span><span class="sxs-lookup"><span data-stu-id="fc178-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="fc178-125">Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="fc178-125">Classes and Objects</span></span>

<span data-ttu-id="fc178-126">I termini *classe* e *oggetto* vengono talvolta usati in modo intercambiabile. Di fatto, però, le classi descrivono il *tipo* degli oggetti, mentre gli oggetti sono *istanze* utilizzabili delle classi.</span><span class="sxs-lookup"><span data-stu-id="fc178-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="fc178-127">L'atto di creare un oggetto viene pertanto chiamato *creazione di istanze*.</span><span class="sxs-lookup"><span data-stu-id="fc178-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="fc178-128">Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="fc178-129">Per definire una classe:</span><span class="sxs-lookup"><span data-stu-id="fc178-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="fc178-130">C# offre anche classi in versione ridotta chiamate *strutture* utili quando è necessario creare una matrice di grandi dimensioni di oggetti e non si vuole usare a tale scopo una quantità eccessiva di memoria.</span><span class="sxs-lookup"><span data-stu-id="fc178-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="fc178-131">Per definire una struttura:</span><span class="sxs-lookup"><span data-stu-id="fc178-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="fc178-132">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-132">For more information, see:</span></span>

- [<span data-ttu-id="fc178-133">class</span><span class="sxs-lookup"><span data-stu-id="fc178-133">class</span></span>](../../language-reference/keywords/class.md)

- [<span data-ttu-id="fc178-134">struct</span><span class="sxs-lookup"><span data-stu-id="fc178-134">struct</span></span>](../../language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="fc178-135">Membri di classi</span><span class="sxs-lookup"><span data-stu-id="fc178-135">Class Members</span></span>

<span data-ttu-id="fc178-136">Ogni classe può avere *membri di classe* diversi che includono proprietà che descrivono i dati della classe, i metodi che definiscono il comportamento della classe e gli eventi che offrono la comunicazione tra classi e oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="fc178-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="fc178-137">Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="fc178-137">Properties and Fields</span></span>

<span data-ttu-id="fc178-138">I campi e le proprietà rappresentano le informazioni contenute in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="fc178-139">I campi sono simili a variabili in quanto possono essere letti o impostati direttamente.</span><span class="sxs-lookup"><span data-stu-id="fc178-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="fc178-140">Per definire un campo:</span><span class="sxs-lookup"><span data-stu-id="fc178-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="fc178-141">Le proprietà dispongono di routine Get e Set, che forniscono un maggiore controllo sul modo in cui i valori vengono impostati o restituiti.</span><span class="sxs-lookup"><span data-stu-id="fc178-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="fc178-142">C# consente di creare un campo privato per archiviare il valore della proprietà o di usare le cosiddette proprietà implementate automaticamente che creano automaticamente questo campo e offrono la logica di base per le routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fc178-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="fc178-143">Per definire una proprietà implementata automaticamente:</span><span class="sxs-lookup"><span data-stu-id="fc178-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="fc178-144">Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:</span><span class="sxs-lookup"><span data-stu-id="fc178-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="fc178-145">La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fc178-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="fc178-146">È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura.</span><span class="sxs-lookup"><span data-stu-id="fc178-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="fc178-147">In C#, è possibile omettere il metodo della proprietà `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="fc178-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="fc178-148">Tuttavia, le proprietà implementate automaticamente non possono essere di sola lettura o di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="fc178-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="fc178-149">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-149">For more information, see:</span></span>

- [<span data-ttu-id="fc178-150">get</span><span class="sxs-lookup"><span data-stu-id="fc178-150">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="fc178-151">set</span><span class="sxs-lookup"><span data-stu-id="fc178-151">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="fc178-152">Metodi</span><span class="sxs-lookup"><span data-stu-id="fc178-152">Methods</span></span>

<span data-ttu-id="fc178-153">Un *metodo* è un'azione che può essere eseguita da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="fc178-154">Per definire un metodo di una classe:</span><span class="sxs-lookup"><span data-stu-id="fc178-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="fc178-155">Una classe può disporre di diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o per i tipi di parametro.</span><span class="sxs-lookup"><span data-stu-id="fc178-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="fc178-156">Per essere in rapporto di overload con un metodo:</span><span class="sxs-lookup"><span data-stu-id="fc178-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="fc178-157">Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="fc178-158">C#, tuttavia, supporta anche i *metodi di estensione* che consentono di aggiungere metodi a una classe esistente al di fuori della definizione effettiva della classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="fc178-159">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-159">For more information, see:</span></span>

- [<span data-ttu-id="fc178-160">Metodi</span><span class="sxs-lookup"><span data-stu-id="fc178-160">Methods</span></span>](../classes-and-structs/methods.md)

- [<span data-ttu-id="fc178-161">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="fc178-161">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="fc178-162">Costruttori</span><span class="sxs-lookup"><span data-stu-id="fc178-162">Constructors</span></span>

<span data-ttu-id="fc178-163">I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="fc178-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="fc178-164">I costruttori in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="fc178-165">Un costruttore può essere eseguito solo una volta alla creazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="fc178-166">Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="fc178-167">Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.</span><span class="sxs-lookup"><span data-stu-id="fc178-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="fc178-168">Per definire un costruttore per una classe:</span><span class="sxs-lookup"><span data-stu-id="fc178-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="fc178-169">Per altre informazioni, vedere [Costruttori](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-169">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="fc178-170">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="fc178-170">Finalizers</span></span>

<span data-ttu-id="fc178-171">I finalizzatori sono usati per distruggere istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="fc178-171">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="fc178-172">In .NET Framework, il Garbage Collector gestisce l'allocazione e il rilascio di memoria per gli oggetti gestiti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc178-172">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="fc178-173">Potrebbero, tuttavia, essere necessari finalizzatori per pulire eventuali risorse non gestite create dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc178-173">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="fc178-174">Può esistere un solo finalizzatore per classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-174">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="fc178-175">Per altre informazioni sui finalizzatori e sull'operazione di Garbage Collection in .NET Framework, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-175">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="fc178-176">Eventi</span><span class="sxs-lookup"><span data-stu-id="fc178-176">Events</span></span>

<span data-ttu-id="fc178-177">Tramite gli eventi, una classe o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="fc178-177">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="fc178-178">La classe che invia o genera l'evento è chiamata *editore* e le classi che ricevono o gestiscono l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="fc178-178">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="fc178-179">Per altre informazioni sugli eventi e sulla loro generazione e gestione, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-179">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="fc178-180">Per dichiarare un evento in una classe, usare la parola chiave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-180">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="fc178-181">Per generare un evento, richiamare il delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fc178-181">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="fc178-182">Per sottoscrivere un evento, utilizzare l'operatore `+=`. Per annullare la sottoscrizione a un evento utilizzare l'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="fc178-182">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="fc178-183">Classi annidate</span><span class="sxs-lookup"><span data-stu-id="fc178-183">Nested Classes</span></span>

<span data-ttu-id="fc178-184">Una classe definita all'interno di un'altra classe è denominata *annidata*.</span><span class="sxs-lookup"><span data-stu-id="fc178-184">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="fc178-185">Per impostazione predefinita, la classe annidata è privata.</span><span class="sxs-lookup"><span data-stu-id="fc178-185">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="fc178-186">Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:</span><span class="sxs-lookup"><span data-stu-id="fc178-186">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="fc178-187">Modificatori di accesso e livelli di accesso</span><span class="sxs-lookup"><span data-stu-id="fc178-187">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="fc178-188">Tutte le classi e i membri della classe possono specificare il livello di accesso offerto alle altre classi usando i *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="fc178-188">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="fc178-189">Sono disponibili i seguenti modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="fc178-189">The following access modifiers are available:</span></span>

|<span data-ttu-id="fc178-190">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="fc178-190">C# Modifier</span></span>|<span data-ttu-id="fc178-191">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc178-191">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="fc178-192">public</span><span class="sxs-lookup"><span data-stu-id="fc178-192">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="fc178-193">Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="fc178-193">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="fc178-194">private</span><span class="sxs-lookup"><span data-stu-id="fc178-194">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="fc178-195">Il tipo o il membro è accessibile solo dal codice nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-195">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="fc178-196">protected</span><span class="sxs-lookup"><span data-stu-id="fc178-196">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="fc178-197">Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fc178-197">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="fc178-198">internal</span><span class="sxs-lookup"><span data-stu-id="fc178-198">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="fc178-199">Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="fc178-199">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="fc178-200">protected internal</span><span class="sxs-lookup"><span data-stu-id="fc178-200">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="fc178-201">Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="fc178-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="fc178-202">private protected</span><span class="sxs-lookup"><span data-stu-id="fc178-202">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="fc178-203">Il tipo o membro è accessibile solo dal codice nella stessa classe o in una classe derivata all'interno dell'assembly della classe di base.</span><span class="sxs-lookup"><span data-stu-id="fc178-203">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="fc178-204">Per altre informazioni, vedere [Access Modifiers](../classes-and-structs/access-modifiers.md) (Modificatori di accesso).</span><span class="sxs-lookup"><span data-stu-id="fc178-204">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="fc178-205">Creazione di istanze di classi</span><span class="sxs-lookup"><span data-stu-id="fc178-205">Instantiating Classes</span></span>

<span data-ttu-id="fc178-206">Per creare un oggetto, è necessario creare un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-206">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="fc178-207">Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-207">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="fc178-208">Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:</span><span class="sxs-lookup"><span data-stu-id="fc178-208">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="fc178-209">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-209">For more information, see:</span></span>

- [<span data-ttu-id="fc178-210">Operatore new</span><span class="sxs-lookup"><span data-stu-id="fc178-210">new Operator</span></span>](../../language-reference/operators/new-operator.md)

- [<span data-ttu-id="fc178-211">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="fc178-211">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="fc178-212">Classi e membri statici</span><span class="sxs-lookup"><span data-stu-id="fc178-212">Static Classes and Members</span></span>

<span data-ttu-id="fc178-213">Un membro statico della classe è una proprietà, una routine o un campo condiviso da tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-213">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="fc178-214">Per definire un membro statico:</span><span class="sxs-lookup"><span data-stu-id="fc178-214">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="fc178-215">Per accedere al membro statico, usare il nome della classe senza creare un oggetto di questa classe:</span><span class="sxs-lookup"><span data-stu-id="fc178-215">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="fc178-216">Le classi statiche in C# hanno solo membri statici e non è possibile crearne un'istanza.</span><span class="sxs-lookup"><span data-stu-id="fc178-216">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="fc178-217">I membri statici, inoltre, non possono accedere a proprietà, campi o metodi non statici.</span><span class="sxs-lookup"><span data-stu-id="fc178-217">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="fc178-218">Per altre informazioni, vedere [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-218">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="fc178-219">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="fc178-219">Anonymous Types</span></span>

<span data-ttu-id="fc178-220">I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fc178-220">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="fc178-221">La classe viene generata direttamente dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="fc178-221">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="fc178-222">La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc178-222">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="fc178-223">Per creare un'istanza di un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="fc178-223">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="fc178-224">Per altre informazioni, vedere [Tipi anonimi](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-224">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="fc178-225">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="fc178-225">Inheritance</span></span>

<span data-ttu-id="fc178-226">L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="fc178-226">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="fc178-227">La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*.</span><span class="sxs-lookup"><span data-stu-id="fc178-227">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="fc178-228">Tuttavia, tutte le classi in C# ereditano in modo implicito dalla classe <xref:System.Object> che supporta la gerarchia di classi .NET e offre servizi di basso livello a tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="fc178-228">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="fc178-229">C# non supporta l'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="fc178-229">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="fc178-230">Vale a dire, è possibile specificare una sola classe base per una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fc178-230">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="fc178-231">Per ereditare da una classe base:</span><span class="sxs-lookup"><span data-stu-id="fc178-231">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="fc178-232">Per impostazione predefinita, tutte le classi possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="fc178-232">By default all classes can be inherited.</span></span> <span data-ttu-id="fc178-233">Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.</span><span class="sxs-lookup"><span data-stu-id="fc178-233">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="fc178-234">Per specificare che una classe non può essere utilizzata come classe base:</span><span class="sxs-lookup"><span data-stu-id="fc178-234">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="fc178-235">Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:</span><span class="sxs-lookup"><span data-stu-id="fc178-235">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="fc178-236">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-236">For more information, see:</span></span>

- [<span data-ttu-id="fc178-237">sealed</span><span class="sxs-lookup"><span data-stu-id="fc178-237">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="fc178-238">abstract</span><span class="sxs-lookup"><span data-stu-id="fc178-238">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="fc178-239">Override di membri</span><span class="sxs-lookup"><span data-stu-id="fc178-239">Overriding Members</span></span>

<span data-ttu-id="fc178-240">Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa.</span><span class="sxs-lookup"><span data-stu-id="fc178-240">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="fc178-241">Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override.</span><span class="sxs-lookup"><span data-stu-id="fc178-241">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="fc178-242">È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fc178-242">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="fc178-243">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="fc178-243">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="fc178-244">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="fc178-244">C# Modifier</span></span>|<span data-ttu-id="fc178-245">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc178-245">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="fc178-246">virtual</span><span class="sxs-lookup"><span data-stu-id="fc178-246">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="fc178-247">Consente a un membro della classe di essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fc178-247">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="fc178-248">override</span><span class="sxs-lookup"><span data-stu-id="fc178-248">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="fc178-249">Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="fc178-249">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="fc178-250">abstract</span><span class="sxs-lookup"><span data-stu-id="fc178-250">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="fc178-251">Richiede che un membro della classe venga sottoposto a override nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fc178-251">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="fc178-252">Modificatore new</span><span class="sxs-lookup"><span data-stu-id="fc178-252">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="fc178-253">Nasconde un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="fc178-253">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="fc178-254">Interfacce</span><span class="sxs-lookup"><span data-stu-id="fc178-254">Interfaces</span></span>

<span data-ttu-id="fc178-255">Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="fc178-255">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="fc178-256">A differenza delle classi, però, le interfacce non forniscono l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="fc178-256">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="fc178-257">Esse sono infatti implementate dalle classi e definite come entità distinte da queste.</span><span class="sxs-lookup"><span data-stu-id="fc178-257">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="fc178-258">Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.</span><span class="sxs-lookup"><span data-stu-id="fc178-258">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="fc178-259">Per definire un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="fc178-259">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="fc178-260">Per implementare un'interfaccia in una classe:</span><span class="sxs-lookup"><span data-stu-id="fc178-260">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="fc178-261">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-261">For more information, see:</span></span>

[<span data-ttu-id="fc178-262">Interfacce</span><span class="sxs-lookup"><span data-stu-id="fc178-262">Interfaces</span></span>](../interfaces/index.md)

[<span data-ttu-id="fc178-263">interface</span><span class="sxs-lookup"><span data-stu-id="fc178-263">interface</span></span>](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="fc178-264">Generics</span><span class="sxs-lookup"><span data-stu-id="fc178-264">Generics</span></span>

<span data-ttu-id="fc178-265">Classi, strutture, interfacce e metodi in .NET Framework possono includere *parametri di tipo* che definiscono tipi di oggetti che possono archiviare o usare.</span><span class="sxs-lookup"><span data-stu-id="fc178-265">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="fc178-266">L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="fc178-266">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="fc178-267">Per definire una classe generica:</span><span class="sxs-lookup"><span data-stu-id="fc178-267">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="fc178-268">Per creare un'istanza di una classe generica:</span><span class="sxs-lookup"><span data-stu-id="fc178-268">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="fc178-269">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-269">For more information, see:</span></span>

- [<span data-ttu-id="fc178-270">Generics</span><span class="sxs-lookup"><span data-stu-id="fc178-270">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="fc178-271">Generics</span><span class="sxs-lookup"><span data-stu-id="fc178-271">Generics</span></span>](../generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="fc178-272">Delegati</span><span class="sxs-lookup"><span data-stu-id="fc178-272">Delegates</span></span>

<span data-ttu-id="fc178-273">Un *delegato* è un tipo che definisce una firma di metodo e può offrire un riferimento a qualsiasi metodo con una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="fc178-273">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="fc178-274">Tramite il delegato è possibile invocare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="fc178-274">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="fc178-275">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="fc178-275">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="fc178-276">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="fc178-276">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="fc178-277">Per altre informazioni sull'uso dei delegati nella gestione degli eventi, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc178-277">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="fc178-278">Per creare un delegato:</span><span class="sxs-lookup"><span data-stu-id="fc178-278">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="fc178-279">Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:</span><span class="sxs-lookup"><span data-stu-id="fc178-279">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="fc178-280">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fc178-280">For more information, see:</span></span>

- [<span data-ttu-id="fc178-281">Delegati</span><span class="sxs-lookup"><span data-stu-id="fc178-281">Delegates</span></span>](../delegates/index.md)

- [<span data-ttu-id="fc178-282">delegate</span><span class="sxs-lookup"><span data-stu-id="fc178-282">delegate</span></span>](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="fc178-283">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc178-283">See also</span></span>

- [<span data-ttu-id="fc178-284">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fc178-284">C# Programming Guide</span></span>](../index.md)
