---
title: Programmazione orientata a oggetti (C#)
ms.date: 02/08/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 01d6f55bf0752f902f351675c4596abbb8ac85c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627890"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="0c7cd-102">Programmazione orientata agli oggetti (C )Object-Oriented programming (C</span><span class="sxs-lookup"><span data-stu-id="0c7cd-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="0c7cd-103">C# offre un supporto completo per la programmazione orientata a oggetti che include incapsulamento, ereditarietà e polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="0c7cd-104">L'*incapsulamento* indica che un gruppo di proprietà, metodi e altri membri correlati vengono considerati come una singola unità o un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="0c7cd-105">L'*ereditarietà* indica la capacità di creare nuove classi sulla base di una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="0c7cd-106">Il *polimorfismo* indica la capacità di usare più classi in modo intercambiabile, anche se in ognuna di esse le stesse proprietà o gli stessi metodi sono implementati in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="0c7cd-107">Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="0c7cd-107">Classes and objects</span></span>

<span data-ttu-id="0c7cd-108">I termini *class* e *object* descrivono rispettivamente il *tipo* di oggetti e le *istanze* delle classi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-108">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="0c7cd-109">L'atto di creare un oggetto viene pertanto chiamato *creazione di istanze*.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-109">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="0c7cd-110">Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-110">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="0c7cd-111">Per definire una classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-111">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="0c7cd-112">In C' sono inoltre disponibili tipi denominati *strutture* che sono utili quando non è necessario il supporto per l'ereditarietà o il polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-112">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span>

<span data-ttu-id="0c7cd-113">Per definire una struttura:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-113">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="0c7cd-114">Per altre informazioni, vedere gli articoli sulle parole chiave [class](../../language-reference/keywords/class.md) e [struct.](../../language-reference/builtin-types/struct.md)</span><span class="sxs-lookup"><span data-stu-id="0c7cd-114">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="0c7cd-115">Membri di classe</span><span class="sxs-lookup"><span data-stu-id="0c7cd-115">Class members</span></span>

<span data-ttu-id="0c7cd-116">Ogni classe può avere *membri di classe* diversi che includono proprietà che descrivono i dati della classe, i metodi che definiscono il comportamento della classe e gli eventi che offrono la comunicazione tra classi e oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-116">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="0c7cd-117">Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-117">Properties and fields</span></span>

<span data-ttu-id="0c7cd-118">I campi e le proprietà rappresentano le informazioni contenute in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-118">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="0c7cd-119">I campi sono come variabili perché possono essere letti o impostati direttamente, in base ai modificatori di accesso applicabili.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-119">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="0c7cd-120">Per definire un campo accessibile dall'interno di istanze della classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-120">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="0c7cd-121">Le `get` proprietà `set` dispongono di e funzioni di accesso, che forniscono un maggiore controllo sulla modalità di impostazione o restituzione dei valori.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-121">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="0c7cd-122">Il linguaggio C, è possibile creare un campo privato per archiviare il valore della proprietà o usare proprietà implementate automaticamente che creano automaticamente questo campo dietro le quinte e forniscono la logica di base per le procedure della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-122">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="0c7cd-123">Per definire una proprietà implementata automaticamente:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-123">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="0c7cd-124">Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-124">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="0c7cd-125">La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-125">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="0c7cd-126">È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-126">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="0c7cd-127">In C#, è possibile omettere il metodo della proprietà `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-127">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="0c7cd-128">Tuttavia, le proprietà implementate automaticamente non possono essere di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-128">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="0c7cd-129">Le proprietà implementate automaticamente di sola lettura possono essere impostate nei costruttori della classe contenitore.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-129">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="0c7cd-130">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-130">For more information, see:</span></span>

- [<span data-ttu-id="0c7cd-131">get</span><span class="sxs-lookup"><span data-stu-id="0c7cd-131">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="0c7cd-132">Impostare</span><span class="sxs-lookup"><span data-stu-id="0c7cd-132">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="0c7cd-133">Metodi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-133">Methods</span></span>

<span data-ttu-id="0c7cd-134">Un *metodo* è un'azione che può essere eseguita da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-134">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="0c7cd-135">Per definire un metodo di una classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-135">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="0c7cd-136">Una classe può disporre di diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o per i tipi di parametro.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-136">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="0c7cd-137">Per essere in rapporto di overload con un metodo:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-137">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="0c7cd-138">Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-138">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="0c7cd-139">C#, tuttavia, supporta anche i *metodi di estensione* che consentono di aggiungere metodi a una classe esistente al di fuori della definizione effettiva della classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-139">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="0c7cd-140">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-140">For more information, see:</span></span>

- [<span data-ttu-id="0c7cd-141">Metodi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-141">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="0c7cd-142">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="0c7cd-142">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="0c7cd-143">Costruttori</span><span class="sxs-lookup"><span data-stu-id="0c7cd-143">Constructors</span></span>

<span data-ttu-id="0c7cd-144">I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-144">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="0c7cd-145">I costruttori in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-145">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="0c7cd-146">Un costruttore può essere eseguito solo una volta alla creazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-146">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="0c7cd-147">Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-147">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="0c7cd-148">Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-148">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="0c7cd-149">Per definire un costruttore per una classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-149">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="0c7cd-150">Per altre informazioni, vedere [Costruttori](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-150">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="0c7cd-151">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="0c7cd-151">Finalizers</span></span>

<span data-ttu-id="0c7cd-152">I finalizzatori sono usati per distruggere istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-152">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="0c7cd-153">In .NET Framework, il Garbage Collector gestisce l'allocazione e il rilascio di memoria per gli oggetti gestiti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-153">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="0c7cd-154">Potrebbero, tuttavia, essere necessari finalizzatori per pulire eventuali risorse non gestite create dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-154">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="0c7cd-155">Può esistere un solo finalizzatore per classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-155">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="0c7cd-156">Per altre informazioni sui finalizzatori e sull'operazione di Garbage Collection in .NET Framework, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-156">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="0c7cd-157">Eventi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-157">Events</span></span>

<span data-ttu-id="0c7cd-158">Tramite gli eventi una classe o un oggetto sono in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-158">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="0c7cd-159">La classe che invia o genera l'evento è chiamata *editore* e le classi che ricevono o gestiscono l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-159">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="0c7cd-160">Per altre informazioni sugli eventi e sulla loro generazione e gestione, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-160">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="0c7cd-161">Per dichiarare un evento in una classe, usare la parola chiave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-161">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="0c7cd-162">Per generare un evento, richiamare il delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-162">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="0c7cd-163">Per sottoscrivere un evento, utilizzare l'operatore `+=`. Per annullare la sottoscrizione a un evento utilizzare l'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-163">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="0c7cd-164">Classi annidate</span><span class="sxs-lookup"><span data-stu-id="0c7cd-164">Nested classes</span></span>

<span data-ttu-id="0c7cd-165">Una classe definita all'interno di un'altra classe è denominata *annidata*.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-165">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="0c7cd-166">Per impostazione predefinita, la classe annidata è privata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-166">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="0c7cd-167">Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-167">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="0c7cd-168">Modificatori di accesso e livelli di accessoAccess modifiers and access levels</span><span class="sxs-lookup"><span data-stu-id="0c7cd-168">Access modifiers and access levels</span></span>

<span data-ttu-id="0c7cd-169">Tutte le classi e i membri della classe possono specificare il livello di accesso offerto alle altre classi usando i *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-169">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="0c7cd-170">Sono disponibili i seguenti modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-170">The following access modifiers are available:</span></span>

|<span data-ttu-id="0c7cd-171">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="0c7cd-171">C# Modifier</span></span>|<span data-ttu-id="0c7cd-172">Definizione</span><span class="sxs-lookup"><span data-stu-id="0c7cd-172">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="0c7cd-173">pubblico</span><span class="sxs-lookup"><span data-stu-id="0c7cd-173">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="0c7cd-174">Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-174">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="0c7cd-175">Privato</span><span class="sxs-lookup"><span data-stu-id="0c7cd-175">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="0c7cd-176">Il tipo o il membro è accessibile solo dal codice nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-176">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="0c7cd-177">Protetto</span><span class="sxs-lookup"><span data-stu-id="0c7cd-177">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="0c7cd-178">Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-178">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="0c7cd-179">Interno</span><span class="sxs-lookup"><span data-stu-id="0c7cd-179">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="0c7cd-180">Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-180">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="0c7cd-181">protected internal</span><span class="sxs-lookup"><span data-stu-id="0c7cd-181">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="0c7cd-182">Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-182">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="0c7cd-183">private protected</span><span class="sxs-lookup"><span data-stu-id="0c7cd-183">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="0c7cd-184">Il tipo o membro è accessibile solo dal codice nella stessa classe o in una classe derivata all'interno dell'assembly della classe di base.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-184">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="0c7cd-185">Per altre informazioni, vedere [Modificatori di accesso](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-185">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="0c7cd-186">Creazione di istanze di classi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-186">Instantiating classes</span></span>

<span data-ttu-id="0c7cd-187">Per creare un oggetto, è necessario creare un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-187">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="0c7cd-188">Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-188">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="0c7cd-189">Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-189">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="0c7cd-190">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-190">For more information, see:</span></span>

- [<span data-ttu-id="0c7cd-191">nuovo operatore</span><span class="sxs-lookup"><span data-stu-id="0c7cd-191">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="0c7cd-192">Inizializzatori di oggetto e di raccoltaObject and Collection Initializers</span><span class="sxs-lookup"><span data-stu-id="0c7cd-192">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="0c7cd-193">Classi e membri statici</span><span class="sxs-lookup"><span data-stu-id="0c7cd-193">Static Classes and Members</span></span>

<span data-ttu-id="0c7cd-194">Un membro statico della classe è una proprietà, una routine o un campo condiviso da tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-194">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="0c7cd-195">Per definire un membro statico:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-195">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="0c7cd-196">Per accedere al membro statico, usare il nome della classe senza creare un oggetto di questa classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-196">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="0c7cd-197">Le classi statiche in C# hanno solo membri statici e non è possibile crearne un'istanza.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-197">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="0c7cd-198">I membri statici, inoltre, non possono accedere a proprietà, campi o metodi non statici.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-198">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="0c7cd-199">Per altre informazioni, vedere [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-199">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="0c7cd-200">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="0c7cd-200">Anonymous types</span></span>

<span data-ttu-id="0c7cd-201">I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-201">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="0c7cd-202">La classe viene generata direttamente dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-202">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="0c7cd-203">La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-203">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="0c7cd-204">Per creare un'istanza di un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-204">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="0c7cd-205">Per altre informazioni, vedere [Tipi anonimi](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-205">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="0c7cd-206">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="0c7cd-206">Inheritance</span></span>

<span data-ttu-id="0c7cd-207">L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-207">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="0c7cd-208">La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-208">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="0c7cd-209">Tuttavia, tutte le classi in C# ereditano in modo implicito dalla classe <xref:System.Object> che supporta la gerarchia di classi .NET e offre servizi di basso livello a tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-209">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="0c7cd-210">C# non supporta l'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-210">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="0c7cd-211">Vale a dire, è possibile specificare una sola classe base per una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-211">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="0c7cd-212">Per ereditare da una classe base:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-212">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="0c7cd-213">Per impostazione predefinita, tutte le classi possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-213">By default all classes can be inherited.</span></span> <span data-ttu-id="0c7cd-214">Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-214">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="0c7cd-215">Per specificare che una classe non può essere utilizzata come classe base:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-215">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="0c7cd-216">Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-216">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="0c7cd-217">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-217">For more information, see:</span></span>

- [<span data-ttu-id="0c7cd-218">Sigillato</span><span class="sxs-lookup"><span data-stu-id="0c7cd-218">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="0c7cd-219">astratto</span><span class="sxs-lookup"><span data-stu-id="0c7cd-219">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="0c7cd-220">Override di membri</span><span class="sxs-lookup"><span data-stu-id="0c7cd-220">Overriding Members</span></span>

<span data-ttu-id="0c7cd-221">Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-221">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="0c7cd-222">Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-222">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="0c7cd-223">È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-223">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="0c7cd-224">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-224">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="0c7cd-225">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="0c7cd-225">C# Modifier</span></span>|<span data-ttu-id="0c7cd-226">Definizione</span><span class="sxs-lookup"><span data-stu-id="0c7cd-226">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="0c7cd-227">Virtuale</span><span class="sxs-lookup"><span data-stu-id="0c7cd-227">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="0c7cd-228">Consente a un membro della classe di essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-228">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="0c7cd-229">prevalere</span><span class="sxs-lookup"><span data-stu-id="0c7cd-229">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="0c7cd-230">Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-230">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="0c7cd-231">astratto</span><span class="sxs-lookup"><span data-stu-id="0c7cd-231">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="0c7cd-232">Richiede che un membro della classe venga sottoposto a override nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-232">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="0c7cd-233">nuovo modificatore</span><span class="sxs-lookup"><span data-stu-id="0c7cd-233">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="0c7cd-234">Nasconde un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-234">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="0c7cd-235">Interfacce</span><span class="sxs-lookup"><span data-stu-id="0c7cd-235">Interfaces</span></span>

<span data-ttu-id="0c7cd-236">Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-236">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="0c7cd-237">A differenza delle classi, però, le interfacce non forniscono l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-237">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="0c7cd-238">Esse sono infatti implementate dalle classi e definite come entità distinte da queste.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-238">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="0c7cd-239">Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-239">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="0c7cd-240">Per definire un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-240">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="0c7cd-241">Per implementare un'interfaccia in una classe:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-241">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="0c7cd-242">Per altre informazioni, vedere l'articolo della guida alla programmazione [sulle interfacce](../interfaces/index.md) e l'articolo di riferimento del linguaggio sulla parola chiave [interface.](../../language-reference/keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="0c7cd-242">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="0c7cd-243">Generics</span><span class="sxs-lookup"><span data-stu-id="0c7cd-243">Generics</span></span>

<span data-ttu-id="0c7cd-244">Classi, strutture, interfacce e metodi in .NET Framework possono includere *parametri di tipo* che definiscono tipi di oggetti che possono archiviare o usare.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-244">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="0c7cd-245">L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-245">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="0c7cd-246">Per definire una classe generica:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-246">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="0c7cd-247">Per creare un'istanza di una classe generica:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-247">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="0c7cd-248">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-248">For more information, see:</span></span>

- [<span data-ttu-id="0c7cd-249">Generics</span><span class="sxs-lookup"><span data-stu-id="0c7cd-249">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="0c7cd-250">Generics</span><span class="sxs-lookup"><span data-stu-id="0c7cd-250">Generics</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="0c7cd-251">Delegati</span><span class="sxs-lookup"><span data-stu-id="0c7cd-251">Delegates</span></span>

<span data-ttu-id="0c7cd-252">Un *delegato* è un tipo che definisce una firma di metodo e può offrire un riferimento a qualsiasi metodo con una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-252">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="0c7cd-253">Tramite il delegato è possibile invocare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-253">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="0c7cd-254">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-254">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="0c7cd-255">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="0c7cd-255">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="0c7cd-256">Per altre informazioni sull'uso dei delegati nella gestione degli eventi, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c7cd-256">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="0c7cd-257">Per creare un delegato:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-257">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="0c7cd-258">Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:</span><span class="sxs-lookup"><span data-stu-id="0c7cd-258">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="0c7cd-259">Per altre informazioni, vedere l'articolo della guida alla programmazione [sui delegati](../delegates/index.md) e l'articolo di riferimento del linguaggio sulla parola chiave [delegate.](../../language-reference/builtin-types/reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="0c7cd-259">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c7cd-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c7cd-260">See also</span></span>

- [<span data-ttu-id="0c7cd-261">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0c7cd-261">C# Programming Guide</span></span>](../index.md)
