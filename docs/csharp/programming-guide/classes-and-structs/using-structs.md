---
title: Utilizzo di struct (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="396a7-102">Utilizzo di struct (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="396a7-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="396a7-103">Il tipo `struct` è adatto a rappresentare oggetti leggeri come `Point`, `Rectangle`e `Color`.</span><span class="sxs-lookup"><span data-stu-id="396a7-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="396a7-104">Sebbene sia altrettanto conveniente rappresentare un punto con una [classe](../../../csharp/language-reference/keywords/class.md) con [proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), lo [struct](../../../csharp/language-reference/keywords/struct.md) potrebbe essere più efficiente in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="396a7-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="396a7-105">Ad esempio, se si dichiara una matrice di 1000 oggetti `Point` , verrà allocata memoria aggiuntiva per fare riferimento a ogni oggetto. In questo caso, lo struct risulterebbe meno costoso.</span><span class="sxs-lookup"><span data-stu-id="396a7-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="396a7-106">Dal momento che [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contiene un oggetto denominato <xref:System.Drawing.Point>, lo struct in questo esempio è invece denominato "CoOrds".</span><span class="sxs-lookup"><span data-stu-id="396a7-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="396a7-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="396a7-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="396a7-108">È un errore definire un costruttore predefinito (senza parametri) per uno struct.</span><span class="sxs-lookup"><span data-stu-id="396a7-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="396a7-109">È anche errato inizializzare un campo di istanza nel corpo di uno struct.</span><span class="sxs-lookup"><span data-stu-id="396a7-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="396a7-110">È possibile inizializzare i membri dello struct solo usando un costruttore con parametri o accedendo ai membri singolarmente dopo la dichiarazione dello struct.</span><span class="sxs-lookup"><span data-stu-id="396a7-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="396a7-111">I membri privati o altrimenti inaccessibili possono essere inizializzati solo in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="396a7-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="396a7-112">Quando si crea un oggetto struct mediante l'operatore [new](../../../csharp/language-reference/keywords/new.md) , questo viene creato e viene chiamato il costruttore appropriato.</span><span class="sxs-lookup"><span data-stu-id="396a7-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="396a7-113">A differenza delle classi, è possibile creare istanze di struct senza usare l'operatore `new` .</span><span class="sxs-lookup"><span data-stu-id="396a7-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="396a7-114">In tal caso, non vi è alcuna chiamata al costruttore, il che rende più efficiente l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="396a7-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="396a7-115">Tuttavia, i campi restano non assegnati e l'oggetto non può essere usato fino all'inizializzazione di tutti i campi.</span><span class="sxs-lookup"><span data-stu-id="396a7-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="396a7-116">Quando uno struct contiene un tipo di riferimento come membro, il costruttore predefinito del membro deve essere richiamato in modo esplicito, altrimenti il membro rimane non assegnato e lo struct non può essere usato.</span><span class="sxs-lookup"><span data-stu-id="396a7-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="396a7-117">(Ciò dà origine all'errore del compilatore CS0171).</span><span class="sxs-lookup"><span data-stu-id="396a7-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="396a7-118">Per gli struct non è prevista la stessa ereditarietà delle classi.</span><span class="sxs-lookup"><span data-stu-id="396a7-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="396a7-119">Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe.</span><span class="sxs-lookup"><span data-stu-id="396a7-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="396a7-120">Gli struct, tuttavia, ereditano dalla classe base <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="396a7-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="396a7-121">Uno struct può implementare interfacce esattamente come le classi.</span><span class="sxs-lookup"><span data-stu-id="396a7-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="396a7-122">Non è possibile dichiarare una classe usando la parola chiave `struct`.</span><span class="sxs-lookup"><span data-stu-id="396a7-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="396a7-123">In C# le classi e gli struct sono semanticamente diversi.</span><span class="sxs-lookup"><span data-stu-id="396a7-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="396a7-124">Uno struct è un tipo di valore, mentre una classe è un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="396a7-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="396a7-125">Per altre informazioni, vedere [Tipi di valore](../../../csharp/language-reference/keywords/value-types.md).</span><span class="sxs-lookup"><span data-stu-id="396a7-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="396a7-126">A meno che non sia richiesta una semantica tipo-riferimento, una classe piccola può essere gestita in modo più efficiente dal sistema se dichiarata come uno struct.</span><span class="sxs-lookup"><span data-stu-id="396a7-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="396a7-127">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="396a7-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="396a7-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="396a7-128">Description</span></span>  
 <span data-ttu-id="396a7-129">Questo esempio mostra l'inizializzazione `struct` tramite costruttori con parametri e valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="396a7-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="396a7-130">Codice</span><span class="sxs-lookup"><span data-stu-id="396a7-130">Code</span></span>  
 <span data-ttu-id="396a7-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="396a7-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="396a7-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="396a7-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="396a7-133">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="396a7-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="396a7-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="396a7-134">Description</span></span>  
 <span data-ttu-id="396a7-135">Questo esempio illustra una funzionalità univoca per struct.</span><span class="sxs-lookup"><span data-stu-id="396a7-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="396a7-136">Crea un oggetto CoOrds senza usare l'operatore `new` .</span><span class="sxs-lookup"><span data-stu-id="396a7-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="396a7-137">Se si sostituisce la parola `struct` con la parola `class`, il programma non verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="396a7-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="396a7-138">Codice</span><span class="sxs-lookup"><span data-stu-id="396a7-138">Code</span></span>  
 <span data-ttu-id="396a7-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="396a7-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="396a7-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="396a7-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396a7-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="396a7-141">See Also</span></span>  
 <span data-ttu-id="396a7-142">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="396a7-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="396a7-143">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="396a7-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="396a7-144">Struct</span><span class="sxs-lookup"><span data-stu-id="396a7-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

