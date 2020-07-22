---
title: Costruttori di istanze - Guida per programmatori C#
description: I costruttori di istanze in C# creano e inizializzano qualsiasi variabile membro di istanza quando si usa la nuova espressione per creare un oggetto di una classe.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: d70e786446fb198afb4e0311757cacb65b706f47
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864202"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="23d6c-103">Costruttori di istanze (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="23d6c-103">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="23d6c-104">I costruttori di istanze vengono usati per creare e inizializzare qualsiasi variabile membro di istanza quando si usa l'espressione [new](../../language-reference/operators/new-operator.md) per creare un oggetto di una [classe](../../language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="23d6c-104">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="23d6c-105">Per inizializzare una classe [statica](../../language-reference/keywords/static.md) o variabili statiche in una classe non statica, definire un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="23d6c-105">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="23d6c-106">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="23d6c-106">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="23d6c-107">Nell'esempio seguente viene illustrato un costruttore di istanze:</span><span class="sxs-lookup"><span data-stu-id="23d6c-107">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> <span data-ttu-id="23d6c-108">Per maggior chiarezza, questa classe contiene campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="23d6c-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="23d6c-109">L'uso di campi pubblici non è una procedura di programmazione consigliata, perché consente a qualsiasi metodo in qualsiasi punto di un programma di accedere senza restrizioni e senza verifiche ai componenti interni di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="23d6c-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="23d6c-110">I membri dati in genere devono essere privati e l'accesso ad essi deve essere consentito solo tramite metodi e proprietà della classe.</span><span class="sxs-lookup"><span data-stu-id="23d6c-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="23d6c-111">Questo costruttore di istanze viene chiamato ogni volta che viene creato un oggetto basato sulla classe `Coords`.</span><span class="sxs-lookup"><span data-stu-id="23d6c-111">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="23d6c-112">Un costruttore come questo, che non accetta argomenti, viene chiamato \*costruttore senza parametri \*.</span><span class="sxs-lookup"><span data-stu-id="23d6c-112">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="23d6c-113">È spesso utile, tuttavia, per fornire costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="23d6c-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="23d6c-114">È ad esempio possibile aggiungere un costruttore alla classe `Coords` che consente di specificare i valori iniziali dei membri dati:</span><span class="sxs-lookup"><span data-stu-id="23d6c-114">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 <span data-ttu-id="23d6c-115">Ciò consente di creare oggetti `Coords` con valori iniziali predefiniti o specifici, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="23d6c-115">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 <span data-ttu-id="23d6c-116">Se una classe non ha un costruttore, viene generato automaticamente un costruttore senza parametri e per inizializzare i campi dell'oggetto vengono usati valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="23d6c-116">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="23d6c-117">Ad esempio, un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) viene inizializzato su 0.</span><span class="sxs-lookup"><span data-stu-id="23d6c-117">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="23d6c-118">Per informazioni sui valori predefiniti del tipo, vedere [valori predefiniti dei tipi C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="23d6c-118">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="23d6c-119">Poiché il costruttore senza parametri della classe `Coords` inizializza tutti i membri dati su zero, può pertanto essere rimosso completamente senza che ciò modifichi il funzionamento della classe.</span><span class="sxs-lookup"><span data-stu-id="23d6c-119">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="23d6c-120">Per un esempio completo sull'uso di più costruttori, vedere l'esempio 1 più avanti in questo argomento. Per un esempio di costruttore generato automaticamente, vedere l'esempio 2.</span><span class="sxs-lookup"><span data-stu-id="23d6c-120">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="23d6c-121">I costruttori di istanze possono anche essere usati per chiamare i costruttori di istanze delle classi di base.</span><span class="sxs-lookup"><span data-stu-id="23d6c-121">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="23d6c-122">Il costruttore di classi può chiamare il costruttore della classe di base mediante l'inizializzatore, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23d6c-122">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 <span data-ttu-id="23d6c-123">In questo esempio la classe `Circle` passa i valori che rappresentano il raggio e l'altezza al costruttore fornito da `Shape` da cui deriva `Circle`.</span><span class="sxs-lookup"><span data-stu-id="23d6c-123">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="23d6c-124">Per un esempio completo sull'uso di `Shape` e `Circle` vedere l'esempio 3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="23d6c-124">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="23d6c-125">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="23d6c-125">Example 1</span></span>  
 <span data-ttu-id="23d6c-126">L'esempio riportato di seguito illustra una classe con due costruttori di classi, uno senza argomenti e uno con due argomenti.</span><span class="sxs-lookup"><span data-stu-id="23d6c-126">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a><span data-ttu-id="23d6c-127">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="23d6c-127">Example 2</span></span>  
 <span data-ttu-id="23d6c-128">In questo esempio, la classe `Person` non ha alcun costruttore. In questo caso viene fornito automaticamente un costruttore senza parametri e i campi vengono inizializzati sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="23d6c-128">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 <span data-ttu-id="23d6c-129">Si noti che il valore predefinito di `age` è `0` e il valore predefinito di `name` è `null`.</span><span class="sxs-lookup"><span data-stu-id="23d6c-129">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="23d6c-130">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="23d6c-130">Example 3</span></span>  
 <span data-ttu-id="23d6c-131">Nell'esempio riportato di seguito viene illustrato l'uso dell'inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="23d6c-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="23d6c-132">La classe `Circle` è derivata dalla classe generale `Shape`e la classe `Cylinder` è derivata dalla classe `Circle`.</span><span class="sxs-lookup"><span data-stu-id="23d6c-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="23d6c-133">Il costruttore di ogni classe derivata usa il relativo inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="23d6c-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 <span data-ttu-id="23d6c-134">Per altri esempi su come chiamare i costruttori della classe di base, vedere [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) e [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="23d6c-134">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d6c-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="23d6c-135">See also</span></span>

- [<span data-ttu-id="23d6c-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="23d6c-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="23d6c-137">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="23d6c-137">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="23d6c-138">Costruttori</span><span class="sxs-lookup"><span data-stu-id="23d6c-138">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="23d6c-139">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="23d6c-139">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="23d6c-140">static</span><span class="sxs-lookup"><span data-stu-id="23d6c-140">static</span></span>](../../language-reference/keywords/static.md)
