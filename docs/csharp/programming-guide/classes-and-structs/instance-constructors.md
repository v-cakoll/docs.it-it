---
title: Costruttori di istanze (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: 26
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
ms.openlocfilehash: f93f622d5bf99ab7e8b1d8338192ff58472813dd
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="e5298-102">Costruttori di istanze (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e5298-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="e5298-103">I costruttori di istanze vengono usati per creare e inizializzare qualsiasi variabile membro di istanza quando si usa l'espressione [new](../../../csharp/language-reference/keywords/new.md) per creare un oggetto di una [classe](../../../csharp/language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="e5298-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="e5298-104">Per inizializzare una classe [statica](../../../csharp/language-reference/keywords/static.md), o variabili statiche in una classe non statica, è necessario definire un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="e5298-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="e5298-105">Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="e5298-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="e5298-106">Nell'esempio seguente viene illustrato un costruttore di istanze:</span><span class="sxs-lookup"><span data-stu-id="e5298-106">The following example shows an instance constructor:</span></span>  
  
 <span data-ttu-id="e5298-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5298-108">Per maggior chiarezza, questa classe contiene campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="e5298-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="e5298-109">L'uso di campi pubblici non è una procedura di programmazione consigliata, perché consente a qualsiasi metodo in qualsiasi punto di un programma di accedere senza restrizioni e senza verifiche ai componenti interni di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5298-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="e5298-110">I membri dati in genere devono essere privati e l'accesso ad essi deve essere consentito solo tramite metodi e proprietà della classe.</span><span class="sxs-lookup"><span data-stu-id="e5298-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="e5298-111">Questo costruttore di istanze viene chiamato ogni volta che viene creato un oggetto basato sulla classe `CoOrds`.</span><span class="sxs-lookup"><span data-stu-id="e5298-111">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="e5298-112">Un costruttore come questo, che non accetta argomenti, viene chiamato *costruttore predefinito*.</span><span class="sxs-lookup"><span data-stu-id="e5298-112">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="e5298-113">È spesso utile, tuttavia, per fornire costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e5298-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="e5298-114">È ad esempio possibile aggiungere un costruttore alla classe `CoOrds` che consente di specificare i valori iniziali dei membri dati:</span><span class="sxs-lookup"><span data-stu-id="e5298-114">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 <span data-ttu-id="e5298-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="e5298-116">Ciò consente di creare oggetti `CoOrd` con valori iniziali predefiniti o specifici, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e5298-116">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 <span data-ttu-id="e5298-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="e5298-118">Se una classe non ha un costruttore, viene generato automaticamente un costruttore predefinito e per inizializzare i campi dell'oggetto vengono usati i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e5298-118">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="e5298-119">Ad esempio, un valore [int](../../../csharp/language-reference/keywords/int.md) viene inizializzato su 0.</span><span class="sxs-lookup"><span data-stu-id="e5298-119">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="e5298-120">Per altre informazioni sui valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e5298-120">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="e5298-121">Poiché il costruttore predefinito della classe `CoOrds` inizializza tutti i membri dati su zero, può pertanto essere rimosso completamente senza modificare il funzionamento della classe.</span><span class="sxs-lookup"><span data-stu-id="e5298-121">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="e5298-122">Per un esempio completo sull'uso di più costruttori, vedere l'esempio 1 più avanti in questo argomento. Per un esempio di costruttore generato automaticamente, vedere l'esempio 2.</span><span class="sxs-lookup"><span data-stu-id="e5298-122">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="e5298-123">I costruttori di istanze possono anche essere usati per chiamare i costruttori di istanze delle classi di base.</span><span class="sxs-lookup"><span data-stu-id="e5298-123">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="e5298-124">Il costruttore di classi può chiamare il costruttore della classe di base mediante l'inizializzatore, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5298-124">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 <span data-ttu-id="e5298-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="e5298-126">In questo esempio la classe `Circle` passa i valori che rappresentano il raggio e l'altezza al costruttore fornito da `Shape` da cui deriva `Circle`.</span><span class="sxs-lookup"><span data-stu-id="e5298-126">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="e5298-127">Per un esempio completo sull'uso di `Shape` e `Circle` vedere l'esempio 3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e5298-127">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="e5298-128">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="e5298-128">Example 1</span></span>  
 <span data-ttu-id="e5298-129">L'esempio riportato di seguito illustra una classe con due costruttori di classi, uno senza argomenti e uno con due argomenti.</span><span class="sxs-lookup"><span data-stu-id="e5298-129">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 <span data-ttu-id="e5298-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="e5298-131">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="e5298-131">Example 2</span></span>  
 <span data-ttu-id="e5298-132">Nell'esempio riportato di seguito la classe `Person` non ha alcun costruttore. In questo caso viene fornito automaticamente un costruttore predefinito e i campi vengono inizializzati sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e5298-132">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 <span data-ttu-id="e5298-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="e5298-134">Si noti che il valore predefinito di `age` è `0` e il valore predefinito di `name` è `null`.</span><span class="sxs-lookup"><span data-stu-id="e5298-134">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="e5298-135">Per altre informazioni sui valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e5298-135">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="e5298-136">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="e5298-136">Example 3</span></span>  
 <span data-ttu-id="e5298-137">Nell'esempio riportato di seguito viene illustrato l'uso dell'inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e5298-137">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="e5298-138">La classe `Circle` è derivata dalla classe generale `Shape`e la classe `Cylinder` è derivata dalla classe `Circle`.</span><span class="sxs-lookup"><span data-stu-id="e5298-138">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="e5298-139">Il costruttore di ogni classe derivata usa il relativo inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e5298-139">The constructor on each derived class is using its base class initializer.</span></span>  
  
 <span data-ttu-id="e5298-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5298-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="e5298-141">Per altri esempi su come chiamare i costruttori della classe di base, vedere [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) e [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="e5298-141">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5298-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5298-142">See Also</span></span>  
 <span data-ttu-id="e5298-143">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5298-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e5298-144">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5298-144">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="e5298-145">[Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="e5298-145">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="e5298-146">[Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="e5298-146">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="e5298-147">static</span><span class="sxs-lookup"><span data-stu-id="e5298-147">static</span></span>](../../../csharp/language-reference/keywords/static.md)

