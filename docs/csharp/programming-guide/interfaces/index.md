---
title: Interfacce (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0552cea71f66ba8c299b1706cab6778c9e3367c9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="interfaces-c-programming-guide"></a><span data-ttu-id="e90cb-102">Interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e90cb-102">Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="e90cb-103">Un'interfaccia contiene le definizioni per un gruppo di funzionalità correlate che possono essere implementate da una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-103">An interface contains definitions for a group of related functionalities that a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md) can implement.</span></span>  
  
 <span data-ttu-id="e90cb-104">Usando le interfacce, è possibile, ad esempio, includere il comportamento di più origini in una classe.</span><span class="sxs-lookup"><span data-stu-id="e90cb-104">By using interfaces, you can, for example, include behavior from multiple sources in a class.</span></span> <span data-ttu-id="e90cb-105">Tale funzionalità è importante in C# perché il linguaggio non supporta l'ereditarietà multipla delle classi.</span><span class="sxs-lookup"><span data-stu-id="e90cb-105">That capability is important in C# because the language doesn't support multiple inheritance of classes.</span></span> <span data-ttu-id="e90cb-106">Inoltre è necessario usare un'interfaccia se si vuole simulare l'ereditarietà per le struct, perché non possono effettivamente ereditare da un'altra struct o classe.</span><span class="sxs-lookup"><span data-stu-id="e90cb-106">In addition, you must use an interface if you want to simulate inheritance for structs, because they can't actually inherit from another struct or class.</span></span>  
  
 <span data-ttu-id="e90cb-107">Per definire un'interfaccia, si usa la parola chiave [interface](../../../csharp/language-reference/keywords/interface.md), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e90cb-107">You define an interface by using the [interface](../../../csharp/language-reference/keywords/interface.md) keyword, as the following example shows.</span></span>  
  
 <span data-ttu-id="e90cb-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e90cb-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="e90cb-109">Qualsiasi classe o struct che implementa l'interfaccia <xref:System.IEquatable%601> deve contenere una definizione per un metodo <xref:System.IEquatable%601.Equals%2A> che corrisponde alla firma specificata dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-109">Any class or struct that implements the <xref:System.IEquatable%601> interface must contain a definition for an <xref:System.IEquatable%601.Equals%2A> method that matches the signature that the interface specifies.</span></span> <span data-ttu-id="e90cb-110">Di conseguenza, è possibile affidarsi a una classe che implementa `IEquatable<T>` per contenere un metodo `Equals` con cui un'istanza della classe può determinare se sia uguale a un'altra istanza della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="e90cb-110">As a result, you can count on a class that implements `IEquatable<T>` to contain an `Equals` method with which an instance of the class can determine whether it's equal to another instance of the same class.</span></span>  
  
 <span data-ttu-id="e90cb-111">La definizione di `IEquatable<T>` non fornisce un'implementazione per `Equals`.</span><span class="sxs-lookup"><span data-stu-id="e90cb-111">The definition of `IEquatable<T>` doesn’t provide an implementation for `Equals`.</span></span> <span data-ttu-id="e90cb-112">L'interfaccia definisce solo la firma.</span><span class="sxs-lookup"><span data-stu-id="e90cb-112">The interface defines only the signature.</span></span> <span data-ttu-id="e90cb-113">In tal modo, un'interfaccia in C# è simile a una classe astratta in cui tutti i metodi sono astratti.</span><span class="sxs-lookup"><span data-stu-id="e90cb-113">In that way, an interface in C# is similar to an abstract class in which all the methods are abstract.</span></span> <span data-ttu-id="e90cb-114">Tuttavia, una classe o struct può implementare più interfacce, ma una classe può ereditare una sola classe, astratta o meno.</span><span class="sxs-lookup"><span data-stu-id="e90cb-114">However, a class or struct can implement multiple interfaces, but a class can inherit only a single class, abstract or not.</span></span> <span data-ttu-id="e90cb-115">Usando le interfacce, è quindi possibile includere il comportamento di più origini in una classe.</span><span class="sxs-lookup"><span data-stu-id="e90cb-115">Therefore, by using interfaces, you can include behavior from multiple sources in a class.</span></span>  
  
 <span data-ttu-id="e90cb-116">Per altre informazioni sulle classi astratte, vedere [Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-116">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="e90cb-117">Le interfacce possono contenere metodi, proprietà, eventi, indicizzatori o qualsiasi combinazione di questi quattro membri.</span><span class="sxs-lookup"><span data-stu-id="e90cb-117">Interfaces can contain methods, properties, events, indexers, or any combination of those four member types.</span></span> <span data-ttu-id="e90cb-118">Per collegamenti a esempi, vedere [Sezioni correlate](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="e90cb-118">For links to examples, see [Related Sections](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span></span> <span data-ttu-id="e90cb-119">Un'interfaccia non può contenere costanti, campi, operatori, costruttori di istanze, finalizzatori o tipi.</span><span class="sxs-lookup"><span data-stu-id="e90cb-119">An interface can't contain constants, fields, operators, instance constructors, finalizers, or types.</span></span> <span data-ttu-id="e90cb-120">I membri di interfaccia sono automaticamente pubblici e non possono includere modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="e90cb-120">Interface members are automatically public, and they can't include any access modifiers.</span></span> <span data-ttu-id="e90cb-121">I membri non possono nemmeno essere [statici](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-121">Members also can't be [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
 <span data-ttu-id="e90cb-122">Per implementare un membro di interfaccia, il corrispondente membro della classe di implementazione deve essere pubblico e non statico e avere lo stesso nome e la stessa firma del membro di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-122">To implement an interface member, the corresponding member of the implementing class must be public, non-static, and have the same name and signature as the interface member.</span></span>  
  
 <span data-ttu-id="e90cb-123">Quando una classe o una struct implementa un'interfaccia, la classe o la struct deve fornire un'implementazione per tutti i membri definiti dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-123">When a class or struct implements an interface, the class or struct must provide an implementation for all of the members that the interface defines.</span></span> <span data-ttu-id="e90cb-124">L'interfaccia stessa non fornisce funzionalità che una classe o struct possa ereditare come può ereditare le funzionalità delle classi base.</span><span class="sxs-lookup"><span data-stu-id="e90cb-124">The interface itself provides no functionality that a class or struct can inherit in the way that it can inherit base class functionality.</span></span> <span data-ttu-id="e90cb-125">Tuttavia, se una classe base implementa un'interfaccia, qualsiasi classe derivata dalla classe base eredita tale implementazione.</span><span class="sxs-lookup"><span data-stu-id="e90cb-125">However, if a base class implements an interface, any class that's derived from the base class inherits that implementation.</span></span>  
  
 <span data-ttu-id="e90cb-126">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia IEquatable<T\>.</span><span class="sxs-lookup"><span data-stu-id="e90cb-126">The following example shows an implementation of the IEquatable<T\> interface.</span></span> <span data-ttu-id="e90cb-127">La classe di implementazione, `Car`, deve fornire un'implementazione del metodo <xref:System.IEquatable%601.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="e90cb-127">The implementing class, `Car`, must provide an implementation of the <xref:System.IEquatable%601.Equals%2A> method.</span></span>  
  
 <span data-ttu-id="e90cb-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e90cb-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="e90cb-129">Le proprietà e gli indicizzatori di una classe possono definire altre funzioni di accesso per una proprietà o un indicizzatore definito in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-129">Properties and indexers of a class can define extra accessors for a property or indexer that's defined in an interface.</span></span> <span data-ttu-id="e90cb-130">Ad esempio, un'interfaccia può dichiarare una proprietà con una funzione di accesso [get](../../../csharp/language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-130">For example, an interface might declare a property that has a [get](../../../csharp/language-reference/keywords/get.md) accessor.</span></span> <span data-ttu-id="e90cb-131">La classe che implementa l'interfaccia può dichiarare la stessa proprietà con una funzione di accesso `get` o [set](../../../csharp/language-reference/keywords/set.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-131">The class that implements the interface can declare the same property with both a `get` and [set](../../../csharp/language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="e90cb-132">Tuttavia, se la proprietà o l'indicizzatore usa l'implementazione esplicita, le funzioni di accesso devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="e90cb-132">However, if the property or indexer uses explicit implementation, the accessors must match.</span></span> <span data-ttu-id="e90cb-133">Per altre informazioni sull'implementazione esplicita, vedere [Implementazione esplicita dell'interfaccia](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) e [Proprietà dell'interfaccia](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-133">For more information about explicit implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) and [Interface Properties](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span></span>  
  
 <span data-ttu-id="e90cb-134">Le Interfacce possono implementare altre interfacce.</span><span class="sxs-lookup"><span data-stu-id="e90cb-134">Interfaces can implement other interfaces.</span></span> <span data-ttu-id="e90cb-135">Una classe può includere un'interfaccia più volte tramite le classi base ereditate o tramite le interfacce implementate da altre interfacce.</span><span class="sxs-lookup"><span data-stu-id="e90cb-135">A class might include an interface multiple times through base classes that it inherits or through interfaces that other interfaces implement.</span></span> <span data-ttu-id="e90cb-136">Tuttavia, la classe può fornire un'implementazione di un'interfaccia solo una volta e solo se la classe dichiara l'interfaccia durante la definizione della classe (`class ClassName : InterfaceName`).</span><span class="sxs-lookup"><span data-stu-id="e90cb-136">However, the class can provide an implementation of an interface only one time and only if the class declares the interface as part of the definition of the class (`class ClassName : InterfaceName`).</span></span> <span data-ttu-id="e90cb-137">Se l'interfaccia viene ereditata perché è stata ereditata una classe base che implementa l'interfaccia, la classe base fornisce l'implementazione dei membri dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-137">If the interface is inherited because you inherited a base class that implements the interface, the base class provides the implementation of the members of the interface.</span></span> <span data-ttu-id="e90cb-138">Tuttavia, la classe derivata può reimplementare i membri dell'interfaccia invece di usare l'implementazione ereditata.</span><span class="sxs-lookup"><span data-stu-id="e90cb-138">However, the derived class can reimplement the interface members instead of using the inherited implementation.</span></span>  
  
 <span data-ttu-id="e90cb-139">Una classe base può implementare anche i membri di interfaccia usando membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="e90cb-139">A base class can also implement interface members by using virtual members.</span></span> <span data-ttu-id="e90cb-140">In tal caso, una classe derivata può modificare il comportamento dell'interfaccia eseguendo l'override dei membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="e90cb-140">In that case, a derived class can change the interface behavior by overriding the virtual members.</span></span> <span data-ttu-id="e90cb-141">Per altre informazioni su membri virtuali, vedere [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="e90cb-141">For more information about virtual members, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="interfaces-summary"></a><span data-ttu-id="e90cb-142">Riepilogo delle interfacce</span><span class="sxs-lookup"><span data-stu-id="e90cb-142">Interfaces Summary</span></span>  
 <span data-ttu-id="e90cb-143">Un'interfaccia presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="e90cb-143">An interface has the following properties:</span></span>  
  
-   <span data-ttu-id="e90cb-144">Un'interfaccia è uguale a una classe base astratta.</span><span class="sxs-lookup"><span data-stu-id="e90cb-144">An interface is like an abstract base class.</span></span> <span data-ttu-id="e90cb-145">Qualsiasi classe o struct che implementa l'interfaccia deve implementarne tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="e90cb-145">Any class or struct that implements the interface must implement all its members.</span></span>  
  
-   <span data-ttu-id="e90cb-146">Non è possibile creare direttamente un'istanza di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-146">An interface can't be instantiated directly.</span></span> <span data-ttu-id="e90cb-147">I membri vengono implementati da qualsiasi classe o struct che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-147">Its members are implemented by any class or struct that implements the interface.</span></span>  
  
-   <span data-ttu-id="e90cb-148">Le interfacce possono contenere eventi, indicizzatori, metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="e90cb-148">Interfaces can contain events, indexers, methods, and properties.</span></span>  
  
-   <span data-ttu-id="e90cb-149">Le interfacce non contengono implementazioni di metodi.</span><span class="sxs-lookup"><span data-stu-id="e90cb-149">Interfaces contain no implementation of methods.</span></span>  
  
-   <span data-ttu-id="e90cb-150">Una classe o struct può implementare più interfacce.</span><span class="sxs-lookup"><span data-stu-id="e90cb-150">A class or struct can implement multiple interfaces.</span></span> <span data-ttu-id="e90cb-151">Una classe può ereditare una classe base e anche implementare una o più interfacce.</span><span class="sxs-lookup"><span data-stu-id="e90cb-151">A class can inherit a base class and also implement one or more interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e90cb-152">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e90cb-152">In This Section</span></span>  
 [<span data-ttu-id="e90cb-153">Implementazione esplicita dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="e90cb-153">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 <span data-ttu-id="e90cb-154">Illustra come creare un membro di una classe specifico di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e90cb-154">Explains how to create a class member that’s specific to an interface.</span></span>  
  
 [<span data-ttu-id="e90cb-155">Procedura: Implementare in modo esplicito i membri di interfaccia</span><span class="sxs-lookup"><span data-stu-id="e90cb-155">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)  
 <span data-ttu-id="e90cb-156">Fornisce un esempio di come implementare in modo esplicito i membri delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="e90cb-156">Provides an example of how to explicitly implement members of interfaces.</span></span>  
  
 [<span data-ttu-id="e90cb-157">Procedura: Implementare in modo esplicito i membri di due interfacce</span><span class="sxs-lookup"><span data-stu-id="e90cb-157">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)  
 <span data-ttu-id="e90cb-158">Fornisce un esempio di come implementare in modo esplicito i membri delle interfacce con l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="e90cb-158">Provides an example of how to explicitly implement members of interfaces with inheritance.</span></span>  
  
##  <span data-ttu-id="e90cb-159"><a name="BKMK_RelatedSections"></a> Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e90cb-159"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="e90cb-160">Proprietà dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="e90cb-160">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="e90cb-161">Indicizzatori nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="e90cb-161">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="e90cb-162">Procedura: Implementare eventi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="e90cb-162">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="e90cb-163">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="e90cb-163">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [<span data-ttu-id="e90cb-164">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e90cb-164">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
  
-   [<span data-ttu-id="e90cb-165">Metodi</span><span class="sxs-lookup"><span data-stu-id="e90cb-165">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="e90cb-166">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="e90cb-166">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
  
-   [<span data-ttu-id="e90cb-167">Classi e membri delle classi astratte e sealed</span><span class="sxs-lookup"><span data-stu-id="e90cb-167">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
  
-   [<span data-ttu-id="e90cb-168">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e90cb-168">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [<span data-ttu-id="e90cb-169">Eventi</span><span class="sxs-lookup"><span data-stu-id="e90cb-169">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
  
-   [<span data-ttu-id="e90cb-170">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="e90cb-170">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="e90cb-171">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="e90cb-171">Featured Book Chapter</span></span>  
 <span data-ttu-id="e90cb-172">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="e90cb-172">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90cb-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e90cb-173">See Also</span></span>  
 <span data-ttu-id="e90cb-174">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e90cb-174">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e90cb-175">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e90cb-175">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

