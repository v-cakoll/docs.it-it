---
title: Common Type System in dettaglio
description: Common Type System in dettaglio
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a><span data-ttu-id="7a775-104">Common Type System in dettaglio</span><span class="sxs-lookup"><span data-stu-id="7a775-104">Common type system in depth</span></span>

<span data-ttu-id="7a775-105">Questo argomento contiene le sezioni seguenti che illustrano Common Type System in dettaglio:</span><span class="sxs-lookup"><span data-stu-id="7a775-105">This topic contains the following sections that explore the common type system in depth:</span></span>

* [<span data-ttu-id="7a775-106">Tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="7a775-106">Types in .NET</span></span>](#types-in-net)

* [<span data-ttu-id="7a775-107">Definizioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-107">Type definitions</span></span>](#type-definitions)

* [<span data-ttu-id="7a775-108">Membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-108">Type members</span></span>](#type-members)

* [<span data-ttu-id="7a775-109">Caratteristiche dei membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-109">Characteristics of type members</span></span>](#characteristics-of-type-members)


## <a name="types-in-net"></a><span data-ttu-id="7a775-110">Tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="7a775-110">Types in .NET</span></span>

<span data-ttu-id="7a775-111">Tutti i tipi in .NET sono tipi valore o tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="7a775-111">All types in .NET are either value types or reference types.</span></span> 

<span data-ttu-id="7a775-112">I tipi di valore sono tipi di dati i cui oggetti sono rappresentati dal valore effettivo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7a775-112">Value types are data types whose objects are represented by the object's actual value.</span></span> <span data-ttu-id="7a775-113">Se un'istanza di un tipo di valore viene assegnata a una variabile, a tale variabile viene fornita una copia aggiornata del valore.</span><span class="sxs-lookup"><span data-stu-id="7a775-113">If an instance of a value type is assigned to a variable, that variable is given a fresh copy of the value.</span></span>

<span data-ttu-id="7a775-114">I tipi di riferimento sono tipi di dati i cui oggetti sono rappresentati da un riferimento (simile a un puntatore) al valore effettivo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7a775-114">Reference types are data types whose objects are represented by a reference (similar to a pointer) to the object's actual value.</span></span> <span data-ttu-id="7a775-115">Se un tipo di riferimento viene assegnato a una variabile, tale variabile fa riferimento (punta) al valore originale.</span><span class="sxs-lookup"><span data-stu-id="7a775-115">If a reference type is assigned to a variable, that variable references (points to) the original value.</span></span> <span data-ttu-id="7a775-116">Non viene effettuata alcuna copia.</span><span class="sxs-lookup"><span data-stu-id="7a775-116">No copy is made.</span></span> 

<span data-ttu-id="7a775-117">Common Type System in .NET supporta le cinque categorie di tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a775-117">The common type system in .NET supports the following five categories of types:</span></span>

* [<span data-ttu-id="7a775-118">Classi</span><span class="sxs-lookup"><span data-stu-id="7a775-118">Classes</span></span>](#classes)

* [<span data-ttu-id="7a775-119">Strutture</span><span class="sxs-lookup"><span data-stu-id="7a775-119">Structures</span></span>](#structures)

* [<span data-ttu-id="7a775-120">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="7a775-120">Enumerations</span></span>](#enumerations)

* [<span data-ttu-id="7a775-121">Interfacce</span><span class="sxs-lookup"><span data-stu-id="7a775-121">Interfaces</span></span>](#interfaces)

* [<span data-ttu-id="7a775-122">Delegati</span><span class="sxs-lookup"><span data-stu-id="7a775-122">Delegates</span></span>](#delegates)

### <a name="classes"></a><span data-ttu-id="7a775-123">Classi</span><span class="sxs-lookup"><span data-stu-id="7a775-123">Classes</span></span>

<span data-ttu-id="7a775-124">Una classe è un tipo riferimento che è possibile derivare direttamente da un'altra classe e che viene derivato in modo implicito da [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="7a775-124">A class is a reference type that can be derived directly from another class and that is derived implicitly from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="7a775-125">La classe definisce le operazioni che un oggetto (un'istanza della classe) può eseguire (metodi, eventi o proprietà) e i dati che l'oggetto contiene (campi).</span><span class="sxs-lookup"><span data-stu-id="7a775-125">The class defines the operations that an object (which is an instance of the class) can perform (methods, events, or properties) and the data that the object contains (fields).</span></span> <span data-ttu-id="7a775-126">Sebbene una classe includa in genere sia la definizione che l'implementazione, a differenza delle interfacce che contengono, ad esempio, solo la definizione senza l'implementazione, può contenere uno o più membri privi di implementazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-126">Although a class generally includes both definition and implementation (unlike interfaces, for example, which contain only definition without implementation), it can have one or more members that have no implementation.</span></span>

<span data-ttu-id="7a775-127">Nella tabella seguente vengono descritte alcune delle caratteristiche che una classe può avere.</span><span class="sxs-lookup"><span data-stu-id="7a775-127">The following table describes some of the characteristics that a class may have.</span></span> <span data-ttu-id="7a775-128">Ogni linguaggio che supporta il runtime fornisce un modo per indicare che una classe o membro di classe dispone di una o più di queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="7a775-128">Each language that supports the runtime provides a way to indicate that a class or class member has one or more of these characteristics.</span></span> <span data-ttu-id="7a775-129">È tuttavia possibile che i singoli linguaggi di programmazione destinati a .NET non rendano disponibili tutte queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="7a775-129">However, individual programming languages that target .NET may not make all these characteristics available.</span></span>

<span data-ttu-id="7a775-130">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7a775-130">Characteristic</span></span> | <span data-ttu-id="7a775-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a775-131">Description</span></span>
-------------- | -----------
<span data-ttu-id="7a775-132">sealed</span><span class="sxs-lookup"><span data-stu-id="7a775-132">sealed</span></span> | <span data-ttu-id="7a775-133">Specifica che da questo tipo non è possibile derivare un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="7a775-133">Specifies that another class cannot be derived from this type.</span></span>
<span data-ttu-id="7a775-134">implementa</span><span class="sxs-lookup"><span data-stu-id="7a775-134">implements</span></span> | <span data-ttu-id="7a775-135">Indica che la classe utilizza una o più interfacce fornendo implementazioni dei membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a775-135">Indicates that the class uses one or more interfaces by providing implementations of interface members.</span></span>
<span data-ttu-id="7a775-136">abstract</span><span class="sxs-lookup"><span data-stu-id="7a775-136">abstract</span></span> | <span data-ttu-id="7a775-137">Indica che non è possibile creare un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="7a775-137">Indicates that the class cannot be instantiated.</span></span> <span data-ttu-id="7a775-138">Per utilizzarla è necessario derivare da essa un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="7a775-138">To use it, you must derive another class from it.</span></span>
<span data-ttu-id="7a775-139">eredita</span><span class="sxs-lookup"><span data-stu-id="7a775-139">inherits</span></span> | <span data-ttu-id="7a775-140">Indica che le istanze della classe possono essere utilizzate ovunque la classe sia specificata.</span><span class="sxs-lookup"><span data-stu-id="7a775-140">Indicates that instances of the class can be used anywhere the base class is specified.</span></span> <span data-ttu-id="7a775-141">Una classe derivata che eredita da una classe di base può utilizzare l'implementazione di qualsiasi membro pubblico fornito dalla classe di base oppure la classe derivata può eseguire l'override dell'implementazione dei membri pubblici con la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-141">A derived class that inherits from a base class can use the implementation of any public members provided by the base class, or the derived class can override the implementation of the public members with its own implementation.</span></span>
<span data-ttu-id="7a775-142">exported o not exported</span><span class="sxs-lookup"><span data-stu-id="7a775-142">exported or not exported</span></span> | <span data-ttu-id="7a775-143">Indica se una classe è visibile all'esterno dell'assembly in cui è definita.</span><span class="sxs-lookup"><span data-stu-id="7a775-143">Indicates whether a class is visible outside the assembly in which it is defined.</span></span> <span data-ttu-id="7a775-144">Questa caratteristica è applicabile unicamente alle classi di primo livello e non alle classi annidate.</span><span class="sxs-lookup"><span data-stu-id="7a775-144">This characteristic applies only to top-level classes and not to nested classes.</span></span>

> [!NOTE]
> <span data-ttu-id="7a775-145">Una classe può anche essere annidata in una struttura o una classe padre.</span><span class="sxs-lookup"><span data-stu-id="7a775-145">A class can also be nested in a parent class or structure.</span></span> <span data-ttu-id="7a775-146">Anche le classi annidate possiedono le caratteristiche dei membri.</span><span class="sxs-lookup"><span data-stu-id="7a775-146">Nested classes also have member characteristics.</span></span> <span data-ttu-id="7a775-147">Per altre informazioni, vedere [Tipi annidati](#nested-types).</span><span class="sxs-lookup"><span data-stu-id="7a775-147">For more information, see [Nested types](#nested-types).</span></span>

<span data-ttu-id="7a775-148">I membri di classe privi di implementazione sono membri astratti.</span><span class="sxs-lookup"><span data-stu-id="7a775-148">Class members that have no implementation are abstract members.</span></span> <span data-ttu-id="7a775-149">Una classe con uno o più membri astratti è essa stessa astratta e non è possibile crearne nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="7a775-149">A class that has one or more abstract members is itself abstract; new instances of it cannot be created.</span></span> <span data-ttu-id="7a775-150">Con alcuni linguaggi destinati al runtime è possibile contrassegnare una classe come astratta anche se nessuno dei relativi membri è astratto.</span><span class="sxs-lookup"><span data-stu-id="7a775-150">Some languages that target the runtime let you mark a class as abstract even if none of its members are abstract.</span></span> <span data-ttu-id="7a775-151">È possibile utilizzare una classe astratta quando si desidera incapsulare un set di base di funzionalità che le classi derivate possono ereditare oppure sottoporre a override nelle circostanze appropriate.</span><span class="sxs-lookup"><span data-stu-id="7a775-151">You can use an abstract class when you want to encapsulate a basic set of functionality that derived classes can inherit or override when appropriate.</span></span> <span data-ttu-id="7a775-152">Alle classi che non sono astratte viene fatto riferimento come a classi concrete.</span><span class="sxs-lookup"><span data-stu-id="7a775-152">Classes that are not abstract are referred to as concrete classes.</span></span>

<span data-ttu-id="7a775-153">Una classe può implementare un numero qualsiasi di interfacce, ma può ereditare solo da una classe di base, oltre che da [System.Object](xref:System.Object), da cui tutte le classi ereditano in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="7a775-153">A class can implement any number of interfaces, but it can inherit from only one base class in addition to [System.Object](xref:System.Object), from which all classes inherit implicitly.</span></span> <span data-ttu-id="7a775-154">Tutte le classi devono avere almeno un costruttore, per l'inizializzazione di nuove istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="7a775-154">All classes must have at least one constructor, which initializes new instances of the class.</span></span> <span data-ttu-id="7a775-155">Se non si definisce in modo esplicito un costruttore, la maggior parte dei compilatori fornisce automaticamente un costruttore predefinito (senza parametri).</span><span class="sxs-lookup"><span data-stu-id="7a775-155">If you do not explicitly define a constructor, most compilers will automatically provide a default (parameterless) constructor.</span></span>

### <a name="structures"></a><span data-ttu-id="7a775-156">Strutture</span><span class="sxs-lookup"><span data-stu-id="7a775-156">Structures</span></span>

<span data-ttu-id="7a775-157">Una struttura è un tipo valore che deriva in modo implicito da [System.ValueType](xref:System.ValueType), che a sua volta deriva da [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="7a775-157">A structure is a value type that derives implicitly from [System.ValueType](xref:System.ValueType), which in turn is derived from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="7a775-158">Una struttura è molto utile per la rappresentazione di valori con requisiti di memoria piccoli e per passare valori come parametri per valori a metodi che dispongono di parametri fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="7a775-158">A structure is very useful for representing values whose memory requirements are small, and for passing values as by-value parameters to methods that have strongly typed parameters.</span></span> <span data-ttu-id="7a775-159">In .NET tutti i tipi di dati primitivi ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), e [UInt64](xref:System.UInt64)) sono definiti come strutture.</span><span class="sxs-lookup"><span data-stu-id="7a775-159">In .NET, all primitive data types ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), and [UInt64](xref:System.UInt64)) are defined as structures.</span></span>

<span data-ttu-id="7a775-160">Analogamente alle classi, le strutture definiscono sia i dati (i campi della struttura) che le operazioni che è possibile eseguire s tali dati (i metodi della struttura).</span><span class="sxs-lookup"><span data-stu-id="7a775-160">Like classes, structures define both data (the fields of the structure) and the operations that can be performed on that data (the methods of the structure).</span></span> <span data-ttu-id="7a775-161">Ciò significa che è possibile chiamare metodi nelle strutture, inclusi i metodi virtuali definiti nelle classi [System.Object](xref:System.Object) e [System.ValueType](xref:System.ValueType) e qualsiasi metodo definito nel tipo valore stesso.</span><span class="sxs-lookup"><span data-stu-id="7a775-161">This means that you can call methods on structures, including the virtual methods defined on the [System.Object](xref:System.Object) and [System.ValueType](xref:System.ValueType) classes, and any methods defined on the value type itself.</span></span> <span data-ttu-id="7a775-162">In altre parole, le strutture possono disporre di campi, proprietà ed eventi, nonché di metodi statici e non statici.</span><span class="sxs-lookup"><span data-stu-id="7a775-162">In other words, structures can have fields, properties, and events, as well as static and nonstatic methods.</span></span> <span data-ttu-id="7a775-163">È possibile creare istanze di strutture, passarle come parametri, archiviarle come variabili locali oppure in un campo di un altro tipo di valore o tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7a775-163">You can create instances of structures, pass them as parameters, store them as local variables, or store them in a field of another value type or reference type.</span></span> <span data-ttu-id="7a775-164">Le strutture possono inoltre implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="7a775-164">Structures can also implement interfaces.</span></span>

<span data-ttu-id="7a775-165">I tipi di valore differiscono dalle classi per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="7a775-165">Value types also differ from classes in several respects.</span></span> <span data-ttu-id="7a775-166">Per prima cosa, anche se ereditano in modo implicito da [System.ValueType](xref:System.ValueType), non possono ereditare direttamente da alcun tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-166">First, although they implicitly inherit from [System.ValueType](xref:System.ValueType), they cannot directly inherit from any type.</span></span> <span data-ttu-id="7a775-167">Analogamente, tutti i tipi di valore sono sealed, ovvero nessun altro tipo può essere derivato da essi.</span><span class="sxs-lookup"><span data-stu-id="7a775-167">Similarly, all value types are sealed, which means that no other type can be derived from them.</span></span> <span data-ttu-id="7a775-168">Non richiedono inoltre costruttori.</span><span class="sxs-lookup"><span data-stu-id="7a775-168">They also do not require constructors.</span></span>

<span data-ttu-id="7a775-169">Per ogni tipo di valore, Common Language Runtime fornisce un tipo sottoposto a boxing corrispondente, ovvero una classe avente lo stesso stato e lo stesso comportamento del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="7a775-169">For each value type, the common language runtime supplies a corresponding boxed type, which is a class that has the same state and behavior as the value type.</span></span> <span data-ttu-id="7a775-170">Un'istanza di un tipo valore viene sottoposta a boxing quando viene passata a un metodo che accetta un parametro di tipo [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="7a775-170">An instance of a value type is boxed when it is passed to a method that accepts a parameter of type [System.Object](xref:System.Object).</span></span> <span data-ttu-id="7a775-171">La conversione unboxing, ovvero la conversione da un'istanza di una classe di nuovo in un'istanza di un tipo di valore, viene eseguita quando il controllo viene restituito da una chiamata al metodo che accetta un tipo di valore come parametro per riferimento.</span><span class="sxs-lookup"><span data-stu-id="7a775-171">It is unboxed (that is, converted from an instance of a class back to an instance of a value type) when control returns from a method call that accepts a value type as a by-reference parameter.</span></span> <span data-ttu-id="7a775-172">In alcuni linguaggi è richiesto l'utilizzo di una sintassi speciale quando il tipo sottoposto a boxing è obbligatorio, mentre in altri il tipo sottoposto a boxing viene utilizzato automaticamente quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="7a775-172">Some languages require that you use special syntax when the boxed type is required; others automatically use the boxed type when it is needed.</span></span> <span data-ttu-id="7a775-173">Quando si definisce un tipo di valore si sta definendo sia il tipo boxed che il tipo unboxed.</span><span class="sxs-lookup"><span data-stu-id="7a775-173">When you define a value type, you are defining both the boxed and the unboxed type.</span></span>

### <a name="enumerations"></a><span data-ttu-id="7a775-174">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="7a775-174">Enumerations</span></span>

<span data-ttu-id="7a775-175">Un'enumerazione (enum) è un tipo valore che eredita direttamente da [System.Enum](xref:System.Enum) e che specifica nomi alternativi per i valori di un tipo primitivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="7a775-175">An enumeration (enum) is a value type that inherits directly from [System.Enum](xref:System.Enum) and that supplies alternate names for the values of an underlying primitive type.</span></span> <span data-ttu-id="7a775-176">Un tipo enumerazione ha un nome, un tipo sottostante che deve essere uno dei tipi intero con o senza segno predefinito, come ad esempio [Byte](xref:System.Byte), [Int32](xref:System.Int32), o [UInt64](xref:System.UInt64), e un set di campi.</span><span class="sxs-lookup"><span data-stu-id="7a775-176">An enumeration type has a name, an underlying type that must be one of the built-in signed or unsigned integer types (such as [Byte](xref:System.Byte), [Int32](xref:System.Int32), or [UInt64](xref:System.UInt64)), and a set of fields.</span></span> <span data-ttu-id="7a775-177">I campi sono campi letterali statici, ognuno dei quali rappresenta una costante.</span><span class="sxs-lookup"><span data-stu-id="7a775-177">The fields are static literal fields, each of which represents a constant.</span></span> <span data-ttu-id="7a775-178">Lo stesso valore può essere assegnato a più campi.</span><span class="sxs-lookup"><span data-stu-id="7a775-178">The same value can be assigned to multiple fields.</span></span> <span data-ttu-id="7a775-179">In questo caso, è necessario contrassegnare uno dei valori come valore di enumerazione primario a scopo di reflection e conversione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="7a775-179">When this occurs, you must mark one of the values as the primary enumeration value for reflection and string conversion.</span></span>

<span data-ttu-id="7a775-180">È possibile assegnare a un'enumerazione un valore del tipo sottostante e viceversa. Nel runtime non è richiesto alcun cast.</span><span class="sxs-lookup"><span data-stu-id="7a775-180">You can assign a value of the underlying type to an enumeration and vice versa (no cast is required by the runtime).</span></span> <span data-ttu-id="7a775-181">È possibile creare un'istanza di un'enumerazione e chiamare i metodi di [System.Enum](xref:System.Enum), nonché qualsiasi metodo definito nel tipo sottostante dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-181">You can create an instance of an enumeration and call the methods of [System.Enum](xref:System.Enum), as well as any methods defined on the enumeration's underlying type.</span></span> <span data-ttu-id="7a775-182">In alcuni linguaggi, tuttavia, potrebbe non essere possibile passare un'enumerazione come parametro quando un'istanza del tipo sottostante è obbligatoria (o viceversa).</span><span class="sxs-lookup"><span data-stu-id="7a775-182">However, some languages might not let you pass an enumeration as a parameter when an instance of the underlying type is required (or vice versa).</span></span>

<span data-ttu-id="7a775-183">Alle enumerazioni si applicano le seguenti ulteriori restrizioni:</span><span class="sxs-lookup"><span data-stu-id="7a775-183">The following additional restrictions apply to enumerations:</span></span> 

* <span data-ttu-id="7a775-184">La definizione dei metodi non può essere eseguita direttamente dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-184">They cannot define their own methods.</span></span>

* <span data-ttu-id="7a775-185">Con un'enumerazione non è possibile implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a775-185">They cannot implement interfaces.</span></span>

* <span data-ttu-id="7a775-186">Con un'enumerazione non è possibile definire proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="7a775-186">They cannot define properties or events.</span></span>

* <span data-ttu-id="7a775-187">Le enumerazioni non possono essere generiche, a meno che non siano generiche solo perché annidate all'interno di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="7a775-187">They cannot be generic, unless they are generic only because they are nested within a generic type.</span></span> <span data-ttu-id="7a775-188">In altre parole, un'enumerazione non può disporre di parametri di tipo propri.</span><span class="sxs-lookup"><span data-stu-id="7a775-188">That is, an enumeration cannot have type parameters of its own.</span></span> 

> [!NOTE]
> <span data-ttu-id="7a775-189">I tipi annidati, incluse le enumerazioni, creati con C# comprendono i parametri di tipo di tutti i tipi generici che li comprendono e sono pertanto generici anche se non hanno parametri di tipo propri.</span><span class="sxs-lookup"><span data-stu-id="7a775-189">Nested types (including enumerations) created with C# include the type parameters of all enclosing generic types, and are therefore generic even if they do not have type parameters of their own.</span></span> <span data-ttu-id="7a775-190">Per altre informazioni, vedere l'argomento di riferimento [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])).</span><span class="sxs-lookup"><span data-stu-id="7a775-190">For more information, see the [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) reference topic.</span></span> 

<span data-ttu-id="7a775-191">L'attributo [FlagsAttribute](xref:System.FlagsAttribute) denota un tipo speciale di enumerazione definito campo di bit.</span><span class="sxs-lookup"><span data-stu-id="7a775-191">The [FlagsAttribute](xref:System.FlagsAttribute) attribute denotes a special kind of enumeration called a bit field.</span></span> <span data-ttu-id="7a775-192">Nel runtime non viene fatta distinzione tra enumerazioni tradizionali e campi di bit, ma è possibile che tale distinzione esista nel linguaggio utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7a775-192">The runtime itself does not distinguish between traditional enumerations and bit fields, but your language might do so.</span></span> <span data-ttu-id="7a775-193">Quando tale distinzione viene effettuata, gli operatori bit per bit possono essere utilizzati sui campi di bit, ma non sulle enumerazioni, per generare valori non denominati.</span><span class="sxs-lookup"><span data-stu-id="7a775-193">When this distinction is made, bitwise operators can be used on bit fields, but not on enumerations, to generate unnamed values.</span></span> <span data-ttu-id="7a775-194">Le enumerazioni sono in genere utilizzate per elenchi di elementi univoci, come giorni della settimana o nomi di paesi o province.</span><span class="sxs-lookup"><span data-stu-id="7a775-194">Enumerations are generally used for lists of unique elements, such as days of the week, country or region names, and so on.</span></span> <span data-ttu-id="7a775-195">I campi di bit sono normalmente utilizzati per elenchi di qualità o quantità che possono ricorrere in combinazioni, come `Red And Big And Fast`.</span><span class="sxs-lookup"><span data-stu-id="7a775-195">Bit fields are generally used for lists of qualities or quantities that might occur in combination, such as `Red And Big And Fast`.</span></span>

<span data-ttu-id="7a775-196">Nell'esempio che segue viene illustrato come utilizzare sia i campi di bit, sia le enumerazioni tradizionali.</span><span class="sxs-lookup"><span data-stu-id="7a775-196">The following example shows how to use both bit fields and traditional enumerations.</span></span>

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a><span data-ttu-id="7a775-197">Interfacce</span><span class="sxs-lookup"><span data-stu-id="7a775-197">Interfaces</span></span>

<span data-ttu-id="7a775-198">Un'interfaccia definisce un contratto che specifica una relazione di tipo "può" o una relazione di tipo "ha".</span><span class="sxs-lookup"><span data-stu-id="7a775-198">An interface defines a contract that specifies a "can do" relationship or a "has a" relationship.</span></span> <span data-ttu-id="7a775-199">Le interfacce vengono spesso usate per implementare funzionalità, ad esempio il confronto e l'ordinamento (interfacce [IComparable](xref:System.IComparable) e [IComparable&lt;T&gt;](xref:System.IComparable%601)), il test di uguaglianza (interfaccia [IEquatable&lt;T&gt;](xref:System.IEquatable%601)) o l'enumerazione di elementi in una raccolta (interfacce [IEnumerable](xref:System.Collections.IEnumerable) e [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601)).</span><span class="sxs-lookup"><span data-stu-id="7a775-199">Interfaces are often used to implement functionality, such as comparing and sorting (the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces), testing for equality (the [IEquatable&lt;T&gt;](xref:System.IEquatable%601) interface), or enumerating items in a collection (the [IEnumerable](xref:System.Collections.IEnumerable) and [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) interfaces).</span></span> <span data-ttu-id="7a775-200">Le interfacce possono disporre di proprietà, metodi ed eventi, ovvero tutti membri astratti. Per questo motivo, anche se l'interfaccia definisce i membri e le relative firme, il compito di definire le funzionalità di ogni membro dell'interfaccia viene lasciato al tipo che la implementa.</span><span class="sxs-lookup"><span data-stu-id="7a775-200">Interfaces can have properties, methods, and events, all of which are abstract members; that is, although the interface defines the members and their signatures, it leaves it to the type that implements the interface to define the functionality of each interface member.</span></span> <span data-ttu-id="7a775-201">Ciò significa che qualsiasi classe o struttura che implementa un'interfaccia deve fornire le definizioni per i membri astratti dichiarati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a775-201">This means that any class or structure that implements an interface must supply definitions for the abstract members declared in the interface.</span></span> <span data-ttu-id="7a775-202">Un'interfaccia può richiedere che qualsiasi classe o struttura che la implementa implementi anche una o più altre interfacce.</span><span class="sxs-lookup"><span data-stu-id="7a775-202">An interface can require any implementing class or structure to also implement one or more other interfaces.</span></span>

<span data-ttu-id="7a775-203">Alle interfacce si applicano le seguenti restrizioni:</span><span class="sxs-lookup"><span data-stu-id="7a775-203">The following restrictions apply to interfaces:</span></span> 

* <span data-ttu-id="7a775-204">Un'interfaccia può essere dichiarata con qualsiasi accessibilità ma i membri di interfaccia devono tutti avere accessibilità pubblica.</span><span class="sxs-lookup"><span data-stu-id="7a775-204">An interface can be declared with any accessibility, but interface members must all have public accessibility.</span></span>

* <span data-ttu-id="7a775-205">Con un'interfaccia non è possibile definire costruttori.</span><span class="sxs-lookup"><span data-stu-id="7a775-205">Interfaces cannot define constructors.</span></span>

* <span data-ttu-id="7a775-206">Le interfacce non possono definire campi.</span><span class="sxs-lookup"><span data-stu-id="7a775-206">Interfaces cannot define fields.</span></span>

* <span data-ttu-id="7a775-207">Le interfacce possono definire solo membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="7a775-207">Interfaces can define only instance members.</span></span> <span data-ttu-id="7a775-208">Non possono definire membri statici.</span><span class="sxs-lookup"><span data-stu-id="7a775-208">They cannot define static members.</span></span>

<span data-ttu-id="7a775-209">Ogni linguaggio deve fornire regole per il mapping di un'implementazione all'interfaccia che richiede il membro, in quanto più interfacce possono dichiarare un membro con la stessa firma e i membri possono disporre di implementazioni separate.</span><span class="sxs-lookup"><span data-stu-id="7a775-209">Each language must provide rules for mapping an implementation to the interface that requires the member, because more than one interface can declare a member with the same signature, and these members can have separate implementations.</span></span>

### <a name="delegates"></a><span data-ttu-id="7a775-210">Delegati</span><span class="sxs-lookup"><span data-stu-id="7a775-210">Delegates</span></span>

<span data-ttu-id="7a775-211">I delegati sono tipi di riferimento che assolvono a una funzione simile a quella dei puntatori a funzione in C++.</span><span class="sxs-lookup"><span data-stu-id="7a775-211">Delegates are reference types that serve a purpose similar to that of function pointers in C++.</span></span> <span data-ttu-id="7a775-212">Vengono usati per i gestori di eventi e le funzioni di callback in .NET.</span><span class="sxs-lookup"><span data-stu-id="7a775-212">They are used for event handlers and callback functions in .NET.</span></span> <span data-ttu-id="7a775-213">Diversamente dai puntatori a funzione, i delegati sono sicuri, verificabili e indipendenti dai tipi.</span><span class="sxs-lookup"><span data-stu-id="7a775-213">Unlike function pointers, delegates are secure, verifiable, and type safe.</span></span> <span data-ttu-id="7a775-214">Un tipo delegato può rappresentare qualsiasi metodo di istanza o metodo statico con una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="7a775-214">A delegate type can represent any instance method or static method that has a compatible signature.</span></span> 

<span data-ttu-id="7a775-215">Un parametro di un delegato è compatibile con il parametro di un metodo corrispondente se il tipo del parametro del delegato è più restrittivo rispetto al tipo del parametro del metodo. In questo modo si garantisce che un argomento passato al delegato possa essere passato in modo sicuro al metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-215">A parameter of a delegate is compatible with the corresponding parameter of a method if the type of the delegate parameter is more restrictive than the type of the method parameter, because this guarantees that an argument passed to the delegate can be passed safely to the method.</span></span>

<span data-ttu-id="7a775-216">Analogamente, il tipo restituito di un delegato è compatibile con il tipo restituito di un metodo se il tipo restituito del metodo è più restrittivo rispetto al tipo restituito del delegato. In questo modo si garantisce la possibilità di eseguire in modo sicuro il cast del valore restituito del metodo nel tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="7a775-216">Similarly, the return type of a delegate is compatible with the return type of a method if the return type of the method is more restrictive than the return type of the delegate, because this guarantees that the return value of the method can be cast safely to the return type of the delegate.</span></span>

<span data-ttu-id="7a775-217">Un delegato con un parametro di tipo [IEnumerable](xref:System.Collections.IEnumerable) e un tipo restituito di tipo [Object](xref:System.Object) può, ad esempio, rappresentare un metodo con un parametro di tipo [Object](xref:System.Object) e un valore restituito di tipo [IEnumerable](xref:System.Collections.IEnumerable).</span><span class="sxs-lookup"><span data-stu-id="7a775-217">For example, a delegate that has a parameter of type [IEnumerable](xref:System.Collections.IEnumerable) and a return type of [Object](xref:System.Object) can represent a method that has a parameter of type [Object](xref:System.Object) and a return value of type [IEnumerable](xref:System.Collections.IEnumerable).</span></span> 

 <span data-ttu-id="7a775-218">Un delegato è associato al metodo che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="7a775-218">A delegate is said to be bound to the method it represents.</span></span> <span data-ttu-id="7a775-219">Oltre a essere associato al metodo, un delegato può essere associato a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7a775-219">In addition to being bound to the method, a delegate can be bound to an object.</span></span> <span data-ttu-id="7a775-220">L'oggetto rappresenta il primo parametro del metodo e viene passato al metodo ogni volta che viene richiamato il delegato.</span><span class="sxs-lookup"><span data-stu-id="7a775-220">The object represents the first parameter of the method, and is passed to the method every time the delegate is invoked.</span></span> <span data-ttu-id="7a775-221">Se il metodo è un metodo di istanza, l'oggetto associato viene passato come parametro `this` implicito (`Me` in Visual Basic). Se il metodo è statico, l'oggetto viene passato come primo parametro formale del metodo e la firma del delegato deve corrispondere ai parametri rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7a775-221">If the method is an instance method, the bound object is passed as the implicit `this` parameter (`Me` in Visual Basic); if the method is static, the object is passed as the first formal parameter of the method, and the delegate signature must match the remaining parameters.</span></span> 
 
 <span data-ttu-id="7a775-222">Tutti i delegati ereditano da [System.MulticastDelegate](xref:System.MulticastDelegate), che eredita da [System.Delegate](xref:System.Delegate).</span><span class="sxs-lookup"><span data-stu-id="7a775-222">All delegates inherit from [System.MulticastDelegate](xref:System.MulticastDelegate), which inherits from [System.Delegate](xref:System.Delegate).</span></span> <span data-ttu-id="7a775-223">I linguaggi C# e Visual Basic non consentono l'ereditarietà da questi tipi.</span><span class="sxs-lookup"><span data-stu-id="7a775-223">The C# and Visual Basic languages don't allow inheritance from these types.</span></span> <span data-ttu-id="7a775-224">Forniscono invece parole chiave per la dichiarazione di delegati.</span><span class="sxs-lookup"><span data-stu-id="7a775-224">Instead, they provide keywords for declaring delegates.</span></span>
 
 <span data-ttu-id="7a775-225">Dal momento che i delegati ereditano da [MulticastDelegate](xref:System.MulticastDelegate), hanno un elenco di chiamate, ovvero un elenco di metodi rappresentati dal delegato che vengono eseguiti quando il delegato viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="7a775-225">Because delegates inherit from [MulticastDelegate](xref:System.MulticastDelegate), a delegate has an invocation list, which is a list of methods that the delegate represents and that are executed when the delegate is invoked.</span></span> <span data-ttu-id="7a775-226">Tutti i metodi dell'elenco ricevono gli argomenti forniti quando viene chiamato il delegato.</span><span class="sxs-lookup"><span data-stu-id="7a775-226">All methods in the list receive the arguments supplied when the delegate is invoked.</span></span>

> [!NOTE]
> <span data-ttu-id="7a775-227">Il valore restituito non è definito per un delegato il cui elenco chiamate contiene più metodi, anche se il delegato dispone di un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="7a775-227">The return value is not defined for a delegate that has more than one method in its invocation list, even if the delegate has a return type.</span></span>

<span data-ttu-id="7a775-228">In molti casi, ad esempio con i metodi di callback, un delegato rappresenta un solo metodo e le uniche azioni che è necessario eseguire sono la creazione e il richiamo del delegato.</span><span class="sxs-lookup"><span data-stu-id="7a775-228">In many cases, such as with callback methods, a delegate represents only one method, and the only actions you have to take are creating the delegate and invoking it.</span></span> 

<span data-ttu-id="7a775-229">Per i delegati che rappresentano più metodi, .NET specifica metodi delle classi di delegati [Delegate](xref:System.Delegate) e [MulticastDelegate](xref:System.MulticastDelegate) per supportare operazioni quali l'aggiunta di un metodo a un elenco di chiamate di un delegato (il metodo [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate))), la rimozione di un metodo (il metodo [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate))) e il recupero dell'elenco di chiamate (il metodo [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList)).</span><span class="sxs-lookup"><span data-stu-id="7a775-229">For delegates that represent multiple methods, .NET provides methods of the [Delegate](xref:System.Delegate) and [MulticastDelegate](xref:System.MulticastDelegate) delegate classes to support operations such as adding a method to a delegate's invocation list (the [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) method), removing a method (the [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) method), and getting the invocation list (the [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) method).</span></span>

> [!NOTE]
> <span data-ttu-id="7a775-230">Non è necessario usare questi metodi per i delegati dei gestori di eventi nei linguaggi C# o Visual Basic perché questi linguaggi specificano la sintassi per l'aggiunta e la rimozione dei gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="7a775-230">It is not necessary to use these methods for event-handler delegates in C# or Visual Basic, because these languages provide syntax for adding and removing event handlers.</span></span>

## <a name="type-definitions"></a><span data-ttu-id="7a775-231">Definizioni di tipo</span><span class="sxs-lookup"><span data-stu-id="7a775-231">Type definitions</span></span>

<span data-ttu-id="7a775-232">Una definizione di tipo include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a775-232">A type definition includes the following:</span></span> 

* <span data-ttu-id="7a775-233">Gli eventuali attributi definiti per il tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-233">Any attributes defined on the type.</span></span>

* <span data-ttu-id="7a775-234">Accessibilità del tipo (visibilità)</span><span class="sxs-lookup"><span data-stu-id="7a775-234">The type's accessibility (visibility).</span></span>

* <span data-ttu-id="7a775-235">Il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-235">The type's name.</span></span>

* <span data-ttu-id="7a775-236">Il tipo base del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-236">The type's base type.</span></span>

* <span data-ttu-id="7a775-237">Le interfacce eventualmente implementate dal tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-237">Any interfaces implemented by the type.</span></span>

* <span data-ttu-id="7a775-238">Le definizioni per ciascuno dei membri del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-238">Definitions for each of the type's members.</span></span>

### <a name="attributes"></a><span data-ttu-id="7a775-239">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a775-239">Attributes</span></span>

<span data-ttu-id="7a775-240">Gli attributi forniscono metadati aggiuntivi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7a775-240">Attributes provide additional user-defined metadata.</span></span> <span data-ttu-id="7a775-241">Comunemente vengono utilizzati per archiviare informazioni aggiuntive su un tipo nell'assembly o per modificare il comportamento di un membro del tipo nella fase di progettazione o nell'ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="7a775-241">Most commonly, they are used to store additional information about a type in its assembly, or to modify the behavior of a type member in either the design-time or run-time environment.</span></span> 

<span data-ttu-id="7a775-242">Gli attributi stessi sono classi che ereditano da [System.Attribute](xref:System.Attribute).</span><span class="sxs-lookup"><span data-stu-id="7a775-242">Attributes are themselves classes that inherit from [System.Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="7a775-243">I linguaggi che supportano l'utilizzo di attributi forniscono ognuno la sintassi necessaria per l'applicazione degli attributi a un elemento del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="7a775-243">Languages that support the use of attributes each have their own syntax for applying attributes to a language element.</span></span> <span data-ttu-id="7a775-244">Gli attributi possono essere applicati a quasi tutti gli elementi del linguaggio. Gli elementi specifici a cui è possibile applicare un attributo sono definiti dall'oggetto [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) applicato alla classe di attributi.</span><span class="sxs-lookup"><span data-stu-id="7a775-244">Attributes can be applied to almost any language element; the specific elements to which an attribute can be applied are defined by the [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) that is applied to that attribute class.</span></span>

### <a name="type-accessibility"></a><span data-ttu-id="7a775-245">Accessibilità dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-245">Type accessibility</span></span>

<span data-ttu-id="7a775-246">Tutti i tipi dispongono di un modificatore che ne regola l'accessibilità da parte di altri tipi.</span><span class="sxs-lookup"><span data-stu-id="7a775-246">All types have a modifier that governs their accessibility from other types.</span></span> <span data-ttu-id="7a775-247">Nella tabella che segue si descrive l'accessibilità dei tipi supportata dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7a775-247">The following table describes the type accessibilities supported by the runtime.</span></span>

<span data-ttu-id="7a775-248">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="7a775-248">Accessibility</span></span> | <span data-ttu-id="7a775-249">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a775-249">Description</span></span>
------------- | -----------
<span data-ttu-id="7a775-250">public</span><span class="sxs-lookup"><span data-stu-id="7a775-250">public</span></span> | <span data-ttu-id="7a775-251">Il tipo è accessibile da tutti gli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a775-251">The type is accessible by all assemblies.</span></span>
<span data-ttu-id="7a775-252">assembly</span><span class="sxs-lookup"><span data-stu-id="7a775-252">assembly</span></span> | <span data-ttu-id="7a775-253">Il tipo è accessibile solo dall'interno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7a775-253">The type is accessible only from within its assembly.</span></span>

<span data-ttu-id="7a775-254">L'accessibilità di un tipo annidato dipende dal relativo dominio di accessibilità, che è determinato sia dall'accessibilità dichiarata del membro che dal dominio di accessibilità del tipo che lo contiene direttamente.</span><span class="sxs-lookup"><span data-stu-id="7a775-254">The accessibility of a nested type depends on its accessibility domain, which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="7a775-255">Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7a775-255">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>

<span data-ttu-id="7a775-256">Il dominio di accessibilità di un membro annidato `M` dichiarato in un tipo `T` all'interno di un programma `P` viene definito come riportato di seguito (si noti che `M` potrebbe essere a sua volta un tipo):</span><span class="sxs-lookup"><span data-stu-id="7a775-256">The accessibility domain of a nested member `M` declared in a type `T`within a program `P` is defined as follows (noting that `M` might itself be a type):</span></span> 

* <span data-ttu-id="7a775-257">Se l'accessibilità dichiarata di `M` è `public`, il dominio di accessibilità di `M` è il dominio di accessibilità di `T`.</span><span class="sxs-lookup"><span data-stu-id="7a775-257">If the declared accessibility of `M` is `public`, the accessibility domain of `M` is the accessibility domain of `T`.</span></span>

* <span data-ttu-id="7a775-258">Se l'accessibilità dichiarata di `M` è `protected internal`, il dominio di accessibilità di `M` è l'intersezione del dominio di accessibilità di `T` con il testo di programma di `P` e il testo di programma di qualsiasi tipo derivato da `T` dichiarato esternamente a `P`.</span><span class="sxs-lookup"><span data-stu-id="7a775-258">If the declared accessibility of `M` is `protected internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `P` and the program text of any type derived from `T` declared outside `P`.</span></span>

* <span data-ttu-id="7a775-259">Se l'accessibilità dichiarata di `M` è `protected`, il dominio di accessibilità di `M` è l'intersezione del dominio di accessibilità di `T` con il testo di programma di `T` e qualsiasi tipo derivato da `T`.</span><span class="sxs-lookup"><span data-stu-id="7a775-259">If the declared accessibility of `M` is `protected`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `T` and any type derived from `T`.</span></span>

* <span data-ttu-id="7a775-260">Se l'accessibilità dichiarata di `M` è `internal`, il dominio di accessibilità di `M` è l'intersezione del dominio di accessibilità di `T` con il testo di programma di `P`.</span><span class="sxs-lookup"><span data-stu-id="7a775-260">If the declared accessibility of `M` is `internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of`P`.</span></span>

* <span data-ttu-id="7a775-261">Se l'accessibilità dichiarata di `M` è `private`, il dominio di accessibilità di `M` è il testo di programma di `T`.</span><span class="sxs-lookup"><span data-stu-id="7a775-261">If the declared accessibility of `M` is `private`, the accessibility domain of `M` is the program text of `T`.</span></span>

### <a name="type-names"></a><span data-ttu-id="7a775-262">Nomi dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-262">Type names</span></span>

<span data-ttu-id="7a775-263">Il sistema di tipi comuni impone solo due restrizioni sui nomi:</span><span class="sxs-lookup"><span data-stu-id="7a775-263">The common type system imposes only two restrictions on names:</span></span> 

* <span data-ttu-id="7a775-264">Tutti i nomi sono codificati come stringhe di caratteri Unicode, ovvero a&16; bit.</span><span class="sxs-lookup"><span data-stu-id="7a775-264">All names are encoded as strings of Unicode (16-bit) characters.</span></span>

* <span data-ttu-id="7a775-265">I nomi non possono avere un valore incorporato (a 16 bit) pari a 0x0000.</span><span class="sxs-lookup"><span data-stu-id="7a775-265">Names are not permitted to have an embedded (16-bit) value of 0x0000.</span></span>

<span data-ttu-id="7a775-266">La maggior parte dei linguaggi impone tuttavia restrizioni aggiuntive per i nomi dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7a775-266">However, most languages impose additional restrictions on type names.</span></span> <span data-ttu-id="7a775-267">Poiché tutti i confronti vengono effettuati byte per byte, sono indipendenti dalle impostazioni locali e fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7a775-267">All comparisons are done on a byte-by-byte basis, and are therefore case-sensitive and locale-independent.</span></span>

<span data-ttu-id="7a775-268">Sebbene un tipo possa fare riferimento a tipi di altri moduli e assembly, deve essere definito completamente all'interno di un modulo .NET.</span><span class="sxs-lookup"><span data-stu-id="7a775-268">Although a type might reference types from other modules and assemblies, a type must be fully defined within one .NET module.</span></span> <span data-ttu-id="7a775-269">A seconda del supporto del compilatore, tuttavia, può essere diviso in più file di codice sorgente. I nomi dei tipi devono essere univoci solo all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7a775-269">(Depending on compiler support, however, it can be divided into multiple source code files.) Type names need be unique only within a namespace.</span></span> <span data-ttu-id="7a775-270">Per identificare completamente un tipo, il relativo nome deve essere qualificato dallo spazio dei nomi che contiene l'implementazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-270">To fully identify a type, the type name must be qualified by the namespace that contains the implementation of the type.</span></span>

### <a name="base-types-and-interfaces"></a><span data-ttu-id="7a775-271">Tipi di base e interfacce</span><span class="sxs-lookup"><span data-stu-id="7a775-271">Base types and interfaces</span></span>

<span data-ttu-id="7a775-272">Un tipo può ereditare valori e comportamenti da un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-272">A type can inherit values and behaviors from another type.</span></span> <span data-ttu-id="7a775-273">Common Type System non consente ai tipi di ereditare da più di un tipo base.</span><span class="sxs-lookup"><span data-stu-id="7a775-273">The common type system does not allow types to inherit from more than one base type.</span></span>

<span data-ttu-id="7a775-274">Un tipo può implementare un numero indefinito di interfacce.</span><span class="sxs-lookup"><span data-stu-id="7a775-274">A type can implement any number of interfaces.</span></span> <span data-ttu-id="7a775-275">Per implementare un'interfaccia un tipo deve implementare tutti i membri virtuali di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a775-275">To implement an interface, a type must implement all the virtual members of that interface.</span></span> <span data-ttu-id="7a775-276">Un metodo virtuale può essere implementato da un tipo derivato e può essere richiamato in modo statico o dinamico.</span><span class="sxs-lookup"><span data-stu-id="7a775-276">A virtual method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span>

## <a name="type-members"></a><span data-ttu-id="7a775-277">Membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-277">Type members</span></span>

<span data-ttu-id="7a775-278">Il runtime consente di definire membri del tipo per specificare il comportamento e lo stato di un tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-278">The runtime enables you to define members of your type, which specifies the behavior and state of a type.</span></span> <span data-ttu-id="7a775-279">I membri dei tipi includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a775-279">Type members include the following:</span></span>

* [<span data-ttu-id="7a775-280">Campi</span><span class="sxs-lookup"><span data-stu-id="7a775-280">Fields</span></span>](#fields)

* [<span data-ttu-id="7a775-281">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7a775-281">Properties</span></span>](#properties)

* [<span data-ttu-id="7a775-282">Metodi</span><span class="sxs-lookup"><span data-stu-id="7a775-282">Methods</span></span>](#methods)

* [<span data-ttu-id="7a775-283">Costruttori</span><span class="sxs-lookup"><span data-stu-id="7a775-283">Constructors</span></span>](#constructors)

* [<span data-ttu-id="7a775-284">Eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-284">Events</span></span>](#events)

* [<span data-ttu-id="7a775-285">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="7a775-285">Nested types</span></span>](#nested-types)

### <a name="fields"></a><span data-ttu-id="7a775-286">Campi</span><span class="sxs-lookup"><span data-stu-id="7a775-286">Fields</span></span>

<span data-ttu-id="7a775-287">Un campo descrive e contiene parte dello stato del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-287">A field describes and contains part of the type's state.</span></span> <span data-ttu-id="7a775-288">I campi possono essere di qualsiasi tipo supportato dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7a775-288">Fields can be of any type supported by the runtime.</span></span> <span data-ttu-id="7a775-289">Nella maggior parte dei casi, i campi sono `private` o `protected`, in modo che siano accessibili solo dall'interno della classe o da una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="7a775-289">Most commonly, fields are either `private` or `protected`, so that they are accessible only from within the class or from a derived class.</span></span> <span data-ttu-id="7a775-290">Se il valore di un campo può essere modificato dall'esterno del relativo tipo, viene in genere utilizzata una funzione di accesso set della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a775-290">If the value of a field can be modified from outside its type, a property set accessor is typically used.</span></span> <span data-ttu-id="7a775-291">I campi esposti pubblicamente sono in genere di sola lettura e possono essere di due tipi:</span><span class="sxs-lookup"><span data-stu-id="7a775-291">Publicly exposed fields are usually read-only and can be of two types:</span></span> 

* <span data-ttu-id="7a775-292">Costanti, il cui valore viene assegnato durante la fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-292">Constants, whose value is assigned at design time.</span></span> <span data-ttu-id="7a775-293">Si tratta di membri statici di una classe, sebbene non vengano definiti utilizzando la parola chiave `static` (`Shared` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="7a775-293">These are static members of a class, although they are not defined using the `static` (`Shared` in Visual Basic) keyword.</span></span>

* <span data-ttu-id="7a775-294">Variabili di sola lettura, i cui valori possono essere assegnati nel costruttore di classi.</span><span class="sxs-lookup"><span data-stu-id="7a775-294">Read-only variables, whose values can be assigned in the class constructor.</span></span>

<span data-ttu-id="7a775-295">Nell'esempio seguente vengono illustrati questi due utilizzi di campi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7a775-295">The following example illustrates these two usages of read-only fields.</span></span>

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a><span data-ttu-id="7a775-296">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7a775-296">Properties</span></span>

<span data-ttu-id="7a775-297">Una proprietà consente di denominare un valore o uno stato del tipo e di definire i metodi per ottenere o impostare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a775-297">A property names a value or state of the type and defines methods for getting or setting the property's value.</span></span> <span data-ttu-id="7a775-298">Le proprietà possono essere tipi primitivi, raccolte di tipi primitivi, tipi definiti dall'utente, oppure raccolte di tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7a775-298">Properties can be primitive types, collections of primitive types, user-defined types, or collections of user-defined types.</span></span> <span data-ttu-id="7a775-299">Sono spesso utilizzate per mantenere l'interfaccia pubblica di un tipo indipendente dalla sua effettiva rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-299">Properties are often used to keep the public interface of a type independent from the type's actual representation.</span></span> <span data-ttu-id="7a775-300">In questo modo le proprietà riflettono valori che non sono archiviati direttamente nella classe, ad esempio quando una proprietà restituisce un valore calcolato, oppure eseguono la convalida prima che i valori vengano assegnati a campi privati.</span><span class="sxs-lookup"><span data-stu-id="7a775-300">This enables properties to reflect values that are not directly stored in the class (for example, when a property returns a computed value) or to perform validation before values are assigned to private fields.</span></span> <span data-ttu-id="7a775-301">Nell'esempio seguente viene illustrato quest'ultimo caso.</span><span class="sxs-lookup"><span data-stu-id="7a775-301">The following example illustrates the latter pattern.</span></span>

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

<span data-ttu-id="7a775-302">Oltre a includere la proprietà stessa, Microsoft Intermediate Language (MSIL) per un tipo contenente una proprietà leggibile include un metodo `get`*_propertyname* e per un tipo contenente una proprietà scrivibile include un metodo `set`*_propertyname*.</span><span class="sxs-lookup"><span data-stu-id="7a775-302">In addition to including the property itself, the Microsoft intermediate language (MSIL) for a type that contains a readable property includes a `get`*_propertyname* method, and the MSIL for a type that contains a writable property includes a `set`*_propertyname* method.</span></span>

### <a name="methods"></a><span data-ttu-id="7a775-303">Metodi</span><span class="sxs-lookup"><span data-stu-id="7a775-303">Methods</span></span>

<span data-ttu-id="7a775-304">Un metodo descrive le operazioni disponibili sul tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-304">A method describes operations that are available on the type.</span></span> <span data-ttu-id="7a775-305">Nella firma di un metodo sono specificati i tipi consentiti di tutti i relativi parametri e del relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="7a775-305">A method's signature specifies the allowable types of all its parameters and of its return value.</span></span>

<span data-ttu-id="7a775-306">Sebbene molti metodi definiscono il numero preciso di parametri necessari per le chiamate al metodo, alcuni metodi supportano un numero di parametri variabile.</span><span class="sxs-lookup"><span data-stu-id="7a775-306">Although most methods define the precise number of parameters required for method calls, some methods support a variable number of parameters.</span></span> <span data-ttu-id="7a775-307">Il parametro finale dichiarato di questi metodi è contrassegnato con l'attributo [ParamArrayAttribute](xref:System.ParamArrayAttribute).</span><span class="sxs-lookup"><span data-stu-id="7a775-307">The final declared parameter of these methods is marked with the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute.</span></span> <span data-ttu-id="7a775-308">I compilatori di linguaggio specificano in genere una parola chiave, ad esempio `params` in C# e `ParamArray` in Visual Basic, che usa esplicitamente l'attributo [ParamArrayAttribute](xref:System.ParamArrayAttribute) non necessario.</span><span class="sxs-lookup"><span data-stu-id="7a775-308">Language compilers typically provide a keyword, such as `params` in C# and `ParamArray` in Visual Basic, that makes explicit use of [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnecessary.</span></span>

### <a name="constructors"></a><span data-ttu-id="7a775-309">Costruttori</span><span class="sxs-lookup"><span data-stu-id="7a775-309">Constructors</span></span>

<span data-ttu-id="7a775-310">Un costruttore è un tipo speciale di metodo che consente di creare nuove istanze di una classe o di una struttura.</span><span class="sxs-lookup"><span data-stu-id="7a775-310">A constructor is a special kind of method that creates new instances of a class or structure.</span></span> <span data-ttu-id="7a775-311">Analogamente a ogni altro metodo, un costruttore può includere parametri. I costruttori, tuttavia, non restituiscono alcun valore, ovvero restituiscono `void`.</span><span class="sxs-lookup"><span data-stu-id="7a775-311">Like any other method, a constructor can include parameters; however, constructors have no return value (that is, they return `void`).</span></span> 

<span data-ttu-id="7a775-312">Se il codice sorgente per una classe non definisce in modo esplicito un costruttore, il compilatore include un costruttore predefinito (senza parametri).</span><span class="sxs-lookup"><span data-stu-id="7a775-312">If the source code for a class does not explicitly define a constructor, the compiler includes a default (parameterless) constructor.</span></span> <span data-ttu-id="7a775-313">Se tuttavia il codice sorgente per una classe definisce solo costruttori con parametri, il compilatore di C# non genera un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="7a775-313">However, if the source code for a class defines only parameterized constructors, the C# compiler doesn't generate a parameterless constructor.</span></span>

<span data-ttu-id="7a775-314">Se il codice sorgente per una struttura definisce i costruttori, essi devono essere con parametri. Una struttura non può definire un costruttore predefinito (senza parametri) e i compilatori non generano costruttori senza parametri per strutture o altri tipi di valori.</span><span class="sxs-lookup"><span data-stu-id="7a775-314">If the source code for a structure defines constructors, they must be parameterized; a structure cannot define a default (parameterless) constructor, and compilers do not generate parameterless constructors for structures or other value types.</span></span> <span data-ttu-id="7a775-315">Tutti i tipi di valori hanno un costruttore predefinito implicito.</span><span class="sxs-lookup"><span data-stu-id="7a775-315">All value types do have an implicit default constructor.</span></span> <span data-ttu-id="7a775-316">Questo costruttore viene implementato da Common Language Runtime e inizializza tutti i campi della struttura sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7a775-316">This constructor is implemented by the common language runtime and initializes all fields of the structure to their default values.</span></span> 

### <a name="events"></a><span data-ttu-id="7a775-317">Eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-317">Events</span></span>

<span data-ttu-id="7a775-318">Un evento definisce una situazione a cui è possibile fornire risposta e metodi per la sottoscrizione, l'annullamento della sottoscrizione e la generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7a775-318">An event defines an incident that can be responded to, and defines methods for subscribing to, unsubscribing from, and raising the event.</span></span> <span data-ttu-id="7a775-319">Gli eventi sono spesso utilizzati per indicare modifiche di stato a tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="7a775-319">Events are often used to inform other types of state changes.</span></span>

### <a name="nested-types"></a><span data-ttu-id="7a775-320">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="7a775-320">Nested types</span></span>

<span data-ttu-id="7a775-321">I tipi annidati sono tipi membri di altri tipi.</span><span class="sxs-lookup"><span data-stu-id="7a775-321">A nested type is a type that is a member of some other type.</span></span> <span data-ttu-id="7a775-322">I tipi annidati devono essere strettamente collegati ai rispettivi tipi contenitori e non devono essere utilizzati come tipi generici.</span><span class="sxs-lookup"><span data-stu-id="7a775-322">Nested types should be tightly coupled to their containing type and must not be useful as a general-purpose type.</span></span> <span data-ttu-id="7a775-323">I tipi annidati risultano utili quando il tipo dichiarante utilizza e crea istanze del tipo annidato e quando il loro utilizzo non viene esposto in membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="7a775-323">Nested types are useful when the declaring type uses and creates instances of the nested type, and use of the nested type is not exposed in public members.</span></span>

<span data-ttu-id="7a775-324">Per alcuni sviluppatori i tipi annidati possono generare confusione e dovrebbero essere visibili pubblicamente solo in casi di assoluta necessità.</span><span class="sxs-lookup"><span data-stu-id="7a775-324">Nested types are confusing to some developers and should not be publicly visible unless there is a compelling reason for visibility.</span></span> <span data-ttu-id="7a775-325">In una libreria progettata correttamente è improbabile che gli sviluppatori debbano utilizzare tipi annidati per creare istanze di oggetti o dichiarare variabili.</span><span class="sxs-lookup"><span data-stu-id="7a775-325">In a well-designed library, developers should rarely have to use nested types to instantiate objects or declare variables.</span></span>

## <a name="characteristics-of-type-members"></a><span data-ttu-id="7a775-326">Caratteristiche dei membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="7a775-326">Characteristics of type members</span></span>

<span data-ttu-id="7a775-327">In Common Type System i membri dei tipi possono disporre di caratteristiche diverse, anche se non è necessario che i linguaggi le supportino tutte.</span><span class="sxs-lookup"><span data-stu-id="7a775-327">The common type system allows type members to have a variety of characteristics; however, languages are not required to support all these characteristics.</span></span> <span data-ttu-id="7a775-328">Nella tabella riportata di seguito vengono descritte le caratteristiche dei membri.</span><span class="sxs-lookup"><span data-stu-id="7a775-328">The following table describes member characteristics.</span></span>

<span data-ttu-id="7a775-329">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7a775-329">Characteristic</span></span> | <span data-ttu-id="7a775-330">Si applica a</span><span class="sxs-lookup"><span data-stu-id="7a775-330">Can apply to</span></span> | <span data-ttu-id="7a775-331">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a775-331">Description</span></span>
-------------- | ------------ | -----------
<span data-ttu-id="7a775-332">abstract</span><span class="sxs-lookup"><span data-stu-id="7a775-332">abstract</span></span> | <span data-ttu-id="7a775-333">Metodi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-333">Methods, properties, and events</span></span> | <span data-ttu-id="7a775-334">Il tipo non fornisce l'implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-334">The type does not supply the method's implementation.</span></span> <span data-ttu-id="7a775-335">I tipi che ereditano o implementano metodi astratti devono fornire un'implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-335">Types that inherit or implement abstract methods must supply an implementation for the method.</span></span> <span data-ttu-id="7a775-336">L'unica eccezione si verifica nel caso in cui il tipo derivato sia esso stesso un tipo astratto.</span><span class="sxs-lookup"><span data-stu-id="7a775-336">The only exception is when the derived type is itself an abstract type.</span></span> <span data-ttu-id="7a775-337">Tutti i metodi astratti sono virtuali.</span><span class="sxs-lookup"><span data-stu-id="7a775-337">All abstract methods are virtual.</span></span>
<span data-ttu-id="7a775-338">private</span><span class="sxs-lookup"><span data-stu-id="7a775-338">private</span></span> | <span data-ttu-id="7a775-339">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-339">All</span></span> | <span data-ttu-id="7a775-340">Accessibile solo dall'interno dello stesso tipo del membro o di un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="7a775-340">Accessible only from within the same type as the member, or within a nested type.</span></span>
<span data-ttu-id="7a775-341">family</span><span class="sxs-lookup"><span data-stu-id="7a775-341">family</span></span> | <span data-ttu-id="7a775-342">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-342">All</span></span> | <span data-ttu-id="7a775-343">Accessibile dall'interno dello stesso tipo del membro e dai tipi derivati che ereditano da esso.</span><span class="sxs-lookup"><span data-stu-id="7a775-343">Accessible from within the same type as the member, and from derived types that inherit from it.</span></span>
<span data-ttu-id="7a775-344">assemby</span><span class="sxs-lookup"><span data-stu-id="7a775-344">assemby</span></span> | <span data-ttu-id="7a775-345">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-345">All</span></span> | <span data-ttu-id="7a775-346">Accessibile solo nell'assembly nel quale il tipo viene definito.</span><span class="sxs-lookup"><span data-stu-id="7a775-346">Accessible only in the assembly in which the type is defined.</span></span>
<span data-ttu-id="7a775-347">family e assembly</span><span class="sxs-lookup"><span data-stu-id="7a775-347">family and assembly</span></span> | <span data-ttu-id="7a775-348">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-348">All</span></span> | <span data-ttu-id="7a775-349">Accessibile solo dai tipi che sono qualificati sia per l'accesso di gruppo che di assembly.</span><span class="sxs-lookup"><span data-stu-id="7a775-349">Accessible only from types that qualify for both family and assembly access.</span></span>
<span data-ttu-id="7a775-350">family o assembly</span><span class="sxs-lookup"><span data-stu-id="7a775-350">family or assemby</span></span> | <span data-ttu-id="7a775-351">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-351">All</span></span> | <span data-ttu-id="7a775-352">Accessibile solo dai tipi che sono qualificati per l'accesso di gruppo o per quello di assembly.</span><span class="sxs-lookup"><span data-stu-id="7a775-352">Accessible only from types that qualify for either family or assembly access.</span></span>
<span data-ttu-id="7a775-353">public</span><span class="sxs-lookup"><span data-stu-id="7a775-353">public</span></span> | <span data-ttu-id="7a775-354">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-354">All</span></span> | <span data-ttu-id="7a775-355">Accessibile da qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-355">Accessible from any type.</span></span>
<span data-ttu-id="7a775-356">final</span><span class="sxs-lookup"><span data-stu-id="7a775-356">final</span></span> | <span data-ttu-id="7a775-357">Metodi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-357">Methods, properties, and events</span></span> | <span data-ttu-id="7a775-358">Il metodo virtuale non può essere sottoposto a override in un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="7a775-358">The virtual method cannot be overridden in a derived type.</span></span>
<span data-ttu-id="7a775-359">initialize-only</span><span class="sxs-lookup"><span data-stu-id="7a775-359">initialize-only</span></span> | <span data-ttu-id="7a775-360">Campi</span><span class="sxs-lookup"><span data-stu-id="7a775-360">Fields</span></span> | <span data-ttu-id="7a775-361">Il valore può essere solo inizializzato e non può essere scritto dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-361">The value can only be initialized, and cannot be written after initialization.</span></span>
<span data-ttu-id="7a775-362">istanza</span><span class="sxs-lookup"><span data-stu-id="7a775-362">instance</span></span> | <span data-ttu-id="7a775-363">Campi, metodi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-363">Fields, methods, properties, and events</span></span> | <span data-ttu-id="7a775-364">Se un membro non è contrassegnato come `static` (C#), `Shared` (Visual Basic), `virtual` (C#) o `Overridable` (Visual Basic), è un membro di istanza (nessuna parola chiave di istanza).</span><span class="sxs-lookup"><span data-stu-id="7a775-364">If a member is not marked as `static` (C#), `Shared` (Visual Basic), `virtual` (C#), or `Overridable` (Visual Basic),  it is an instance member (there is no instance keyword).</span></span> <span data-ttu-id="7a775-365">Ci saranno tante copie di tali membri in memoria quanti sono gli oggetti che li utilizzano.</span><span class="sxs-lookup"><span data-stu-id="7a775-365">There will be as many copies of such members in memory as there are objects that use it.</span></span>
<span data-ttu-id="7a775-366">valore letterale</span><span class="sxs-lookup"><span data-stu-id="7a775-366">literal</span></span> | <span data-ttu-id="7a775-367">Campi</span><span class="sxs-lookup"><span data-stu-id="7a775-367">Fields</span></span> | <span data-ttu-id="7a775-368">Il valore assegnato al campo è un valore fisso, noto in fase di compilazione, di un tipo di valore incorporato.</span><span class="sxs-lookup"><span data-stu-id="7a775-368">The value assigned to the field is a fixed value, known at compile time, of a built-in value type.</span></span> <span data-ttu-id="7a775-369">Ai campi literal viene a volte fatto riferimento come a costanti.</span><span class="sxs-lookup"><span data-stu-id="7a775-369">Literal fields are sometimes referred to as constants.</span></span>
<span data-ttu-id="7a775-370">newslot o override</span><span class="sxs-lookup"><span data-stu-id="7a775-370">newslot or override</span></span> | <span data-ttu-id="7a775-371">Tutti</span><span class="sxs-lookup"><span data-stu-id="7a775-371">All</span></span> | <span data-ttu-id="7a775-372">Definisce come il membro interagisce con membri ereditati aventi la stessa firma: `newslot` nasconde i membri ereditati aventi la stessa firma; `override` sostituisce la definizione di un metodo virtuale ereditato.</span><span class="sxs-lookup"><span data-stu-id="7a775-372">Defines how the member interacts with inherited members that have the same signature: `newslot` hides inherited members that have the same signature; `override` replaces the definition of an inherited virtual method.</span></span> <span data-ttu-id="7a775-373">Il valore predefinito è newslot.</span><span class="sxs-lookup"><span data-stu-id="7a775-373">The default is newslot.</span></span>
<span data-ttu-id="7a775-374">statico</span><span class="sxs-lookup"><span data-stu-id="7a775-374">static</span></span> | <span data-ttu-id="7a775-375">Campi, metodi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-375">Fields, methods, properties, and events</span></span> | <span data-ttu-id="7a775-376">Il membro appartiene al tipo sul quale viene definito, non a un'istanza specifica del tipo. Il membro esiste anche se non viene creata un'istanza del tipo ed è condiviso tra tutte le istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="7a775-376">The member belongs to the type it is defined on, not to a particular instance of the type; the member exists even if an instance of the type is not created, and it is shared among all instances of the type.</span></span>
<span data-ttu-id="7a775-377">virtuale</span><span class="sxs-lookup"><span data-stu-id="7a775-377">virtual</span></span> | <span data-ttu-id="7a775-378">Metodi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="7a775-378">Methods, properties, and events</span></span> | <span data-ttu-id="7a775-379">Il metodo può essere implementato da un tipo derivato e può essere richiamato in modo statico o dinamico.</span><span class="sxs-lookup"><span data-stu-id="7a775-379">The method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span> <span data-ttu-id="7a775-380">Se viene utilizzata la chiamata dinamica, il tipo dell'istanza che effettua la chiamata in fase di esecuzione, e non il tipo noto in fase di compilazione, determina l'implementazione del metodo chiamata.</span><span class="sxs-lookup"><span data-stu-id="7a775-380">If dynamic invocation is used, the type of the instance that makes the call at run time (rather than the type known at compile time) determines which implementation of the method is called.</span></span> <span data-ttu-id="7a775-381">Per richiamare un metodo virtuale in modo statico, potrebbe essere necessario eseguire il cast della variabile in un tipo che utilizza la versione desiderata del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-381">To invoke a virtual method statically, the variable might have to be cast to a type that uses the desired version of the method.</span></span>

### <a name="overloading"></a><span data-ttu-id="7a775-382">Overload</span><span class="sxs-lookup"><span data-stu-id="7a775-382">Overloading</span></span>

<span data-ttu-id="7a775-383">Ciascun membro di tipo dispone di una firma univoca.</span><span class="sxs-lookup"><span data-stu-id="7a775-383">Each type member has a unique signature.</span></span> <span data-ttu-id="7a775-384">La firma di un metodo è costituita dal nome del metodo e da un elenco di parametri, ovvero l'ordine e i tipi degli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-384">Method signatures consist of the method name and a parameter list (the order and types of the method's arguments).</span></span> <span data-ttu-id="7a775-385">All'interno di un tipo è possibile definire più metodi con lo stesso nome, purché la relativa firma sia diversa.</span><span class="sxs-lookup"><span data-stu-id="7a775-385">Multiple methods with the same name can be defined within a type as long as their signatures differ.</span></span> <span data-ttu-id="7a775-386">Quando vengono definiti due o più metodi con lo stesso nome si dice che il metodo è stato sottoposto a overload.</span><span class="sxs-lookup"><span data-stu-id="7a775-386">When two or more methods with the same name are defined, the method is said to be overloaded.</span></span> <span data-ttu-id="7a775-387">Ad esempio, in [System.Char](xref:System.Char) il metodo `IsDigit` è sottoposto a overload.</span><span class="sxs-lookup"><span data-stu-id="7a775-387">For example, in [System.Char](xref:System.Char), the `IsDigit` method is overloaded.</span></span> <span data-ttu-id="7a775-388">Un metodo usa un oggetto [Char](xref:System.Char).</span><span class="sxs-lookup"><span data-stu-id="7a775-388">One method takes a [Char](xref:System.Char).</span></span> <span data-ttu-id="7a775-389">L'altro metodo usa un oggetto [String](xref:System.String) e un oggetto [Int32](xref:System.Int32).</span><span class="sxs-lookup"><span data-stu-id="7a775-389">The other method takes a [String](xref:System.String) and an [Int32](xref:System.Int32).</span></span> 

> [!NOTE]
> <span data-ttu-id="7a775-390">Il tipo restituito non viene considerato parte della firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a775-390">The return type is not considered part of a method's signature.</span></span> <span data-ttu-id="7a775-391">Ciò significa che i metodi non possono essere sottoposti a overload se differiscono unicamente per il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="7a775-391">That is, methods cannot be overloaded if they differ only by return type.</span></span>

### <a name="inheriting-overriding-and-hiding-members"></a><span data-ttu-id="7a775-392">Eredità, override e membri nascosti</span><span class="sxs-lookup"><span data-stu-id="7a775-392">Inheriting, overriding, and hiding members</span></span>

<span data-ttu-id="7a775-393">Un tipo derivato eredita tutti i membri del relativo tipo di base, ovvero tali membri vengono definiti e resi disponibili nel tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="7a775-393">A derived type inherits all members of its base type; that is, these members are defined on, and available to, the derived type.</span></span> <span data-ttu-id="7a775-394">Il comportamento o le qualità dei membri ereditati possono essere modificati in due modi:</span><span class="sxs-lookup"><span data-stu-id="7a775-394">The behavior or qualities of inherited members can be modified in two ways:</span></span> 

* <span data-ttu-id="7a775-395">È possibile nascondere un membro ereditato con un tipo derivato definendo un nuovo membro con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="7a775-395">A derived type can hide an inherited member by defining a new member with the same signature.</span></span> <span data-ttu-id="7a775-396">Questa operazione può essere eseguita per rendere privato un membro precedentemente pubblico oppure per definire un nuovo comportamento per un metodo ereditato contrassegnato come `final`.</span><span class="sxs-lookup"><span data-stu-id="7a775-396">This might be done to make a previously public member private or to define new behavior for an inherited method that is marked as `final`.</span></span>

* <span data-ttu-id="7a775-397">Con un tipo derivato è possibile eseguire l'override di un metodo virtuale ereditato.</span><span class="sxs-lookup"><span data-stu-id="7a775-397">A derived type can override an inherited virtual method.</span></span> <span data-ttu-id="7a775-398">Nel metodo con cui viene eseguito l'override si fornisce una nuova definizione del metodo che sarà richiamato in base al tipo del valore in fase di esecuzione anziché in base al tipo della variabile nota in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7a775-398">The overriding method provides a new definition of the method that will be invoked based on the type of the value at run time rather than the type of the variable known at compile time.</span></span> <span data-ttu-id="7a775-399">Un metodo può sottoporre a override un metodo virtuale solo se quest'ultimo non è contrassegnato come `final` e se il nuovo metodo è accessibile almeno quanto il metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="7a775-399">A method can override a virtual method only if the virtual method is not marked as `final` and the new method is at least as accessible as the virtual method.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a775-400">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a775-400">See also</span></span>

[<span data-ttu-id="7a775-401">Conversione di tipi in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a775-401">Type conversion in the .NET Framework</span></span>](type-conversion.md)
