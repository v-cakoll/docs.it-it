---
title: Classi generiche (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
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
ms.openlocfilehash: 17ec9f5d26c01b7f7f7f95026bfdfaa88d709b60
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="388e8-102">Classi generiche (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="388e8-102">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="388e8-103">Le classi generiche incapsulano operazioni che non sono specifiche di un determinato tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="388e8-103">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="388e8-104">L'uso più comune per le classi generiche è con raccolte come elenchi collegati, tabelle hash, stack, code, alberi e così via.</span><span class="sxs-lookup"><span data-stu-id="388e8-104">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="388e8-105">Le operazioni come l'aggiunta e la rimozione di elementi dalla raccolta vengono eseguite praticamente allo stesso modo, indipendentemente dal tipo dei dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="388e8-105">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="388e8-106">Per la maggior parte degli scenari che richiedono classi di raccolta, l'approccio consigliato consiste nell'usare quelle disponibili nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="388e8-106">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET Framework class library.</span></span> <span data-ttu-id="388e8-107">Per altre informazioni sull'uso di queste classi, vedere [Generics nella libreria di classi .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="388e8-107">For more information about using these classes, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="388e8-108">Normalmente, per creare classi generiche è possibile iniziare da una classe concreta esistente, modificando quindi i tipi in parametri di tipo uno per volta fino a raggiungere l'equilibrio ottimale tra generalizzazione e usabilità.</span><span class="sxs-lookup"><span data-stu-id="388e8-108">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="388e8-109">Ecco alcuni aspetti importanti di cui tenere conto quando si creano classi generiche personalizzate:</span><span class="sxs-lookup"><span data-stu-id="388e8-109">When creating your own generic classes, important considerations include the following:</span></span>  
  
-   <span data-ttu-id="388e8-110">Tipi da generalizzare in parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="388e8-110">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="388e8-111">Di norma, maggiore è il numero di tipi che è possibile parametrizzare, più flessibile e riutilizzabile sarà il codice.</span><span class="sxs-lookup"><span data-stu-id="388e8-111">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="388e8-112">Tuttavia, una generalizzazione eccessiva può creare codice difficile da leggere e comprendere per gli altri sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="388e8-112">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
-   <span data-ttu-id="388e8-113">Vincoli, se presenti, da applicare ai parametri di tipo. Vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="388e8-113">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="388e8-114">Una buona regola consiste nell'applicare il numero massimo di vincoli possibile, ma che permetta di continuare a gestire tutti i tipi necessari.</span><span class="sxs-lookup"><span data-stu-id="388e8-114">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="388e8-115">Se, ad esempio, la classe generica è destinata solo all'uso con tipi riferimento, applicare il vincolo di classe.</span><span class="sxs-lookup"><span data-stu-id="388e8-115">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="388e8-116">In questo modo, si eviterà l'uso indesiderato della classe con tipi valore e sarà possibile usare l'operatore `as` in `T` e verificare la presenza di valori null.</span><span class="sxs-lookup"><span data-stu-id="388e8-116">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
-   <span data-ttu-id="388e8-117">Se suddividere il comportamento generico in classi e sottoclassi base.</span><span class="sxs-lookup"><span data-stu-id="388e8-117">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="388e8-118">Poiché le classi generiche possono fungere da classi base, valgono le stesse considerazioni di progettazione relative alle classi non generiche.</span><span class="sxs-lookup"><span data-stu-id="388e8-118">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="388e8-119">Vedere le regole sull'ereditarietà da classi base generiche più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="388e8-119">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
-   <span data-ttu-id="388e8-120">Se implementare una o più interfacce generiche.</span><span class="sxs-lookup"><span data-stu-id="388e8-120">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="388e8-121">Se, ad esempio, si progetta una classe che verrà usata per creare elementi in una raccolta basata su generics, potrebbe essere necessario implementare un'interfaccia come <xref:System.IComparable%601>, dove `T` è il tipo della classe.</span><span class="sxs-lookup"><span data-stu-id="388e8-121">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="388e8-122">Per un esempio di una classe generica semplice, vedere [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="388e8-122">For an example of a simple generic class, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span>  
  
 <span data-ttu-id="388e8-123">Le regole per i parametri di tipo e i vincoli hanno diverse implicazioni per il comportamento delle classi generiche, in particolare riguardo a ereditarietà e accessibilità dei membri.</span><span class="sxs-lookup"><span data-stu-id="388e8-123">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="388e8-124">Prima di continuare, è utile comprendere alcuni termini.</span><span class="sxs-lookup"><span data-stu-id="388e8-124">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="388e8-125">Per una classe generica, il codice client `Node<T>,` può fare riferimento alla classe specificando un argomento tipo, per creare un tipo costruito chiuso (`Node<int>`).</span><span class="sxs-lookup"><span data-stu-id="388e8-125">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="388e8-126">In alternativa, può lasciare il parametro di tipo non specificato, ad esempio quando si specifica una classe base generica, per creare un tipo costruito aperto (`Node<T>`).</span><span class="sxs-lookup"><span data-stu-id="388e8-126">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="388e8-127">Le classi generiche possono ereditare da classi concrete, classi costruite chiuse o classi base costruite aperte:</span><span class="sxs-lookup"><span data-stu-id="388e8-127">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 <span data-ttu-id="388e8-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span></span>  
  
 <span data-ttu-id="388e8-129">Le classi non generiche, ovvero concrete, possono ereditare da classi base costruite chiuse, ma non da classi costruite aperte o da parametri di tipo, perché in fase di esecuzione il codice client non può in alcun modo specificare l'argomento tipo necessario per creare un'istanza della classe base.</span><span class="sxs-lookup"><span data-stu-id="388e8-129">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 <span data-ttu-id="388e8-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span></span>  
  
 <span data-ttu-id="388e8-131">Le classi generiche che ereditano da tipi costruiti aperti devono specificare gli argomenti tipo per qualsiasi parametro di tipo di classe base che non viene condiviso dalla classe che eredita, come mostrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="388e8-131">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 <span data-ttu-id="388e8-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span></span>  
  
 <span data-ttu-id="388e8-133">Le classi generiche che ereditano da tipi costruiti aperti devono specificare vincoli che implichino o siano un superset dei vincoli sul tipo di base:</span><span class="sxs-lookup"><span data-stu-id="388e8-133">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 <span data-ttu-id="388e8-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span></span>  
  
 <span data-ttu-id="388e8-135">I tipi generici possono usare più parametri di tipo e vincoli, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="388e8-135">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 <span data-ttu-id="388e8-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span></span>  
  
 <span data-ttu-id="388e8-137">I tipo costruiti aperti e i tipi costruiti chiusi possono essere usati come parametri di metodo:</span><span class="sxs-lookup"><span data-stu-id="388e8-137">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 <span data-ttu-id="388e8-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="388e8-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span></span>  
  
 <span data-ttu-id="388e8-139">Se una classe generica implementa un'interfaccia, è possibile eseguire il cast di tutte le istanze della classe all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="388e8-139">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="388e8-140">Le classi generiche sono invariabili.</span><span class="sxs-lookup"><span data-stu-id="388e8-140">Generic classes are invariant.</span></span> <span data-ttu-id="388e8-141">In altri termini, se un parametro di input specifica un oggetto `List<BaseClass>`, se si prova a specificare un oggetto `List<DerivedClass>`, viene restituito un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="388e8-141">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388e8-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388e8-142">See Also</span></span>  
 <span data-ttu-id="388e8-143"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="388e8-143"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="388e8-144">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="388e8-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="388e8-145">[Generics](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="388e8-145">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="388e8-146">[Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390)  (Salvataggio dello stato degli enumeratori)</span><span class="sxs-lookup"><span data-stu-id="388e8-146">[Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390) </span></span>  
 <span data-ttu-id="388e8-147">[An Inheritance Puzzle, Part One](http://go.microsoft.com/fwlink/?LinkId=112380) (Indovinello sull'ereditarietà - Parte 1)</span><span class="sxs-lookup"><span data-stu-id="388e8-147">[An Inheritance Puzzle, Part One](http://go.microsoft.com/fwlink/?LinkId=112380)</span></span>

