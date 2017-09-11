---
title: Orientato a oggetti di programmazione (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5491b3bd5a25908194d02063f688a319509bb77
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="e83bd-102">Programmazione orientata agli oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e83bd-102">Object-Oriented Programming (Visual Basic)</span></span>
<span data-ttu-id="e83bd-103">Visual Basic fornisce supporto completo perla programmazione orientata agli oggetti inclusi incapsulamento, ereditarietà e polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="e83bd-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="e83bd-104">*Incapsulamento* indica che un gruppo di proprietà correlate, metodi e gli altri membri vengono considerati come una singola unità o un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e83bd-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="e83bd-105">*Ereditarietà* descrive la possibilità di creare nuove classi basate su una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="e83bd-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="e83bd-106">*Polimorfismo* significa che è possibile avere più classi che possono essere utilizzate in modo intercambiabile, anche se ciascuna classe implementa le stesse proprietà o metodi in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="e83bd-107">In questa sezione vengono descritti i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e83bd-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="e83bd-108">Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="e83bd-108">Classes and Objects</span></span>](#Classes)  
  
    -   [<span data-ttu-id="e83bd-109">Membri di classe</span><span class="sxs-lookup"><span data-stu-id="e83bd-109">Class Members</span></span>](#Members)  
  
         [<span data-ttu-id="e83bd-110">Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="e83bd-110">Properties and Fields</span></span>](#Properties)  
  
         [<span data-ttu-id="e83bd-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="e83bd-111">Methods</span></span>](#Methods)  
  
         [<span data-ttu-id="e83bd-112">Costruttori</span><span class="sxs-lookup"><span data-stu-id="e83bd-112">Constructors</span></span>](#Constructors)  
  
         [<span data-ttu-id="e83bd-113">Distruttori</span><span class="sxs-lookup"><span data-stu-id="e83bd-113">Destructors</span></span>](#Destructors)  
  
         [<span data-ttu-id="e83bd-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="e83bd-114">Events</span></span>](#Events)  
  
         [<span data-ttu-id="e83bd-115">Classi annidate</span><span class="sxs-lookup"><span data-stu-id="e83bd-115">Nested Classes</span></span>](#NestedClasses)  
  
    -   [<span data-ttu-id="e83bd-116">Modificatori di accesso e livelli di accesso</span><span class="sxs-lookup"><span data-stu-id="e83bd-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)  
  
    -   [<span data-ttu-id="e83bd-117">Creazione di classi</span><span class="sxs-lookup"><span data-stu-id="e83bd-117">Instantiating Classes</span></span>](#InstantiatingClasses)  
  
    -   [<span data-ttu-id="e83bd-118">Le classi condivise e i membri</span><span class="sxs-lookup"><span data-stu-id="e83bd-118">Shared Classes and Members</span></span>](#Static)  
  
    -   [<span data-ttu-id="e83bd-119">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e83bd-119">Anonymous Types</span></span>](#AnonymousTypes)  
  
-   [<span data-ttu-id="e83bd-120">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e83bd-120">Inheritance</span></span>](#Inheritance)  
  
    -   [<span data-ttu-id="e83bd-121">Override di membri</span><span class="sxs-lookup"><span data-stu-id="e83bd-121">Overriding Members</span></span>](#Overriding)  
  
-   [<span data-ttu-id="e83bd-122">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e83bd-122">Interfaces</span></span>](#Interfaces)  
  
-   [<span data-ttu-id="e83bd-123">Generics</span><span class="sxs-lookup"><span data-stu-id="e83bd-123">Generics</span></span>](#Generics)  
  
-   [<span data-ttu-id="e83bd-124">Delegati</span><span class="sxs-lookup"><span data-stu-id="e83bd-124">Delegates</span></span>](#Delegates)  
  
##  <span data-ttu-id="e83bd-125"><a name="Classes"></a>Classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="e83bd-125"><a name="Classes"></a> Classes and Objects</span></span>  
 <span data-ttu-id="e83bd-126">Le condizioni di *classe* e *oggetto* vengono talvolta utilizzati in modo intercambiabile, ma in realtà, le classi descrivono il *tipo* degli oggetti, mentre gli oggetti sono utilizzabili *istanze* delle classi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="e83bd-127">L'atto di creare un oggetto viene pertanto chiamato *la creazione di istanze*.</span><span class="sxs-lookup"><span data-stu-id="e83bd-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="e83bd-128">Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="e83bd-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>  
  
 <span data-ttu-id="e83bd-129">Per definire una classe:</span><span class="sxs-lookup"><span data-stu-id="e83bd-129">To define a class:</span></span>  
  
```vb  
Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="e83bd-130">Visual Basic fornisce inoltre una versione ridotta delle classi chiamate *strutture* che sono utili quando è necessario creare una matrice di oggetti di grandi dimensioni e si desidera utilizzare una quantità eccessiva di memoria per tale.</span><span class="sxs-lookup"><span data-stu-id="e83bd-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>  
  
 <span data-ttu-id="e83bd-131">Per definire una struttura:</span><span class="sxs-lookup"><span data-stu-id="e83bd-131">To define a structure:</span></span>  
  
```vb  
Structure SampleStructure  
End Structure  
```  
  
 <span data-ttu-id="e83bd-132">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-132">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-133">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="e83bd-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="e83bd-134">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="e83bd-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
###  <span data-ttu-id="e83bd-135"><a name="Members"></a>Membri di classe</span><span class="sxs-lookup"><span data-stu-id="e83bd-135"><a name="Members"></a> Class Members</span></span>  
 <span data-ttu-id="e83bd-136">Ogni classe può avere diversi *i membri della classe* che includono proprietà che descrivono dati relativi a classi, metodi che definiscono il comportamento della classe e gli eventi che forniscono la comunicazione tra classi e oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>  
  
####  <span data-ttu-id="e83bd-137"><a name="Properties"></a>Proprietà e campi</span><span class="sxs-lookup"><span data-stu-id="e83bd-137"><a name="Properties"></a> Properties and Fields</span></span>  
 <span data-ttu-id="e83bd-138">I campi e le proprietà rappresentano le informazioni contenute in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e83bd-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="e83bd-139">I campi sono simili a variabili in quanto possono essere letti o impostati direttamente.</span><span class="sxs-lookup"><span data-stu-id="e83bd-139">Fields are like variables because they can be read or set directly.</span></span>  
  
 <span data-ttu-id="e83bd-140">Per definire un campo:</span><span class="sxs-lookup"><span data-stu-id="e83bd-140">To define a field:</span></span>  
  
```vb  
Class SampleClass  
    Public SampleField As String  
End Class  
```  
  
 <span data-ttu-id="e83bd-141">Le proprietà dispongono di routine Get e Set, che forniscono un maggiore controllo sul modo in cui i valori vengono impostati o restituiti.</span><span class="sxs-lookup"><span data-stu-id="e83bd-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>  
  
 <span data-ttu-id="e83bd-142">Visual Basic consente di creare un campo privato per archiviare il valore della proprietà o utilizzare le cosiddette proprietà implementate automaticamente che creano automaticamente questo campo e forniscono la logica di base per le routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="e83bd-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>  
  
 <span data-ttu-id="e83bd-143">Per definire una proprietà implementata automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e83bd-143">To define an auto-implemented property:</span></span>  
  
```vb  
Class SampleClass  
    Public Property SampleProperty as String  
End Class  
```  
  
 <span data-ttu-id="e83bd-144">Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:</span><span class="sxs-lookup"><span data-stu-id="e83bd-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>  
  
```vb  
Class SampleClass  
    Private m_Sample As String  
    Public Property Sample() As String  
        Get  
            ' Return the value stored in the field.  
            Return m_Sample  
        End Get  
        Set(ByVal Value As String)  
            ' Store the value in the field.  
            m_Sample = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="e83bd-145">La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e83bd-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="e83bd-146">È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura.</span><span class="sxs-lookup"><span data-stu-id="e83bd-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="e83bd-147">In Visual Basic è possibile utilizzare le parole chiave `ReadOnly` e `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="e83bd-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="e83bd-148">Proprietà implementate automaticamente, tuttavia, non può essere in sola lettura o in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e83bd-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>  
  
 <span data-ttu-id="e83bd-149">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-149">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-150">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="e83bd-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="e83bd-151">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="e83bd-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
  
-   [<span data-ttu-id="e83bd-152">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="e83bd-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
  
-   [<span data-ttu-id="e83bd-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="e83bd-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
-   [<span data-ttu-id="e83bd-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="e83bd-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
  
####  <span data-ttu-id="e83bd-155"><a name="Methods"></a>Metodi</span><span class="sxs-lookup"><span data-stu-id="e83bd-155"><a name="Methods"></a> Methods</span></span>  
 <span data-ttu-id="e83bd-156">Oggetto *metodo* che un oggetto può eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="e83bd-156">A *method* is an action that an object can perform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e83bd-157">In Visual Basic, è possibile creare un metodo in due modi: se il metodo non restituisce un valore, viene utilizzata l'istruzione `Sub`, se invece un metodo restituisce un valore, viene utilizzata l'istruzione `Function`.</span><span class="sxs-lookup"><span data-stu-id="e83bd-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>  
  
 <span data-ttu-id="e83bd-158">Per definire un metodo di una classe:</span><span class="sxs-lookup"><span data-stu-id="e83bd-158">To define a method of a class:</span></span>  
  
```vb  
Class SampleClass  
    Public Function SampleFunc(ByVal SampleParam As String)  
        ' Add code here  
    End Function  
End Class  
```  
  
 <span data-ttu-id="e83bd-159">Una classe può avere diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o tipi di parametro.</span><span class="sxs-lookup"><span data-stu-id="e83bd-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>  
  
 <span data-ttu-id="e83bd-160">Per essere in rapporto di overload con un metodo:</span><span class="sxs-lookup"><span data-stu-id="e83bd-160">To overload a method:</span></span>  
  
```vb  
Overloads Sub Display(ByVal theChar As Char)  
    ' Add code that displays Char data.  
End Sub  
Overloads Sub Display(ByVal theInteger As Integer)  
    ' Add code that displays Integer data.  
End Sub  
```  
  
 <span data-ttu-id="e83bd-161">Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="e83bd-162">Tuttavia, Visual Basic supporta anche *metodi di estensione* che consente di aggiungere metodi a una classe esistente di fuori della definizione effettiva della classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>  
  
 <span data-ttu-id="e83bd-163">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-163">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-164">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="e83bd-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="e83bd-165">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="e83bd-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="e83bd-166">Overload</span><span class="sxs-lookup"><span data-stu-id="e83bd-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
-   [<span data-ttu-id="e83bd-167">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="e83bd-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
  
####  <span data-ttu-id="e83bd-168"><a name="Constructors"></a>Costruttori</span><span class="sxs-lookup"><span data-stu-id="e83bd-168"><a name="Constructors"></a> Constructors</span></span>  
 <span data-ttu-id="e83bd-169">I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="e83bd-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="e83bd-170">I costruttori in genere inizializzano i membri dati del nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="e83bd-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="e83bd-171">Un costruttore può essere eseguito solo una volta alla creazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="e83bd-172">Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="e83bd-173">Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.</span><span class="sxs-lookup"><span data-stu-id="e83bd-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>  
  
 <span data-ttu-id="e83bd-174">Per definire un costruttore per una classe:</span><span class="sxs-lookup"><span data-stu-id="e83bd-174">To define a constructor for a class:</span></span>  
  
```vb  
Class SampleClass  
    Sub New(ByVal s As String)  
        // Add code here.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="e83bd-175">Per ulteriori informazioni, vedere: [la durata degli oggetti: come gli oggetti sono creare e distruggere](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
####  <span data-ttu-id="e83bd-176"><a name="Destructors"></a>Distruttori</span><span class="sxs-lookup"><span data-stu-id="e83bd-176"><a name="Destructors"></a> Destructors</span></span>  
 <span data-ttu-id="e83bd-177">I distruttori sono utilizzati per distruggere istanze di classi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="e83bd-178">In .NET Framework, il Garbage Collector gestisce l'allocazione e il rilascio di memoria per gli oggetti gestiti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83bd-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="e83bd-179">Potrebbero, tuttavia, essere necessari distruttori per pulire eventuali risorse non gestite create dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e83bd-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="e83bd-180">Può esistere un solo distruttore per classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-180">There can be only one destructor for a class.</span></span>  
  
 <span data-ttu-id="e83bd-181">Per ulteriori informazioni sui distruttori e garbage collection in .NET Framework, vedere [operazione di Garbage Collection](../../../standard/garbagecollection/index.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbagecollection/index.md).</span></span>  
  
####  <span data-ttu-id="e83bd-182"><a name="Events"></a>Eventi</span><span class="sxs-lookup"><span data-stu-id="e83bd-182"><a name="Events"></a> Events</span></span>  
 <span data-ttu-id="e83bd-183">Tramite gli eventi una classe o un oggetto sono in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="e83bd-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="e83bd-184">La classe che invia (o genera) l'evento viene chiamata il *publisher* e le classi che ricevono (o gestiscono) l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="e83bd-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="e83bd-185">Per ulteriori informazioni sugli eventi, come essi vengono generati e gestiti, vedere [eventi](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span><span class="sxs-lookup"><span data-stu-id="e83bd-185">For more information about events, how they are raised and handled, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
-   <span data-ttu-id="e83bd-186">Per dichiarare gli eventi, utilizzare il [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
-   <span data-ttu-id="e83bd-187">Per generare eventi, utilizzare il [istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
-   <span data-ttu-id="e83bd-188">Per specificare i gestori eventi utilizzando una modalità dichiarativa, utilizzare il [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) istruzione e [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="e83bd-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>  
  
-   <span data-ttu-id="e83bd-189">Per poter aggiungere, rimuovere e modificare il gestore dell'evento associato a un evento, utilizzare il [AddHandler (istruzione)](../../../visual-basic/language-reference/statements/addhandler-statement.md) e [RemoveHandler (istruzione)](../../../visual-basic/language-reference/statements/removehandler-statement.md) con il [AddressOf (operatore)](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>  
  
####  <span data-ttu-id="e83bd-190"><a name="NestedClasses"></a>Classi annidate</span><span class="sxs-lookup"><span data-stu-id="e83bd-190"><a name="NestedClasses"></a> Nested Classes</span></span>  
 <span data-ttu-id="e83bd-191">Una classe definita all'interno di un'altra classe è denominata *nidificate*.</span><span class="sxs-lookup"><span data-stu-id="e83bd-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="e83bd-192">Per impostazione predefinita, la classe annidata è privata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-192">By default, the nested class is private.</span></span>  
  
```vb  
Class Container  
    Class Nested  
    ' Add code here.  
    End Class  
End Class  
```  
  
 <span data-ttu-id="e83bd-193">Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:</span><span class="sxs-lookup"><span data-stu-id="e83bd-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>  
  
```vb  
Dim nestedInstance As Container.Nested = New Container.Nested()  
```  
  
###  <span data-ttu-id="e83bd-194"><a name="AccessModifiers"></a>Modificatori di accesso e livelli di accesso</span><span class="sxs-lookup"><span data-stu-id="e83bd-194"><a name="AccessModifiers"></a> Access Modifiers and Access Levels</span></span>  
 <span data-ttu-id="e83bd-195">Tutte le classi e membri di classe possono specificare quale livello di accesso forniscono alle altre classi utilizzando *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="e83bd-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>  
  
 <span data-ttu-id="e83bd-196">Sono disponibili i seguenti modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="e83bd-196">The following access modifiers are available:</span></span>  
  
|<span data-ttu-id="e83bd-197">Modificatore di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83bd-197">Visual Basic Modifier</span></span>|<span data-ttu-id="e83bd-198">Definizione</span><span class="sxs-lookup"><span data-stu-id="e83bd-198">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="e83bd-199">Public</span><span class="sxs-lookup"><span data-stu-id="e83bd-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="e83bd-200">Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e83bd-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|  
|[<span data-ttu-id="e83bd-201">Private</span><span class="sxs-lookup"><span data-stu-id="e83bd-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="e83bd-202">Il tipo o il membro è accessibile solo dal codice nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-202">The type or member can only be accessed by code in the same class.</span></span>|  
|[<span data-ttu-id="e83bd-203">Protected</span><span class="sxs-lookup"><span data-stu-id="e83bd-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="e83bd-204">Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|  
|[<span data-ttu-id="e83bd-205">Friend</span><span class="sxs-lookup"><span data-stu-id="e83bd-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="e83bd-206">Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="e83bd-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|  
|`Protected Friend`|<span data-ttu-id="e83bd-207">Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="e83bd-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|  
  
 <span data-ttu-id="e83bd-208">Per ulteriori informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-208">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
###  <span data-ttu-id="e83bd-209"><a name="InstantiatingClasses"></a>Creazione di classi</span><span class="sxs-lookup"><span data-stu-id="e83bd-209"><a name="InstantiatingClasses"></a> Instantiating Classes</span></span>  
 <span data-ttu-id="e83bd-210">Per creare un oggetto, è necessario creare un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>  
  
```vb  
Dim sampleObject as New SampleClass()  
```  
  
 <span data-ttu-id="e83bd-211">Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>  
  
```vb  
' Set a property value.  
sampleObject.SampleProperty = "Sample String"  
' Call a method.  
sampleObject.SampleMethod()  
```  
  
 <span data-ttu-id="e83bd-212">Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:</span><span class="sxs-lookup"><span data-stu-id="e83bd-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>  
  
```vb  
Dim sampleObject = New SampleClass With   
    {.FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="e83bd-213">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-213">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-214">Operatore New</span><span class="sxs-lookup"><span data-stu-id="e83bd-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
  
-   [<span data-ttu-id="e83bd-215">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e83bd-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
  
###  <span data-ttu-id="e83bd-216"><a name="Static"></a>Le classi condivise e i membri</span><span class="sxs-lookup"><span data-stu-id="e83bd-216"><a name="Static"></a> Shared Classes and Members</span></span>  
 <span data-ttu-id="e83bd-217">Un membro condiviso della classe è una proprietà, procedura o campo condiviso da tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="e83bd-218">Per definire un membro condiviso:</span><span class="sxs-lookup"><span data-stu-id="e83bd-218">To define a shared member:</span></span>  
  
```vb  
Class SampleClass  
    Public Shared SampleString As String = "Sample String"  
End Class  
```  
  
 <span data-ttu-id="e83bd-219">Per accedere al membro condiviso, utilizzare il nome della classe senza creare un oggetto di questa classe:</span><span class="sxs-lookup"><span data-stu-id="e83bd-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>  
  
```vb  
MsgBox(SampleClass.SampleString)  
```  
  
 <span data-ttu-id="e83bd-220">Moduli condivisi in Visual Basic condiviso solo membri e non possono essere creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="e83bd-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="e83bd-221">Membri condivisi non possono accedere inoltre non condivisi di proprietà, campi o metodi</span><span class="sxs-lookup"><span data-stu-id="e83bd-221">Shared members also cannot access non-shared properties, fields or methods</span></span>  
  
 <span data-ttu-id="e83bd-222">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-222">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-223">Shared</span><span class="sxs-lookup"><span data-stu-id="e83bd-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
  
-   [<span data-ttu-id="e83bd-224">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="e83bd-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
###  <span data-ttu-id="e83bd-225"><a name="AnonymousTypes"></a>Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e83bd-225"><a name="AnonymousTypes"></a> Anonymous Types</span></span>  
 <span data-ttu-id="e83bd-226">I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e83bd-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="e83bd-227">La classe viene generata direttamente dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="e83bd-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="e83bd-228">La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e83bd-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>  
  
 <span data-ttu-id="e83bd-229">Per creare un'istanza di un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="e83bd-229">To create an instance of an anonymous type:</span></span>  
  
```vb  
' sampleObject is an instance of a simple anonymous type.  
Dim sampleObject =   
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="e83bd-230">Per ulteriori informazioni, vedere: [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="e83bd-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
##  <span data-ttu-id="e83bd-231"><a name="Inheritance"></a>Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e83bd-231"><a name="Inheritance"></a> Inheritance</span></span>  
 <span data-ttu-id="e83bd-232">L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="e83bd-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="e83bd-233">La classe i cui membri vengono ereditati è denominata la *classe di base*, mentre la classe che eredita tali membri è denominata la *derivata*.</span><span class="sxs-lookup"><span data-stu-id="e83bd-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="e83bd-234">Tuttavia, tutte le classi in Visual Basic ereditano in modo implicito dalla <xref:System.Object>classe che supporta la gerarchia di classi .NET e fornisce servizi di basso livello per tutte le classi.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="e83bd-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e83bd-235">Visual Basic non supporta l'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="e83bd-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="e83bd-236">Vale a dire, è possibile specificare solo una classe base per una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-236">That is, you can specify only one base class for a derived class.</span></span>  
  
 <span data-ttu-id="e83bd-237">Per ereditare da una classe base:</span><span class="sxs-lookup"><span data-stu-id="e83bd-237">To inherit from a base class:</span></span>  
  
```vb  
Class DerivedClass  
    Inherits BaseClass  
End Class  
```  
  
 <span data-ttu-id="e83bd-238">Per impostazione predefinita, tutte le classi possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="e83bd-238">By default all classes can be inherited.</span></span> <span data-ttu-id="e83bd-239">Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.</span><span class="sxs-lookup"><span data-stu-id="e83bd-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>  
  
 <span data-ttu-id="e83bd-240">Per specificare che una classe non può essere utilizzata come classe base:</span><span class="sxs-lookup"><span data-stu-id="e83bd-240">To specify that a class cannot be used as a base class:</span></span>  
  
```vb  
NotInheritable Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="e83bd-241">Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:</span><span class="sxs-lookup"><span data-stu-id="e83bd-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>  
  
```vb  
MustInherit Class BaseClass  
End Class  
```  
  
 <span data-ttu-id="e83bd-242">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-242">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-243">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="e83bd-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
  
-   [<span data-ttu-id="e83bd-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="e83bd-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
  
-   [<span data-ttu-id="e83bd-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="e83bd-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
  
###  <span data-ttu-id="e83bd-246"><a name="Overriding"></a>Override di membri</span><span class="sxs-lookup"><span data-stu-id="e83bd-246"><a name="Overriding"></a> Overriding Members</span></span>  
 <span data-ttu-id="e83bd-247">Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa.</span><span class="sxs-lookup"><span data-stu-id="e83bd-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="e83bd-248">Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override.</span><span class="sxs-lookup"><span data-stu-id="e83bd-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="e83bd-249">È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>  
  
 <span data-ttu-id="e83bd-250">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="e83bd-250">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
|<span data-ttu-id="e83bd-251">Modificatore di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83bd-251">Visual Basic Modifier</span></span>|<span data-ttu-id="e83bd-252">Definizione</span><span class="sxs-lookup"><span data-stu-id="e83bd-252">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="e83bd-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="e83bd-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="e83bd-254">Consente a un membro della classe di essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-254">Allows a class member to be overridden in a derived class.</span></span>|  
|[<span data-ttu-id="e83bd-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="e83bd-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="e83bd-256">Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="e83bd-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|  
|[<span data-ttu-id="e83bd-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e83bd-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="e83bd-258">Consente di impedire l'override di un membro in una classe che eredita.</span><span class="sxs-lookup"><span data-stu-id="e83bd-258">Prevents a member from being overridden in an inheriting class.</span></span>|  
|[<span data-ttu-id="e83bd-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e83bd-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="e83bd-260">Richiede che un membro della classe venga sottoposto a override nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e83bd-260">Requires that a class member to be overridden in the derived class.</span></span>|  
|[<span data-ttu-id="e83bd-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="e83bd-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="e83bd-262">Nasconde un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="e83bd-262">Hides a member inherited from a base class</span></span>|  
  
##  <span data-ttu-id="e83bd-263"><a name="Interfaces"></a>Interfacce</span><span class="sxs-lookup"><span data-stu-id="e83bd-263"><a name="Interfaces"></a> Interfaces</span></span>  
 <span data-ttu-id="e83bd-264">Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="e83bd-265">A differenza delle classi, però, le interfacce non forniscono l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e83bd-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="e83bd-266">Esse sono infatti implementate dalle classi e definite come entità distinte da queste.</span><span class="sxs-lookup"><span data-stu-id="e83bd-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="e83bd-267">Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.</span><span class="sxs-lookup"><span data-stu-id="e83bd-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>  
  
 <span data-ttu-id="e83bd-268">Per definire un'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="e83bd-268">To define an interface:</span></span>  
  
```vb  
Public Interface ISampleInterface  
    Sub DoSomething()  
End Interface  
```  
  
 <span data-ttu-id="e83bd-269">Per implementare un'interfaccia in una classe:</span><span class="sxs-lookup"><span data-stu-id="e83bd-269">To implement an interface in a class:</span></span>  
  
```vb  
Class SampleClass  
    Implements ISampleInterface  
    Sub DoSomething  
        ' Method implementation.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="e83bd-270">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-270">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-271">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e83bd-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
  
-   [<span data-ttu-id="e83bd-272">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="e83bd-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   [<span data-ttu-id="e83bd-273">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="e83bd-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
  
##  <span data-ttu-id="e83bd-274"><a name="Generics"></a>Generics</span><span class="sxs-lookup"><span data-stu-id="e83bd-274"><a name="Generics"></a> Generics</span></span>  
 <span data-ttu-id="e83bd-275">Classi, strutture, interfacce e metodi in .NET Framework possono includere *parametri di tipo* che definiscono i tipi di oggetti che possono archiviare o utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e83bd-275">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="e83bd-276">L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="e83bd-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  
  
 <span data-ttu-id="e83bd-277">Per definire una classe generica:</span><span class="sxs-lookup"><span data-stu-id="e83bd-277">To define a generic class:</span></span>  
  
```vb  
Class SampleGeneric(Of T)  
    Public Field As T  
End Class  
```  
  
 <span data-ttu-id="e83bd-278">Per creare un'istanza di una classe generica:</span><span class="sxs-lookup"><span data-stu-id="e83bd-278">To create an instance of a generic class:</span></span>  
  
```vb  
Dim sampleObject As New SampleGeneric(Of String)  
sampleObject.Field = "Sample string"  
```  
  
 <span data-ttu-id="e83bd-279">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-279">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-280">Generics</span><span class="sxs-lookup"><span data-stu-id="e83bd-280">Generics</span></span>](https://msdn.microsoft.com/library/ms172192)  
  
-   [<span data-ttu-id="e83bd-281">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83bd-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
  
##  <span data-ttu-id="e83bd-282"><a name="Delegates"></a>Delegati</span><span class="sxs-lookup"><span data-stu-id="e83bd-282"><a name="Delegates"></a> Delegates</span></span>  
 <span data-ttu-id="e83bd-283">Oggetto *delegare* è un tipo che definisce una firma di metodo e può fornire un riferimento a qualsiasi metodo con una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="e83bd-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="e83bd-284">Tramite il delegato è possibile invocare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="e83bd-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="e83bd-285">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="e83bd-285">Delegates are used to pass methods as arguments to other methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e83bd-286">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="e83bd-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="e83bd-287">Per ulteriori informazioni sull'utilizzo dei delegati nella gestione degli eventi, vedere [eventi](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span><span class="sxs-lookup"><span data-stu-id="e83bd-287">For more information about using delegates in event handling, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
 <span data-ttu-id="e83bd-288">Per creare un delegato:</span><span class="sxs-lookup"><span data-stu-id="e83bd-288">To create a delegate:</span></span>  
  
```vb  
Delegate Sub SampleDelegate(ByVal str As String)  
```  
  
 <span data-ttu-id="e83bd-289">Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:</span><span class="sxs-lookup"><span data-stu-id="e83bd-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>  
  
```vb  
Class SampleClass  
    ' Method that matches the SampleDelegate signature.  
    Sub SampleSub(ByVal str As String)  
        ' Add code here.  
    End Sub  
    ' Method that instantiates the delegate.  
    Sub SampleDelegateSub()  
        Dim sd As SampleDelegate = AddressOf SampleSub  
        sd("Sample string")  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="e83bd-290">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e83bd-290">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e83bd-291">Delegati</span><span class="sxs-lookup"><span data-stu-id="e83bd-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
  
-   [<span data-ttu-id="e83bd-292">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="e83bd-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
-   [<span data-ttu-id="e83bd-293">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="e83bd-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
  
## <a name="see-also"></a><span data-ttu-id="e83bd-294">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e83bd-294">See Also</span></span>  
 [<span data-ttu-id="e83bd-295">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83bd-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
