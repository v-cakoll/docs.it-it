---
title: Costruttori di istanze - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 621b8ca7510b0b9916c9c46f201ff77402c3c655
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75964716"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="e2b6a-102">Costruttori di istanze (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e2b6a-102">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="e2b6a-103">I costruttori di istanze vengono usati per creare e inizializzare qualsiasi variabile membro di istanza quando si usa l'espressione [new](../../language-reference/operators/new-operator.md) per creare un oggetto di una [classe](../../language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="e2b6a-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="e2b6a-104">Per inizializzare una classe [statica](../../language-reference/keywords/static.md) o variabili statiche in una classe non statica, definire un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-104">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="e2b6a-105">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="e2b6a-105">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="e2b6a-106">Nell'esempio seguente viene illustrato un costruttore di istanze:</span><span class="sxs-lookup"><span data-stu-id="e2b6a-106">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> <span data-ttu-id="e2b6a-107">Per maggior chiarezza, questa classe contiene campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-107">For clarity, this class contains public fields.</span></span> <span data-ttu-id="e2b6a-108">L'uso di campi pubblici non è una procedura di programmazione consigliata, perché consente a qualsiasi metodo in qualsiasi punto di un programma di accedere senza restrizioni e senza verifiche ai componenti interni di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-108">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="e2b6a-109">I membri dati in genere devono essere privati e l'accesso ad essi deve essere consentito solo tramite metodi e proprietà della classe.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-109">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="e2b6a-110">Questo costruttore di istanze viene chiamato ogni volta che viene creato un oggetto basato sulla classe `Coords`.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-110">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="e2b6a-111">Un costruttore come questo, che non accetta argomenti, viene chiamato \*costruttore senza parametri \*.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-111">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="e2b6a-112">È spesso utile, tuttavia, per fornire costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-112">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="e2b6a-113">È ad esempio possibile aggiungere un costruttore alla classe `Coords` che consente di specificare i valori iniziali dei membri dati:</span><span class="sxs-lookup"><span data-stu-id="e2b6a-113">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 <span data-ttu-id="e2b6a-114">Ciò consente di creare oggetti `Coords` con valori iniziali predefiniti o specifici, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e2b6a-114">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 <span data-ttu-id="e2b6a-115">Se una classe non ha un costruttore, viene generato automaticamente un costruttore senza parametri e per inizializzare i campi dell'oggetto vengono usati valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-115">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="e2b6a-116">Ad esempio, un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) viene inizializzato su 0.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-116">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="e2b6a-117">Per informazioni sui valori predefiniti del tipo, vedere [Valori predefiniti dei tipi C .](../../language-reference/builtin-types/default-values.md)</span><span class="sxs-lookup"><span data-stu-id="e2b6a-117">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="e2b6a-118">Poiché il costruttore senza parametri della classe `Coords` inizializza tutti i membri dati su zero, può pertanto essere rimosso completamente senza che ciò modifichi il funzionamento della classe.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-118">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="e2b6a-119">Per un esempio completo sull'uso di più costruttori, vedere l'esempio 1 più avanti in questo argomento. Per un esempio di costruttore generato automaticamente, vedere l'esempio 2.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-119">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="e2b6a-120">I costruttori di istanze possono anche essere usati per chiamare i costruttori di istanze delle classi di base.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-120">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="e2b6a-121">Il costruttore di classi può chiamare il costruttore della classe di base mediante l'inizializzatore, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e2b6a-121">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 <span data-ttu-id="e2b6a-122">In questo esempio la classe `Circle` passa i valori che rappresentano il raggio e l'altezza al costruttore fornito da `Shape` da cui deriva `Circle`.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-122">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="e2b6a-123">Per un esempio completo sull'uso di `Shape` e `Circle` vedere l'esempio 3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-123">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="e2b6a-124">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="e2b6a-124">Example 1</span></span>  
 <span data-ttu-id="e2b6a-125">L'esempio riportato di seguito illustra una classe con due costruttori di classi, uno senza argomenti e uno con due argomenti.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-125">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a><span data-ttu-id="e2b6a-126">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="e2b6a-126">Example 2</span></span>  
 <span data-ttu-id="e2b6a-127">In questo esempio, la classe `Person` non ha alcun costruttore. In questo caso viene fornito automaticamente un costruttore senza parametri e i campi vengono inizializzati sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-127">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 <span data-ttu-id="e2b6a-128">Si noti che il valore predefinito di `age` è `0` e il valore predefinito di `name` è `null`.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-128">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="e2b6a-129">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="e2b6a-129">Example 3</span></span>  
 <span data-ttu-id="e2b6a-130">Nell'esempio riportato di seguito viene illustrato l'uso dell'inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-130">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="e2b6a-131">La classe `Circle` è derivata dalla classe generale `Shape`e la classe `Cylinder` è derivata dalla classe `Circle`.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-131">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="e2b6a-132">Il costruttore di ogni classe derivata usa il relativo inizializzatore della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e2b6a-132">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 <span data-ttu-id="e2b6a-133">Per altri esempi su come chiamare i costruttori della classe di base, vedere [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) e [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="e2b6a-133">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b6a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2b6a-134">See also</span></span>

- [<span data-ttu-id="e2b6a-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e2b6a-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e2b6a-136">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="e2b6a-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="e2b6a-137">Costruttori</span><span class="sxs-lookup"><span data-stu-id="e2b6a-137">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="e2b6a-138">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="e2b6a-138">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="e2b6a-139">Statico</span><span class="sxs-lookup"><span data-stu-id="e2b6a-139">static</span></span>](../../language-reference/keywords/static.md)
