---
title: Programmazione orientata a oggetti (C#)
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 98dd5147ab54375ec851ccd9b981a68098a53270
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241890"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="77252-102">Programmazione orientata a oggetti (C#)</span><span class="sxs-lookup"><span data-stu-id="77252-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="77252-103">C# offre un supporto completo per la programmazione orientata a oggetti che include incapsulamento, ereditarietà e polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="77252-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="77252-104">L'*incapsulamento* indica che un gruppo di proprietà, metodi e altri membri correlati vengono considerati come una singola unità o un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="77252-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="77252-105">L'*ereditarietà* indica la capacità di creare nuove classi sulla base di una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="77252-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="77252-106">Il *polimorfismo* indica la capacità di usare più classi in modo intercambiabile, anche se in ognuna di esse le stesse proprietà o gli stessi metodi sono implementati in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="77252-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="77252-107">Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="77252-107">Classes and objects</span></span>

<span data-ttu-id="77252-108">I termini *classe* e *oggetto* descrivono rispettivamente il *tipo* di oggetti e le *istanze* delle classi.</span><span class="sxs-lookup"><span data-stu-id="77252-108">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="77252-109">L'atto di creare un oggetto viene pertanto chiamato *creazione di istanze*.</span><span class="sxs-lookup"><span data-stu-id="77252-109">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="77252-110">Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="77252-110">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="77252-111">Per definire una classe:</span><span class="sxs-lookup"><span data-stu-id="77252-111">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="77252-112">C# fornisce anche tipi denominati *strutture* che risultano utili quando non è necessario il supporto per l'ereditarietà o il polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="77252-112">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span>

<span data-ttu-id="77252-113">Per definire una struttura:</span><span class="sxs-lookup"><span data-stu-id="77252-113">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="77252-114">Per altre informazioni, vedere gli articoli sulle parole chiave [Class](../../language-reference/keywords/class.md) e [struct](../../language-reference/builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="77252-114">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="77252-115">Membri di classe</span><span class="sxs-lookup"><span data-stu-id="77252-115">Class members</span></span>

<span data-ttu-id="77252-116">Ogni classe può avere *membri di classe* diversi che includono proprietà che descrivono i dati della classe, i metodi che definiscono il comportamento della classe e gli eventi che offrono la comunicazione tra classi e oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="77252-116">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="77252-117">Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="77252-117">Properties and fields</span></span>

<span data-ttu-id="77252-118">I campi e le proprietà rappresentano le informazioni contenute in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="77252-118">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="77252-119">I campi sono simili a variabili in quanto possono essere letti o impostati direttamente, in base ai modificatori di accesso applicabili.</span><span class="sxs-lookup"><span data-stu-id="77252-119">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="77252-120">Per definire un campo a cui è possibile accedere dall'interno di istanze della classe:</span><span class="sxs-lookup"><span data-stu-id="77252-120">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="77252-121">Le proprietà dispongono `get` di `set` funzioni di accesso e, che forniscono un maggiore controllo sulla modalità di impostazione o di restituzione dei valori.</span><span class="sxs-lookup"><span data-stu-id="77252-121">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="77252-122">C# consente di creare un campo privato per archiviare il valore della proprietà o usare proprietà implementate automaticamente che creano automaticamente questo campo in background e forniscono la logica di base per le routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="77252-122">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="77252-123">Per definire una proprietà implementata automaticamente:</span><span class="sxs-lookup"><span data-stu-id="77252-123">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="77252-124">Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:</span><span class="sxs-lookup"><span data-stu-id="77252-124">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="77252-125">La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="77252-125">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="77252-126">È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura.</span><span class="sxs-lookup"><span data-stu-id="77252-126">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="77252-127">In C#, è possibile omettere il metodo della proprietà `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="77252-127">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="77252-128">Tuttavia, le proprietà implementate automaticamente non possono essere di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="77252-128">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="77252-129">Le proprietà implementate automaticamente di sola lettura possono essere impostate nei costruttori della classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="77252-129">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="77252-130">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77252-130">For more information, see:</span></span>

- [<span data-ttu-id="77252-131">get</span><span class="sxs-lookup"><span data-stu-id="77252-131">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="77252-132">set</span><span class="sxs-lookup"><span data-stu-id="77252-132">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="77252-133">Metodi</span><span class="sxs-lookup"><span data-stu-id="77252-133">Methods</span></span>

<span data-ttu-id="77252-134">Un *metodo* è un'azione che può essere eseguita da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="77252-134">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="77252-135">Per definire un metodo di una classe:</span><span class="sxs-lookup"><span data-stu-id="77252-135">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="77252-136">Una classe può disporre di diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o per i tipi di parametro.</span><span class="sxs-lookup"><span data-stu-id="77252-136">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="77252-137">Per essere in rapporto di overload con un metodo:</span><span class="sxs-lookup"><span data-stu-id="77252-137">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="77252-138">Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="77252-138">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="77252-139">C#, tuttavia, supporta anche i *metodi di estensione* che consentono di aggiungere metodi a una classe esistente al di fuori della definizione effettiva della classe.</span><span class="sxs-lookup"><span data-stu-id="77252-139">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="77252-140">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77252-140">For more information, see:</span></span>

- [<span data-ttu-id="77252-141">Metodi</span><span class="sxs-lookup"><span data-stu-id="77252-141">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="77252-142">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="77252-142">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="77252-143">Costruttori</span><span class="sxs-lookup"><span data-stu-id="77252-143">Constructors</span></span>

<span data-ttu-id="77252-144">I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="77252-144">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="77252-145">I costruttori in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="77252-145">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="77252-146">Un costruttore può essere eseguito solo una volta alla creazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="77252-146">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="77252-147">Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe.</span><span class="sxs-lookup"><span data-stu-id="77252-147">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="77252-148">Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.</span><span class="sxs-lookup"><span data-stu-id="77252-148">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="77252-149">Per definire un costruttore per una classe:</span><span class="sxs-lookup"><span data-stu-id="77252-149">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="77252-150">Per altre informazioni, vedere [Costruttori](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="77252-150">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="77252-151">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="77252-151">Finalizers</span></span>

<span data-ttu-id="77252-152">Viene utilizzato un finalizzatore per distruggere le istanze delle classi.</span><span class="sxs-lookup"><span data-stu-id="77252-152">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="77252-153">In .NET, il Garbage Collector gestisce automaticamente l'allocazione e il rilascio di memoria per gli oggetti gestiti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="77252-153">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="77252-154">Potrebbero, tuttavia, essere necessari finalizzatori per pulire eventuali risorse non gestite create dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="77252-154">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="77252-155">Può essere presente un solo finalizzatore per una classe.</span><span class="sxs-lookup"><span data-stu-id="77252-155">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="77252-156">Per ulteriori informazioni sui finalizzatori e Garbage Collection in .NET, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="77252-156">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="77252-157">Eventi</span><span class="sxs-lookup"><span data-stu-id="77252-157">Events</span></span>

<span data-ttu-id="77252-158">Tramite gli eventi una classe o un oggetto sono in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="77252-158">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="77252-159">La classe che invia o genera l'evento è chiamata *editore* e le classi che ricevono o gestiscono l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="77252-159">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="77252-160">Per altre informazioni sugli eventi e sulla loro generazione e gestione, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="77252-160">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="77252-161">Per dichiarare un evento in una classe, usare la parola chiave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="77252-161">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="77252-162">Per generare un evento, richiamare il delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="77252-162">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="77252-163">Per sottoscrivere un evento, utilizzare l'operatore `+=`. Per annullare la sottoscrizione a un evento utilizzare l'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="77252-163">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="77252-164">Classi annidate</span><span class="sxs-lookup"><span data-stu-id="77252-164">Nested classes</span></span>

<span data-ttu-id="77252-165">Una classe definita all'interno di un'altra classe è denominata *annidata*.</span><span class="sxs-lookup"><span data-stu-id="77252-165">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="77252-166">Per impostazione predefinita, la classe annidata è privata.</span><span class="sxs-lookup"><span data-stu-id="77252-166">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="77252-167">Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:</span><span class="sxs-lookup"><span data-stu-id="77252-167">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="77252-168">Modificatori di accesso e livelli di accesso</span><span class="sxs-lookup"><span data-stu-id="77252-168">Access modifiers and access levels</span></span>

<span data-ttu-id="77252-169">Tutte le classi e i membri della classe possono specificare il livello di accesso offerto alle altre classi usando i *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="77252-169">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="77252-170">Sono disponibili i seguenti modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="77252-170">The following access modifiers are available:</span></span>

| <span data-ttu-id="77252-171">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="77252-171">C# Modifier</span></span> | <span data-ttu-id="77252-172">Definizione</span><span class="sxs-lookup"><span data-stu-id="77252-172">Definition</span></span> |
|--|--|
| [<span data-ttu-id="77252-173">pubblico</span><span class="sxs-lookup"><span data-stu-id="77252-173">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="77252-174">Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="77252-174">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="77252-175">private</span><span class="sxs-lookup"><span data-stu-id="77252-175">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="77252-176">Il tipo o il membro è accessibile solo dal codice nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="77252-176">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="77252-177">protected</span><span class="sxs-lookup"><span data-stu-id="77252-177">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="77252-178">Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="77252-178">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="77252-179">internal</span><span class="sxs-lookup"><span data-stu-id="77252-179">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="77252-180">Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="77252-180">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="77252-181">protected internal</span><span class="sxs-lookup"><span data-stu-id="77252-181">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="77252-182">Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="77252-182">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="77252-183">protetto privato</span><span class="sxs-lookup"><span data-stu-id="77252-183">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="77252-184">Il tipo o membro è accessibile solo dal codice nella stessa classe o in una classe derivata all'interno dell'assembly della classe di base.</span><span class="sxs-lookup"><span data-stu-id="77252-184">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="77252-185">Per altre informazioni, vedere [Modificatori di accesso](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="77252-185">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="77252-186">Creazione di istanze di classi</span><span class="sxs-lookup"><span data-stu-id="77252-186">Instantiating classes</span></span>

<span data-ttu-id="77252-187">Per creare un oggetto, è necessario creare un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="77252-187">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="77252-188">Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="77252-188">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="77252-189">Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:</span><span class="sxs-lookup"><span data-stu-id="77252-189">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="77252-190">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77252-190">For more information, see:</span></span>

- [<span data-ttu-id="77252-191">Operatore New</span><span class="sxs-lookup"><span data-stu-id="77252-191">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="77252-192">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="77252-192">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="77252-193">Classi e membri statici</span><span class="sxs-lookup"><span data-stu-id="77252-193">Static Classes and Members</span></span>

<span data-ttu-id="77252-194">Un membro statico della classe è una proprietà, una routine o un campo condiviso da tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="77252-194">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="77252-195">Per definire un membro statico:</span><span class="sxs-lookup"><span data-stu-id="77252-195">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="77252-196">Per accedere al membro statico, usare il nome della classe senza creare un oggetto di questa classe:</span><span class="sxs-lookup"><span data-stu-id="77252-196">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="77252-197">Le classi statiche in C# hanno solo membri statici e non è possibile crearne un'istanza.</span><span class="sxs-lookup"><span data-stu-id="77252-197">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="77252-198">I membri statici, inoltre, non possono accedere a proprietà, campi o metodi non statici.</span><span class="sxs-lookup"><span data-stu-id="77252-198">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="77252-199">Per altre informazioni, vedere [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="77252-199">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="77252-200">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="77252-200">Anonymous types</span></span>

<span data-ttu-id="77252-201">I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="77252-201">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="77252-202">La classe viene generata direttamente dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="77252-202">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="77252-203">La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="77252-203">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="77252-204">Per creare un'istanza di un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="77252-204">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="77252-205">Per altre informazioni, vedere [Tipi anonimi](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="77252-205">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="77252-206">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="77252-206">Inheritance</span></span>

<span data-ttu-id="77252-207">L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="77252-207">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="77252-208">La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*.</span><span class="sxs-lookup"><span data-stu-id="77252-208">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="77252-209">Tuttavia, tutte le classi in C# ereditano in modo implicito dalla classe <xref:System.Object> che supporta la gerarchia di classi .NET e offre servizi di basso livello a tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="77252-209">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="77252-210">C# non supporta l'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="77252-210">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="77252-211">Vale a dire, è possibile specificare una sola classe base per una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="77252-211">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="77252-212">Per ereditare da una classe base:</span><span class="sxs-lookup"><span data-stu-id="77252-212">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="77252-213">Per impostazione predefinita, tutte le classi possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="77252-213">By default all classes can be inherited.</span></span> <span data-ttu-id="77252-214">Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.</span><span class="sxs-lookup"><span data-stu-id="77252-214">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="77252-215">Per specificare che una classe non può essere utilizzata come classe base:</span><span class="sxs-lookup"><span data-stu-id="77252-215">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="77252-216">Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:</span><span class="sxs-lookup"><span data-stu-id="77252-216">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="77252-217">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77252-217">For more information, see:</span></span>

- [<span data-ttu-id="77252-218">sealed</span><span class="sxs-lookup"><span data-stu-id="77252-218">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="77252-219">astratta</span><span class="sxs-lookup"><span data-stu-id="77252-219">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="77252-220">Override di membri</span><span class="sxs-lookup"><span data-stu-id="77252-220">Overriding Members</span></span>

<span data-ttu-id="77252-221">Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa.</span><span class="sxs-lookup"><span data-stu-id="77252-221">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="77252-222">Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override.</span><span class="sxs-lookup"><span data-stu-id="77252-222">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="77252-223">È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="77252-223">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="77252-224">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="77252-224">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="77252-225">Modificatore di C#</span><span class="sxs-lookup"><span data-stu-id="77252-225">C# Modifier</span></span> | <span data-ttu-id="77252-226">Definizione</span><span class="sxs-lookup"><span data-stu-id="77252-226">Definition</span></span> |
|--|--|
| [<span data-ttu-id="77252-227">virtuale</span><span class="sxs-lookup"><span data-stu-id="77252-227">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="77252-228">Consente a un membro della classe di essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="77252-228">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="77252-229">override</span><span class="sxs-lookup"><span data-stu-id="77252-229">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="77252-230">Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="77252-230">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="77252-231">astratta</span><span class="sxs-lookup"><span data-stu-id="77252-231">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="77252-232">Richiede che un membro della classe venga sottoposto a override nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="77252-232">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="77252-233">Modificatore new</span><span class="sxs-lookup"><span data-stu-id="77252-233">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="77252-234">Nasconde un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="77252-234">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="77252-235">Interfacce</span><span class="sxs-lookup"><span data-stu-id="77252-235">Interfaces</span></span>

<span data-ttu-id="77252-236">Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="77252-236">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="77252-237">A differenza delle classi, però, le interfacce non forniscono l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="77252-237">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="77252-238">Esse sono infatti implementate dalle classi e definite come entità distinte da queste.</span><span class="sxs-lookup"><span data-stu-id="77252-238">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="77252-239">Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.</span><span class="sxs-lookup"><span data-stu-id="77252-239">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="77252-240">Per definire un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="77252-240">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="77252-241">Per implementare un'interfaccia in una classe:</span><span class="sxs-lookup"><span data-stu-id="77252-241">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="77252-242">Per ulteriori informazioni, vedere l'articolo della Guida alla programmazione sulle [interfacce](../interfaces/index.md) e l'articolo di riferimento per il linguaggio sulla parola chiave [Interface](../../language-reference/keywords/interface.md) .</span><span class="sxs-lookup"><span data-stu-id="77252-242">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="77252-243">Generics</span><span class="sxs-lookup"><span data-stu-id="77252-243">Generics</span></span>

<span data-ttu-id="77252-244">Classi, strutture, interfacce e metodi in .NET possono includere *parametri di tipo* che definiscono tipi di oggetti che possono archiviare o usare.</span><span class="sxs-lookup"><span data-stu-id="77252-244">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="77252-245">L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="77252-245">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="77252-246">Per definire una classe generica:</span><span class="sxs-lookup"><span data-stu-id="77252-246">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="77252-247">Per creare un'istanza di una classe generica:</span><span class="sxs-lookup"><span data-stu-id="77252-247">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="77252-248">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77252-248">For more information, see:</span></span>

- [<span data-ttu-id="77252-249">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="77252-249">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="77252-250">Generics - Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77252-250">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="77252-251">Delegati</span><span class="sxs-lookup"><span data-stu-id="77252-251">Delegates</span></span>

<span data-ttu-id="77252-252">Un *delegato* è un tipo che definisce una firma di metodo e può offrire un riferimento a qualsiasi metodo con una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="77252-252">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="77252-253">Tramite il delegato è possibile invocare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="77252-253">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="77252-254">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="77252-254">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="77252-255">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="77252-255">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="77252-256">Per altre informazioni sull'uso dei delegati nella gestione degli eventi, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="77252-256">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="77252-257">Per creare un delegato:</span><span class="sxs-lookup"><span data-stu-id="77252-257">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="77252-258">Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:</span><span class="sxs-lookup"><span data-stu-id="77252-258">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
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

<span data-ttu-id="77252-259">Per ulteriori informazioni, vedere l'articolo della Guida alla programmazione sui [delegati](../delegates/index.md) e l'articolo di riferimento per il linguaggio sulla parola chiave [delegate](../../language-reference/builtin-types/reference-types.md) .</span><span class="sxs-lookup"><span data-stu-id="77252-259">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="77252-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77252-260">See also</span></span>

- [<span data-ttu-id="77252-261">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77252-261">C# Programming Guide</span></span>](../index.md)
